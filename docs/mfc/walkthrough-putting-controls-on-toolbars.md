---
title: '연습: 도구 모음에 컨트롤 배치'
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: 2a801e61c49301d9b8780bbf7eb77025990337ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360265"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>연습: 도구 모음에 컨트롤 배치

이 문서에서는 도구 모음에 Windows 컨트롤이 포함된 도구 모음 단추를 추가하는 방법에 대해 설명합니다. MFC에서 도구 모음 단추는 CMFCToolBarBarComboBoxButton 클래스, [CMFCToolBar편집상자 단추 클래스,](../mfc/reference/cmfctoolbareditboxbutton-class.md) [CMFC드롭다운툴버튼 단추 클래스](../mfc/reference/cmfcdropdowntoolbarbutton-class.md)또는 [CMFCToolBarMenuButton 클래스와](../mfc/reference/cmfctoolbarmenubutton-class.md)같은 [CMFCToolBarButton 클래스-파생](../mfc/reference/cmfctoolbarbutton-class.md)클래스여야 합니다. [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="adding-controls-to-toolbars"></a>도구 모음에 컨트롤 추가

도구 모음에 컨트롤을 추가 하려면 다음 단계를 따르십시오.

1. 부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다. Visual Studio의 **도구 모음 편집기를** 사용하여 단추를 만드는 방법에 대한 자세한 내용은 [도구 모음 편집기](../windows/toolbar-editor.md) 문서를 참조하세요.

1. 부모 도구 모음에서 모든 비트맵의 단추에 대한 도구 모음 이미지(단추 아이콘)를 예약합니다.

1. `AFX_WM_RESETTOOLBAR` 메시지를 처리하는 메시지 처리기에서 다음 단계를 수행합니다.

   1. `CMFCToolbarButton` 파생 클래스를 사용하여 단추 컨트롤을 생성합니다.

   1. [CMFCToolBar::ReplaceButton을](../mfc/reference/cmfctoolbar-class.md#replacebutton)사용하여 더미 버튼을 새 컨트롤로 바꿉꿉니까? `ReplaceButton`은 단추 개체를 복사하고 복사본을 유지하므로 스택에서 단추 개체를 생성할 수 있습니다.

> [!NOTE]
> 응용 프로그램에서 사용자 지정을 사용하도록 설정한 경우 **사용자 지정** 대화 상자의 도구 모음 탭의 **도구** 모음 단추를 사용하여 다시 컴파일한 후 응용 프로그램에서 업데이트된 컨트롤을 확인하여 도구 **모음을** 다시 설정해야 할 수 있습니다. 도구 모음 상태는 Windows 레지스트리에 저장되며 레지스트리 정보는 애플리케이션이 시작하는 동안 `ReplaceButton` 메서드가 실행된 후 로드됩니다.

## <a name="toolbar-controls-and-customization"></a>도구 모음 컨트롤 및 사용자 지정

**사용자 지정** 대화 상자의 **명령** 탭에는 응용 프로그램에서 사용할 수 있는 명령 목록이 포함되어 있습니다. 기본적으로 사용자 **지정** 대화 상자는 응용 프로그램 메뉴를 처리하고 각 메뉴 범주의 표준 도구 모음 단추 목록을 작성합니다. 도구 모음 컨트롤에서 제공하는 확장된 기능을 유지하려면 표준 도구 모음 단추를 **사용자 지정** 대화 상자의 사용자 지정 컨트롤로 바꿔야 합니다.

사용자 지정을 사용하도록 설정하면 [CMFCToolBarsCustomizeDialog](../mfc/reference/cmfctoolbarscustomizedialog-class.md) `OnViewCustomize` 클래스 클래스를 사용하여 사용자 지정 처리기에서 **사용자 지정** 대화 상자를 만듭니다. [CMFCToolBars사용자 지정Dialog::Create를](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create)호출하여 **사용자 지정** 대화 상자를 표시하기 전에 [CMFCToolBars사용자 정의Dialog::바꾸기 단추를](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) 호출하여 표준 단추를 새 컨트롤로 바꿉꿉습니다.

## <a name="example-creating-a-find-combo-box"></a>예제: 찾기 콤보 상자 만들기

이 섹션에서는 도구 모음에 나타나고 최근에 사용한 검색 문자열을 포함하는 **콤보** 찾기 컨트롤을 만드는 방법에 대해 설명합니다. 사용자는 컨트롤에 문자열을 입력한 다음 Enter 키를 눌러 문서를 검색하거나 Esc 키를 눌러 주 프레임에 포커스를 반환합니다. 이 예제에서는 문서가 [CEditView 클래스](../mfc/reference/ceditview-class.md)파생 뷰에 표시된다고 가정합니다.

### <a name="creating-the-find-control"></a>찾기 컨트롤 만들기

먼저 콤보 **찾기** 상자 컨트롤을 만듭니다.

1. 애플리케이션 리소스에 단추와 해당 명령을 추가합니다.

   1. 애플리케이션 리소스에서 `ID_EDIT_FIND` 명령 ID로 애플리케이션의 도구 모음이나 도구 모음과 연결된 모든 비트맵에 새 버튼을 추가합니다.

   1. `ID_EDIT_FIND` 명령 ID를 사용하여 새 메뉴 항목을 만듭니다.

   1. 새로운 문자열 "텍스트 찾기\n찾기"를 문자열 테이블에 추가하고 `ID_EDIT_FIND_COMBO` 명령 ID를 할당합니다. 이 ID는 콤보 **찾기** 상자 단추의 명령 ID로 사용됩니다.

        > [!NOTE]
        > `ID_EDIT_FIND`는 `CEditView`에 의해 처리되는 표준 명령이므로 이 명령을 위해 특수한 처리기를 구현하지 않아도 됩니다.  그러나 새 `ID_EDIT_FIND_COMBO` 명령에 대한 처리기를 구현해야 합니다.

1. [CComboBox](../mfc/reference/ccombobox-class.md) `CFindComboBox`클래스에서 파생된 새 클래스를 만듭니다.

1. `CFindComboBox` 클래스에서 `PreTranslateMessage` 가상 메서드를 재정의합니다. 이 방법을 사용하면 콤보 상자에서 [WM_KEYDOWN](/windows/win32/inputdev/wm-keydown) 메시지를 처리할 수 있습니다. 사용자가 Esc 키를 누르면(`VK_ESCAPE`) 주 프레임 창으로 포커스를 반환합니다. 사용자가 Enter 키를 누르면(`VK_ENTER`) `WM_COMMAND` 명령 ID를 포함하는 `ID_EDIT_FIND_COMBO` 메시지를 주 프레임 창에 게시합니다.

1. [CMFCToolBarComboBoxButton 클래스에서](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)파생된 콤보 상자 **찾기** 단추에 대한 클래스를 만듭니다. 이 예제에서는 `CFindComboButton`라는 이름으로 지정됩니다.

1. `CMFCToolbarComboBoxButton`의 생성자에는 세 개의 매개 변수(단추의 명령 ID, 단추 이미지 인덱스 및 콤보 상자의 스타일)가 있습니다. 이러한 매개 변수를 다음과 같이 설정합니다.

   1. `ID_EDIT_FIND_COMBO`를 명령 ID로 전달합니다.

   1. [CCommandManager::GetCmdImage를](reference/internal-classes.md) `ID_EDIT_FIND` 사용하여 이미지 인덱스를 가져옵니다.

   1. 사용 가능한 콤보 상자 스타일 목록은 [콤보 상자 스타일을](../mfc/reference/styles-used-by-mfc.md#combo-box-styles)참조하십시오.

1. `CFindComboButton` 클래스에서 `CMFCToolbarComboBoxButton::CreateCombo` 메서드를 재정의합니다. 여기서 `CFindComboButton` 개체를 만들고 해당 개체에 대한 포인터를 반환해야 합니다.

1. [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로를 사용하여 콤보 단추를 영구적으로 만듭니다. 작업 영역 관리자가 Windows 레지스트리에서 단추의 상태를 자동으로 로드 및 저장합니다.

1. 문서 뷰에서 `ID_EDIT_FIND_COMBO` 처리기를 구현합니다. [CMFCToolBar::GetCommandButtons를](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) `ID_EDIT_FIND_COMBO` 사용하여 모든 콤보 상자 **찾기** 단추를 검색합니다. 사용자 지정으로 인해 명령 ID가 동일한 단추의 복사본이 여러 개 있을 수 있습니다.

1. `ID_EDIT_FIND` 메시지 처리기에서 `OnFind` [CMFCToolBar::IsLastCommandFromButton을](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) 사용하여 찾기 명령이 **콤보** 찾기 상자 단추에서 전송되었는지 여부를 확인합니다. 명령을 보낸 경우 텍스트를 찾고 콤보 상자에 검색 문자열을 추가합니다.

### <a name="adding-the-find-control-to-the-main-toolbar"></a>주 도구 모음에 찾기 컨트롤 추가

도구 모음에 콤보 상자 단추를 추가하려면 다음 단계를 따르십시오.

1. 주 프레임 창의 `AFX_WM_RESETTOOLBAR` 메시지 처리기 `OnToolbarReset`을 구현합니다.

    > [!NOTE]
    > 애플리케이션이 시작하는 동안 도구 모음이 초기화되는 경우 또는 도구 모음이 사용자 지정 동안 다시 설정되는 경우 프레임워크는 이 메시지를 주 프레임 창으로 보냅니다. 두 경우 모두 표준 도구 모음 단추를 사용자 지정 콤보 상자 **찾기** 단추로 바꿔야 합니다.

1. `AFX_WM_RESETTOOLBAR` 처리기에서 도구 모음 ID, 즉 AFX_WM_RESETTOOLBAR 메시지의 *WPARAM을* 검사합니다. 도구 모음 ID가 콤보 **찾기** 상자 단추를 포함하는 도구 모음의 ID와 같으면 [CMFCToolBar::ReplaceButton을](../mfc/reference/cmfctoolbar-class.md#replacebutton) 호출하여 **찾기** 단추(즉, 명령 ID가 `ID_EDIT_FIND)` 있는 단추를 `CFindComboButton` 개체와 함께)로 바꿉습니다.

    > [!NOTE]
    > `CFindComboBox`이 단추 개체를 복사하고 복사본을 유지하므로 스택에서 `ReplaceButton`를 생성할 수 있습니다.

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>사용자 지정 대화 상자에 찾기 컨트롤 추가

사용자 지정 `OnViewCustomize`처리기에서 [CMFCToolBarsCustomizeDialog::바꾸기 단추를](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) **개체로 바꾸기** 단추(즉, 명령 `ID_EDIT_FIND`ID가 `CFindComboButton` 있는 단추)를 호출합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../mfc/hierarchy-chart.md)<br/>
[클래스](../mfc/reference/mfc-classes.md)<br/>
[CMFC툴바 클래스](../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton 클래스](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFC툴바콤보박스버튼 클래스](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCToolBars커렌드디아로그 클래스](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
