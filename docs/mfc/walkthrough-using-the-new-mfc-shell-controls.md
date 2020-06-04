---
title: '연습: 새 MFC 셸 컨트롤 사용'
ms.date: 04/25/2019
helpviewer_keywords:
- shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
ms.openlocfilehash: 5786fbbf7ec9f31e7d895a96dae27b8fc95abda1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360220"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>연습: 새 MFC 셸 컨트롤 사용

이 연습에서는 파일 탐색기와 유사한 응용 프로그램을 만듭니다. 두 개의 창이 있는 창을 만듭니다. 왼쪽 창에는 계층적 보기에서 바탕 화면을 표시하는 [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) 개체가 표시됩니다. 오른쪽 창에는 왼쪽 창에서 선택한 폴더의 파일을 표시하는 [CMFCShellListCtrl이](../mfc/reference/cmfcshelllistctrl-class.md) 표시됩니다.

## <a name="prerequisites"></a>사전 요구 사항

- Visual Studio 2017 이상에서 MFC 지원은 선택적 구성 요소입니다. 설치하려면 Windows 시작 메뉴에서 Visual Studio 설치 관리자를 엽니다. 사용 중인 Visual Studio 버전을 찾아 **수정** 단추를 선택합니다. **C++** 타일이 있는 데스크톱 개발이 선택되어 있는지 확인합니다. **선택적 구성 요소에서** **MFC 지원** 단추를 확인합니다.

- 이 연습에서는 **일반 개발 설정을**사용하도록 Visual Studio를 설정했다고 가정합니다. 다른 개발 설정을 사용하는 경우 이 연습에서 사용하는 일부 Visual Studio 창이 기본적으로 표시되지 않을 수 있습니다.

## <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC 응용 프로그램 마법사를 사용하여 새 MFC 응용 프로그램을 만들려면

이러한 단계는 사용 중인 Visual Studio 버전에 따라 다릅니다. 선호하는 버전의 Visual Studio에 대한 설명서를 보려면 **버전** 선택기 컨트롤을 사용합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker range="vs-2019"

### <a name="to-create-an-mfc-project-in-visual-studio-2019"></a>비주얼 스튜디오 2019에서 MFC 프로젝트를 만들려면

1. 주 메뉴에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트 만들기** 대화 상자를 엽니다.

1. 상단의 검색 상자에서 **MFC를** 입력한 다음 결과 목록에서 **MFC 앱을** 선택합니다.

1. **다음**을 클릭합니다. 다음 페이지에서 프로젝트의 이름을 입력하고 원하는 경우 프로젝트 위치를 지정합니다.

1. **만들기** 단추를 선택하여 프로젝트를 만듭니다.

   **MFC 응용 프로그램 마법사가** 표시되면 다음 옵션을 사용합니다.

   1. 왼쪽에 있는 **응용 프로그램 유형을** 선택합니다. 그런 다음 **단일 문서를** 선택하고 **문서/보기 아키텍처 지원을**선택합니다. **프로젝트 스타일에서** **Visual Studio를**선택하고 **시각적 스타일 및 색상** 드롭다운 목록에서 Office **2007(파란색 테마)을**선택합니다.

   1. 복합 **문서 지원** 창에서 **없음을**선택합니다.

   1. **문서 템플릿 속성** 창을 변경하지 마십시오.

   1. 사용자 **인터페이스 기능** 창에서 메뉴 **막대 사용 및 도구 모음** 옵션을 선택했는지 확인합니다. 다른 모든 옵션은 그대로 둡니다.

   1. 고급 **기능** 창에서 **ActiveX 컨트롤,** **공통 제어 매니페스트**및 **탐색 창을 선택합니다.** 다른 모든 것을 그대로 두십시오. **탐색 창** 옵션을 사용하면 마법사가 `CMFCShellTreeCtrl` 이미 포함된 창의 왼쪽에 창을 만듭니다.

   1. **생성된 클래스** 창을 변경하지 않으므로 **완료를** 클릭하여 새 MFC 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-an-mfc-project-in-visual-studio-2017-or-earlier"></a>Visual Studio 2017 또는 이전 환경에서 MFC 프로젝트를 만들려면

1. **MFC 응용 프로그램 마법사를** 사용하여 새 MFC 응용 프로그램을 만듭니다. 마법사를 실행하려면 **파일** 메뉴에서 **새로**를 선택한 다음 **프로젝트**를 선택합니다. **새 프로젝트** 대화 상자가 표시됩니다.

1. 새 **프로젝트** 대화 상자에서 **프로젝트 유형** 창에서 **Visual C++** 노드를 확장하고 **MFC를**선택합니다. 그런 다음 템플릿 창에서 **MFC 응용 프로그램을** **선택합니다.** 프로젝트의 이름을 `MFCShellControls` 입력하고 **확인을**클릭합니다.

   **MFC 응용 프로그램 마법사가** 표시되면 다음 옵션을 사용합니다.

   1. 응용 **프로그램 유형** 창에서 **응용 프로그램 유형**아래에서 **탭된 문서** 옵션을 선택 취소합니다. 다음으로 **단일 문서를** 선택하고 **문서/보기 아키텍처 지원을**선택합니다. **프로젝트 스타일에서** **Visual Studio를**선택하고 **시각적 스타일 및 색상** 드롭다운 목록에서 Office **2007(파란색 테마)을**선택합니다.

   1. 복합 **문서 지원** 창에서 **없음을**선택합니다.

   1. **문서 템플릿 문자열** 창을 변경하지 마십시오.

   1. 데이터베이스 **지원** 창(Visual Studio 2015 이상)에서 응용 프로그램이 데이터베이스를 사용하지 않으므로 **없음을** 선택합니다.

   1. 사용자 **인터페이스 기능** 창에서 메뉴 **막대 사용 및 도구 모음** 옵션을 선택했는지 확인합니다. 다른 모든 옵션은 그대로 둡니다.

   1. 고급 **기능** 창에서 **고급 기능**에서 **ActiveX 컨트롤** 및 공통 제어 **매니페스트만**선택합니다. **고급 프레임 창**아래에서 탐색 **창** 옵션만 선택합니다. 마법사가 `CMFCShellTreeCtrl` 이미 포함된 창의 왼쪽에 창을 만듭니다.

   1. **생성된 클래스** 창을 변경하지 않으므로 **완료를** 클릭하여 새 MFC 프로젝트를 만듭니다.

::: moniker-end

응용 프로그램을 빌드하고 실행하여 응용 프로그램을 성공적으로 만들었는지 확인합니다. 응용 프로그램을 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드를**선택합니다. 응용 프로그램이 성공적으로 빌드되면 **디버그** 메뉴에서 **디버깅 시작을** 선택하여 응용 프로그램을 실행합니다.

마법사는 폴더 **보기** 및 **일정** 보기가 있는 창 왼쪽에 표준 메뉴 모음, 표준 도구 모음, 표준 상태 표시줄 및 Outlook 막대가 있는 응용 프로그램을 자동으로 만듭니다.

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>문서 보기에 셸 목록 컨트롤을 추가하려면

1. 이 섹션에서는 마법사가 만든 뷰에 `CMFCShellListCtrl` 인스턴스를 추가합니다. **솔루션 탐색기에서** **MFCShellControlsView.h를** 두 번 클릭하여 뷰 헤더 파일을 엽니다.

   `#pragma once` 지시문을 헤더 파일 의 맨 위에 배치합니다. 바로 아래에 이 코드를 추가하여 다음 `CMFCShellListCtrl`에 대한 헤더 파일을 포함합니다.

   ```cpp
   #include <afxShellListCtrl.h>
   ```

   이제 type. `CMFCShellListCtrl` 먼저 헤더 파일에서 다음 주석을 찾습니다.

   ```cpp
   // Generated message map functions
   ```

   해당 주석 바로 위에 이 코드를 추가합니다.

   ```cpp
   private:
   CMFCShellListCtrl m_wndList;
   ```

1. **MFC 응용 프로그램 마법사는** `CMFCShellTreeCtrl` 이미 `CMainFrame` 클래스에서 개체를 만들었지만 보호된 멤버입니다. 나중에 개체에 액세스하므로 지금 개체에 대한 접근자만들기를 만듭니다. **솔루션 탐색기에서**MainFrm.h 헤더 파일을 두 번 클릭하여 엽니다. 다음 주석을 찾습니다.

   ```cpp
   // Attributes
   ```

   바로 아래에 다음 메서드 선언을 추가합니다.

   ```cpp
   public:
       CMFCShellTreeCtrl& GetShellTreeCtrl();
   ```

   그런 다음 **솔루션 탐색기에서**MainFrm.cpp 소스 파일을 두 번 클릭하여 엽니다. 해당 파일의 맨 아래에 다음 메서드 정의를 추가합니다.

   ```cpp
   CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()
   {
        return m_wndTree;
   }
   ```

1. 이제 windows `CMFCShellControlsView` 메시지를 처리하도록 `WM_CREATE` 클래스를 업데이트합니다. 클래스 **보기** 창을 열고 `CMFCShellControlsView` 클래스를 선택합니다. 마우스 오른쪽 단추를 클릭하고 **속성**을 선택합니다.

   그런 다음 [클래스 마법사에서](reference/mfc-class-wizard.md) **메시지** 탭을 클릭합니다. `WM_CREATE` 다음 의 드롭다운 목록에서 `WM_CREATE` ** \<onCreate에> 추가를**선택합니다. 명령은 우리를 위해 메시지 처리기를 만들고 자동으로 MFC 메시지 맵을 업데이트합니다.

   메서드에서 `OnCreate` 이제 개체를 `CMFCShellListCtrl` 만듭니다. MFCShellControlsView.cpp 소스 파일에서 `OnCreate` 메서드 정의를 찾아 구현을 다음 코드로 바꿉니다.

    ```cpp
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)
    {
        if (CView::OnCreate(lpCreateStruct) == -1)
            return -1;

        CRect rectDummy (0, 0, 0, 0);

        m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT,
            rectDummy, this, 1);

        return 0;
    }
    ```

1. 이전 단계를 반복하지만 `WM_SIZE` 메시지에 대해 반복합니다. 사용자가 응용 프로그램 창의 크기를 변경할 때마다 응용 프로그램 보기가 다시 그려집니다. 메서드의 정의를 `OnSize` 다음 코드로 바꿉니다.

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

1. 마지막 단계는 `CMFCShellTreeCtrl` [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) 메서드를 사용하여 및 `CMFCShellListCtrl` 개체를 연결하는 것입니다. 호출한 `CMFCShellTreeCtrl::SetRelatedList`후 `CMFCShellListCtrl` `CMFCShellTreeCtrl`에서 선택한 항목의 내용을 자동으로 표시합니다. `OnActivateView` [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview)에서 재정의되는 메서드의 개체를 연결합니다.

   클래스 선언 내에서 MFCShellControlsView.h `CMFCShellControlsView` 헤더 파일에서 다음 메서드 선언을 추가합니다.

    ```cpp
    protected:
    virtual void OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView);
    ```

   다음으로 메서드에 대한 정의를 MFCShellControlsView.cpp 소스 파일에 추가합니다.

    ```cpp
    void CMFCShellControlsView::OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView)
    {
        if (bActivate&& AfxGetMainWnd() != NULL)
        {
            ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);
        }

        CView::OnActivateView(bActivate,
            pActivateView,
            pDeactiveView);
    }
    ```

   클래스에서 메서드를 `CMainFrame` 호출하기 때문에 MFCShellControlsView.cpp 소스 파일 의 맨 위에 `#include` 지시문을 추가해야 합니다.

    ```cpp
    #include "MainFrm.h"
    ```

1. 응용 프로그램을 빌드하고 실행하여 응용 프로그램을 성공적으로 만들었는지 확인합니다. 응용 프로그램을 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드를**선택합니다. 응용 프로그램이 성공적으로 빌드되면 **디버그** 메뉴에서 **디버깅 시작을** 선택하여 실행합니다.

   이제 뷰 창에서 `CMFCShellTreeCtrl` 선택한 항목에 대한 세부 정보가 표시됩니다. 에서 `CMFCShellTreeCtrl`노드를 클릭하면 자동으로 `CMFCShellListCtrl` 업데이트됩니다. 마찬가지로 `CMFCShellListCtrl`에서 폴더를 두 번 클릭하면 `CMFCShellTreeCtrl` 자동으로 업데이트됩니다.

   트리 컨트롤 또는 목록 컨트롤의 항목을 마우스 오른쪽 단추로 클릭합니다. 실제 **파일 탐색기를**사용하는 것과 동일한 컨텍스트 메뉴가 표시됩니다.

## <a name="next-steps"></a>다음 단계

- 마법사는 폴더 창과 **일정** 창이 모두 있는 Outlook **막대를** 만들었습니다. **탐색기** 창에 **캘린더** 창을 두는 것은 의미가 없으므로 지금 해당 창을 제거합니다.

- 큰 `CMFCShellListCtrl` **아이콘,** **작은 아이콘,** **목록**및 **세부 정보와**같은 다른 모드에서 파일 보기를 지원합니다. 이 기능을 구현하려면 응용 프로그램을 업데이트합니다. 힌트: [시각적 C++ 샘플을](../overview/visual-cpp-samples.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[연습](../mfc/walkthroughs-mfc.md)
