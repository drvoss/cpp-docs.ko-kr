---
title: 대화 상자 편집기(C++)
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
- vc.editors.dialog
helpviewer_keywords:
- resource editors [C++], Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes [C++], editing
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog Editor [C++], showing or hiding toolbar
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog Editor [C++], accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog Editor [C++], switching between controls and code
- Dialog Editor [C++], shortcut keys
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
ms.openlocfilehash: f1544d3a8e14f9373e21b77d888860d24ab1ed6a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370290"
---
# <a name="dialog-editor-c"></a>대화 상자 편집기(C++)

**대화 상자 편집기를** 사용하면 대화 상자 리소스를 만들거나 편집할 수 있습니다.

- 편집기를 열려면 **리소스 보기** 창에서 대화 상자의 .rc 파일을 두 번 클릭하거나**다른 Windows** > **리소스 보기** **보기** > 로 이동합니다.

새 대화 상자 또는 대화 상자 템플릿을 만드는 첫 번째 단계 중 하나는 컨트롤을 추가하는 것입니다. 대화 **상자 편집기에서**특정 크기, 모양 또는 정렬에 맞게 컨트롤을 정렬하거나 대화 상자 내에서 작업하도록 컨트롤을 이동할 수 있습니다. 또한 컨트롤을 쉽게 삭제할 수 있습니다.

대화 상자를 템플릿으로 저장하여 다시 사용할 수 있습니다. 대화 상자 디자인과 이를 구현하는 코드 편집 간을 쉽게 전환할 수도 있습니다.

**대화 상자 편집기에서**단일 또는 여러 컨트롤의 속성을 편집할 수도 있습니다. 탭 순서, 즉 **탭** 키를 누를 때 컨트롤이 포커스를 얻는 순서를 변경하거나 사용자가 키보드를 사용하여 컨트롤을 선택할 수 있는 액세스 키 또는 키 조합을 정의할 수 있습니다.

**대화 상자 편집기를** 사용하면 ActiveX 컨트롤을 비롯한 사용자 지정 컨트롤을 사용할 수도 있습니다. [양식 보기,](../mfc/reference/cformview-class.md) [레코드 보기](../data/record-views-mfc-data-access.md)또는 대화 [상자 막대를](../mfc/dialog-bars.md)편집할 수도 있습니다.

Visual Studio 2015부터는 대화 **상자 편집기를** 사용하여 사용자가 대화 상자크기를 조정할 때 컨트롤의 이동 및 크기 조정 방법을 지정하는 동적 레이아웃을 정의할 수 있습니다. 자세한 내용은 [Dynamic Layout](../mfc/dynamic-layout.md)을 참조하세요.

리소스에 대한 자세한 내용은 [대화 상자](../windows/creating-a-new-dialog-box.md) 및 [대화](../windows/controls-in-dialog-boxes.md)상자 컨트롤 을 만드는 방법을 참조하세요.

> [!TIP]
> **대화 상자 편집기를**사용하는 동안 대부분의 경우 오른쪽 마우스 단추를 사용하여 자주 사용하는 명령의 바로 가기 메뉴를 표시할 수 있습니다.

## <a name="dialog-editor-toolbar"></a>대화 상자 편집기 도구 모음

**대화 상자 편집기** 도구 모음에는 대화 상자의 컨트롤 레이아웃(예: 크기 및 정렬)을 정렬하기 위한 단추가 포함되어 있습니다. **대화 상자 편집기** 도구 모음 단추는 **형식** 메뉴의 명령에 해당합니다.

|아이콘|의미|아이콘|의미|
|----------|-------------|----------|-------------|
|![테스트 대화 상자 단추](../mfc/media/vcdialogeditortestdialog.png "vcDialog편집자테스트디아로그")|대화 상자 테스트|![전체 공간 단추](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|옆으로|
|![왼쪽 맞춤 단추](../mfc/media/vcdialogeditoralignlefts.png "vcDialog편집정렬왼쪽")|왼쪽 맞춤|![아래 공간 단추](../mfc/media/vcdialogeditordown.png "vcDialogEditor다운")|아래로|
|![오른쪽 맞춤 단추](../mfc/media/vcdialogeditoralignrights.png "vcDialog편집자정렬권리")|오른쪽 맞춤|![같은 너비로 단추](../mfc/media/vcdialogeditorsamewidth.png "vcDialog편집기폭")|같은 너비로|
|![위쪽 맞춤 단추](../mfc/media/vcdialogeditoraligntops.png "vcDialog편집정렬탑")|위쪽 맞춤|![같은 높이로 단추](../mfc/media/vcdialogeditormakesameheight.png "vcDialog편집기만들기동일높이높이")|같은 높이로|
|![아래쪽 맞춤 단추](../mfc/media/vcdialogeditoralignbottoms.png "vcDialog편집정렬 바닥")|아래쪽 맞춤|![같은 크기로 단추](../mfc/media/vcdialogeditorsamesize.png "vcDialog편집자사메사이즈")|같은 크기로|
|![세로 가운데 단추](../mfc/media/vcdialogeditorvertical.png "vcDialog편집기수직")|Vertical|![모눈 설정/해제 단추](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditor토글그리드")|모눈 설정/해제|
|![가로 가운데 단추](../mfc/media/vcdialogeditorhorizontal.png "vcDialog편집수평")|수평적 크기 조정|![안내선 설정/해제 단추](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|안내선 설정/해제|

- **대화 상자 편집기** 도구 모음을 표시하거나 숨기려면 메뉴 **도구로** > 이동**도구 모음** > **대화 상자 편집기로**이동합니다.

C++ 프로젝트에서 **대화 상자 편집기를** 열면 **대화 상자 편집기** 도구 모음이 솔루션 맨 위에 자동으로 나타나지만 도구 모음을 명시적으로 닫으면 다음에 대화 상자 **편집기를**열 때 호출해야 합니다. 사용 가능한 도구 모음 및 창 목록에서 디스플레이를 선택하여 표시를 전환할 수 있습니다.

## <a name="switch-between-dialog-box-controls-and-code"></a>대화 상자 컨트롤과 코드 간 전환

MFC 응용 프로그램에서 대화 상자 컨트롤을 두 번 클릭하여 처리기 코드로 이동하거나 스텁 처리기 함수를 빠르게 만들 수 있습니다.

컨트롤을 선택한 경우 속성 [창에서](/visualstudio/ide/reference/properties-window) **ControlEvents** 단추 또는 **메시지** 단추를 선택하여 선택한 항목에 사용할 수 있는 Windows 메시지 및 이벤트의 전체 목록을 볼 수 있습니다. 목록에서 선택하여 처리기 함수를 만들거나 편집합니다.

- **대화 상자 편집기에서**코드로 이동하려면 대화 상자 내의 컨트롤을 두 번 클릭하여 가장 최근에 구현된 메시지 처리 기능에 대한 선언으로 이동합니다.

   ATL 기반 대화 상자 클래스의 경우 항상 생성자 정의로 이동합니다.

- 컨트롤을 선택한 컨트롤의 이벤트를 보려면 **속성** 창에서 **ControlEvents** 단추를 선택합니다.

   단일 컨트롤에 대화 상자에 포커스가 있는 경우 마우스 오른쪽 단추로 클릭하고 **이벤트 처리기 추가를**선택할 수 있습니다. 이렇게 하면 처리기가 추가되는 클래스를 지정할 수 있습니다. 자세한 내용은 [이벤트 처리기 추가를](../ide/adding-an-event-handler-visual-cpp.md)참조하십시오.

   > [!NOTE]
   > 대화 상자에 포커스가 있는 경우 **ControlEvents** 단추를 선택하면 대화 상자의 모든 컨트롤 목록이 노출되며, 이 경우 개별 컨트롤에 대한 이벤트를 편집하도록 확장할 수 있습니다.

- 대화 상자를 선택한 대화 상자에 대한 메시지를 보려면 **속성** 창에서 **메시지** 단추를 선택합니다.

## <a name="accelerator-keys"></a>액셀러레이터 키

다음은 **대화 상자 편집기** 명령에 대한 기본 가속기 키입니다.  

|명령|구성|Description|
|-------------|----------|-----------------|
|Format.AlignBottoms|**화살표** + **아래로** **이동하는** + Ctrl|선택한 컨트롤의 아래쪽 가장자리를 지배적인 컨트롤과 정렬합니다.|
|Format.AlignCenters|**시프트** + **F9**|선택한 컨트롤의 수직 중심을 지배적인 컨트롤과 정렬합니다.|
|Format.AlignLefts|**Ctrl** + **시프트** + **왼쪽 화살표**|선택한 컨트롤의 왼쪽 가장자리를 지배적인 컨트롤과 정렬합니다.|
|Format.AlignMiddles|**F9**|선택한 컨트롤의 수평 중심을 지배적인 컨트롤과 정렬합니다.|
|Format.AlignRights|**Ctrl** + **시프트** + **오른쪽 화살표**|선택한 컨트롤의 오른쪽 가장자리를 지배적인 컨트롤과 정렬합니다.|
|Format.AlignTops|**Ctrl** + **시프트** + **업 애로우**|선택한 컨트롤의 위쪽 가장자리를 지배적인 컨트롤과 정렬합니다.|
|Format.ButtonBottom|**Ctrl** + **B**|선택한 단추를 대화 상자의 아래쪽 가운데를 따라 배치합니다.|
|Format.ButtonRight|**Ctrl** + **R**|선택한 단추를 대화 상자의 오른쪽 상단 모서리에 배치합니다.|
|Format.CenterHorizontal|**Ctrl** + **시프트** + **F9**|대화 상자 내에서 컨트롤을 가로로 중심으로 합니다.|
|Format.CenterVertical|**Ctrl** + **F9**|대화 상자 내에서 컨트롤을 세로로 중심으로 합니다.|
|Format.CheckMnemonics|**Ctrl** + **M**|암기의 고유성을 확인합니다.|
|형식.크기토콘텐츠|**시프트** + **F7**|선택한 컨트롤의 크기를 캡션 텍스트에 맞게 조정합니다.|
|Format.SpaceAcross|**Alt** + **왼쪽 화살표**|선택한 컨트롤을 가로로 균등하게 공백으로 설정합니다.|
|Format.SpaceDown|**아래쪽 화살표 를 아래로 높이 지고** + **있습니다.**|선택한 컨트롤을 수직으로 균등하게 간격을 두는 다.|
|Format.TabOrder|**Ctrl** + **D**|대화 상자 내에서 컨트롤의 순서를 설정합니다.|
|Format.TestDialog|**Ctrl** + **T**|대화 상자를 실행하여 모양과 동작을 테스트합니다.|
|Format.ToggleGuides|**Ctrl** + **G**|대화 상자 편집을 위해 그리드, 지침 및 그리드 를 순환하지 않습니다.|

- 바로 가기 키를 변경하려면 메뉴 **도구** > **옵션으로**이동하여 **환경** 폴더에서 **키보드를** 선택합니다.

   자세한 내용은 [바로 가기 키 식별 및 사용자 지정](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)을 참조하세요.

- 설정을 변경하려면 메뉴 **도구** > **가져오기 및 내보내기 설정으로**이동합니다.

   대화 상자에서 사용할 수 있는 옵션과 표시되는 메뉴 명령의 이름과 위치는 활성 설정 또는 버전에 따라 **도움말에** 설명된 내용과 다를 수 있습니다.  자세한 내용은 [시각적 스튜디오 IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하십시오.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고 항목

[리소스 편집기](../windows/resource-editors.md)<br/>
[방법: 대화 상자 만들기](../windows/creating-a-new-dialog-box.md)<br/>
[대화 상자 컨트롤](../windows/controls-in-dialog-boxes.md)<br/>
<!--
[Controls](../mfc/controls-mfc.md)<br/>
[Control Classes](../mfc/control-classes.md)<br/>
[Dialog Box Classes](../mfc/dialog-box-classes.md)<br/>
[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)-->
