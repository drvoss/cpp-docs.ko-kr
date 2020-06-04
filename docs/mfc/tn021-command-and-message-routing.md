---
title: 'TN021: 명령 및 메시지 라우팅'
ms.date: 06/28/2018
f1_keywords:
- vc.routing
helpviewer_keywords:
- TN021
- command routing [MFC], technical note TN021
- Windows messages [MFC], routing
ms.assetid: b5952c8b-123e-406c-a36d-a6ac7c6df307
ms.openlocfilehash: bdd405bda5c0af9e04a50eee4ef5738f3a53259e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370404"
---
# <a name="tn021-command-and-message-routing"></a>TN021: 명령 및 메시지 라우팅

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 참고에서는 명령 라우팅 및 디스패치 아키텍처와 일반 창 메시지 라우팅의 고급 항목에 대해 설명합니다.

여기에 설명된 아키텍처, 특히 Windows 메시지, 제어 알림 및 명령 간의 차이점에 대한 일반적인 자세한 내용은 Visual C++를 참조하십시오. 이 참고 는 인쇄된 문서에 설명된 문제에 대해 매우 잘 알고 있으며 매우 고급 항목만 해결한다고 가정합니다.

## <a name="command-routing-and-dispatch-mfc-10-functionality-evolves-to-mfc-20-architecture"></a>명령 라우팅 및 디스패치 MFC 1.0 기능은 MFC 2.0 아키텍처로 발전합니다.

Windows에는 메뉴 명령, 가속기 키 및 대화 상자 제어 알림에 대한 알림을 제공하기 위해 오버로드된 WM_COMMAND 메시지가 있습니다.

MFC 1.0은 `CWnd` 파생 클래스에서 명령 처리기(예: "OnFileNew")가 특정 WM_COMMAND 대한 응답으로 호출되도록 허용하여 약간 빌드되었습니다. 이는 메시지 맵이라는 데이터 구조와 함께 붙어 있으며 공간 효율적인 명령 메커니즘을 만듭니다.

MFC 1.0은 제어 알림을 명령 메시지에서 분리하는 추가 기능도 제공했습니다. 명령은 16비트 ID로 표시되며 명령 ID라고도 합니다. 명령은 일반적으로 `CFrameWnd` (즉, 메뉴 선택 또는 번역 된 가속기)에서 시작하여 다양한 다른 창으로 라우팅됩니다.

MFC 1.0은 MDI(다중 문서 인터페이스)의 구현을 위해 제한된 의미로 명령 라우팅을 사용했습니다. (MDI 프레임 창은 활성 MDI 자식 창에 명령을 위임합니다.)

이 기능은 MFC 2.0에서 일반화되고 확장되어 창 개체뿐만 아니라 더 넓은 범위의 개체에서 명령을 처리할 수 있습니다. 메시지를 라우팅하기 위한 보다 공식적이고 확장 가능한 아키텍처를 제공하고 명령 의 현재 가용성을 반영하기 위해 UI 개체(예: 메뉴 항목 및 도구 모음 단추)를 업데이트하기 위해 명령 대상 라우팅을 다시 사용합니다.

## <a name="command-ids"></a>명령 ID

명령 라우팅 및 바인딩 프로세스에 대한 설명은 Visual C++를 참조하십시오. [기술 참고 20](../mfc/tn020-id-naming-and-numbering-conventions.md) ID 이름에 대 한 정보가 포함 되어 있습니다.

명령 ID에 대 한 일반 접두사 "ID_"를 사용 합니다. 명령 ID는 >= 0x8000입니다. 명령 ID와 동일한 ID를 가진 STRINGTABLE 리소스가 있는 경우 메시지 줄 또는 상태 표시줄에 명령 설명 문자열이 표시됩니다.

응용 프로그램의 리소스에서 명령 ID는 여러 위치에 나타날 수 있습니다.

- 메시지 줄 프롬프트와 동일한 ID를 가지는 하나의 STRINGTABLE 리소스에서

- 아마도 동일한 명령을 호출 하는 메뉴 항목에 연결 된 많은 MENU 리소스에서.

- (고급) GOSUB 명령에 대한 대화 상자 단추에 있습니다.

응용 프로그램의 소스 코드에서 명령 ID는 여러 위치에 나타날 수 있습니다.

- 리소스에서. H(또는 다른 주요 기호 헤더 파일)를 사용하여 응용 프로그램별 명령 암호를 정의합니다.

- 도구 모음을 만드는 데 사용되는 ID 배열에서 일 수 있습니다.

- ON_COMMAND 매크로에서.

- 아마도 ON_UPDATE_COMMAND_UI 매크로에서.

현재 명령 ID가 필요한 MFC의 유일한 구현은 >= 0x8000은 GOSUB 대화 상자/명령의 구현입니다.

## <a name="gosub-commands-using-command-architecture-in-dialogs"></a>대화 상자에서 명령 아키텍처를 사용하는 GOSUB 명령

라우팅 및 사용 명령의 명령 아키텍처는 프레임 창, 메뉴 항목, 도구 모음 단추, 대화 상자 단추, 기타 컨트롤 막대 및 기타 사용자 인터페이스 요소에서 작동하여 필요에 따라 업데이트하고 명령을 라우팅하거나 주 명령 대상(일반적으로 주 프레임 창)으로 코드를 제어하도록 설계되었습니다. 해당 주 명령 대상은 명령 또는 제어 알림을 적절히 다른 명령 대상 개체로 라우팅할 수 있습니다.

대화 상자 의 컨트롤 ID를 적절한 명령 ID에 할당하는 경우 대화 상자(모달 또는 모데리스)는 명령 아키텍처의 일부 기능의 이점을 활용할 수 있습니다. 대화 상자에 대한 지원은 자동이 아니므로 몇 가지 추가 코드를 작성해야 할 수 있습니다.

이러한 모든 기능이 제대로 작동하려면 명령 ID가 >= 0x8000이어야 합니다. 많은 대화 상자가 동일한 프레임으로 라우팅될 수 있기 때문에 공유 명령은 >= 0x8000이어야 하며 특정 대화 상자의 비공유 IDC는 <= 0x7FFF여야 합니다.

단추의 IDC가 적절한 명령 ID로 설정된 일반 모달 대화 상자에 일반 단추를 배치할 수 있습니다. 사용자가 단추를 선택하면 대화 상자의 소유자(일반적으로 주 프레임 창)가 다른 명령과 마찬가지로 명령을 가져옵니다. 일반적으로 다른 대화 상자(첫 번째 대화 상자의 GOSUB)를 가져오는 데 사용되므로 GOSUB 명령이라고 합니다.

대화 상자에서 함수를 `CWnd::UpdateDialogControls` 호출하고 주 프레임 창의 주소를 전달할 수도 있습니다. 이 함수는 프레임에 명령 처리기가 있는지 여부에 따라 대화 상자 컨트롤을 활성화하거나 사용하지 않도록 설정합니다. 이 함수는 응용 프로그램의 유휴 루프에서 컨트롤 막대에 대해 자동으로 호출되지만 이 기능을 사용하려는 일반 대화 상자에 대해 직접 호출해야 합니다.

## <a name="when-on_update_command_ui-is-called"></a>ON_UPDATE_COMMAND_UI 호출될 때

모든 프로그램의 메뉴 항목의 활성화/확인 된 상태를 항상 유지 하는 것은 계산 비용이 많이 드는 문제가 될 수 있습니다. 일반적인 방법은 사용자가 POPUP를 선택할 때만 메뉴 항목을 활성화/확인하는 것입니다. MFC 2.0 구현은 WM_INITMENUPOPUP 메시지를 `CFrameWnd` 처리하고 명령 라우팅 아키텍처를 사용하여 ON_UPDATE_COMMAND_UI 처리기를 통해 메뉴의 상태를 결정합니다.

`CFrameWnd`또한 상태 표시줄에서 선택한 현재 메뉴 항목(메시지 줄이라고도 함)을 설명하기 위해 WM_ENTERIDLE 메시지를 처리합니다.

Visual C++에서 편집한 응용 프로그램의 메뉴 구조는 WM_INITMENUPOPUP 시간에 사용할 수 있는 잠재적명령을 나타내는 데 사용됩니다. ON_UPDATE_COMMAND_UI 처리기는 메뉴의 상태 또는 텍스트를 수정하거나 고급 용도(예: File MRU 목록 또는 OLE 동사 팝업 메뉴)를 위해 메뉴를 그릴 전에 메뉴 구조를 실제로 수정할 수 있습니다.

응용 프로그램이 유휴 루프에 들어갈 때 도구 모음(및 기타 컨트롤 모음)에 대해 동일한 종류의 ON_UPDATE_COMMAND_UI 처리가 수행됩니다. 컨트롤 막대에 대한 자세한 내용은 *클래스 라이브러리 참조* 및 기술 참고 [31을](../mfc/tn031-control-bars.md) 참조하십시오.

## <a name="nested-pop-up-menus"></a>중첩 팝업 메뉴

중첩된 메뉴 구조를 사용하는 경우 팝업 메뉴의 첫 번째 메뉴 항목에 대한 ON_UPDATE_COMMAND_UI 처리기가 두 가지 경우 호출됩니다.

첫째, 팝업 메뉴 자체에 대 한 호출 됩니다. 팝업 메뉴에는 ID가 없으며 팝업 메뉴의 첫 번째 메뉴 항목의 ID를 사용하여 전체 팝업 메뉴를 참조하기 때문에 이 문제가 필요합니다. 이 경우 `CCmdUI` 개체의 *m_pSubMenu* 멤버 변수는 NULL이 아닌 변수가 되며 팝업 메뉴를 가리킵니다.

둘째, 팝업 메뉴의 메뉴 항목을 그릴 바로 전에 호출됩니다. 이 경우 ID는 첫 번째 메뉴 항목만 *m_pSubMenu* 을 참조하며 `CCmdUI` 개체의 m_pSubMenu 멤버 변수는 NULL이 됩니다.

이렇게 하면 메뉴 항목과 구별되는 팝업 메뉴를 활성화할 수 있지만 일부 메뉴 인식 코드를 작성해야 합니다. 예를 들어 다음 구조의 중첩 된 메뉴에서 :

```Output
File>
    New>
    Sheet (ID_NEW_SHEET)
    Chart (ID_NEW_CHART)
```

ID_NEW_SHEET 및 ID_NEW_CHART 명령을 독립적으로 사용하거나 사용하지 않도록 설정할 수 있습니다. 둘 중 하나를 사용하도록 설정한 경우 **새** 팝업 메뉴를 사용하도록 설정해야 합니다.

ID_NEW_SHEET 대한 명령 처리기(팝업의 첫 번째 명령)는 다음과 같습니다.

```cpp
void CMyApp::OnUpdateNewSheet(CCmdUI* pCmdUI)
{
    if (pCmdUI->m_pSubMenu != NULL)
    {
        // enable entire pop-up for "New" sheet and chart
        BOOL bEnable = m_bCanCreateSheet || m_bCanCreateChart;
        // CCmdUI::Enable is a no-op for this case, so we
        // must do what it would have done.
        pCmdUI->m_pMenu->EnableMenuItem(pCmdUI->m_nIndex,
            MF_BYPOSITION |
            (bEnable  MF_ENABLED : (MF_DISABLED | MF_GRAYED)));

        return;
    }
    // otherwise just the New Sheet command
    pCmdUI->Enable(m_bCanCreateSheet);
}
```

ID_NEW_CHART 대한 명령 처리기는 일반 업데이트 명령 처리기가 될 것이며 다음과 같습니다.

```cpp
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)
{
    pCmdUI->Enable(m_bCanCreateChart);
}
```

## <a name="on_command-and-on_bn_clicked"></a>ON_COMMAND 및 ON_BN_CLICKED

**ON_COMMAND** 및 **ON_BN_CLICKED** 대한 메시지 맵 매크로는 동일합니다. MFC 명령 및 제어 알림 라우팅 메커니즘은 명령 ID만 사용하여 라우팅할 위치를 결정합니다. 제어 알림 0 **(BN_CLICKED)의**제어 알림은 명령으로 해석됩니다.

> [!NOTE]
> 실제로 모든 제어 알림 메시지는 명령 처리기 체인을 통과합니다. 예를 들어 기술적으로 문서 클래스의 **EN_CHANGE** 대한 컨트롤 알림 처리기를 작성할 수 있습니다. 이 기능의 실제 응용 프로그램이 거의 없고 ClassWizard에서 이 기능을 지원하지 않으며 이 기능을 사용하면 코드가 취약할 수 있으므로 일반적으로 권장되지 않습니다.

## <a name="disabling-the-automatic-disabling-of-button-controls"></a>단추 컨트롤의 자동 비활성화 를 사용 하지 않도록 설정 합니다.

대화 상자 막대에 단추 컨트롤을 배치하거나 **CWnd::UpdateDialogControls를** 직접 호출하는 위치를 사용하는 대화 상자에서 **ON_COMMAND** 또는 **ON_UPDATE_COMMAND_UI** 처리기가 없는 단추는 프레임워크에서 자동으로 비활성화됩니다. 경우에 따라 처리기가 필요하지 않지만 단추를 활성화된 상태로 유지하려고 합니다. 이를 달성하는 가장 쉬운 방법은 더미 명령 처리기 (ClassWizard로 쉽게 수행)를 추가하고 아무 것도하지 않는 것입니다.

## <a name="window-message-routing"></a>창 메시지 라우팅

다음은 MFC 클래스에 대한 몇 가지 고급 항목과 Windows 메시지 라우팅 및 기타 항목이 이러한 항목에 미치는 영향에 대해 설명합니다. 여기에 있는 정보는 간략하게 설명되어 있습니다. 공용 API에 대한 자세한 내용은 *클래스 라이브러리 참조를* 참조하십시오. 구현 세부 정보에 대한 자세한 내용은 MFC 라이브러리 소스 코드를 참조하십시오.

모든 **CWnd-파생**클래스에서 매우 중요한 항목인 창 정리에 대한 자세한 내용은 [기술 참고 17을](../mfc/tn017-destroying-window-objects.md) 참조하십시오.

## <a name="cwnd-issues"></a>CWnd 문제

구현 멤버 함수 **CWnd:OnChildNotify는** 부모(또는 "소유자")로 이동하는 메시지, 명령 및 제어 알림을 후크하거나 알림을 받을 수 있는 자식 창(컨트롤이라고도 함)에 대한 강력하고 확장 가능한 아키텍처를 제공합니다. 자식 창(/control)이 C++ **CWnd** 개체 자체인 경우 **가상 기능 OnChildNotify가** 원래 메시지(즉, **MSG** 구조)의 매개 변수를 먼저 호출합니다. 자식 창은 메시지를 그대로 두거나, 메시지를 먹거나, 부모에 대한 메시지를 수정할 수 있습니다(드문 경우).

기본 **CWnd** 구현은 다음 메시지를 처리하고 **OnChildNotify** 후크를 사용하여 자식 창(컨트롤)이 메시지에서 처음 액세스할 수 있도록 합니다.

- **WM_MEASUREITEM** 및 **WM_DRAWITEM(셀프** 드로우용)

- **WM_COMPAREITEM** 및 **WM_DELETEITEM(셀프** 드로우용)

- **WM_HSCROLL** **및 WM_VSCROLL**

- **WM_CTLCOLOR**

- **WM_PARENTNOTIFY**

**OnChildNotify** 후크는 소유자-그리기 메시지를 자체 그리기 메시지로 변경하는 데 사용됩니다.

**OnChildNotify** 후크 외에도 스크롤 메시지에는 추가 라우팅 동작이 있습니다. 스크롤 막대 및 **WM_HSCROLL** 및 **WM_VSCROLL** 메시지의 소스에 대한 자세한 내용은 아래를 참조하십시오.

## <a name="cframewnd-issues"></a>CFrameWnd 문제

**CFrameWnd** 클래스는 대부분의 명령 라우팅 및 사용자 인터페이스 업데이트 구현을 제공합니다. 이 응용 프로그램의 기본 프레임 창에 주로 사용 됩니다 **(CWinApp::m_pMainWnd)** 하지만 모든 프레임 창에 적용 됩니다.

주 프레임 창은 메뉴 표시줄이 있는 창이며 상태 표시줄 또는 메시지 줄의 상위 창입니다. 명령 라우팅 및 WM_INITMENUPOPUP 대한 위의 토론을 **참조하십시오.**

**CFrameWnd** 클래스는 활성 보기의 관리를 제공합니다. 다음 메시지는 활성 보기를 통해 라우팅됩니다.

- 모든 명령 메시지(활성 보기가 먼저 액세스하게 됩니다).

- **형제** 스크롤 막대의 WM_HSCROLL 및 **WM_VSCROLL** 메시지(아래 참조).

- **WM_ACTIVATE(및** MDI의 **경우 WM_MDIACTIVATE)는** 가상 함수 **CView::OnActivateView에**대한 호출로 전환됩니다.

## <a name="cmdiframewndcmdichildwnd-issues"></a>CMDIFrameWnd/CMDIChildWnd 문제

두 MDI 프레임 창 클래스는 **CFrameWnd에서** 파생되므로 **CFrameWnd에서**제공되는 동일한 종류의 명령 라우팅 및 사용자 인터페이스 업데이트에 대해 모두 사용할 수 있습니다. 일반적인 MDI 응용 프로그램에서는 기본 프레임 창(즉 **CMDIFrameWnd** 개체)만 메뉴 막대와 상태 표시줄을 보유하므로 명령 라우팅 구현의 주요 소스입니다.

일반적인 라우팅 체계는 활성 MDI 자식 창이 명령에 먼저 액세스한다는 것입니다. 기본 **PreTranslateMessage** 함수는 일반적으로 **TranslateMDISysAccel(마지막)에서** 처리하는 표준 MDI 시스템 명령 가속기뿐만 아니라 MDI 자식 창(첫 번째)과 MDI 프레임(두 번째)에 대한 가속기 테이블을 처리합니다.

## <a name="scroll-bar-issues"></a>스크롤 막대 문제

/스크롤 메시지(WM_HSCROLL**WM_HSCROLL**/**OnHScroll** 및/또는 **WM_VSCROLL****OnVScroll)을**처리할 때는 스크롤 막대 메시지가 어디에서 왔는지에 의존하지 않도록 처리기 코드를 작성해야 합니다. 스크롤 메시지는 실제 스크롤 막대 컨트롤또는 스크롤 막대 컨트롤이 아닌 **WS_HSCROLL**/**WS_VSCROLL** 스크롤 막대에서 올 수 있기 때문에 일반적인 Windows 문제만이 아닙니다.

MFC는 스크롤 막대 컨트롤을 스크롤중인 창의 자식 또는 형제가 될 수 있도록 확장합니다(실제로 스크롤 막대와 스크롤되는 창 간의 부모/자식 관계는 무엇이든 될 수 있음). 이는 스플리터 창이 있는 공유 스크롤 막대에 특히 중요합니다. 공유 스크롤 막대 문제에 대한 자세한 내용을 포함하여 **CSplitterWnd의** 구현에 대한 자세한 내용은 [기술 참고 29를](../mfc/tn029-splitter-windows.md) 참조하십시오.

참고로 작성 시 지정된 스크롤 막대 스타일이 트랩되고 Windows로 전달되지 않는 두 개의 **CWnd** 파생 클래스가 있습니다. 생성 루틴으로 전달되면 **WS_HSCROLL** 및 **WS_VSCROLL** 독립적으로 설정할 수 있지만 생성 후에는 변경할 수 없습니다. 물론 창에서 만든 WS_SCROLL 스타일 비트를 직접 테스트하거나 설정해서는 안 됩니다.

**CMDIFrameWnd의** 경우 **만들기** 또는 **로드프레임에** 전달하는 스크롤 막대 스타일은 MDICLIENT를 만드는 데 사용됩니다. 스크롤 가능한 MDICLIENT 영역(예: Windows 프로그램 관리자)을 사용하려면 **CMDIFrameWnd**를 만드는 데 사용되는 스타일에 대해 스크롤 막대**스타일(WS_HSCROLL** &#124; **WS_VSCROLL)을**모두 설정해야 합니다.

**CSplitterWnd의** 경우 스크롤 막대 스타일은 스플리터 영역에 대한 특수 공유 스크롤 막대에 적용됩니다. 정적 스플리터 창의 경우 일반적으로 스크롤 막대 스타일을 설정하지 않습니다. 동적 스플리터 창의 경우 일반적으로 분할 할 방향에 대해 스크롤 막대 스타일이 설정됩니다 **WS_VSCROLL** **WS_HSCROLL.**

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
