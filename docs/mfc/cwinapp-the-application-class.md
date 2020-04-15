---
title: 'CWinApp: 애플리케이션 클래스'
ms.date: 11/04/2016
helpviewer_keywords:
- application class [MFC]
- CWinApp class [MFC], CWinThread
- MFC, WinMain and
- CWinApp class [MFC], multithreading
- CWinThread class [MFC], and CWinApp
- InitApplication method [MFC]
- WinMain method [MFC]
- WinMain method [MFC], in MFC
- CWinApp class [MFC], WinMain
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
ms.openlocfilehash: 007a4e53fd9b3eae612947cd76ee352776572d4f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373533"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: 애플리케이션 클래스

MFC의 기본 응용 프로그램 클래스는 Windows 운영 체제용 응용 프로그램의 초기화, 실행 및 종료를 캡슐화합니다. 프레임워크에 빌드된 응용 프로그램에는 [CWinApp에서](../mfc/reference/cwinapp-class.md)파생된 클래스의 개체가 하나만 있어야 합니다. 이 개체는 창을 작성하기 전에 생성됩니다.

`CWinApp`에서 `CWinThread`파생됩니다. 최근 버전의 MFC에서 `InitInstance`에서 는 `ExitInstance`" `OnIdle` **실행**및 멤버 `CWinThread`함수가 실제로 클래스에 있습니다. 이러한 함수는 여기서 멤버인 것처럼 `CWinApp` 설명하며, 토론에서는 기본 스레드가 아닌 응용 프로그램 개체로서의 역할과 관련이 있습니다.

> [!NOTE]
> 응용 프로그램 클래스는 응용 프로그램의 기본 실행 스레드를 구성합니다. Win32 API 함수를 사용하여 보조 실행 스레드를 만들 수도 있습니다. 이러한 스레드는 MFC 라이브러리를 사용할 수 있습니다. 자세한 내용은 [다중 스레딩](../parallel/multithreading-support-for-older-code-visual-cpp.md)을 참조하십시오.

Windows 운영 체제의 모든 프로그램과 마찬가지로 프레임워크 `WinMain` 응용 프로그램에는 함수가 있습니다. 그러나 프레임워크 응용 프로그램에서는 을 `WinMain`작성하지 않습니다. 클래스 라이브러리에서 제공되며 응용 프로그램이 시작될 때 호출됩니다. `WinMain`창 클래스 등록과 같은 표준 서비스를 수행합니다. 그런 다음 응용 프로그램 개체의 멤버 함수를 호출하여 응용 프로그램을 초기화하고 실행합니다. `WinMain` (호출하는 `WinMain` 멤버 함수를 `CWinApp` 재정의하여 사용자 지정할 수 있습니다.)

응용 프로그램을 초기화하려면 응용 프로그램 `InitApplication` 개체 `InitInstance` 및 멤버 함수를 `WinMain` 호출합니다. 응용 프로그램의 메시지 루프를 `WinMain` 실행하려면 **Run** 멤버 함수를 호출합니다. 종료 시 `WinMain` 응용 프로그램 개체의 `ExitInstance` 멤버 함수를 호출합니다.

> [!NOTE]
> 이 설명서에 **굵게 표시된** 이름은 Microsoft 재단 클래스 라이브러리 및 Visual C++에서 제공하는 요소를 나타냅니다. `monospaced` 유형에 표시된 이름은 만들거나 재정의하는 요소를 나타냅니다.

## <a name="see-also"></a>참고 항목

[일반 MFC 항목](../mfc/general-mfc-topics.md)<br/>
[CWinApp 및 MFC 애플리케이션 마법사](../mfc/cwinapp-and-the-mfc-application-wizard.md)<br/>
[재정의 가능한 CWinApp 멤버 기능](../mfc/overridable-cwinapp-member-functions.md)<br/>
[특수 CWinApp 서비스](../mfc/special-cwinapp-services.md)
