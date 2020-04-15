---
title: 뷰 스크롤 및 크기 조정
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
ms.openlocfilehash: 366f0e2953e5190f80a2877804bff2fc7dbbd520
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372782"
---
# <a name="scrolling-and-scaling-views"></a>뷰 스크롤 및 크기 조정

MFC는 스크롤하는 뷰와 해당 뷰를 표시하는 프레임 창 크기로 자동으로 배율이 조정되는 뷰를 지원합니다. 클래스는 `CScrollView` 두 가지 종류의 뷰를 모두 지원합니다.

스크롤 및 크기 조정에 대한 자세한 내용은 *MFC 참조의* [클래스 CScrollView를](../mfc/reference/cscrollview-class.md) 참조하십시오. 스크롤 예제는 [낙서 샘플을](../overview/visual-cpp-samples.md)참조하십시오.

## <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- 보기 스크롤

- 뷰 크기 조정

- [좌표 보기](/windows/win32/gdi/window-coordinate-system)

## <a name="scrolling-a-view"></a><a name="_core_scrolling_a_view"></a>보기 스크롤

문서의 크기가 뷰에서 표시할 수 있는 크기보다 큰 경우가 종종 있습니다. 이는 문서의 데이터가 증가하거나 사용자가 뷰를 프레임하는 창을 축소하기 때문에 발생할 수 있습니다. 이러한 경우 뷰는 스크롤을 지원해야 합니다.

모든 뷰는 해당 `OnHScroll` 및 `OnVScroll` 멤버 함수에서 스크롤 막대 메시지를 처리할 수 있습니다. 이러한 함수에서 스크롤 막대 메시지 처리를 구현하거나 모든 작업을 직접 수행하거나 `CScrollView` 클래스를 사용하여 스크롤을 처리할 수 있습니다.

`CScrollView`은 다음을 수행합니다.

- 창 및 뷰포트 크기 및 매핑 모드 관리

- 스크롤 막대 메시지에 대한 응답으로 자동으로 스크롤됩니다.

"페이지"(사용자가 스크롤 막대 샤프트를 클릭할 때)와 "선"(사용자가 스크롤 화살표를 클릭할 때)에 대해 스크롤할 양을 지정할 수 있습니다. 뷰의 특성에 맞게 이러한 값을 계획합니다. 예를 들어 그래픽 뷰의 경우 1픽셀 단위로 스크롤하지만 텍스트 문서의 선 높이를 기준으로 증분할 수 있습니다.

## <a name="scaling-a-view"></a><a name="_core_scaling_a_view"></a>뷰 크기 조정

뷰가 프레임 창의 크기에 자동으로 맞추도록 하려면 스크롤 `CScrollView` 대신 크기 조정에 사용할 수 있습니다. 논리적 뷰는 창의 클라이언트 영역에 맞게 늘어나거나 축소됩니다. 배율 조정된 뷰에는 스크롤 막대가 없습니다.

## <a name="see-also"></a>참고 항목

[뷰 사용](../mfc/using-views.md)
