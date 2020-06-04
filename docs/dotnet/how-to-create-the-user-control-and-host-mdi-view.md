---
title: '방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
ms.openlocfilehash: 72501ba32d3b8b9a5c5fd8dd0c56f0628642b147
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374463"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기

다음 단계에서는 .NET Framework 사용자 컨트롤을 만들고, 컨트롤 클래스 라이브러리(특히 Windows 컨트롤 라이브러리 프로젝트)에서 사용자 컨트롤을 작성한 다음 프로젝트를 어셈블리로 컴파일하는 방법을 보여 준다. 그런 다음 [CView 클래스](../mfc/reference/cview-class.md) 및 [CWinFormsView](../mfc/reference/cwinformsview-class.md)클래스에서 파생된 클래스를 사용하는 MFC 응용 프로그램에서 컨트롤을 사용할 수 있습니다.

Windows Forms 사용자 컨트롤을 만들고 컨트롤 클래스 라이브러리를 작성하는 방법에 대한 자세한 내용은 [사용자 컨트롤 작성 방법을](/dotnet/framework/winforms/controls/how-to-author-composite-controls)참조하십시오.

> [!NOTE]
> 경우에 따라 타사 Grid 컨트롤과 같은 Windows Forms 컨트롤은 MFC 응용 프로그램에서 호스팅될 때 안정적으로 재생되지 않을 수 있습니다. 권장되는 해결 방법은 MFC 응용 프로그램에 Windows Forms 사용자 컨트롤을 배치하고 타사 그리드 컨트롤을 사용자 컨트롤 내부에 배치하는 것입니다.

이 절차에서는 [대화 상자에서 사용자 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)의 절차에 따라 WindowsFormsControlLibrary1이라는 Windows Forms 컨트롤 라이브러리 프로젝트를 만들었다고 가정합니다.

### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면

1. MFC 응용 프로그램 프로젝트를 만듭니다.

   **파일** 메뉴에서 **새로**를 선택한 다음 **프로젝트를**클릭합니다. 시각적 **C++** 폴더에서 **MFC 응용 프로그램을**선택합니다.

   **이름** 상자에 **솔루션** `MFC02` 설정을 입력하고 변경하여 **솔루션에 추가합니다.** **확인**을 클릭합니다.

   **MFC 응용 프로그램 마법사에서**모든 기본값을 적용한 다음 **완료를**클릭합니다. 이렇게 하면 여러 문서 인터페이스가 있는 MFC 응용 프로그램이 만들어집니다.

1. CLR(공통 언어 런타임) 지원을 위한 프로젝트를 구성합니다.

   **솔루션 탐색기에서**프로젝트 `MFC01` 노드를 마우스 오른쪽 단추로 클릭하고 컨텍스트 메뉴에서 **속성을** 선택합니다. **속성 페이지** 대화 상자가 나타납니다.

   **구성 속성에서** **일반**을 선택합니다. 프로젝트 기본값 섹션에서 **공통 언어 런타임 지원을** 공통 언어 **런타임 지원(/clr)으로** **설정합니다.**

   **구성 속성에서** **C/C++를** 확장하고 **일반** 노드를 클릭합니다. **디버그 정보 형식을** **프로그램 데이터베이스(/Zi)로**설정합니다.

   코드 생성 노드를 **클릭합니다.** 설정 **최소 재생성** **없음(/Gm-)으로**설정합니다. 또한 **기본 런타임 검사를** **기본값으로**설정합니다.

   **확인을** 클릭하여 변경 내용을 적용합니다.

1. *pch.h(Visual* Studio 2017 및 이전 의*stdafx.h)에서* 다음 줄을 추가합니다.

    ```
    #using <System.Windows.Forms.dll>
    ```

1. .NET 컨트롤에 대한 참조를 추가합니다.

   **솔루션 탐색기에서**프로젝트 `MFC02` 노드를 마우스 오른쪽 단추로 클릭하고 **참조** **추가를**선택합니다. 속성 **페이지에서**새 **참조 추가를**클릭하고 프로젝트 **탭에서** WindowsFormsControlLibrary1을 선택하고 **확인을**클릭합니다. 이렇게 하면 프로그램이 컴파일되도록 [/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션 의 형태로 참조가 추가됩니다. 또한 프로그램이 실행되도록 `MFC02` WindowsFormsControlLibrary1.dll을 프로젝트 디렉터리로 복사합니다.

1. stdafx.h에서 다음 줄을 찾으십시오.

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   위에 다음 줄을 추가합니다.

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. [CWinFormsView에서](../mfc/reference/cwinformsview-class.md)상속되도록 뷰 클래스를 수정합니다.

   MFC02View.h에서 코드가 다음과 같이 표시되도록 [CView를](../mfc/reference/cview-class.md) [CWinFormsView로](../mfc/reference/cwinformsview-class.md) 바꿉니다.

    ```
    class CMFC02View : public CWinFormsView
    {
    };
    ```

   MDI 응용 프로그램에 추가 보기를 추가하려면 생성한 각 뷰에 대해 [CWinApp::AddDocTemplate를](../mfc/reference/cwinapp-class.md#adddoctemplate) 호출해야 합니다.

1. MFC02View.cpp 파일을 수정하여 IMPLEMENT_DYNCREATE 매크로 및 메시지 맵에서 CView를 CWinFormsView로 변경하고 기존 빈 생성기를 아래 표시된 생성물로 바꿉니다.

    ```
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)

    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)
    {
    }
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)
    //leave existing body as is
    END_MESSAGE_MAP()
    ```

1. 프로젝트를 빌드하고 실행합니다.

   **솔루션 탐색기에서**MFC02를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정을**선택합니다.

   **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

   **디버그** 메뉴에서 **디버깅하지 않고 시작을 클릭합니다.**

## <a name="see-also"></a>참고 항목

[Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
