---
title: 'TN040: MFC-OLE 인플레이스 크기 조정 및 확대/축소'
ms.date: 11/04/2016
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
ms.openlocfilehash: 65f9ef04c9740e8e6f0a8e72d9d6c39008198755
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372161"
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>TN040: MFC/OLE 내부 크기 조정 및 확대/축소

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 노트에서는 현재 편집과 관련된 문제와 서버가 올바른 확대/축소 및 장소 크기 조정을 수행하는 방법에 대해 설명합니다. WYSIWYG 개념은 컨테이너와 서버가 서로 협력하고 특히 OLE 사양을 거의 동일한 방식으로 해석한다는 점에서 한 단계 더 발전합니다.

컨테이너와 서버 간의 긴밀한 상호 작용으로 인해 내부 활성화를 지원하기 때문에 최종 사용자의 많은 기대치가 유지되어야 합니다.

- 편집에 그려진 `COleServerItem::OnDraw` 메타파일(재정의에 그려진 메타파일)은 편집 도구가 표시되지 않는 경우를 제외하고 편집을 위해 그릴 때와 정확히 같아야 합니다.

- 컨테이너가 확대되면 서버 창도 확대해야 합니다!

- 컨테이너와 서버 모두 동일한 메트릭을 사용하여 편집할 개체를 표시해야 합니다. 즉, 디스플레이 장치에서 렌더링할 때 인치당 물리적 픽셀이 아닌 인치당 *논리* 픽셀 수에 따라 매핑 모드를 사용합니다.

> [!NOTE]
> 내부 활성화는 포함된 항목(연결되지 않음)에만 적용되므로 확대/축소는 포함된 객체에만 적용됩니다. 둘 다에 `COleServerDoc` API가 `COleServerItem` 표시되며 확대/축소에 사용됩니다. 이 이분법에 대한 이유는 연결된 항목과 포함된 항목 모두에 대해 `COleServerItem` 유효한 함수만(공통 구현을 가질 수 있음) 포함된 개체에 대해서만 `COleServerDoc` 유효한 함수가 클래스에 위치하기 때문입니다(서버의 관점에서 보면 포함된 **문서임).**

서버가 컨테이너의 확대/축소 계수를 인식하고 편집 인터페이스를 적절하게 수정해야 한다는 점에서 대부분의 부담은 서버 구현자에 있습니다. 그러나 서버가 컨테이너가 사용하는 확대/축소 계수를 결정하는 방법은 무엇입니까?

## <a name="mfc-support-for-zooming"></a>확대/축소를 위한 MFC 지원

현재 확대/축소 계수는 `COleServerDoc::GetZoomFactor`를 호출하여 결정할 수 있습니다. 문서가 활성 상태가 아닐 때 이 것을 호출하면 항상 100% 확대/축소 비율(또는 1:1 비율)이 생성됩니다. 활성 상태인 상태에서 호출하면 100% 이외의 것을 반환할 수 있습니다.

올바르게 확대 /축소의 예는 MFC OLE 샘플 [HIERSVR을](../overview/visual-cpp-samples.md)참조하십시오. HIERSVR을 확대하는 것은 텍스트를 표시하고 텍스트는 일반적으로 선형 방식으로 확장되지 않는다는 사실로 인해 복잡합니다(힌트, 타이포그래피 규칙, 디자인 너비 및 높이는 모두 문제를 복잡하게 만듭니다). 그래도 HIERSVR은 줌을 올바르게 구현하기 위한 적절한 참조이며 MFC 자습서 [SCRIBBLE(7단계)도](../overview/visual-cpp-samples.md) 마찬가지입니다.

`COleServerDoc::GetZoomFactor`은 컨테이너 또는 사용자 및 `COleServerItem` `COleServerDoc` 클래스의 구현에서 사용할 수 있는 여러 가지 메트릭을 기반으로 확대/축소 계수를 결정합니다. 즉, 현재 확대/축소 계수는 다음 수식에 의해 결정됩니다.

```
Position Rectangle (PR) / Container Extent (CE)
```

위치 사각형은 컨테이너에 의해 결정됩니다. 호출될 때 `COleClientItem::OnGetItemPosition` 내부 활성화 중에 서버로 반환되며 컨테이너가 서버를 `COleServerDoc::OnSetItemRects` 호출할 때 업데이트됩니다(호출 포함). `COleClientItem::SetItemRects`

컨테이너 익스텐디는 계산하기가 약간 더 복잡합니다. 컨테이너가 호출된 `COleServerItem::OnSetExtent` 경우(호출 `COleClientItem::SetExtent`사용) 컨테이너 익스텐트값은 논리적 인치당 픽셀 수에 따라 픽셀로 변환됩니다. 컨테이너가 SetExtent(일반적으로 경우)라고 하지 않은 경우 컨테이너 익스텐트는 `COleServerItem::OnGetExtent`에서 반환되는 크기입니다. 따라서 컨테이너가 SetExtent라고 하지 않은 경우 프레임워크는 컨테이너가 설정된 범위(반환된 `COleServerItem::GetExtent`값)의 100%로 호출한 것으로 가정합니다. 다른 방법으로 설명하면 프레임워크는 컨테이너가 항목의 100% (더 이상, 더 이상) 표시되고 있다고 가정합니다.

비슷한 이름을 가지고 있지만 `COleServerItem::OnSetExtent` `COleServerItem::OnGetExtent` 항목의 동일한 특성을 조작하지는 않는다는 점에 유의해야 합니다. `OnSetExtent`서버가 컨테이너에 표시되는 개체의 양을 알려주도록 호출되며(확대/축소 `OnGetExtent` 계수에 관계 없이) 컨테이너에서 호출되어 개체의 이상적인 크기를 결정합니다.

관련된 각 API를 살펴보면 다음을 보다 명확하게 파악할 수 있습니다.

## <a name="coleserveritemongetextent"></a>COleServerItem::OnGetExtent

이 함수는 항목의 HIMETRIC 단위로 "자연 크기"를 반환해야 합니다. "자연스러운 크기"를 생각하는 가장 좋은 방법은 인쇄할 때 나타날 수 있는 크기로 정의하는 것입니다. 여기에 반환되는 크기는 특정 항목 내용에 대해 일정합니다(예: 특정 항목에 대해 상수인 메타파일). 확대/축소가 항목에 적용될 때 이 크기는 변경되지 않습니다. 일반적으로 컨테이너가 호출하여 `OnSetExtent`항목에 더 많거나 적은 공간을 제공하는 경우 변경되지 않습니다. 변경의 예로는 컨테이너에서 보낸 마지막 익스텐트에 따라 텍스트를 래핑하는 "여백" 기능이 없는 간단한 텍스트 편집기의 경우일 수 있습니다. 서버가 변경되면 서버는 시스템 레지스트리에서 OLEMISC_RECOMPOSEONRESIZE 비트를 설정해야 합니다(이 옵션에 대한 자세한 내용은 OLE SDK 설명서 참조).

## <a name="coleserveritemonsetextent"></a>COleServerItem::OnSetExtent

이 함수는 컨테이너가 개체의 "더 많거나 적은"을 표시할 때 호출됩니다. 대부분의 컨테이너는 이 것을 전혀 호출하지 않습니다. 기본 구현은 컨테이너에서 받은 마지막 값을 'm_sizeExtent'에 저장하며, 위에서 설명한 컨테이너 익스텐트 값을 계산할 `COleServerDoc::GetZoomFactor` 때 사용됩니다.

## <a name="coleserverdoconsetitemrects"></a>콜레서버독::온셋아이템렉트

이 함수는 문서가 활성 상태일 때만 호출됩니다. 컨테이너가 항목의 위치 또는 항목에 적용된 클리핑을 업데이트할 때 호출됩니다. 위에서 설명한 대로 위치 사각형은 확대/축소 계수 계산을 위한 분자를 제공합니다. 서버는 를 호출하여 `COleServerDoc::RequestPositionChange`항목 위치를 변경해 달라고 요청할 수 있습니다. 컨테이너는 호출(호출)을 `OnSetItemRects` `COleServerItem::SetItemRects`통해 이 요청에 응답할 수도 있거나 응답하지 않을 수 있습니다.

## <a name="coleserverdocondraw"></a>콜레서버독::온드로우

재정의하는 메타파일은 현재 확대/축소 계수에 관계없이 정확히 동일한 메타파일을 `COleServerItem::OnDraw` 생성한다는 것을 깨닫는 것이 중요합니다. 컨테이너는 메타파일의 크기를 적절히 조정합니다. 이는 `OnDraw` 뷰와 서버 항목의 의 중요한 차이점입니다. `OnDraw` 뷰는 확대/축소를 처리하고 항목은 *확대/축소 가능한* 메타파일을 생성하고 컨테이너에 남겨 적절한 확대/축소를 수행합니다.

서버가 올바르게 작동하는지 확인하는 가장 좋은 방법은 문서가 활성 `COleServerDoc::GetZoomFactor` 상태인지 구현을 사용하는 것입니다.

## <a name="mfc-support-for-in-place-resizing"></a>MFC 인플레이스 크기 조정 지원

MFC는 OLE 2 사양에 설명된 대로 현재 크기 조정 인터페이스를 완전히 구현합니다. 사용자 인터페이스는 `COleResizeBar` 클래스, WM_SIZECHILD 사용자 지정 메시지 및 에서 이 `COleIPFrameWnd`메시지의 특수 처리에 의해 지원됩니다.

이 메시지의 다른 처리를 프레임워크에서 제공하는 것과 다르게 구현할 수 있습니다. 위에서 설명한 대로 프레임워크는 컨테이너까지 크기 조정 결과를 남깁니다. 컨테이너의 처리 중에 컨테이너 익스텐트및 위치 `COleClientItem::OnChangeItemPosition` 사각형을 모두 설정하여 반응하는 경우(호출의 결과로 `COleServerDoc::RequestPositionChange`호출) 위치 크기 조정은 편집 창에 항목의 "더 많거나 적은"을 표시합니다. 처리 `COleClientItem::OnChangeItemPosition`중에 위치 사각형을 설정하여 컨테이너가 반응하면 확대/축소 계수가 변경되고 항목이 "확대 또는 축소"로 표시됩니다.

서버는 이 협상 중에 발생하는 작업을 어느 정도 제어할 수 있습니다. 예를 들어 스프레드시트는 사용자가 항목을 제자리에서 편집하는 동안 창 크기를 조정할 때 더 많거나 적은 셀을 표시하도록 선택될 수 있습니다. 워드 프로세서는 "페이지 여백"을 변경하여 창과 동일하도록 하고 텍스트를 새 여백으로 다시 래핑하도록 할 수 있습니다. 서버는 크기 조정이 완료될 때 자연 `COleServerItem::OnGetExtent`범위(반환되는 크기)를 변경하여 이를 구현합니다. 이렇게 하면 위치 사각형과 컨테이너 익스텐트가 동일한 양만큼 변경되어 확대/축소 계수가 동일하지만 보기 영역은 더 크거나 작아집니다. 또한 에 의해 `OnDraw`생성된 메타파일에 더 많거나 적은 문서가 표시됩니다. 이 경우 사용자가 보기 영역이 아닌 항목 크기를 조정할 때 문서 자체가 변경됩니다.

클래스의 WM_SIZECHILD 메시지를 재정의하여 `COleResizeBar` 사용자 지정 크기 조정을 구현하고 `COleIPFrameWnd` 제공된 사용자 인터페이스를 계속 활용할 수 있습니다. WM_SIZECHILD 세부 사항에 대한 자세한 내용은 [기술 참고 24를](../mfc/tn024-mfc-defined-messages-and-resources.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
