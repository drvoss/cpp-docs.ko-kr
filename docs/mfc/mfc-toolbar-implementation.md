---
title: MFC 도구 모음 구현
ms.date: 11/04/2016
helpviewer_keywords:
- toolbars [MFC], creating
- buttons [MFC], MFC toolbars
- toolbars [MFC], docking
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- floating toolbars [MFC]
- toolbars [MFC], floating
- docking toolbars [MFC]
- bitmaps [MFC], toolbar
- toolbar controls [MFC]
- CToolBarCtrl class [MFC], implementing toolbars
- tool tips [MFC], enabling
- toolbars [MFC]
- toolbars [MFC], implementing MFC toolbars
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
ms.openlocfilehash: 38811be765d4427c4083b8f142b54fb67b9076a0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359312"
---
# <a name="mfc-toolbar-implementation"></a>MFC 도구 모음 구현

도구 모음은 컨트롤의 비트맵 이미지를 포함하는 컨트롤 [모음입니다.](../mfc/control-bars.md) 이러한 이미지는 푸시버튼, 확인란 또는 라디오 버튼처럼 동작할 수 있습니다. MFC는 도구 모음을 관리하기 위해 클래스 [CToolbar를](../mfc/reference/ctoolbar-class.md) 제공합니다.

이 도구를 사용하도록 설정하면 MFC 도구 모음 사용자는 창 가장자리에 도킹하거나 응용 프로그램 창 내의 아무 곳이나 "플로트"할 수 있습니다. MFC는 개발 환경과 같은 사용자 지정 가능한 도구 모음을 지원하지 않습니다.

MFC는 또한 도구 설명: 단추 위에 마우스를 배치할 때 도구 모음 단추의 목적을 설명 하는 작은 팝업 창 지원. 기본적으로 사용자가 도구 모음 단추를 누르면 상태 문자열이 상태 표시줄에 나타납니다(있는 경우). "fly by" 상태 표시줄을 활성화하여 마우스를 누르지 않고 단추 위에 놓일 때 상태 문자열을 표시할 수 있습니다.

> [!NOTE]
> MFC 버전 4.0에서는 MFC와 관련된 이전 구현 대신 Windows 95 및 이후 기능을 사용하여 도구 모음 및 도구 설명이 구현됩니다.

이전 버전과의 호환성을 위해 MFC는 클래스에서 `COldToolBar`이전 도구 모음 구현을 유지합니다. 이전 버전의 MFC에 대한 `COldToolBar` `CToolBar`설명서는 에서 설명합니다.

응용 프로그램 마법사에서 도구 모음 옵션을 선택하여 프로그램에서 첫 번째 도구 모음을 만듭니다. 추가 도구 모음을 만들 수도 있습니다.

다음은 이 문서에서 소개합니다.

- [도구 모음 단추](#_core_toolbar_buttons)

- [도구 모음 고정 및 고정 해제](#_core_docking_and_floating_toolbars)

- [도구 모음 및 도구 팁](#_core_toolbars_and_tool_tips)

- [CToolBar 및 CToolBarCtrl 클래스](#_core_the_ctoolbar_and_ctoolbarctrl_classes)

- [도구 모음 비트맵](#_core_the_toolbar_bitmap)

## <a name="toolbar-buttons"></a><a name="_core_toolbar_buttons"></a>도구 모음 단추

도구 모음의 단추는 메뉴의 항목과 유사합니다. 두 종류의 사용자 인터페이스 개체는 처리기 함수를 제공하여 프로그램에서 처리하는 명령을 생성합니다. 종종 도구 모음 단추는 메뉴 명령의 기능을 복제하여 동일한 기능에 대한 대체 사용자 인터페이스를 제공합니다. 이러한 중복은 버튼과 메뉴 항목에 동일한 ID를 부여하여 간단하게 정렬됩니다.

도구 모음의 단추가 나타나고 푸시버튼, 확인란 또는 라디오 단추로 동작하게 만들 수 있습니다. 자세한 내용은 클래스 [CToolBar](../mfc/reference/ctoolbar-class.md)를 참조하십시오.

## <a name="docking-and-floating-toolbars"></a><a name="_core_docking_and_floating_toolbars"></a>도킹 및 부동 도구 모음

MFC 도구 모음은 다음을 수행할 수 있습니다.

- 부모 창의 한쪽을 따라 고정된 상태로 유지합니다.

- 사용자가 지정한 상위 창의 모든 측면이나 측면에 드래그하여 "도킹"하거나 연결합니다.

- 사용자가 편리한 위치로 이동할 수 있도록 자체 미니 프레임 창에서 프레임 창에서 "부동"하거나 분리할 수 있습니다.

- 부동 상태에서 크기를 조정합니다.

자세한 내용은 [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)을 참조하십시오.

## <a name="toolbars-and-tool-tips"></a><a name="_core_toolbars_and_tool_tips"></a>도구 모음 및 도구 설명

MFC 도구 모음은 도구 모음 단추의 목적에 대한 간단한 텍스트 설명이 포함된 작은 팝업 창인 "도구 설명"을 표시하도록 만들 수도 있습니다. 사용자가 도구 모음 단추 위로 마우스를 이동하면 도구 설명 창이 나타나 힌트를 제공합니다. 자세한 내용은 [도구 모음 도구 모음 도구 모음 팁을](../mfc/toolbar-tool-tips.md)참조하십시오.

## <a name="the-ctoolbar-and-ctoolbarctrl-classes"></a><a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a>CToolBar 및 CToolBarCtrl 클래스

클래스 [CToolBar를](../mfc/reference/ctoolbar-class.md)통해 응용 프로그램의 도구 모음을 관리합니다. MFC 버전 4.0을 `CToolBar` 현재 Windows 95 이상 및 Windows NT 버전 3.51 이상에서 사용할 수 있는 도구 모음 공통 컨트롤을 사용하도록 다시 구현되었습니다.

MFC는 운영 체제 지원을 사용하기 때문에 이 다시 구현하면 도구 모음에 대한 MFC 코드가 줄어듭니다. 다시 구현하면 기능도 향상됩니다. 멤버 함수를 사용하여 `CToolBar` 도구 모음을 조작하거나 기본 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체에 대한 참조를 얻고 도구 모음 사용자 지정 및 추가 기능을 위해 해당 멤버 함수를 호출할 수 있습니다.

> [!TIP]
> `CToolBar`이전 MFC 구현에 많은 투자를 한 경우 해당 지원은 계속 사용할 수 있습니다. [이전 도구 모음을 사용하는](../mfc/using-your-old-toolbars.md)문서를 참조하십시오.

또한 MFC 일반 샘플 [DOCKTOOL을](../overview/visual-cpp-samples.md)참조하십시오.

## <a name="the-toolbar-bitmap"></a><a name="_core_the_toolbar_bitmap"></a>도구 모음 비트맵

생성되면 `CToolBar` 오브젝트는 각 단추에 대해 하나의 이미지가 포함된 단일 비트맵을 로드하여 도구 모음 이미지를 만듭니다. 응용 프로그램 마법사는 Visual C++ [도구 모음 편집기로](../windows/toolbar-editor.md)사용자 지정할 수 있는 표준 도구 모음 비트맵을 만듭니다.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [도구 모음 기본 사항](../mfc/toolbar-fundamentals.md)

- [도구 모음 고정 및 고정 해제](../mfc/docking-and-floating-toolbars.md)

- [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)

- [도구 모음 컨트롤 작업](../mfc/working-with-the-toolbar-control.md)

- [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스

## <a name="see-also"></a>참고 항목

[도구 모음](../mfc/toolbars.md)<br/>
[도구 모음 편집기](../windows/toolbar-editor.md)
