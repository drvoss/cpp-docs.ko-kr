---
title: CCreateContext 구조체
ms.date: 11/04/2016
f1_keywords:
- CCreateContext
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
ms.openlocfilehash: 29fc6210b9888b6a5ba5aaf15b66242c29c15dc8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369375"
---
# <a name="ccreatecontext-structure"></a>CCreateContext 구조체

프레임워크는 문서와 연결된 프레임 창 및 뷰를 만들 때 `CCreateContext` 구조를 사용합니다.

## <a name="syntax"></a>구문

```
struct CCreateContext
```

## <a name="remarks"></a>설명

`CCreateContext`는 구조이며 기본 클래스가 없습니다.

창을 만들 때 이 구조의 값은 문서의 구성 요소를 해당 데이터 뷰에 연결하는 데 사용되는 정보를 제공합니다. 생성 프로세스의 `CCreateContext` 일부를 재정의하는 경우에만 사용해야 합니다.

구조체에는 `CCreateContext` 문서, 프레임 창, 뷰 및 문서 템플릿에 대한 포인터가 포함되어 있습니다. 또한 만들 뷰의 `CRuntimeClass` 유형을 식별하는 포인터가 포함되어 있습니다. 런타임 클래스 정보와 현재 문서 포인터는 새 뷰를 동적으로 만드는 데 사용됩니다. 다음 표는 각 `CCreateContext` 멤버를 사용하는 방법과 시기를 제시합니다.

|멤버|Type|그것은 무엇을 위해|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`을 클릭하여 만들 새 뷰를 만듭니다.|
|`m_pCurrentDoc`|`CDocument*`|새 뷰와 연결될 기존 문서입니다.|
|`m_pNewDocTemplate`|`CDocTemplate*`|새 MDI 프레임 창 작성과 관련된 문서 템플릿입니다.|
|`m_pLastView`|`CView*`|스플리터 창 뷰를 만들거나 문서에서 두 번째 뷰를 만들 때와 같이 추가 뷰가 모델링되는 원래 뷰입니다.|
|`m_pCurrentFrame`|`CFrameWnd*`|문서에 두 번째 프레임 창을 만들 때와 같이 추가 프레임 창이 모델링되는 프레임 창입니다.|

문서 템플릿이 문서및 관련 구성 요소를 만들면 구조체에 `CCreateContext` 저장된 정보의 유효성을 검사합니다. 예를 들어 존재하지 않는 문서에 대한 보기를 만들 면 안 됩니다.

> [!NOTE]
> 모든 `CCreateContext` 포인터는 선택 사항이며 지정되지 않았거나 알 수 없는 경우 일 수 `NULL` 있습니다.

`CCreateContext`"참조"에 나열된 멤버 함수에서 사용됩니다. 이러한 함수를 재정의하려는 경우 특정 정보에 대한 설명을 참조하십시오.

다음은 몇 가지 일반적인 지침입니다.

- 에서와 `CWnd::Create` `CFrameWnd::Create` `CFrameWnd::LoadFrame`같이 창 만들기에 대한 인수로 전달되면 create 컨텍스트는 새 창을 연결해야 하는 내용을 지정합니다. 대부분의 창의 경우 전체 구조는 `NULL` 선택 사항이며 포인터를 전달할 수 있습니다.

- 와 같은 `CFrameWnd::OnCreateClient`재정의 가능한 멤버 함수의 `CCreateContext` 경우 인수는 선택 사항입니다.

- 뷰 만들기와 관련된 멤버 함수의 경우 뷰를 만들기에 충분한 정보를 제공해야 합니다. 예를 들어 분할자 창의 첫 번째 뷰의 경우 뷰 클래스 정보와 현재 문서를 제공해야 합니다.

일반적으로 프레임워크 기본값을 사용하는 경우 을 무시할 `CCreateContext`수 있습니다. 고급 수정을 시도하는 경우 Microsoft 재단 클래스 라이브러리 소스 코드 또는 VIEWEX와 같은 샘플 프로그램이 안내합니다. 필수 매개 변수를 잊어버린 경우 프레임워크 어설션을 통해 잊어버린 내용을 알 수 있습니다.

자세한 `CCreateContext`내용은 MFC 샘플 [VIEWEX](../../overview/visual-cpp-samples.md)를 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)<br/>
[CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[C스플리터Wnd::만들기](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[C스플리터Wnd::만들기보기](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd::Create](../../mfc/reference/cwnd-class.md#create)
