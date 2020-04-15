---
title: '방법: Windows Forms 컨트롤에 명령 라우팅 추가'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: ad64a12051c22a0cfca99d3ec9c5abef579902f4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365165"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>방법: Windows Forms 컨트롤에 명령 라우팅 추가

[CWinFormsView](../mfc/reference/cwinformsview-class.md) 는 명령 및 업데이트 명령 UI 메시지를 사용자 컨트롤로 라우팅하여 MFC 명령(예: 프레임 메뉴 항목 및 도구 모음 단추)을 처리할 수 있도록 합니다.

사용자 컨트롤은 다음 예제와 같이 [ICommandTarget::초기화를](../mfc/reference/icommandtarget-interface.md#initialize) 사용하여 `m_CmdSrc`명령 소스 개체에 대한 참조를 에 저장합니다. 사용하려면 `ICommandTarget` mfcmifc80.dll에 대한 참조를 추가해야 합니다.

`CWinFormsView`은 관리되는 사용자 컨트롤로 전달하여 몇 가지 일반적인 MFC 뷰 알림을 처리합니다. 이러한 알림에는 [OnInitialUpdate,](../mfc/reference/iview-interface.md#oninitialupdate) [OnUpdate](../mfc/reference/iview-interface.md#onupdate) 및 [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) 메서드가 포함됩니다.

이 항목에서는 이전에 [완료한 방법: 대화 상자에서 사용자 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) 및 [방법: 사용자 컨트롤 만들기 및 MDI 보기 호스트](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)를 완료한 것으로 가정합니다.

### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면

1. 방법: [대화 상자에서 사용자 컨트롤 및 호스트 만들기에서](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)만든 Windows 양식 제어 라이브러리 열기.

1. mfcmifc80.dll에 대한 참조를 추가하면 **솔루션 탐색기에서**프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **참조** **추가를**선택한 다음 Microsoft Visual Studio 10.0\VC\atlmfc\lib로 검색할 수 있습니다.

1. UserControl1.Designer.cs 열고 문을 사용하여 다음을 추가합니다.

    ```
    using Microsoft.VisualC.MFC;
    ```

1. 또한 UserControl1.Designer.cs 다음 줄을 변경합니다.

    ```
    partial class UserControl1
    ```

   다음과 같이 변경합니다.

    ```
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget
    ```

1. 클래스 정의의 첫 번째 줄로 `UserControl1`추가합니다.

    ```
    private ICommandSource m_CmdSrc;
    ```

1. 다음 메서드 정의를 추가합니다(다음 `UserControl1` 단계에서 MFC 컨트롤의 ID를 만듭니다).

    ```
    public void Initialize (ICommandSource cmdSrc)
    {
       m_CmdSrc = cmdSrc;
       // need ID of control in MFC dialog and callback function
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));
    }

    private void singleMenuHandler (uint cmdUI)
    {
       // User command handler code
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");
    }
    ```

1. [방법: 사용자 컨트롤 만들기 및 MDI 보기 호스트에서](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)만든 MFC 응용 프로그램을 엽니다.

1. 을 호출하는 메뉴 옵션을 `singleMenuHandler`추가합니다.

   리소스 **Resource View** 보기(Ctrl+Shift+E)로 이동하여 **메뉴** 폴더를 확장한 다음 **IDR_MFC02TYPE**두 번 클릭합니다. 그러면 메뉴 편집기가 표시됩니다.

   **보기** 메뉴 의 맨 아래에 메뉴 옵션을 추가합니다. **속성** 창에서 메뉴 옵션의 ID를 확인합니다. 파일을 저장합니다.

   **솔루션 탐색기에서**Resource.h 파일을 열고 방금 추가한 메뉴 옵션의 ID 값을 복사한 다음 해당 `m_CmdSrc.AddCommandHandler` 값을 C# 프로젝트의 `Initialize` 메서드에서 호출에 첫 번째 매개 변수로 붙여 넣습니다(필요한 경우 대체). `32771`

1. 프로젝트를 빌드하고 실행합니다.

   **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

   **디버그** 메뉴에서 **디버깅하지 않고 시작을 클릭합니다.**

   추가한 메뉴 옵션을 선택합니다. .dll의 메서드가 호출됩니다.

## <a name="see-also"></a>참고 항목

[Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[ICommandSource 인터페이스](../mfc/reference/icommandsource-interface.md)<br/>
[ICommandTarget 인터페이스](../mfc/reference/icommandtarget-interface.md)
