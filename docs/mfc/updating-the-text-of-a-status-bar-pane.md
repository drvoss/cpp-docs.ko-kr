---
title: 상태 표시줄 창의 텍스트 업데이트
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- ON_UPDATE_COMMAND_UI macro [MFC]
- user interface objects [MFC], updating
- text, status bar
- CStatusBar class [MFC], updating
- SetText method [MFC]
- panes, status bar
- status bars [MFC], updating
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
ms.openlocfilehash: 723046fc1721cc46608e00f19a4431ef081be13d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366683"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>상태 표시줄 창의 텍스트 업데이트

이 문서에서는 MFC 상태 표시줄 창에 나타나는 텍스트를 변경하는 방법을 설명합니다. [CStatusBar](../mfc/reference/cstatusbar-class.md) 클래스의 창 개체인 상태 표시줄에는 여러 "창"이 포함되어 있습니다. 각 창은 정보를 표시하는 데 사용할 수 있는 상태 표시줄의 직사각형 영역입니다. 예를 들어 대부분의 응용 프로그램은 가장 오른쪽 창에 CAPS LOCK, NUM LOCK 및 기타 키의 상태를 표시합니다. 응용 프로그램은 종종 "메시지 창"이라고도 하는 가장 왼쪽 창(창 0)에 유익한 텍스트를 표시합니다. 예를 들어 기본 MFC 상태 표시줄은 메시지 창을 사용하여 현재 선택한 메뉴 항목 또는 도구 모음 단추를 설명하는 문자열을 표시합니다. [상태 표시줄의](../mfc/status-bar-implementation-in-mfc.md) 그림은 응용 프로그램 마법사가 만든 MFC 응용 프로그램의 상태 표시줄을 보여 주며 있습니다.

기본적으로 MFC는 `CStatusBar` 창을 만들 때 창을 사용하지 않습니다. 창을 활성화하려면 상태 표시줄에서 각 창에 대해 ON_UPDATE_COMMAND_UI 매크로를 사용하고 창을 업데이트해야 합니다. 창은 WM_COMMAND 메시지를 보내지 않으므로(도구 모음 단추와 는 안 됨) 코드를 수동으로 입력해야 합니다.

예를 들어 한 창에 `ID_INDICATOR_PAGE` 명령 식별자가 있고 문서에 현재 페이지 번호가 포함되어 있다고 가정합니다. 다음 절차에서는 상태 표시줄에 새 창을 만드는 방법을 설명합니다.

### <a name="to-make-a-new-pane"></a>새 창을 만들려면

1. 창의 명령 ID를 정의합니다.

   **보기** 메뉴에서 **리소스 보기를 클릭합니다.** 프로젝트 리소스를 마우스 오른쪽 단추로 클릭하고 **리소스 기호를 클릭합니다.** 리소스 기호 대화 상자에서 을 `New`클릭합니다. 명령 ID 이름을 입력합니다. `ID_INDICATOR_PAGE` ID값을 지정하거나 리소스 심볼 대화 상자에서 제안한 값을 수락합니다. 예를 들어 `ID_INDICATOR_PAGE`, 에 대해 기본값을 수락합니다. 리소스 기호 대화 상자를 닫습니다.

1. 창에 표시할 기본 문자열을 정의합니다.

   리소스 보기가 열려 있는 경우 응용 프로그램에 대한 리소스 유형을 나열하는 **창에서 문자열 테이블을** 두 번 클릭합니다. 문자열 **테이블** 편집기가 열려 있는 경우 **삽입** 메뉴에서 **새 문자열을** 선택합니다. 창의 명령 `ID_INDICATOR_PAGE`ID(예:)를 선택하고 "페이지"와 같은 기본 문자열 값을 입력합니다. 문자열 편집기닫습니다. 컴파일러 오류를 방지하려면 기본 문자열이 필요합니다.

1. *창을 표시기* 배열에 추가합니다.

   파일 MAINFRM에서. CPP를 사용하여 *표시기 배열을 찾습니다.* 이 배열은 왼쪽에서 오른쪽으로 상태 표시줄의 모든 표시기에 대한 명령 아이디를 나열합니다. 배열의 적절한 지점에서 다음과 같이 창의 명령 ID를 `ID_INDICATOR_PAGE`입력합니다.

   [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]

창에 텍스트를 표시하는 권장 되는 방법은 창에 대 `SetText` `CCmdUI` 한 업데이트 처리기 함수에서 클래스의 멤버 함수를 호출 하는 것입니다. 예를 들어 현재 페이지 번호를 포함하는 정수 변수 *m_nPage* 설정하고 창의 `SetText` 텍스트를 해당 숫자의 문자열 버전으로 설정하는 데 사용할 수 있습니다.

> [!NOTE]
> 이 `SetText` 방법을 권장합니다. `CStatusBar` 멤버 함수를 `SetPaneText`호출하여 약간 낮은 수준에서 이 작업을 수행할 수 있습니다. 그럼에도 불구하고 여전히 업데이트 처리기가 필요합니다. 창에 대한 이러한 처리기가 없으면 MFC는 창을 자동으로 비활성화하여 콘텐츠를 지워보습니다.

다음 절차에서는 업데이트 처리기 함수를 사용하여 창에 텍스트를 표시하는 방법을 보여 주었습니다.

#### <a name="to-make-a-pane-display-text"></a>창 표시 텍스트를 만들려면

1. 명령에 대한 명령 업데이트 처리기를 추가합니다.

   (MAINFRM에서)에 대해 여기에 표시된 `ID_INDICATOR_PAGE` 대로 처리기에 대한 프로토타입을 수동으로 추가합니다. H:

   [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]

1. 적절한 . CPP 파일은 다음과 같이 처리기의 정의를 `ID_INDICATOR_PAGE` 추가합니다(MAINFRM). CPP:

   [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]

   이 처리기의 마지막 세 줄은 텍스트를 표시하는 코드입니다.

1. 적절한 메시지 맵에서 다음과 같이 ON_UPDATE_COMMAND_UI 매크로를 `ID_INDICATOR_PAGE` 추가합니다(MAINFRM). CPP:

   [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]

*m_nPage* 멤버 변수(클래스)의 `CMainFrame`값을 정의하면 이 기술을 사용하면 응용 프로그램이 다른 표시기를 업데이트하는 것과 동일한 방식으로 유휴 처리 중에 페이지 번호가 창에 나타납니다. *m_nPage* 변경되면 다음 유휴 루프 중에 디스플레이가 변경됩니다.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [사용자 인터페이스 개체 업데이트(프로그램 조건이 변경될 때 도구 모음 단추 및 메뉴 항목을 업데이트하는 방법)](../mfc/how-to-update-user-interface-objects.md)

## <a name="see-also"></a>참고 항목

[MFC의 상태 표시줄 구현](../mfc/status-bar-implementation-in-mfc.md)<br/>
[CStatusBar 클래스](../mfc/reference/cstatusbar-class.md)
