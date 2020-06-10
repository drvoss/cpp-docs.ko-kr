---
title: 특수 CWinApp 서비스
ms.date: 11/04/2016
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
helpviewer_keywords:
- files [MFC], most recently used
- DragAcceptFiles method [MFC]
- MRU lists
- GDI+, initializing for MFC
- GDI+, suppressing background thread [MFC]
- CWinApp class [MFC], shell registration
- application objects [MFC], services
- CWinApp class [MFC], initializing GDI+
- MFC, shell registration
- CWinApp class [MFC], File Manager drag and drop
- LoadStdProfileSettings method [MFC]
- MFC, most-recently-used file list
- RegisterShellFileTypes method [MFC]
- drag and drop [MFC], files
- registering file types
- Shell, registering file types
- services, provided by CWinApp
- CWinApp class [MFC], recently used documents
- CWinApp class [MFC], services
- files [MFC], drag and drop
- EnableShellOpen method [MFC]
- registry [MFC], most recently used files
- MFC, file operations
- registration [MFC], shell
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
ms.openlocfilehash: 1f5abcdab3eda1304879b122acc8072951a0e6c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363911"
---
# <a name="special-cwinapp-services"></a>특수 CWinApp 서비스

메시지 루프를 실행하고 응용 프로그램을 초기화하고 그 후 정리 할 수있는 기회를 제공하는 것 외에도 [CWinApp은](../mfc/reference/cwinapp-class.md) 몇 가지 다른 서비스를 제공합니다.

## <a name="shell-registration"></a><a name="_core_shell_registration"></a>셸 등록

기본적으로 MFC 애플리케이션 마법사를 사용하면 파일 탐색기 또는 파일 관리자에서 두 번 클릭하여 애플리케이션에서 생성된 데이터 파일을 열 수 있습니다. 응용 프로그램이 MDI 응용 프로그램이고 응용 프로그램이 만드는 파일에 대한 확장자를 지정하는 경우 MFC 응용 프로그램 마법사는 [RegisterShellFileType및](../mfc/reference/cwinapp-class.md#registershellfiletypes) `InitInstance` [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen) 멤버 함수에 대한 호출을 [CWinApp의](../mfc/reference/cwinapp-class.md) 멤버 함수에 추가하여 작성합니다.

`RegisterShellFileTypes`는 사용자의 애플리케이션 문서 형식을 파일 탐색기 또는 파일 관리자에 등록합니다. 이 함수는 Windows에서 유지 관리되는 등록 데이터베이스에 항목을 추가합니다. 항목은 각 문서 유형을 등록하고, 파일 확장자를 해당 파일 형식과 연결하고, 애플리케이션을 열기 위한 명령줄을 지정하고, 해당 형식의 문서를 열기 위해 DDE(동적 데이터 교환) 명령을 지정합니다.

`EnableShellOpen`은 파일 탐색기 또는 파일 관리자에서 DDE 명령을 수신하도록 허용하여 프로세스를 완료하고 사용자가 선택한 파일을 엽니다.

`CWinApp`의 이러한 자동 등록 지원 덕분에 애플리케이션에 .reg 파일을 포함하거나 특별한 설치 작업을 수행할 필요가 없습니다.

응용 프로그램에 대한 GDI+를 [초기화하려면(InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 함수에서 [GdiplusStartup을](/windows/win32/api/gdiplusinit/nf-gdiplusinit-gdiplusstartup) 호출하여) GDI+ 백그라운드 스레드를 억제해야 합니다.

`SuppressBackgroundThread` [GdiplusStartupInput](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput) 구조의 멤버를 **TRUE로**설정하여 이 작업을 수행할 수 있습니다. GDI+ 백그라운드 스레드를 억제할 때 응용 프로그램의 메시지 루프를 입력하고 종료하기 직전에 `NotificationHook` 및 `NotificationUnhook` 호출해야 합니다. 이러한 호출에 대한 자세한 내용은 [GdiplusStartupOutput](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput)을 참조하십시오. 따라서 호출하는 `GdiplusStartup` 좋은 장소와 후크 알림 함수는 아래와 같이 가상 함수 [CWinApp::Run의](../mfc/reference/cwinapp-class.md#run)재정의에 있을 것입니다.

[!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]

백그라운드 GDI+ 스레드를 숨기지 않으면, 해당 기본 창이 생성되기 전에 DDE 명령이 애플리케이션에 너무 빨리 실행될 수 있습니다. 셸에서 실행된 DDE 명령은 중간에 중단되어 오류 메시지가 나타날 수 있습니다.

## <a name="file-manager-drag-and-drop"></a><a name="_core_file_manager_drag_and_drop"></a>파일 관리자 드래그 앤 드롭

파일은 파일 관리자 또는 파일 탐색기의 파일 보기 창에서 애플리케이션의 창으로 끌어 놓을 수 있습니다. 예를 들어 MDI 애플리케이션의 기본 창에 하나 이상의 파일을 끌어 놓을 수 있도록 설정해야 할 수 있습니다. 여기에서 애플리케이션은 해당 파일에 대한 파일 이름을 검색하고 MDI 자식 창을 열 수 있습니다.

응용 프로그램에서 파일 드래그 앤 드롭을 활성화하려면 MFC 응용 프로그램 마법사에서 의 주 프레임 창에 `InitInstance`대해 [CWnd](../mfc/reference/cwnd-class.md) 멤버 함수 [DragAcceptFiles에](../mfc/reference/cwnd-class.md#dragacceptfiles) 대한 호출을 작성합니다. 끌어서 놓기 기능을 구현할 필요가 없으면 이 호출을 제거할 수 있습니다.

> [!NOTE]
> 또한 OLE를 사용하면 문서 간 또는 문서 내에서의 데이터 끌기와 같은 보다 일반적인 끌어서 놓기 기능을 구현할 수도 있습니다. 자세한 내용은 OLE [끌어놓기](../mfc/drag-and-drop-ole.md)문서를 참조하십시오.

## <a name="keeping-track-of-the-most-recently-used-documents"></a><a name="_core_keeping_track_of_the_most_recently_used_documents"></a> 가장 최근에 사용한 문서 추적

사용자가 파일을 열고 닫을 때 애플리케이션 개체는 최근에 사용된 4개 파일에 대한 추적을 유지합니다. 이러한 파일의 이름은 파일 메뉴에 추가되며 변경될 경우 업데이트됩니다. 프레임워크는 레지스트리 또는 .ini 파일에서 프로젝트와 동일한 이름을 사용해서 이러한 파일 이름을 저장하고, 애플리케이션이 시작될 때 파일에서 이를 읽어옵니다. MFC 응용 프로그램 마법사가 만드는 재정의에는 `InitInstance` 가장 최근에 사용한 파일 이름을 포함하여 레지스트리 또는 .ini 파일에서 정보를 로드하는 [CWinApp](../mfc/reference/cwinapp-class.md) 멤버 함수 [LoadStdProfileSettings에](../mfc/reference/cwinapp-class.md#loadstdprofilesettings)대한 호출이 포함됩니다.

이러한 항목은 다음과 같이 저장됩니다.

- Windows NT, Windows 2000 이상에서 값은 레지스트리 키에 저장됩니다.

- Windows 3.x에서 값은 WIN.INI 파일에 저장됩니다.

- Windows 95 이상에서 값은 WIN.INI 의 캐시된 버전에 저장됩니다.

## <a name="see-also"></a>참고 항목

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)
