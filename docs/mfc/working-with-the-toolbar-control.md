---
title: ToolBar 컨트롤 사용
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: 371f1944fae655556bbc9f89d7ffcce7cc326e5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365243"
---
# <a name="working-with-the-toolbar-control"></a>ToolBar 컨트롤 사용

이 문서에서는 도구 모음을 보다 잘 제어하기 위해 [CToolBar의](../mfc/reference/ctoolbar-class.md) 기본 구조인 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체에 액세스하는 방법을 설명합니다. 이 항목은 고급 항목입니다.

## <a name="procedures"></a>프로시저

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>CToolBar 개체의 기본 도구 모음 공통 컨트롤에 액세스하려면

1. [CToolBar 를 호출::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).

`GetToolBarCtrl`은 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체에 대한 참조를 반환합니다. 참조를 사용하여 도구 모음 컨트롤 클래스의 멤버 함수를 호출할 수 있습니다.

> [!CAUTION]
> `CToolBarCtrl` **Get** 함수를 호출하는 것은 안전하지만 **Set** 함수를 호출하는 경우 주의하십시오. 이 항목은 고급 항목입니다. 일반적으로 기본 도구 모음 컨트롤에 액세스할 필요가 없습니다.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [컨트롤(Windows 공통 컨트롤)](../mfc/controls-mfc.md)

- [도구 모음 기본 사항](../mfc/toolbar-fundamentals.md)

- [도구 모음 고정 및 고정 해제](../mfc/docking-and-floating-toolbars.md)

- [도구 모음의 동적으로 크기 조정](../mfc/docking-and-floating-toolbars.md)

- [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)

- [플라이비 상태 표시줄 업데이트](../mfc/toolbar-tool-tips.md)

- [도구 팁 알림 처리](../mfc/handling-tool-tip-notifications.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스

- [사용자 지정 알림 처리](../mfc/handling-customization-notifications.md)

- [여러 도구 모음](../mfc/toolbar-fundamentals.md)

- [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)

- [컨트롤 바](../mfc/control-bars.md)

Windows 공통 컨트롤 사용에 대한 일반적인 내용은 [일반 컨트롤](/windows/win32/Controls/common-controls-intro)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)
