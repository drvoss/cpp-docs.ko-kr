---
title: 'TN028: 상황에 맞는 도움말 지원'
ms.date: 11/04/2016
f1_keywords:
- vc.help
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
ms.openlocfilehash: 502edc837d7886dd60ab5107fb194c1490a76928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370324"
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: 상황에 맞는 도움말 지원

이 노트에서는 도움말 컨텍스트 아이디 및 MFC의 기타 도움말 문제를 할당하는 규칙을 설명합니다. 상황에 맞는 도움말 지원에는 Visual C++에서 사용할 수 있는 도움말 컴파일러가 필요합니다.

> [!NOTE]
> MFC는 WinHelp를 사용하여 상황에 맞는 도움말을 구현하는 것 외에도 HTML 도움말을 사용하는 것도 지원합니다. HTML 도움말을 사용하여 이 지원 및 프로그래밍에 대한 자세한 내용은 [HTML 도움말: 프로그램에 대한 컨텍스트 구분 도움말을](../mfc/html-help-context-sensitive-help-for-your-programs.md)참조하십시오.

## <a name="types-of-help-supported"></a>지원되는 도움말 유형

Windows 응용 프로그램에서 구현된 컨텍스트 구분 도움말에는 두 가지 유형이 있습니다. "F1 도움말"이라고 하는 첫 번째 도움말은 현재 활성 개체를 기반으로 적절한 컨텍스트를 사용하여 WinHelp를 시작하는 것입니다. 두 번째는 "시프트 + F1"모드입니다. 이 모드에서는 마우스 커서가 도움말 커서로 변경되고 사용자가 개체를 클릭합니다. 이 시점에서 WinHelp는 사용자가 클릭한 개체에 대한 도움말을 제공하기 위해 시작됩니다.

Microsoft 재단 클래스는 이러한 형태의 도움말을 모두 구현합니다. 또한 프레임워크는 도움말 인덱스 및 도움말 사용의 두 가지 간단한 도움말 명령을 지원합니다.

## <a name="help-files"></a>도움말 파일

Microsoft Foundation 클래스는 단일 도움말 파일을 가정합니다. 해당 도움말 파일은 응용 프로그램과 동일한 이름과 경로를 가져야 합니다. 예를 들어 실행 파일이 C:\MyApplication\MyHelp.exe인 경우 도움말 파일은 C:\MyApplication\MyHelp.hlp여야 합니다. [CWinApp 클래스의](../mfc/reference/cwinapp-class.md) *m_pszHelpFilePath* 멤버 변수를 통해 경로를 설정합니다.

## <a name="help-context-ranges"></a>도움말 컨텍스트 범위

MFC의 기본 구현을 위해서는 도움말 컨텍스트 아이디 할당에 대한 몇 가지 규칙을 따르는 프로그램이 필요합니다. 이러한 규칙은 특정 컨트롤에 할당된 다양한 아이디입니다. 다양한 도움말 관련 멤버 함수의 다양한 구현을 제공하여 이러한 규칙을 재정의할 수 있습니다.

```
0x00000000 - 0x0000FFFF : user defined
0x00010000 - 0x0001FFFF : commands (menus/command buttons)
0x00010000 + ID_
(note: 0x18000-> 0x1FFFF is the practical range since command IDs are>=0x8000)
0x00020000 - 0x0002FFFF : windows and dialogs
0x00020000 + IDR_
(note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)
0x00030000 - 0x0003FFFF : error messages (based on error string ID)
0x00030000 + IDP_
0x00040000 - 0x0004FFFF : special purpose (non-client areas)
0x00040000 + HitTest area
0x00050000 - 0x0005FFFF : controls (those that are not commands)
0x00040000 + IDW_
```

## <a name="simple-help-commands"></a>간단한 "도움말" 명령

Microsoft 재단 클래스에서 구현하는 두 가지 간단한 도움말 명령이 있습니다.

- ID_HELP_INDEX 의해 구현되는 [::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)

- CWinApp에 의해 구현되는 [ID_HELP_USING::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)

첫 번째 명령에는 응용 프로그램에 대한 도움말 인덱스가 표시됩니다. 두 번째는 WinHelp 프로그램 사용에 대한 사용자 도움말을 보여 줍니다.

## <a name="context-sensitive-help-f1-help"></a>상황에 맞는 도움말(F1 도움말)

F1 키는 일반적으로 주 창의 가속기 테이블에 배치 된 가속기에 의해 ID_HELP ID가있는 명령으로 변환됩니다. ID_HELP 명령은 기본 창 또는 대화 상자에 id가 있는 ID_HELP 단추로 생성할 수도 있습니다.

ID_HELP 명령이 생성되는 방법에 관계없이 명령 처리기에 도달할 때까지 일반 명령으로 라우팅됩니다. MFC 명령 라우팅 아키텍처에 대한 자세한 내용은 [기술 참고 21을](../mfc/tn021-command-and-message-routing.md)참조하십시오. 응용 프로그램에 도움말이 활성화되어 있으면 ID_HELP 명령은 [CWinApp::OnHelp](../mfc/reference/cwinapp-class.md#onhelp)에 의해 처리됩니다. 응용 프로그램 개체는 도움말 메시지를 받은 다음 명령을 적절 하 게 라우팅 합니다. 이는 기본 명령 라우팅이 가장 구체적인 컨텍스트를 결정하는 데 적합하지 않기 때문에 필요합니다.

`CWinApp::OnHelp`다음 순서로 WinHelp를 시작하려고 시도합니다.

1. 도움말 ID를 `AfxMessageBox` 사용 하 고 활성 통화를 확인 합니다. 메시지 상자가 현재 활성 상태인 경우 해당 메시지 상자에 적합한 컨텍스트를 사용하여 WinHelp가 시작됩니다.

1. WM_COMMANDHELP 메시지를 활성 창으로 보냅니다. WinHelp를 실행 하여 해당 창이 응답하지 않으면 메시지가 처리되거나 현재 창이 최상위 창이 될 때까지 동일한 메시지가 해당 창의 상위 로 전송됩니다.

1. ID_DEFAULT_HELP 명령을 기본 창으로 보냅니다. 이렇게 하면 기본 도움말이 호출됩니다. 이 명령은 일반적으로 에 `CWinApp::OnHelpIndex`매핑됩니다.

기본 ID 기본 값(예: 명령의 경우 0x10000, 대화 상자와 같은 리소스의 경우 0x20000)을 전역적으로 재정의하려면 응용 프로그램이 [CWinApp::WinHelp](../mfc/reference/cwinapp-class.md#winhelp)를 재정의해야 합니다.

이 기능과 도움말 컨텍스트가 결정되는 방식을 재정의하려면 WM_COMMANDHELP 메시지를 처리해야 합니다. 현재 MDI 자식 창만큼 이나 마찬가지이기 때문에 프레임워크가 제공하는 것보다 더 구체적인 도움말 라우팅을 제공할 수 있습니다. 또한 해당 개체의 현재 내부 상태 또는 대화 상자 내의 활성 컨트롤을 기반으로 특정 창이나 대화 상자에 대해 보다 구체적인 도움말을 제공할 수도 있습니다.

## <a name="wm_commandhelp"></a>WM_COMMANDHELP

```

afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)
```

WM_COMMANDHELP 도움말이 요청될 때 활성 창에서 수신되는 개인 Windows MFC 메시지입니다. 창이 이 메시지를 수신하면 `CWinApp::WinHelp` 창의 내부 상태와 일치하는 컨텍스트를 호출할 수 있습니다.

*lParam*<br/>
현재 사용 가능한 도움말 컨텍스트를 포함합니다. 도움말 컨텍스트가 결정되지 않은 경우 *lParam은* 0입니다. 구현은 `OnCommandHelp` *lParam의* 컨텍스트 ID를 사용하여 다른 컨텍스트를 결정하거나 `CWinApp::WinHelp`에 전달할 수 있습니다.

*wParam*<br/>
사용되지 않으며 0이 됩니다.

함수가 `OnCommandHelp` 호출하는 `CWinApp::WinHelp`경우 **TRUE를**반환해야 합니다. **TRUE를** 반환하면 이 명령의 라우팅이 다른 클래스와 다른 창으로 중지됩니다.

## <a name="help-mode-shiftf1-help"></a>도움말 모드(시프트+F1 도움말)

컨텍스트에 민감한 도움말의 두 번째 형식입니다. 일반적으로 이 모드는 SHIFT+F1을 누르거나 메뉴/도구 모음을 통해 입력됩니다. 명령(ID_CONTEXT_HELP)으로 구현됩니다. 메시지 필터 후크는 모달 대화 상자 또는 메뉴가 활성화되어 있는 동안이 명령을 변환하는 데 사용되지 않으므로 응용 프로그램이 주 메시지`CWinApp::Run`펌프 ()를 실행하는 경우에만이 명령을 사용할 수 있습니다.

이 모드를 입력하면 응용 프로그램이 일반적으로 해당 영역에 대한 자체 커서(예: 창 주위의 크기 조정 테두리)를 표시하는 경우에도 도움말 마우스 커서가 응용 프로그램의 모든 영역에 표시됩니다. 사용자는 마우스 나 키보드를 사용하여 명령을 선택할 수 있습니다. 명령을 실행하는 대신 해당 명령에 대한 도움말이 표시됩니다. 또한 사용자는 도구 모음의 단추와 같이 화면에 표시되는 개체를 클릭할 수 있으며 해당 개체에 대한 도움말이 표시됩니다. 이 도움말 모드는 `CWinApp::OnContextHelp`에서 제공합니다.

이 루프를 실행하는 동안 메뉴에 액세스하는 키를 제외한 모든 키보드 입력이 비활성 상태입니다. 또한 사용자가 가속기 키를 누르고 해당 명령에 대한 도움말을 받을 수 있도록 명령 변환이 계속 수행됩니다. `PreTranslateMessage`

SHIFT+F1 도움말 모드에서 수행해서는 `PreTranslateMessage` 안 되는 특정 번역 또는 작업이 있는 경우 해당 작업을 수행하기 `CWinApp` 전에 *m_bHelpMode* 멤버를 확인해야 합니다. `CDialog` 예를 들어 `PreTranslateMessage` 를 호출하기 `IsDialogMessage`전에 이를 검사합니다. SHIFT+F1 모드에서 모더리스 대화 상자에서 "대화 상자 탐색" 키가 비활성화됩니다. 또한 이 `CWinApp::OnIdle` 루프 중에는 여전히 호출됩니다.

사용자가 메뉴에서 명령을 선택하면 해당 명령의 도움말로 처리됩니다(WM_COMMANDHELP 통해 아래 참조). 사용자가 응용 프로그램 창의 가시 영역을 클릭하면 비클라이언트 클릭인지 클라이언트 클릭인지 여부를 결정합니다. `OnContextHelp`자동으로 클라이언트 클릭에 비 클라이언트 클릭의 매핑을 처리합니다. 클라이언트 클릭인 경우 클릭한 창에 WM_HELPHITTEST 보냅니다. 해당 창에서 zero가 아닌 값을 반환하는 경우 해당 값은 도움말의 컨텍스트로 사용됩니다. 0을 `OnContextHelp` 반환하는 경우 부모 창(및 실패, 부모 등)을 시도합니다. 도움말 컨텍스트를 확인할 수 없는 경우 기본값은 ID_DEFAULT_HELP 명령을 기본 창으로 보내는 것이며, `CWinApp::OnHelpIndex`이 명령은 에 매핑됩니다.

## <a name="wm_helphittest"></a>WM_HELPHITTEST

```

afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)
```

WM_HELPHITTEST SHIFT+F1 도움말 모드에서 클릭한 활성 창에서 수신되는 MFC 개인 창 메시지입니다. 창에서 이 메시지를 받으면 WinHelp에서 사용할 **DWORD** 도움말 ID를 반환합니다.

LOWORD(lParam)에는 창의 클라이언트 영역을 기준으로 마우스를 클릭한 X축 장치 좌표가 포함되어 있습니다.

HIWORD(lParam)에는 Y축 좌표가 포함되어 있습니다.

*wParam*<br/>
사용되지 않으며 0이 됩니다. 반환 값이 0이 아닌 경우 WinHelp는 해당 컨텍스트에서 호출됩니다. 반환 값이 0이면 부모 창이 도움말을 쿼리합니다.

대부분의 경우 이미 가지고 있을 수 있는 적중 테스트 코드를 활용할 수 있습니다. WM_HELPHITTEST 메시지 `CToolBar::OnHelpHitTest` 처리의 예는 (코드는 버튼 및 도구 설명에 사용되는 적중 테스트 `CControlBar`코드를 활용)의 구현을 참조하십시오.

## <a name="mfc-application-wizard-support-and-makehm"></a>MFC 응용 프로그램 마법사 지원 및 MAKEHM

MFC 응용 프로그램 마법사는 도움말 파일(.cnt 및 .hpj 파일)을 빌드하는 데 필요한 파일을 만듭니다. 또한 Microsoft 도움말 컴파일러에서 허용하는 미리 빌드된 .rtf 파일도 다수 포함되어 있습니다. 대부분의 항목이 완료되었지만 특정 응용 프로그램에 맞게 일부 항목을 수정해야 할 수도 있습니다.

MAKEHM이라는 유틸리티에서 "도움말 매핑" 파일을 자동으로 생성합니다. MAKEHM 유틸리티는 응용 프로그램의 리소스를 번역할 수 있습니다. 도움말 매핑 파일에 대한 H 파일입니다. 다음은 그 예입니다.

```
#define IDD_MY_DIALOG   2000
#define ID_MY_COMMAND   150
```

다음으로 변환됩니다.

```
HIDD_MY_DIALOG    0x207d0
HID_MY_COMMAND    0x10096
```

이 형식은 주제 이름(왼쪽에 있는 기호)과 컨텍스트 ID(오른쪽의 숫자)를 매핑하는 도움말 컴파일러 기능과 호환됩니다.

MAKEHM에 대한 소스 코드는 MFC 프로그래밍 유틸리티 샘플 [MAKEHM에서](../overview/visual-cpp-samples.md)사용할 수 있습니다.

## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>MFC 응용 프로그램 마법사를 실행한 후 도움말 지원 추가

응용 프로그램에 도움말을 추가하는 가장 좋은 방법은 응용 프로그램을 만들기 전에 MFC 응용 프로그램 마법사의 고급 기능 페이지에서 "상황에 맞는 도움말" 옵션을 확인하는 것입니다. 이렇게 하면 MFC 응용 프로그램 마법사가 도움말을 `CWinApp`지원하기 위해 -derived 클래스에 필요한 메시지 맵 항목을 자동으로 추가합니다.

## <a name="help-on-message-boxes"></a>메시지 상자에 대한 도움말

메시지 상자에 대한 도움말(경고라고도 함)은 `AfxMessageBox` `MessageBox` Windows API의 래퍼인 함수를 통해 지원됩니다.

문자열 ID와 함께 `AfxMessageBox`사용할 두 가지 버전이 있으며 다른 버전은 문자열에`LPCSTR`대한 포인터와 함께 사용됩니다 ( ) .

```
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```

두 경우 모두 선택적 도움말 ID가 있습니다.

첫 번째 경우 nIDHelp의 기본값은 0이며 이 메시지 상자에 대한 도움말없음을 나타냅니다. 메시지 상자가 활성화되어 있는 동안 사용자가 F1을 누르면 응용 프로그램에서 도움말을 지원하는 경우에도 도움말이 수신되지 않습니다. 바람직하지 않은 경우 nIDHelp에 대한 도움말 ID를 제공해야 합니다.

두 번째 경우 nIDHelp의 기본값은 -1이며, 이는 도움말 ID가 nID Prompt와 동일하다는 것을 나타냅니다. 물론 응용 프로그램이 도움말을 사용하도록 설정된 경우에만 도움말이 작동합니다. 메시지 상자에 도움말 지원이 없는 경우 nIDHelp에 대해 0을 제공해야 합니다. 메시지를 도움말을 사용하도록 설정하지만 nIDPrompt와 다른 도움말 ID를 원할 경우 nIDPrompt와 다른 nIDHelp에 대해 긍정적인 값을 제공하기만 하면 됩니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
