---
title: 도구 모음 기본 사항
ms.date: 11/04/2016
f1_keywords:
- RT_TOOLBAR
helpviewer_keywords:
- embedding toolbar in frame window class [MFC]
- application wizards [MFC], installing default application toolbars
- toolbars [MFC], creating
- resources [MFC], toolbar
- toolbar controls [MFC], toolbars created using Application Wizard
- toolbar controls [MFC], command ID
- RT_TOOLBAR resource [MFC]
- toolbars [MFC], adding default using Application Wizard
- LoadBitmap method [MFC], toolbars
- Toolbar editor [MFC], Application Wizard
- command IDs [MFC], toolbar buttons
- SetButtons method [MFC]
- CToolBar class [MFC], default toolbars in Application Wizard
- frame window classes [MFC], toolbar embedded in
- LoadToolBar method [MFC]
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
ms.openlocfilehash: d4e8793337beb2eed533fe04daf549ec21efc61d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373475"
---
# <a name="toolbar-fundamentals"></a>도구 모음 기본 사항

이 문서에서는 응용 프로그램 마법사에서 옵션을 선택하여 응용 프로그램에 기본 도구 모음을 추가할 수 있는 기본 MFC 구현에 대해 설명합니다. 다음 내용을 다룹니다.

- [응용 프로그램 마법사 도구 모음 옵션](#_core_the_appwizard_toolbar_option)

- [코드의 도구 모음](#_core_the_toolbar_in_code)

- [도구 모음 리소스 편집](#_core_editing_the_toolbar_resource)

- [여러 도구 모음](#_core_multiple_toolbars)

## <a name="the-application-wizard-toolbar-option"></a><a name="_core_the_appwizard_toolbar_option"></a>응용 프로그램 마법사 도구 모음 옵션

기본 버튼이 있는 단일 도구 모음을 얻으려면 사용자 인터페이스 기능이라고 표시된 페이지에서 표준 도킹 도구 모음 옵션을 선택합니다. 이렇게 하면 응용 프로그램에 다음과 같은 코드가 추가됩니다.

- 도구 모음 개체를 만듭니다.

- 도킹 또는 플로팅 기능을 포함하여 도구 모음을 관리합니다.

## <a name="the-toolbar-in-code"></a><a name="_core_the_toolbar_in_code"></a>코드의 도구 모음

도구 모음은 응용 프로그램 클래스의 `CMainFrame` 데이터 멤버로 선언된 [CToolBar](../mfc/reference/ctoolbar-class.md) 개체입니다. 즉, 도구 모음 개체는 주 프레임 창 개체에 포함됩니다. 즉, MFC는 프레임 창을 만들 때 도구 모음을 만들고 프레임 창을 파괴할 때 도구 모음을 파괴합니다. 여러 문서 인터페이스(MDI) 응용 프로그램의 다음 부분 클래스 선언은 포함된 도구 모음및 포함된 상태 표시줄에 대한 데이터 멤버를 표시합니다. `OnCreate` 멤버 함수의 재정의도 표시됩니다.

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

도구 모음 만들기에서 발생합니다. `CMainFrame::OnCreate` MFC는 프레임에 대한 창을 만든 후 표시되기 전에 [OnCreate를](../mfc/reference/cwnd-class.md#oncreate) 호출합니다. 응용 `OnCreate` 프로그램 마법사가 생성하는 기본값은 다음과 같은 도구 모음 작업을 수행합니다.

1. 기본 `CToolBar` [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체를 만들기 위해 개체의 멤버 [만들기](../mfc/reference/ctoolbar-class.md#create) 함수를 호출합니다.

1. [LoadToolBar를](../mfc/reference/ctoolbar-class.md#loadtoolbar) 호출하여 도구 모음 리소스 정보를 로드합니다.

1. 도킹, 부동 및 공구 팁을 활성화하는 기능을 호출합니다. 이러한 호출에 대한 자세한 내용은 [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)을 참조하십시오.

> [!NOTE]
> MFC 일반 샘플 [DOCKTOOL에는](../overview/visual-cpp-samples.md) 이전 및 새 MFC 도구 모음의 그림이 포함되어 있습니다. 사용하는 `COldToolbar` 도구 모음은 2단계에서 `LoadBitmap` 호출이 필요합니다(대신)와 `LoadToolBar`에 `SetButtons`대한 호출 새 도구 모음에는 `LoadToolBar`에 대한 호출이 필요합니다.

도킹, 부동 및 공구 팁 호출은 선택 사항입니다. 원하는 `OnCreate` 경우 해당 줄을 제거할 수 있습니다. 그 결과 고정된 상태로 유지되고, 부동 또는 다시 도킹할 수 없으며, 공구 팁을 표시할 수 없는 도구 모음이 생성됩니다.

## <a name="editing-the-toolbar-resource"></a><a name="_core_editing_the_toolbar_resource"></a>도구 모음 리소스 편집

응용 프로그램 마법사를 사용하여 얻을 기본 도구 모음은 MFC 버전 4.0에 도입된 **RT_TOOLBAR** 사용자 지정 리소스를 기반으로 합니다. [도구 모음 편집기에서](../windows/toolbar-editor.md)이 리소스를 편집할 수 있습니다. 편집기에서 단추를 쉽게 추가, 삭제 및 다시 정렬할 수 있습니다. 여기에는 Visual C++의 일반 그래픽 편집기와 매우 유사한 단추에 대한 그래픽 편집기도 포함되어 있습니다. 이전 버전의 Visual C++에서 도구 모음을 편집한 경우 이제 작업이 훨씬 쉬워집니다.

도구 모음 단추를 명령에 연결하려면 단추에 와 같은 `ID_MYCOMMAND`명령 ID를 지정합니다. 도구 모음 편집기에서 단추의 속성 페이지에 명령 ID를 지정합니다. 그런 다음 명령에 대한 처리기 함수를 만듭니다(자세한 내용은 [메시지에 대한 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md) 참조).

새 [CToolBar](../mfc/reference/ctoolbar-class.md) 멤버 함수는 **RT_TOOLBAR** 리소스와 함께 작동합니다. [LoadToolBar는](../mfc/reference/ctoolbar-class.md#loadtoolbar) 이제 [LoadBitmap을](../mfc/reference/ctoolbar-class.md#loadbitmap) 대신하여 도구 모음 단추 이미지의 비트맵을 로드하고 [SetButtons를](../mfc/reference/ctoolbar-class.md#setbuttons) 사용하여 단추 스타일을 설정하고 비트맵 이미지로 단추를 연결합니다.

도구 모음 편집기 사용에 대한 자세한 내용은 [도구 모음 편집기](../windows/toolbar-editor.md)를 참조하십시오.

## <a name="multiple-toolbars"></a><a name="_core_multiple_toolbars"></a>여러 도구 모음

응용 프로그램 마법사는 하나의 기본 도구 모음을 제공합니다. 응용 프로그램에 두 개 이상의 도구 모음이 필요한 경우 기본 도구 모음에 대해 마법사에서 생성한 코드를 기반으로 추가 도구 모음에 대한 코드를 모델링할 수 있습니다.

명령의 결과로 도구 모음을 표시하려면 다음을 수행해야 합니다.

- 도구 모음 편집기로 새 도구 모음 리소스를 만들고 LoadToolbar 멤버 `OnCreate` 함수를 사용하여 [로드합니다.](../mfc/reference/ctoolbar-class.md#loadtoolbar)

- 기본 프레임 창 클래스에 새 [CToolBar](../mfc/reference/ctoolbar-class.md) 개체를 포함합니다.

- 도구 모음을 도킹하거나 `OnCreate` 플로트하고 스타일을 설정하는 등 적절한 함수 호출을 합니다.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [MFC 도구 모음 구현(도구 모음에 대한 개요 정보)](../mfc/mfc-toolbar-implementation.md)

- [도구 모음 고정 및 고정 해제](../mfc/docking-and-floating-toolbars.md)

- [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스

- [도구 모음 컨트롤 사용](../mfc/working-with-the-toolbar-control.md)

- [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>참고 항목

[MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)
