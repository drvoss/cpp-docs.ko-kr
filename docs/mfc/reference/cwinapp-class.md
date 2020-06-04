---
title: CWinApp 클래스
ms.date: 07/15/2019
f1_keywords:
- CWinApp
- AFXWIN/CWinApp
- AFXWIN/CWinApp::CWinApp
- AFXWIN/CWinApp::AddDocTemplate
- AFXWIN/CWinApp::AddToRecentFileList
- AFXWIN/CWinApp::ApplicationRecoveryCallback
- AFXWIN/CWinApp::CloseAllDocuments
- AFXWIN/CWinApp::CreatePrinterDC
- AFXWIN/CWinApp::DelRegTree
- AFXWIN/CWinApp::DoMessageBox
- AFXWIN/CWinApp::DoWaitCursor
- AFXWIN/CWinApp::EnableD2DSupport
- AFXWIN/CWinApp::EnableHtmlHelp
- AFXWIN/CWinApp::EnableTaskbarInteraction
- AFXWIN/CWinApp::ExitInstance
- AFXWIN/CWinApp::GetApplicationRecoveryParameter
- AFXWIN/CWinApp::GetApplicationRecoveryPingInterval
- AFXWIN/CWinApp::GetApplicationRestartFlags
- AFXWIN/CWinApp::GetAppRegistryKey
- AFXWIN/CWinApp::GetDataRecoveryHandler
- AFXWIN/CWinApp::GetFirstDocTemplatePosition
- AFXWIN/CWinApp::GetHelpMode
- AFXWIN/CWinApp::GetNextDocTemplate
- AFXWIN/CWinApp::GetPrinterDeviceDefaults
- AFXWIN/CWinApp::GetProfileBinary
- AFXWIN/CWinApp::GetProfileInt
- AFXWIN/CWinApp::GetProfileString
- AFXWIN/CWinApp::GetSectionKey
- AFXWIN/CWinApp::HideApplication
- AFXWIN/CWinApp::HtmlHelp
- AFXWIN/CWinApp::InitInstance
- AFXWIN/CWinApp::IsTaskbarInteractionEnabled
- AFXWIN/CWinApp::LoadCursor
- AFXWIN/CWinApp::LoadIcon
- AFXWIN/CWinApp::LoadOEMCursor
- AFXWIN/CWinApp::LoadOEMIcon
- AFXWIN/CWinApp::LoadStandardCursor
- AFXWIN/CWinApp::LoadStandardIcon
- AFXWIN/CWinApp::OnDDECommand
- AFXWIN/CWinApp::OnIdle
- AFXWIN/CWinApp::OpenDocumentFile
- AFXWIN/CWinApp::ParseCommandLine
- AFXWIN/CWinApp::PreTranslateMessage
- AFXWIN/CWinApp::ProcessMessageFilter
- AFXWIN/CWinApp::ProcessShellCommand
- AFXWIN/CWinApp::ProcessWndProcException
- AFXWIN/CWinApp::Register
- AFXWIN/CWinApp::RegisterWithRestartManager
- AFXWIN/CWinApp::ReopenPreviousFilesAtRestart
- AFXWIN/CWinApp::RestartInstance
- AFXWIN/CWinApp::RestoreAutosavedFilesAtRestart
- AFXWIN/CWinApp::Run
- AFXWIN/CWinApp::RunAutomated
- AFXWIN/CWinApp::RunEmbedded
- AFXWIN/CWinApp::SaveAllModified
- AFXWIN/CWinApp::SelectPrinter
- AFXWIN/CWinApp::SetHelpMode
- AFXWIN/CWinApp::SupportsApplicationRecovery
- AFXWIN/CWinApp::SupportsAutosaveAtInterval
- AFXWIN/CWinApp::SupportsAutosaveAtRestart
- AFXWIN/CWinApp::SupportsRestartManager
- AFXWIN/CWinApp::Unregister
- AFXWIN/CWinApp::WinHelp
- AFXWIN/CWinApp::WriteProfileBinary
- AFXWIN/CWinApp::WriteProfileInt
- AFXWIN/CWinApp::WriteProfileString
- AFXWIN/CWinApp::EnableShellOpen
- AFXWIN/CWinApp::LoadStdProfileSettings
- AFXWIN/CWinApp::OnContextHelp
- AFXWIN/CWinApp::OnFileNew
- AFXWIN/CWinApp::OnFileOpen
- AFXWIN/CWinApp::OnFilePrintSetup
- AFXWIN/CWinApp::OnHelp
- AFXWIN/CWinApp::OnHelpFinder
- AFXWIN/CWinApp::OnHelpIndex
- AFXWIN/CWinApp::OnHelpUsing
- AFXWIN/CWinApp::RegisterShellFileTypes
- AFXWIN/CWinApp::SetAppID
- AFXWIN/CWinApp::SetRegistryKey
- AFXWIN/CWinApp::UnregisterShellFileTypes
- AFXWIN/CWinApp::m_bHelpMode
- AFXWIN/CWinApp::m_eHelpType
- AFXWIN/CWinApp::m_hInstance
- AFXWIN/CWinApp::m_lpCmdLine
- AFXWIN/CWinApp::m_nCmdShow
- AFXWIN/CWinApp::m_pActiveWnd
- AFXWIN/CWinApp::m_pszAppID
- AFXWIN/CWinApp::m_pszAppName
- AFXWIN/CWinApp::m_pszExeName
- AFXWIN/CWinApp::m_pszHelpFilePath
- AFXWIN/CWinApp::m_pszProfileName
- AFXWIN/CWinApp::m_pszRegistryKey
- AFXWIN/CWinApp::m_dwRestartManagerSupportFlags
- AFXWIN/CWinApp::m_nAutosaveInterval
- AFXWIN/CWinApp::m_pDataRecoveryHandler
helpviewer_keywords:
- CWinApp [MFC], CWinApp
- CWinApp [MFC], AddDocTemplate
- CWinApp [MFC], AddToRecentFileList
- CWinApp [MFC], ApplicationRecoveryCallback
- CWinApp [MFC], CloseAllDocuments
- CWinApp [MFC], CreatePrinterDC
- CWinApp [MFC], DelRegTree
- CWinApp [MFC], DoMessageBox
- CWinApp [MFC], DoWaitCursor
- CWinApp [MFC], EnableD2DSupport
- CWinApp [MFC], EnableHtmlHelp
- CWinApp [MFC], EnableTaskbarInteraction
- CWinApp [MFC], ExitInstance
- CWinApp [MFC], GetApplicationRecoveryParameter
- CWinApp [MFC], GetApplicationRecoveryPingInterval
- CWinApp [MFC], GetApplicationRestartFlags
- CWinApp [MFC], GetAppRegistryKey
- CWinApp [MFC], GetDataRecoveryHandler
- CWinApp [MFC], GetFirstDocTemplatePosition
- CWinApp [MFC], GetHelpMode
- CWinApp [MFC], GetNextDocTemplate
- CWinApp [MFC], GetPrinterDeviceDefaults
- CWinApp [MFC], GetProfileBinary
- CWinApp [MFC], GetProfileInt
- CWinApp [MFC], GetProfileString
- CWinApp [MFC], GetSectionKey
- CWinApp [MFC], HideApplication
- CWinApp [MFC], HtmlHelp
- CWinApp [MFC], InitInstance
- CWinApp [MFC], IsTaskbarInteractionEnabled
- CWinApp [MFC], LoadCursor
- CWinApp [MFC], LoadIcon
- CWinApp [MFC], LoadOEMCursor
- CWinApp [MFC], LoadOEMIcon
- CWinApp [MFC], LoadStandardCursor
- CWinApp [MFC], LoadStandardIcon
- CWinApp [MFC], OnDDECommand
- CWinApp [MFC], OnIdle
- CWinApp [MFC], OpenDocumentFile
- CWinApp [MFC], ParseCommandLine
- CWinApp [MFC], PreTranslateMessage
- CWinApp [MFC], ProcessMessageFilter
- CWinApp [MFC], ProcessShellCommand
- CWinApp [MFC], ProcessWndProcException
- CWinApp [MFC], Register
- CWinApp [MFC], RegisterWithRestartManager
- CWinApp [MFC], ReopenPreviousFilesAtRestart
- CWinApp [MFC], RestartInstance
- CWinApp [MFC], RestoreAutosavedFilesAtRestart
- CWinApp [MFC], Run
- CWinApp [MFC], RunAutomated
- CWinApp [MFC], RunEmbedded
- CWinApp [MFC], SaveAllModified
- CWinApp [MFC], SelectPrinter
- CWinApp [MFC], SetHelpMode
- CWinApp [MFC], SupportsApplicationRecovery
- CWinApp [MFC], SupportsAutosaveAtInterval
- CWinApp [MFC], SupportsAutosaveAtRestart
- CWinApp [MFC], SupportsRestartManager
- CWinApp [MFC], Unregister
- CWinApp [MFC], WinHelp
- CWinApp [MFC], WriteProfileBinary
- CWinApp [MFC], WriteProfileInt
- CWinApp [MFC], WriteProfileString
- CWinApp [MFC], EnableShellOpen
- CWinApp [MFC], LoadStdProfileSettings
- CWinApp [MFC], OnContextHelp
- CWinApp [MFC], OnFileNew
- CWinApp [MFC], OnFileOpen
- CWinApp [MFC], OnFilePrintSetup
- CWinApp [MFC], OnHelp
- CWinApp [MFC], OnHelpFinder
- CWinApp [MFC], OnHelpIndex
- CWinApp [MFC], OnHelpUsing
- CWinApp [MFC], RegisterShellFileTypes
- CWinApp [MFC], SetAppID
- CWinApp [MFC], SetRegistryKey
- CWinApp [MFC], UnregisterShellFileTypes
- CWinApp [MFC], m_bHelpMode
- CWinApp [MFC], m_eHelpType
- CWinApp [MFC], m_hInstance
- CWinApp [MFC], m_lpCmdLine
- CWinApp [MFC], m_nCmdShow
- CWinApp [MFC], m_pActiveWnd
- CWinApp [MFC], m_pszAppID
- CWinApp [MFC], m_pszAppName
- CWinApp [MFC], m_pszExeName
- CWinApp [MFC], m_pszHelpFilePath
- CWinApp [MFC], m_pszProfileName
- CWinApp [MFC], m_pszRegistryKey
- CWinApp [MFC], m_dwRestartManagerSupportFlags
- CWinApp [MFC], m_nAutosaveInterval
- CWinApp [MFC], m_pDataRecoveryHandler
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
ms.openlocfilehash: 4bb1ade4182424cbdcbf0d7ba69af88bbb88abe6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750678"
---
# <a name="cwinapp-class"></a>CWinApp 클래스

Windows 애플리케이션 개체를 파생하는 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CWinApp : public CWinThread
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CWinApp ::CWinApp](#cwinapp)|`CWinApp` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CWinApp::AddDocTemplate](#adddoctemplate)|응용 프로그램의 사용 가능한 문서 템플릿 목록에 문서 템플릿을 추가합니다.|
|[CWinApp::추가최신파일리스트](#addtorecentfilelist)|가장 최근에 사용한(MRU) 파일 목록에 파일 이름을 추가합니다.|
|[CWinApp:::응용 프로그램 복구콜백](#applicationrecoverycallback)|응용 프로그램이 예기치 않게 종료될 때 프레임워크에서 호출됩니다.|
|[CWinApp::닫기모든 문서](#closealldocuments)|열려 있는 모든 문서를 닫습니다.|
|[CWinApp::만들기 프린터DC](#createprinterdc)|프린터 장치 컨텍스트를 만듭니다.|
|[CWinApp::D엘레그트리](#delregtree)|지정된 키와 모든 하위 키를 삭제합니다.|
|[CWinApp::D오 메시지 상자](#domessagebox)|응용 프로그램에 대한 [AfxMessageBox를](cstring-formatting-and-message-box-display.md#afxmessagebox) 구현합니다.|
|[CWinApp::DoWaitCursor](#dowaitcursor)|대기 커서를 켜고 끕니다.|
|[CWinApp::인에이블D2D지원](#enabled2dsupport)|응용 프로그램 D2D 지원을 활성화합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.|
|[CWinApp::사용HTML도움말](#enablehtmlhelp)|WinHelp 가 아니라 응용 프로그램에 대한 HTML도움말을 구현합니다.|
|[CWinApp:::인에이블태스크바상호작용](#enabletaskbarinteraction)|작업 표시줄 상호 작용을 활성화합니다.|
|[CWinApp::Exit인스턴스](#exitinstance)|응용 프로그램이 종료될 때 정리를 위해 재정의합니다.|
|[CWinApp::GetApplicationRecovery매개 변수](#getapplicationrecoveryparameter)|응용 프로그램 복구 메서드에 대 한 입력 매개 변수를 검색합니다.|
|[CWinApp::GetApplication복구간격](#getapplicationrecoverypinginterval)|다시 시작 관리자가 복구 콜백 함수가 반환될 때까지 기다리는 시간을 반환합니다.|
|[CWinApp::GetApplication다시 시작 플래그](#getapplicationrestartflags)|다시 시작 관리자에 대한 플래그를 반환합니다.|
|[CWinApp::GetApp레지스트리키](#getappregistrykey)|"소프트웨어"\레지스트리Key\ProfileName에 HKEY_CURRENT_USER\\키를 반환합니다.|
|[CWinApp::GetDataRecovery처리기](#getdatarecoveryhandler)|응용 프로그램의 이 인스턴스에 대한 데이터 복구 처리기를 가져옵니다.|
|[CWinApp::GetFirstDoc템플릿 포지션](#getfirstdoctemplateposition)|첫 번째 문서 템플릿의 위치를 검색합니다.|
|[CWinApp:::GetHelpMode](#gethelpmode)|응용 프로그램에서 사용하는 도움말 유형을 검색합니다.|
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|문서 템플릿의 위치를 검색합니다. 재귀적으로 사용할 수 있습니다.|
|[CWinApp::getprinterDevice기본값](#getprinterdevicedefaults)|프린터 장치 기본값을 검색합니다.|
|[CWinApp::GetProfile바이너리](#getprofilebinary)|응용 프로그램의 의 항목에서 이진 데이터를 검색합니다. INI 파일입니다.|
|[CWinApp::GetProfileInt](#getprofileint)|응용 프로그램의 항목에서 정수 를 검색합니다. INI 파일입니다.|
|[CWinApp:::GetProfileString](#getprofilestring)|응용 프로그램의 의 항목에서 문자열을 검색합니다. INI 파일입니다.|
|[CWinApp::getsectionKey](#getsectionkey)|HKEY_CURRENT_USER\\"소프트웨어"\레지스트리키\AppName\lpszSection에 대한 키를 반환합니다.|
|[CWinApp::숨기기 응용 프로그램](#hideapplication)|모든 문서를 닫기 전에 응용 프로그램을 숨깁니다.|
|[CWinApp::Html도움말](#htmlhelp)|Windows `HTMLHelp` 함수를 호출합니다.|
|[CWinApp::Initinstance](#initinstance)|Windows 개체 를 만드는 등 Windows 인스턴스 초기화를 수행 하도록 재정의 합니다.|
|[CWinApp::IsTaskbar상호작용 사용 가능](#istaskbarinteractionenabled)|Windows 7 작업 표시줄 상호 작용이 활성화되어 있는지 여부를 알려줍니다.|
|[CWinApp ::로드 커서](#loadcursor)|커서 리소스를 로드합니다.|
|[CWinApp ::로드 아이콘](#loadicon)|아이콘 리소스를 로드합니다.|
|[CWinApp::로드OEM커서](#loadoemcursor)|OCR_ 상수가 WINDOWS에서 지정하는 **Windows** OEM 미리 정의된 커서를 로드합니다. H.|
|[CWinApp ::로드OEM아이콘](#loadoemicon)|OIC_ 상수가 WINDOWS에서 지정하는 **Windows** OEM 미리 정의된 아이콘을 로드합니다. H.|
|[CWinApp::로드스탠다드커서](#loadstandardcursor)|IDC_ 상수가 WINDOWS에서 지정하는 **Windows** 미리 정의된 커서를 로드합니다. H.|
|[CWinApp :: 로드 스탠다드아이콘](#loadstandardicon)|**IDI_** 상수가 WINDOWS에서 지정하는 Windows 미리 정의된 아이콘을 로드합니다. H.|
|[CWinApp:::OnDDECommand](#onddecommand)|동적 데이터 교환 (DDE) 실행 명령에 대 한 응답으로 프레임 워크에 의해 호출 됩니다.|
|[CWinApp ::: 온들](#onidle)|응용 프로그램별 유휴 시간 처리를 수행하려면 재정의합니다.|
|[CWinApp::오픈 문서파일](#opendocumentfile)|파일에서 문서를 여는 프레임워크에서 호출합니다.|
|[CWinApp::P거칠은 커맨드라인](#parsecommandline)|명령줄에서 개별 매개 변수와 플래그를 구문 분석합니다.|
|[CWinApp::P다시 번역 메시지](#pretranslatemessage)|메시지가 Windows [함수TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage로](/windows/win32/api/winuser/nf-winuser-dispatchmessage)전달되기 전에 메시지를 필터링합니다.|
|[CWinApp::P로케이션메시지필터](#processmessagefilter)|응용 프로그램에 도달하기 전에 특정 메시지를 가로채는 것입니다.|
|[CWinApp::P로키스셸커맨드](#processshellcommand)|명령줄 인수 및 플래그를 처리합니다.|
|[CWinApp::P로스WndProc예외](#processwndprocexception)|응용 프로그램의 메시지 및 명령 처리기에 의해 throw된 처리되지 않은 모든 예외를 차단합니다.|
|[CWinApp::등록](#register)|사용자 지정 등록을 수행합니다.|
|[CWinApp::레지스터위드리스타트매니저](#registerwithrestartmanager)|응용 프로그램을 다시 시작 관리자에 등록합니다.|
|[CWinApp::다시 열기이전파일다시 시작](#reopenpreviousfilesatrestart)|다시 시작 관리자가 응용 프로그램이 예기치 않게 종료될 때 열려 있던 파일을 다시 열지 여부를 결정합니다.|
|[CWinApp::다시 시작 인스턴스](#restartinstance)|다시 시작 관리자에 의해 시작 된 응용 프로그램을 다시 시작 처리 합니다.|
|[CWinApp::복원자동 저장파일다시 시작](#restoreautosavedfilesatrestart)|다시 시작 관리자가 응용 프로그램을 다시 시작할 때 자동 저장된 파일을 복원하는지 여부를 결정합니다.|
|[CWinApp :: 실행](#run)|기본 메시지 루프를 실행합니다. 재정의하여 메시지 루프를 사용자 지정합니다.|
|[CWinApp::실행 자동화](#runautomated)|**/자동화** 옵션에 대한 응용 프로그램의 명령줄을 테스트합니다. 더 이상 사용되지 않습니다. 대신 [ParseCommandLine](#parsecommandline)을 호출한 후 [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) 값을 사용합니다.|
|[CWinApp:::실행 임베디드](#runembedded)|**/포함** 옵션에 대한 응용 프로그램의 명령줄을 테스트합니다. 더 이상 사용되지 않습니다. 대신, [ParseCommandLine을](#parsecommandline)호출 한 후 [CCommandLineInfo:m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) 값을 사용 합니다.|
|[CWinApp:::SaveAll수정](#saveallmodified)|수정된 모든 문서를 저장하라는 메시지를 사용자에게 표시합니다.|
|[CWinApp::선택 프린터](#selectprinter)|인쇄 대화 상자를 통해 사용자가 이전에 표시한 프린터를 선택합니다.|
|[CWinApp:::세트헬프 모드](#sethelpmode)|응용 프로그램에서 사용하는 도움말 유형을 설정하고 초기화합니다.|
|[CWinApp::지원응용 프로그램 복구](#supportsapplicationrecovery)|다시 시작 관리자가 예기치 않게 종료된 응용 프로그램을 복구하는지 여부를 결정합니다.|
|[CWinApp::지원자동 저장간격](#supportsautosaveatinterval)|다시 시작 관리자가 정기적으로 열려 있는 문서를 자동으로 저장하는지 여부를 결정합니다.|
|[CWinApp::지원자동 저장다시 시작](#supportsautosaveatrestart)|다시 시작 관리자가 응용 프로그램을 다시 시작할 때 열려 있는 문서를 자동으로 저장하는지 여부를 결정합니다.|
|[CWinApp::지원 다시 시작 관리자](#supportsrestartmanager)|응용 프로그램이 다시 시작 관리자를 지원하는지 여부를 결정합니다.|
|[CWinApp::등록 취소](#unregister)|개체에 의해 등록된 것으로 알려진 `CWinApp` 모든 등록을 취소합니다.|
|[CWinApp:::윈헬프](#winhelp)|Windows `WinHelp` 함수를 호출합니다.|
|[CWinApp::쓰기 프로필 바이너리](#writeprofilebinary)|응용 프로그램의 항목에 이진 데이터를 씁니다. INI 파일입니다.|
|[CWinApp::쓰기 프로필인트](#writeprofileint)|응용 프로그램의 항목에 정수를 씁니다. INI 파일입니다.|
|[CWinApp::쓰기 프로필 스트링](#writeprofilestring)|응용 프로그램의 항목에 문자열을 씁니다. INI 파일입니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CWinApp::인에이블쉘오픈](#enableshellopen)|사용자가 Windows 파일 관리자에서 데이터 파일을 열 수 있습니다.|
|[CWinApp::로드스트드 프로파일설정](#loadstdprofilesettings)|로드 표준. INI 파일 설정을 활성화하고 MRU 파일 목록 기능을 사용할 수 있습니다.|
|[CWinApp:::에 컨텍스트 도움말](#oncontexthelp)|응용 프로그램 내에서 SHIFT+F1 도움말을 처리합니다.|
|[CWinApp::온파일뉴](#onfilenew)|ID_FILE_NEW 명령을 구현합니다.|
|[CWinApp::온파일 열기](#onfileopen)|ID_FILE_OPEN 명령을 구현합니다.|
|[CWinApp::온파일 프린트셋업](#onfileprintsetup)|ID_FILE_PRINT_SETUP 명령을 구현합니다.|
|[CWinApp:::에 도움](#onhelp)|현재 컨텍스트를 사용하여 애플리케이션 내에서 F1 도움말을 처리합니다.|
|[CWinApp:::에 도움말 파인더](#onhelpfinder)|ID_HELP_FINDER 및 ID_DEFAULT_HELP 명령을 처리합니다.|
|[CWinApp:::온헬드 인덱스](#onhelpindex)|ID_HELP_INDEX 명령을 처리하고 기본 도움말 항목을 제공합니다.|
|[CWinApp::에 도움 사용](#onhelpusing)|ID_HELP_USING 명령을 처리합니다.|
|[CWinApp::레지스터쉘파일타입](#registershellfiletypes)|Windows 파일 관리자를 사용 하 여 모든 응용 프로그램의 문서 형식을 등록 합니다.|
|[CWinApp ::SetAppID](#setappid)|응용 프로그램에 대한 응용 프로그램 사용자 모델 ID를 명시적으로 설정합니다. 이 메서드는 사용자 인터페이스가 사용자에게 표시되기 전에 호출해야 합니다(가장 좋은 장소는 응용 프로그램 생성자).|
|[CWinApp:::세트레지스트리키](#setregistrykey)|응용 프로그램 설정을 대신 레지스트리에 저장합니다. INI 파일.|
|[CWinApp::레지스터 쉘파일 형식](#unregistershellfiletypes)|Windows 파일 관리자를 사용 하 여 모든 응용 프로그램의 문서 형식을 등록 취소 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CWinApp::m_bHelpMode](#m_bhelpmode)|사용자가 도움말 컨텍스트 모드에 있는지 나타냅니다(일반적으로 SHIFT+F1로 호출).|
|[CWinApp::m_eHelpType](#m_ehelptype)|응용 프로그램에서 사용하는 도움말 유형을 지정합니다.|
|[CWinApp::m_hInstance](#m_hinstance)|응용 프로그램의 현재 인스턴스를 식별합니다.|
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|응용 프로그램의 명령줄을 지정하는 null 종료 된 문자열을 가리킵니다.|
|[CWinApp::m_nCmdShow](#m_ncmdshow)|창이 처음에 표시되는 방법을 지정합니다.|
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|OLE 서버가 활성 상태일 때 컨테이너 응용 프로그램의 기본 창에 대한 포인터입니다.|
|[CWinApp::m_pszAppID](#m_pszappid)|응용 프로그램 사용자 모델 ID입니다.|
|[CWinApp::m_pszAppName](#m_pszappname)|애플리케이션의 이름을 지정합니다.|
|[CWinApp::m_pszExeName](#m_pszexename)|응용 프로그램의 모듈 이름입니다.|
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|응용 프로그램의 도움말 파일에 대한 경로입니다.|
|[CWinApp::m_pszProfileName](#m_pszprofilename)|응용 프로그램의 . INI 파일 이름입니다.|
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|응용 프로그램 프로필 설정을 저장하기 위한 전체 레지스트리 키를 결정하는 데 사용됩니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|다시 시작 관리자의 행동 방식을 결정하는 플래그입니다.|
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|자동 저장 사이의 밀리초 길이입니다.|
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|응용 프로그램의 데이터 복구 처리기에 대한 포인터입니다.|

## <a name="remarks"></a>설명

응용 프로그램 개체는 응용 프로그램(및 응용 프로그램의 각 인스턴스)을 초기화하고 응용 프로그램을 실행하기 위한 멤버 함수를 제공합니다.

Microsoft Foundation 클래스를 사용하는 각 응용 프로그램에는 `CWinApp`에서 파생된 개체가 하나만 포함될 수 있습니다. 이 개체는 다른 C++ 전역 개체가 생성될 때 `WinMain` 생성되며 Windows에서 Microsoft Foundation 클래스 라이브러리에서 제공하는 함수를 호출할 때 이미 사용할 수 있습니다. 전역 수준에서 `CWinApp` 파생 개체를 선언합니다.

에서 `CWinApp`응용 프로그램 클래스를 파생 하는 경우 [InitInstance](#initinstance) 멤버 함수를 재정의 하여 응용 프로그램의 기본 창 개체를 만듭니다.

`CWinApp` Microsoft 재단 클래스 라이브러리는 구성원 기능 외에도 `CWinApp` 개체 및 기타 전역 정보에 액세스하는 다음과 같은 전역 함수를 제공합니다.

- [아fxGetApp](application-information-and-management.md#afxgetapp) 개체에 대한 포인터를 `CWinApp` 가져옵니다.

- [AfxGet인스턴스핸들](application-information-and-management.md#afxgetinstancehandle) 현재 응용 프로그램 인스턴스에 대한 핸들을 가져옵니다.

- [AfxGet리소스핸들](application-information-and-management.md#afxgetresourcehandle) 응용 프로그램의 리소스에 대한 핸들을 가져옵니다.

- [AfxGetApp네임](application-information-and-management.md#afxgetappname) 응용 프로그램의 이름이 포함된 문자열에 대한 포인터를 가져옵니다. 또는 개체에 대한 포인터가 `CWinApp` 있는 경우 `m_pszExeName` 응용 프로그램의 이름을 얻는 데 사용합니다.

[CWinApp: 다음의](../../mfc/cwinapp-the-application-class.md) 개요를 포함하여 `CWinApp` 클래스에 대한 자세한 내용은 응용 프로그램 클래스를 참조하십시오.

- `CWinApp`-파생 코드는 응용 프로그램 마법사에 의해 작성되었습니다.

- `CWinApp`응용 프로그램의 실행 순서에서 역할입니다.

- `CWinApp`'의 기본 멤버 함수 구현.

- `CWinApp`'의 키 재정의.

데이터 `m_hPrevInstance` 멤버가 더 이상 존재하지 않습니다. 응용 프로그램의 다른 인스턴스가 실행 되고 있는지 확인 하려면 명명 된 mutex를 사용 합니다. 뮤텍스 열기가 실패하면 실행 중인 응용 프로그램의 다른 인스턴스가 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cwinappadddoctemplate"></a><a name="adddoctemplate"></a>CWinApp::AddDocTemplate

이 멤버 함수를 호출하여 응용 프로그램에서 유지 관리하는 사용 가능한 문서 템플릿 목록에 문서 템플릿을 추가합니다.

```cpp
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>매개 변수

*템플릿*<br/>
추가할 포인터입니다. `CDocTemplate`

### <a name="remarks"></a>설명

[RegisterShellFileType](#registershellfiletypes)을 호출하기 전에 모든 문서 템플릿을 응용 프로그램에 추가해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

## <a name="cwinappaddtorecentfilelist"></a><a name="addtorecentfilelist"></a>CWinApp::추가최신파일리스트

MRU 파일 목록에 *lpszPathName을* 추가하려면 이 멤버 함수를 호출합니다.

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
파일의 경로입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 사용하기 전에 [LoadStdProfileSettings](#loadstdprofilesettings) 멤버 함수를 호출하여 현재 MRU 파일 목록을 로드해야 합니다.

프레임워크는 파일을 열거나 As 저장 명령을 실행하여 새 이름으로 파일을 저장할 때 이 멤버 함수를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

## <a name="cwinappapplicationrecoverycallback"></a><a name="applicationrecoverycallback"></a>CWinApp:::응용 프로그램 복구콜백

응용 프로그램이 예기치 않게 종료될 때 프레임워크에서 호출됩니다.

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>매개 변수

*lpvParam*<br/>
【인】 나중에 사용할 수 있습니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 0입니다. 오류가 발생하면 0이 아닙니다.

### <a name="remarks"></a>설명

응용 프로그램이 다시 시작 관리자를 지원하는 경우 프레임워크는 응용 프로그램이 예기치 않게 종료될 때 이 함수를 호출합니다.

기본 구현은 `ApplicationRecoveryCallback` 을 `CDataRecoveryHandler` 사용하여 현재 열려 있는 문서 목록을 레지스트리에 저장합니다. 이 메서드는 파일을 자동으로 저장하지 않습니다.

동작을 사용자 지정하려면 파생 된 [CWinApp 클래스에서이](../../mfc/reference/cwinapp-class.md) 함수를 재정의하거나 [CWinApp::RegisterWithRestartManager에](#registerwithrestartmanager)매개 변수로 자신의 응용 프로그램 복구 방법을 전달합니다.

## <a name="cwinappclosealldocuments"></a><a name="closealldocuments"></a>CWinApp::닫기모든 문서

종료하기 전에 열려 있는 모든 문서를 닫도록 이 멤버 함수를 호출합니다.

```cpp
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>매개 변수

*bEndSession*<br/>
Windows 세션이 종료되는지 여부를 지정합니다. 세션이 종료되는 경우 true입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

호출하기 전에 `CloseAllDocuments`응용 [프로그램을](#hideapplication) 호출합니다.

## <a name="cwinappcreateprinterdc"></a><a name="createprinterdc"></a>CWinApp::만들기 프린터DC

선택한 프린터에서 프린터 장치 컨텍스트(DC)를 만들려면 이 멤버 함수를 호출합니다.

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>매개 변수

*Dc*<br/>
프린터 장치 컨텍스트에 대한 참조입니다.

### <a name="return-value"></a>Return Value

프린터 장치 컨텍스트가 성공적으로 생성된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

`CreatePrinterDC`을 사용해 인쇄할 수 있도록 참조로 전달하는 장치 컨텍스트를 초기화합니다.

이 기능이 성공하면 인쇄를 완료하면 장치 컨텍스트를 삭제해야 합니다. [CDC](../../mfc/reference/cdc-class.md) 개체의 소멸자가 수행하도록 하거나 [CDC::DeleteDC를](../../mfc/reference/cdc-class.md#deletedc)호출하여 명시적으로 수행할 수 있습니다.

## <a name="cwinappcwinapp"></a><a name="cwinapp"></a>CWinApp ::CWinApp

개체를 `CWinApp` 생성하고 응용 프로그램 이름으로 저장할 *lpszAppName을* 전달합니다.

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszApp이름*<br/>
Windows에서 사용하는 응용 프로그램 이름을 포함하는 null 종료 문자열입니다. 이 인수가 제공되지 않거나 NULL인 경우 리소스 문자열 AFX_IDS_APP_TITLE 또는 실행 파일의 파일 이름을 `CWinApp` 사용합니다.

### <a name="remarks"></a>설명

파생 클래스의 하나의 전역 `CWinApp`개체를 생성해야 합니다. 응용 프로그램에 개체가 하나만 `CWinApp` 있을 수 있습니다. 생성자는 `CWinApp` 개체의 멤버 함수를 `WinMain` 호출하여 응용 프로그램을 초기화하고 실행할 수 있도록 개체에 대한 포인터를 저장합니다.

## <a name="cwinappdelregtree"></a><a name="delregtree"></a>CWinApp::D엘레그트리

특정 레지스트리 키와 모든 하위 키를 삭제합니다.

```
LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName);

LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*h부모키*<br/>
레지스트리 키를 처리합니다.

*스트키 이름*<br/>
삭제할 레지스트리 키의 이름입니다.

*Ptm*<br/>
CAtlTransactionManager 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값이 ERROR_SUCCESS. 함수가 실패하면 반환 값은 Winerror.h에 정의된 제로가 아닌 오류 코드입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 지정된 키와 하위 키를 삭제합니다.

## <a name="cwinappdomessagebox"></a><a name="domessagebox"></a>CWinApp::D오 메시지 상자

프레임워크는 이 멤버 함수를 호출하여 전역 함수 [AfxMessageBox에](cstring-formatting-and-message-box-display.md#afxmessagebox)대한 메시지 상자를 구현합니다.

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>매개 변수

*lpsz프롬프트*<br/>
메시지 상자의 텍스트 주소입니다.

*nType*<br/>
메시지 상자 [스타일](../../mfc/reference/styles-used-by-mfc.md#message-box-styles).

*니드프롬프트*<br/>
도움말 컨텍스트 문자열에 대한 인덱스입니다.

### <a name="return-value"></a>Return Value

`AfxMessageBox`와 동일한 값을 반환합니다.

### <a name="remarks"></a>설명

메시지 상자를 열려면 이 멤버 함수를 호출하지 마십시오. 대신 `AfxMessageBox` 사용합니다.

이 멤버 함수를 재정의하여 응용 프로그램 `AfxMessageBox` 전체의 호출 처리를 사용자 지정합니다.

## <a name="cwinappdowaitcursor"></a><a name="dowaitcursor"></a>CWinApp::DoWaitCursor

이 멤버 함수는 [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)및 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)를 구현하기 위해 프레임워크에서 호출됩니다.

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>매개 변수

*nCode*<br/>
이 매개 변수가 1이면 대기 커서가 나타납니다. 0이면 참조 수를 증가하지 않고 대기 커서가 복원됩니다. -1이면 대기 커서가 종료됩니다.

### <a name="remarks"></a>설명

기본값은 모래 시계 커서를 구현합니다. `DoWaitCursor`참조 수를 유지합니다. 양수면 모래 시계 커서가 표시됩니다.

일반적으로 직접 호출하지는 `DoWaitCursor` 않지만 이 멤버 함수를 재정의하여 대기 커서를 변경하거나 대기 커서가 표시되는 동안 추가 처리를 수행할 수 있습니다.

대기 커서를 구현하는 보다 쉽고 간소화된 방법을 `CWaitCursor`위해 을 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

## <a name="cwinappenabled2dsupport"></a><a name="enabled2dsupport"></a>CWinApp::인에이블D2D지원

Visual Studio 2010 SP1이 필요합니다.

응용 프로그램 D2D 지원을 활성화합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>매개 변수

*d2d팩토리타입*<br/>
D2D 팩터리의 스레딩 모델과 생성되는 리소스입니다.

*쓰기팩토리타입*<br/>
write 팩터리 개체를 공유하거나 격리할지 여부를 지정하는 값입니다.

### <a name="return-value"></a>Return Value

D2D 지원이 활성화된 경우 TRUE를 반환하고 FALSE - 그렇지 않으면

## <a name="cwinappenablehtmlhelp"></a><a name="enablehtmlhelp"></a>CWinApp::사용HTML도움말

`CWinApp`응용 프로그램의 도움을 위해 HTMLHelp를 사용 하려면 -derived 클래스의 생성자 내에서이 멤버 함수를 호출 합니다.

```cpp
void EnableHtmlHelp();
```

### <a name="remarks"></a>설명

## <a name="cwinappenableshellopen"></a><a name="enableshellopen"></a>CWinApp::인에이블쉘오픈

일반적으로 `InitInstance` 재정의에서 이 함수를 호출하여 응용 프로그램의 사용자가 Windows 파일 관리자 내에서 파일을 두 번 클릭할 때 데이터 파일을 열 수 있도록 합니다.

```cpp
void EnableShellOpen();
```

### <a name="remarks"></a>설명

이 `RegisterShellFileTypes` 함수와 함께 멤버 함수를 호출하거나 을 제공합니다. 문서 유형의 수동 등록을 위한 응용 프로그램과 함께 REG 파일.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

## <a name="cwinappenabletaskbarinteraction"></a><a name="enabletaskbarinteraction"></a>CWinApp:::인에이블태스크바상호작용

작업 표시줄 상호 작용을 활성화합니다.

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
Windows 7 작업 표시줄과의 상호 작용을 활성화할지(TRUE) 또는 사용 안 함(FALSE)을 지정합니다.

### <a name="return-value"></a>Return Value

작업 표시줄 상호 작용을 사용하거나 사용하지 않도록 설정할 수 있는 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 주 창을 만들기 전에 호출 해야 합니다., 그렇지 않으면 어설션 하 고 FALSE를 반환 합니다.

## <a name="cwinappexitinstance"></a><a name="exitinstance"></a>CWinApp::Exit인스턴스

`Run` 멤버 함수 내에서 프레임워크에서 호출하여 응용 프로그램의 이 인스턴스를 종료합니다.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Return Value

응용 프로그램의 종료 코드; 0은 오류가 없음을 나타내고 값이 0보다 큰 값은 오류를 나타냅니다. 이 값은 에서 `WinMain`반환 값으로 사용됩니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하지 말고 `Run` 멤버 함수 내에서 호출하지 마십시오.

이 함수의 기본 구현은 응용 프로그램의 에 프레임 워크 옵션을 씁니다. INI 파일입니다. 응용 프로그램이 종료될 때 정리하려면 이 함수를 재정의합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

## <a name="cwinappgetapplicationrecoveryparameter"></a><a name="getapplicationrecoveryparameter"></a>CWinApp::GetApplicationRecovery매개 변수

응용 프로그램 복구 메서드에 대 한 입력 매개 변수를 검색합니다.

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>Return Value

응용 프로그램 복구 메서드의 기본 입력 매개 변수입니다.

### <a name="remarks"></a>설명

이 함수의 기본 동작은 NULL을 반환합니다.

자세한 내용은 [CWinApp:::응용 프로그램 복구호출](#applicationrecoverycallback)을 참조하십시오.

## <a name="cwinappgetapplicationrecoverypinginterval"></a><a name="getapplicationrecoverypinginterval"></a>CWinApp::GetApplication복구간격

다시 시작 관리자가 복구 콜백 함수가 반환될 때까지 기다리는 시간을 반환합니다.

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>Return Value

밀리초 단위의 시간 길이입니다.

### <a name="remarks"></a>설명

다시 시작 관리자에 등록된 응용 프로그램이 예기치 않게 종료되면 응용 프로그램은 열려 있는 문서를 저장하려고 시도하고 복구 콜백 기능을 호출합니다. 기본 복구 콜백 기능은 [CWinApp:::응용 프로그램 복구호출](#applicationrecoverycallback)입니다.

프레임워크가 복구 콜백 함수가 반환될 때까지 기다리는 시간은 ping 간격입니다. 재정의하거나 `CWinApp::GetApplicationRecoveryPingInterval` 에 사용자 지정 값을 제공하여 ping 간격을 사용자 지정할 수 있습니다. `RegisterWithRestartManager`

## <a name="cwinappgetapplicationrestartflags"></a><a name="getapplicationrestartflags"></a>CWinApp::GetApplication다시 시작 플래그

다시 시작 관리자에 대한 플래그를 반환합니다.

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>Return Value

다시 시작 관리자의 플래그입니다. 기본 구현은 0을 반환합니다.

### <a name="remarks"></a>설명

다시 시작 관리자에 대 한 플래그는 기본 구현에 영향을 주지 않습니다. 그들은 나중에 사용하기 위해 제공됩니다.

[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)를 사용하여 다시 시작 관리자로 응용 프로그램을 등록할 때 플래그를 설정합니다.

다시 시작 관리자 플래그에 대 한 가능한 값은 다음과 같습니다.

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

## <a name="cwinappgetappregistrykey"></a><a name="getappregistrykey"></a>CWinApp::GetApp레지스트리키

"소프트웨어"\레지스트리키\프로필 이름에 대한 HKEY_CURRENT_USER\\대한 키를 반환합니다.

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*Ptm*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 응용 프로그램 키; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

## <a name="cwinappgetdatarecoveryhandler"></a><a name="getdatarecoveryhandler"></a>CWinApp::GetDataRecovery처리기

응용 프로그램의 이 인스턴스에 대한 데이터 복구 처리기를 가져옵니다.

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>Return Value

응용 프로그램의 이 인스턴스에 대한 데이터 복구 처리기입니다.

### <a name="remarks"></a>설명

다시 시작 관리자를 사용하는 각 응용 프로그램에는 [CDataRecoveryHandler 클래스의](../../mfc/reference/cdatarecoveryhandler-class.md)인스턴스가 하나 있어야 합니다. 이 클래스는 열려 있는 문서를 모니터링하고 파일을 자동으로 저장합니다. 의 동작은 `CDataRecoveryHandler` 다시 시작 관리자의 구성에 따라 달라집니다. 자세한 내용은 [CDataRecoveryHandler 클래스를](../../mfc/reference/cdatarecoveryhandler-class.md)참조하십시오.

이 메서드는 Windows Vista보다 이전의 운영 체제에서 NULL을 반환합니다. 다시 시작 관리자는 Windows Vista 이전의 운영 체제에서 지원되지 않습니다.

응용 프로그램에 현재 데이터 복구 처리기가 없는 경우 이 메서드는 하나를 만들고 포인터를 반환합니다.

## <a name="cwinappgetfirstdoctemplateposition"></a><a name="getfirstdoctemplateposition"></a>CWinApp::GetFirstDoc템플릿 포지션

응용 프로그램에서 첫 번째 문서 템플릿의 위치를 가져옵니다.

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>Return Value

반복 또는 개체 포인터 검색에 사용할 수 있는 POSITION 값입니다. 목록이 비어 있는 경우 NULL입니다.

### <a name="remarks"></a>설명

[GetNextDocTemplate호출에서](#getnextdoctemplate) 반환된 위치 값을 사용하여 첫 번째 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체를 가져옵니다.

## <a name="cwinappgethelpmode"></a><a name="gethelpmode"></a>CWinApp:::GetHelpMode

응용 프로그램에서 사용하는 도움말 유형을 검색합니다.

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>Return Value

응용 프로그램에서 사용하는 도움말 유형입니다. 자세한 내용은 [CWinApp:m_eHelpType](#m_ehelptype) 를 참조하십시오.

## <a name="cwinappgetnextdoctemplate"></a><a name="getnextdoctemplate"></a>CWinApp::GetNextDocTemplate

*pos로*식별된 문서 템플릿을 *pos* 가져옵니다.

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
이전 호출 또는 `GetNextDocTemplate` [GetFirstDocTemplatePosition에](#getfirstdoctemplateposition)의해 반환된 위치 값에 대한 참조입니다. 이 호출에 의해 값이 다음 위치로 업데이트됩니다.

### <a name="return-value"></a>Return Value

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

에 대한 `GetNextDocTemplate` 호출을 사용하여 초기 위치를 설정하는 경우 정방향 반복 루프에서 `GetFirstDocTemplatePosition`사용할 수 있습니다.

위치 값이 유효한지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

검색된 문서 템플릿이 마지막으로 사용 가능한 경우 *pos의* 새 값이 NULL로 설정됩니다.

## <a name="cwinappgetprinterdevicedefaults"></a><a name="getprinterdevicedefaults"></a>CWinApp::getprinterDevice기본값

이 멤버 함수를 호출하여 인쇄할 프린터 장치 컨텍스트를 준비합니다.

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>매개 변수

*pPrintDlg*<br/>
[PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Windows 에서 현재 프린터 기본값을 검색합니다. 필요에 따라 INI 파일또는 인쇄 설정에서 사용자가 설정한 마지막 프린터 구성을 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

## <a name="cwinappgetprofilebinary"></a><a name="getprofilebinary"></a>CWinApp::GetProfile바이너리

이 멤버 함수를 호출하여 응용 프로그램 레지스트리 또는 의 지정된 섹션 내의 항목에서 이진 데이터를 검색합니다. INI 파일입니다.

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다.

*lpsz항목*<br/>
값을 검색할 항목이 포함된 null로 끝나는 문자열을 가리킵니다.

*ppData*<br/>
데이터의 주소를 수신할 포인터를 가리킵니다.

*p바이트*<br/>
데이터 크기(바이트)를 받게 되는 UINT를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 대/소문자를 구분하지 않으므로 *lpszSection* 및 *lpszEntry* 매개 변수의 문자열은 경우에 따라 다를 수 있습니다.

> [!NOTE]
> `GetProfileBinary`버퍼를 할당하고 \* *ppData에서*해당 주소를 반환합니다. 호출자는 **delete []** 를 사용하여 버퍼를 해제할 책임이 있습니다.

> [!IMPORTANT]
> 이 함수에서 반환된 데이터는 NULL로 끝나지 않아도 되며 호출자는 유효성 검사를 수행해야 합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/win32/SecBP/avoiding-buffer-overruns)를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

추가 예는 [CWinApp::WriteProfileBinary](#writeprofilebinary)을 참조하십시오.

## <a name="cwinappgetprofileint"></a><a name="getprofileint"></a>CWinApp::GetProfileInt

.INI 파일 또는 애플리케이션 레지스트리의 지정된 섹션 내에 있는 항목으로 정수 값을 검색하려면 이 멤버 함수를 호출합니다.

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다.

*lpsz항목*<br/>
값을 검색할 항목이 포함된 null로 끝나는 문자열을 가리킵니다.

*n기본값*<br/>
프레임워크에서 항목을 찾을 수 없는 경우 반환할 기본값을 지정합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 문자열의 정수 값은 지정된 항목 다음에 오게 됩니다. 함수에서 항목을 찾을 수 없는 경우 반환 값은 *nDefault* 매개 변수의 값입니다. 지정한 항목에 해당하는 값이 정수가 아닌 경우 반환 값은 0입니다.

이 멤버 함수는 .INI 파일에서 값에 대한 16 진수 표기법을 지원합니다. 서명된 정수를 검색할 때 값을 **int로**캐스팅해야 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 대/소문자를 구분하지 않으므로 *lpszSection* 및 *lpszEntry* 매개 변수의 문자열은 경우에 따라 다를 수 있습니다.

> [!IMPORTANT]
> 이 함수에서 반환된 데이터는 NULL로 끝나지 않아도 되며 호출자는 유효성 검사를 수행해야 합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/win32/SecBP/avoiding-buffer-overruns)를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

추가 예는 [CWinApp::WriteProfileInt](#writeprofileint)를 참조하십시오.

## <a name="cwinappgetprofilestring"></a><a name="getprofilestring"></a>CWinApp:::GetProfileString

이 멤버 함수를 호출하여 응용 프로그램의 레지스트리 또는 에서 지정된 섹션 내의 항목과 연결된 문자열을 검색합니다. INI 파일입니다.

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다.

*lpsz항목*<br/>
검색할 문자열이 포함된 null 종료된 문자열을 가리킵니다. 이 값은 NULL이 아니어야 합니다.

*lpsz기본값*<br/>
초기화 파일에서 항목을 찾을 수 없는 경우 지정된 항목의 기본 문자열 값을 가리킵니다.

### <a name="return-value"></a>Return Value

반환 값은 응용 프로그램의 의 문자열입니다. 문자열을 찾을 수 없는 경우 INI 파일 또는 *lpszDefault입니다.* 프레임워크에서 지원하는 최대 문자열 길이는 _MAX_PATH. *lpszDefault가* NULL이면 반환 값은 빈 문자열입니다.

### <a name="remarks"></a>설명

> [!IMPORTANT]
> 이 함수에서 반환된 데이터는 NULL로 끝나지 않아도 되며 호출자는 유효성 검사를 수행해야 합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/win32/SecBP/avoiding-buffer-overruns)를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

또 다른 예는 [CWinApp::GetProfileInt](#getprofileint)에 대한 예제를 참조하십시오.

## <a name="cwinappgetsectionkey"></a><a name="getsectionkey"></a>CWinApp::getsectionKey

"소프트웨어"를\\HKEY_CURRENT_USER 키를 반환합니다.\레지스트리Key\AppName\lpszSection.

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
가져올 키의 이름입니다.

*Ptm*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 섹션 키; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

## <a name="cwinapphideapplication"></a><a name="hideapplication"></a>CWinApp::숨기기 응용 프로그램

열려 있는 문서를 닫기 전에 응용 프로그램을 숨기려면 이 멤버 함수를 호출합니다.

```cpp
void HideApplication();
```

## <a name="cwinapphtmlhelp"></a><a name="htmlhelp"></a>CWinApp::Html도움말

HTMLHelp 응용 프로그램을 호출하려면 이 멤버 함수를 호출합니다.

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>매개 변수

*dwData*<br/>
추가 데이터를 지정합니다. 사용되는 값은 *nCmd* 매개 변수의 값에 따라 다릅니다. 기본값은 `0x000F` [HH_HELP_CONTEXT](/previous-versions/windows/desktop/htmlhelp/hh-help-context-command)의미합니다.

*nCmd*<br/>
요청한 도움말의 형식을 지정합니다. 가능한 값 목록과 *dwData* 매개 변수에 미치는 영향은 Windows SDK의 [HtmlHelpW](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpw) 또는 [HtmlHelpA](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpa) API 함수에 설명된 *uCommand* 매개 변수를 참조하십시오.

### <a name="remarks"></a>설명

또한 프레임워크는 HTMLHelp 응용 프로그램을 호출하기 위해 이 함수를 호출합니다.

응용 프로그램이 종료되면 프레임워크가 HTMLHelp 응용 프로그램을 자동으로 닫습니다.

## <a name="cwinappinitinstance"></a><a name="initinstance"></a>CWinApp::Initinstance

Windows를 사용하면 동일한 프로그램의 여러 복사본을 동시에 실행할 수 있습니다.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Return Value

초기화가 성공하면 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

응용 프로그램 초기화는 개념적으로 두 섹션으로 나뉩니다: 프로그램이 처음 실행될 때 수행되는 일회성 응용 프로그램 초기화와 처음 을 포함하여 프로그램의 복사본이 실행될 때마다 실행되는 인스턴스 초기화가 있습니다. 프레임워크의 구현은 `WinMain` 이 함수를 호출합니다.

재정의하여 `InitInstance` Windows에서 실행 중인 응용 프로그램의 각 새 인스턴스를 초기화합니다. 일반적으로 주 창 `InitInstance` 개체를 생성하고 `CWinThread::m_pMainWnd` 해당 창을 가리키도록 데이터 멤버를 설정하도록 재정의합니다. 이 멤버 함수 재정의에 대한 자세한 내용은 [CWinApp: 응용 프로그램 클래스](../../mfc/cwinapp-the-application-class.md)를 참조하십시오.

> [!NOTE]
> MFC 응용 프로그램은 단일 스레드 아파트(STA)로 초기화되어야 합니다. 재정의에서 [CoInitializeEx를](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) 호출하는 경우 COINIT_MULTITHREADED 대신 COINIT_APARTMENTTHREADED 지정합니다. `InitInstance`

### <a name="example"></a>예제

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

## <a name="cwinappistaskbarinteractionenabled"></a><a name="istaskbarinteractionenabled"></a>CWinApp::IsTaskbar상호작용 사용 가능

Windows 7 작업 표시줄 상호 작용이 활성화되어 있는지 여부를 알려줍니다.

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>Return Value

운영 체제가 Windows 7 이상인 경우 `EnableTaskbarInteraction` TRUE를 반환합니다.

### <a name="remarks"></a>설명

작업 표시줄 상호 작용은 MDI 응용 프로그램이 마우스 포인터가 응용 프로그램 작업 표시줄 단추 위에 있을 때 나타나는 별도의 탭된 축소판 그림에 MDI 자식의 내용을 표시한다는 것을 의미합니다.

## <a name="cwinapploadcursor"></a><a name="loadcursor"></a>CWinApp ::로드 커서

*lpszResourceName또는* 현재 실행 파일에서 *nIDResource에* 의해 지정된 커서 리소스를 로드합니다.

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
커서 리소스의 이름을 포함하는 null 종료 된 문자열을 가리킵니다. 이 인수에 `CString` 대해 a를 사용할 수 있습니다.

*nIDResource*<br/>
커서 리소스의 ID입니다. 리소스 목록은 Windows SDK의 [LoadCursor를](/windows/win32/api/winuser/nf-winuser-loadcursorw) 참조하십시오.

### <a name="return-value"></a>Return Value

성공한 경우 커서에 대한 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

`LoadCursor`커서가 이전에 로드되지 않은 경우에만 커서를 메모리에 로드합니다. 그렇지 않으면 기존 리소스의 핸들을 검색합니다.

[LoadStandardCursor](#loadstandardcursor) 또는 [LoadOEMCursor](#loadoemcursor) 멤버 함수를 사용하여 미리 정의된 Windows 커서에 액세스합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

## <a name="cwinapploadicon"></a><a name="loadicon"></a>CWinApp ::로드 아이콘

*lpszResourceName또는* 실행 파일에서 *nIDResource에* 의해 지정된 아이콘 리소스를 로드합니다.

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
아이콘 리소스의 이름을 포함 하는 null 종료 된 문자열을 가리킵니다. 이 인수에 `CString` 대해서도 사용할 수 있습니다.

*nIDResource*<br/>
아이콘 리소스의 ID 번호입니다.

### <a name="return-value"></a>Return Value

성공하면 아이콘에 대한 핸들; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

`LoadIcon`아이콘이 이전에 로드되지 않은 경우에만 아이콘을 로드합니다. 그렇지 않으면 기존 리소스의 핸들을 검색합니다.

[LoadStandardIcon](#loadstandardicon) 또는 [LoadOEMIcon](#loadoemicon) 멤버 함수를 사용하여 미리 정의된 Windows 아이콘에 액세스할 수 있습니다.

> [!NOTE]
> 이 멤버 함수는 Win32 API 함수 [LoadIcon을](/windows/win32/api/winuser/nf-winuser-loadiconw)호출하며, 크기가 SM_CXICON 및 시스템 메트릭 값을 SM_CYICON 아이콘만 로드할 수 있습니다.

## <a name="cwinapploadoemcursor"></a><a name="loadoemcursor"></a>CWinApp::로드OEM커서

*nIDCursor*에 의해 지정된 Windows 미리 정의된 커서 리소스를 로드합니다.

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>매개 변수

*니드커서*<br/>
**OCR_** 미리 정의된 Windows 커서를 지정하는 상수 식별자를 매니페스트합니다. WINDOWS에서 `#define OEMRESOURCE` OCR_ `#include \<afxwin.h>` 상수에 액세스하려면 이전에 있어야 합니다. **OCR_** H.

### <a name="return-value"></a>Return Value

성공한 경우 커서에 대한 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

`LoadOEMCursor` 또는 [LoadStandardCursor](#loadstandardcursor) 멤버 함수를 사용하여 미리 정의된 Windows 커서에 액세스합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

## <a name="cwinapploadoemicon"></a><a name="loadoemicon"></a>CWinApp ::로드OEM아이콘

*nIDIcon*.

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>매개 변수

*니디콘*<br/>
미리 정의된 Windows 아이콘을 지정하는 **OIC_** 매니페스트 상수 식별자를 명시합니다. WINDOWS에서 `#define OEMRESOURCE` `#include \<afxwin.h>` **OIC_** 상수에 액세스하려면 이전에 있어야 합니다. H.

### <a name="return-value"></a>Return Value

성공하면 아이콘에 대한 핸들; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

또는 `LoadOEMIcon` [LoadStandardIcon](#loadstandardicon) 멤버 함수를 사용하여 미리 정의된 Windows 아이콘에 액세스합니다.

## <a name="cwinapploadstandardcursor"></a><a name="loadstandardcursor"></a>CWinApp::로드스탠다드커서

*lpszCursorName* 지정 하는 Windows 미리 정의 된 커서 리소스를 로드 합니다.

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>매개 변수

*lpszCursor이름*<br/>
**IDC_** 미리 정의된 Windows 커서를 지정하는 상수 식별자를 매니페스트합니다. 이러한 식별자는 WINDOWS에서 정의됩니다. H. 다음 목록은 *lpszCursorName에*대해 가능한 미리 정의된 값과 의미를 보여 주며 다음과 같이 표시됩니다.

- IDC_ARROW 표준 화살표 커서

- IDC_IBEAM 표준 텍스트 삽입 커서

- Windows에서 시간이 많이 걸리는 작업을 수행할 때 사용되는 IDC_WAIT 모래 시계 커서

- 선택을 위한 IDC_CROSS 십자선 커서

- 똑바로 가리키는 IDC_UPARROW 화살표

- IDC_SIZE 사용되지 않고 지원되지 않습니다. IDC_SIZEALL 사용

- IDC_SIZEALL 네 개의 뾰족한 화살표입니다. 창 크기를 조정하는 데 사용할 커서입니다.

- IDC_ICON 사용되지 않으며 지원되지 않습니다. IDC_ARROW 사용합니다.

- IDC_SIZENWSE 왼쪽 상단과 오른쪽 아래 끝에 있는 양면 화살표

- IDC_SIZENESW 오른쪽 상단과 왼쪽 아래 끝에 있는 양면 화살표

- IDC_SIZEWE 수평 양방향 화살표

- IDC_SIZENS 수직 양방향 화살표

### <a name="return-value"></a>Return Value

성공한 경우 커서에 대한 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

`LoadStandardCursor` 또는 [LoadOEMCursor](#loadoemcursor) 멤버 함수를 사용하여 미리 정의된 Windows 커서에 액세스합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

## <a name="cwinapploadstandardicon"></a><a name="loadstandardicon"></a>CWinApp :: 로드 스탠다드아이콘

*lpszIconName* 지정 하는 Windows 미리 정의 된 아이콘 리소스를 로드 합니다.

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>매개 변수

*lpszIconName*<br/>
미리 정의된 Windows 아이콘을 지정하는 매니페스트 상수 식별자입니다. 이러한 식별자는 WINDOWS에서 정의됩니다. H. 가능한 미리 정의된 값 과 그 설명의 목록은 Windows SDK의 [LoadIcon에서](/windows/win32/api/winuser/nf-winuser-loadiconw) *lpIconName* 매개 변수를 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 아이콘에 대한 핸들; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

`LoadStandardIcon` 또는 [LoadOEMIcon](#loadoemicon) 멤버 함수를 사용하여 미리 정의된 Windows 아이콘에 액세스합니다.

## <a name="cwinapploadstdprofilesettings"></a><a name="loadstdprofilesettings"></a>CWinApp::로드스트드 프로파일설정

[InitInstance](#initinstance) 멤버 함수 내에서 이 멤버 함수를 호출하여 가장 최근에 사용한(MRU) 파일 및 마지막 미리 보기 상태의 목록을 활성화하고 로드합니다.

```cpp
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>매개 변수

*nMaxMRU*<br/>
추적할 최근에 사용한 파일 수입니다.

### <a name="remarks"></a>설명

*nMaxMRU가* 0이면 MRU 목록이 유지되지 않습니다.

## <a name="cwinappm_bhelpmode"></a><a name="m_bhelpmode"></a>CWinApp::m_bHelpMode

TRUE 응용 프로그램이 도움말 컨텍스트 모드(일반적으로 SHIFT + F1로 호출됨)에 있는 경우 그렇지 않으면 거짓.

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>설명

도움말 컨텍스트 모드에서 커서는 물음표가 되고 사용자는 화면으로 이동할 수 있습니다. 도움말 모드에서 특수 처리를 구현하려는 경우 이 플래그를 검사합니다. `m_bHelpMode`는 BOOL 형식의 공용 변수입니다.

## <a name="cwinappm_dwrestartmanagersupportflags"></a><a name="m_dwrestartmanagersupportflags"></a>CWinApp::m_dwRestartManagerSupportFlags

다시 시작 관리자의 행동 방식을 결정하는 플래그입니다.

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>설명

관리자를 다시 시작하려면 `m_dwRestartManagerSupportFlags` 원하는 동작으로 설정합니다. 다음 표에는 사용 가능한 플래그가 표시됩니다.

|||
|-|-|
|플래그|Description|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|응용 프로그램은 [CWinApp를 사용하여 등록됩니다::RegisterWithRestartManager](#registerwithrestartmanager). 다시 시작 관리자는 예기치 않게 종료되는 경우 응용 프로그램을 다시 시작해야 합니다.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY|응용 프로그램이 다시 시작 관리자에 등록되고 다시 시작 관리자는 응용 프로그램을 다시 시작할 때 복구 콜백 함수를 호출합니다. 기본 복구 콜백 기능은 [CWinApp:::응용 프로그램 복구호출](#applicationrecoverycallback)입니다.|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|자동 저장이 활성화되고 다시 시작 관리자가 응용 프로그램을 다시 시작할 때 열려 있는 문서를 자동으로 저장합니다.|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|자동 저장이 활성화되고 다시 시작 관리자가 정기적으로 열려 있는 문서를 자동으로 저장합니다. 간격은 [CWinApp에](#m_nautosaveinterval)의해 정의됩니다 ::m_nAutosaveInterval .|
|- AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|다시 시작 관리자는 예기치 않은 종료에서 응용 프로그램을 다시 시작한 후 이전에 열린 문서를 엽니다. [CDataRecoveryHandler 클래스는](../../mfc/reference/cdatarecoveryhandler-class.md) 열려 있는 문서 목록을 저장하고 복원하는 것을 처리합니다.|
|- AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|다시 시작 관리자는 응용 프로그램을 다시 시작한 후 자동으로 저장된 파일을 복원하라는 메시지를 사용자에게 표시합니다. 클래스는 `CDataRecoveryHandler` 사용자를 쿼리합니다.|
|- AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_SUPPORT_RECOVER, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES 연합.|
|- AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES 연합.|
|- AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES, AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES 연합.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|노조는 ofAFX_RESTART_MANAGER_SUPPORT_RECOVERY, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES, AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|

## <a name="cwinappm_ehelptype"></a><a name="m_ehelptype"></a>CWinApp::m_eHelpType

이 데이터 멤버의 형식은 `CWinApp` 클래스 내에서 정의되는 AFX_HELP_TYPE 수거된 형식입니다.

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>설명

AFX_HELP_TYPE 열거형은 다음과 같이 정의됩니다.

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- 응용 프로그램의 도움말을 HTML 도움말로 설정하려면 [SetHelpMode를](#sethelpmode) 호출하고 을 지정합니다. `afxHTMLHelp`

- 응용 프로그램의 도움말을 WinHelp로 설정하려면 를 호출하고 `SetHelpMode` 지정합니다. `afxWinHelp`

## <a name="cwinappm_hinstance"></a><a name="m_hinstance"></a>CWinApp::m_hInstance

에 Windows에서 전달된 *hInstance* `WinMain`매개 변수에 해당합니다.

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>설명

`m_hInstance` 데이터 멤버는 Windows에서 실행 중인 응용 프로그램의 현재 인스턴스에 대한 핸들입니다. 이 값은 전역 함수 [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)에서 반환됩니다. `m_hInstance`은 HINSTANCE 형식의 공용 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

## <a name="cwinappm_lpcmdline"></a><a name="m_lpcmdline"></a>CWinApp::m_lpCmdLine

에 Windows에서 전달되는 *lpCmdLine* `WinMain`매개 변수에 해당합니다.

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>설명

응용 프로그램의 명령줄을 지정하는 null 종료 된 문자열을 가리킵니다. 응용 `m_lpCmdLine` 프로그램을 시작할 때 사용자가 입력한 모든 명령줄 인수에 액세스하는 데 사용합니다. `m_lpCmdLine`는 LPTSTR 형식의 공용 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

## <a name="cwinappm_nautosaveinterval"></a><a name="m_nautosaveinterval"></a>CWinApp::m_nAutosaveInterval

자동 저장 사이의 밀리초 길이입니다.

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>설명

설정된 간격으로 열려 있는 문서를 자동으로 저장하도록 다시 시작 관리자를 구성할 수 있습니다. 응용 프로그램이 파일을 자동으로 저장하지 않으면 이 매개 변수는 영향을 주지 않습니다.

## <a name="cwinappm_ncmdshow"></a><a name="m_ncmdshow"></a>CWinApp::m_nCmdShow

에 Windows에서 전달된 *nCmdShow* `WinMain`매개 변수에 해당합니다.

```
int m_nCmdShow;
```

### <a name="remarks"></a>설명

응용 프로그램의 `m_nCmdShow` 기본 창에 대 한 [CWnd::ShowWindow를](../../mfc/reference/cwnd-class.md#showwindow) 호출할 때 인수로 전달 해야 합니다. `m_nCmdShow`는 **int**형식의 공용 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

## <a name="cwinappm_pactivewnd"></a><a name="m_pactivewnd"></a>CWinApp::m_pActiveWnd

이 데이터 멤버를 사용하여 OLE 서버 응용 프로그램이 활성화된 OLE 컨테이너 응용 프로그램의 기본 창에 대한 포인터를 저장합니다.

### <a name="remarks"></a>설명

이 데이터 멤버가 NULL이면 응용 프로그램이 활성 상태가 아닙니다.

프레임 창이 OLE 컨테이너 응용 프로그램에서 활성화될 때 프레임워크는 이 멤버 변수를 설정합니다.

## <a name="cwinappm_pdatarecoveryhandler"></a><a name="m_pdatarecoveryhandler"></a>CWinApp::m_pDataRecoveryHandler

응용 프로그램의 데이터 복구 처리기에 대한 포인터입니다.

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>설명

응용 프로그램의 데이터 복구 처리기는 열린 문서를 모니터링하고 자동으로 저장합니다. 프레임워크는 데이터 복구 처리기를 사용하여 응용 프로그램이 예기치 않게 종료된 후 다시 시작될 때 자동 저장된 파일을 복원합니다. 자세한 내용은 [CDataRecoveryHandler 클래스를](../../mfc/reference/cdatarecoveryhandler-class.md)참조하십시오.

## <a name="cwinappm_pszappname"></a><a name="m_pszappname"></a>CWinApp::m_pszAppName

애플리케이션의 이름을 지정합니다.

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>설명

응용 프로그램 이름은 [CWinApp](#cwinapp) 생성자로 전달된 매개 변수에서 올 수 있으며, 지정되지 않은 경우 id가 있는 리소스 문자열에 AFX_IDS_APP_TITLE 수 있습니다. 리소스에서 응용 프로그램 이름을 찾을 수 없는 경우 프로그램의 에서 제공됩니다. EXE 파일 이름입니다.

글로벌 함수 [AfxGetAppName에](application-information-and-management.md#afxgetappname)의해 반환됩니다. `m_pszAppName`는 **형식 const char의**<strong>\*</strong>공용 변수입니다.

> [!NOTE]
> `m_pszAppName`에 값을 할당하는 경우 힙에 동적으로 할당되어야 합니다. `CWinApp` 소멸자는 이 포인터를 통해 **무료()를**호출합니다. `_tcsdup`많은 사람들이 () 런타임 라이브러리 함수를 사용하여 할당을 수행하려고 합니다. 또한 새 값을 할당하기 전에 현재 포인터와 연결된 메모리를 확보합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

## <a name="cwinappm_pszexename"></a><a name="m_pszexename"></a>CWinApp::m_pszExeName

확장자 없이 응용 프로그램의 실행 파일의 이름을 포함 합니다.

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>설명

[m_pszAppName](#m_pszappname)달리 이 이름은 공백을 포함할 수 없습니다. `m_pszExeName`는 **형식 const char의**<strong>\*</strong>공용 변수입니다.

> [!NOTE]
> `m_pszExeName`에 값을 할당하는 경우 힙에 동적으로 할당되어야 합니다. `CWinApp` 소멸자는 이 포인터를 통해 **무료()를**호출합니다. `_tcsdup`많은 사람들이 () 런타임 라이브러리 함수를 사용하여 할당을 수행하려고 합니다. 또한 새 값을 할당하기 전에 현재 포인터와 연결된 메모리를 확보합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

## <a name="cwinappm_pszhelpfilepath"></a><a name="m_pszhelpfilepath"></a>CWinApp::m_pszHelpFilePath

응용 프로그램의 도움말 파일에 대한 경로를 포함합니다.

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>설명

기본적으로 프레임워크는 "를 `m_pszHelpFilePath` 사용하여 응용 프로그램의 이름으로 초기화합니다. HLP"가 추가되었습니다. 도움말 파일의 이름을 변경하려면 `m_pszHelpFilePath` 원하는 도움말 파일의 전체 이름이 포함된 문자열을 가리키도록 설정합니다. 이 작업을 수행하는 편리한 장소는 응용 프로그램의 [InitInstance](#initinstance) 함수입니다. `m_pszHelpFilePath`는 **형식 const char의**<strong>\*</strong>공용 변수입니다.

> [!NOTE]
> `m_pszHelpFilePath`에 값을 할당하는 경우 힙에 동적으로 할당되어야 합니다. `CWinApp` 소멸자는 이 포인터를 통해 **무료()를**호출합니다. `_tcsdup`많은 사람들이 () 런타임 라이브러리 함수를 사용하여 할당을 수행하려고 합니다. 또한 새 값을 할당하기 전에 현재 포인터와 연결된 메모리를 확보합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

## <a name="cwinappm_pszprofilename"></a><a name="m_pszprofilename"></a>CWinApp::m_pszProfileName

응용 프로그램의 이름을 포함합니다. INI 파일입니다.

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>설명

`m_pszProfileName`는 **형식 const char의**<strong>\*</strong>공용 변수입니다.

> [!NOTE]
> `m_pszProfileName`에 값을 할당하는 경우 힙에 동적으로 할당되어야 합니다. `CWinApp` 소멸자는 이 포인터를 통해 **무료()를**호출합니다. `_tcsdup`많은 사람들이 () 런타임 라이브러리 함수를 사용하여 할당을 수행하려고 합니다. 또한 새 값을 할당하기 전에 현재 포인터와 연결된 메모리를 확보합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

## <a name="cwinappm_pszregistrykey"></a><a name="m_pszregistrykey"></a>CWinApp::m_pszRegistryKey

레지스트리 또는 INI 파일에서 응용 프로그램 프로필 설정이 저장되는 위치를 결정하는 데 사용됩니다.

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>설명

일반적으로 이 데이터 멤버는 읽기 전용으로 처리됩니다.

- 값은 레지스트리 키에 저장됩니다. 응용 프로그램 프로필 설정의 이름은 다음 레지스트리 키에 추가됩니다 HKEY_CURRENT_USER.

`m_pszRegistryKey`에 값을 할당하는 경우 힙에 동적으로 할당되어야 합니다. `CWinApp` 소멸자는 이 포인터를 통해 **무료()를**호출합니다. `_tcsdup`많은 사람들이 () 런타임 라이브러리 함수를 사용하여 할당을 수행하려고 합니다. 또한 새 값을 할당하기 전에 현재 포인터와 연결된 메모리를 확보합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

## <a name="cwinappm_pszappid"></a><a name="m_pszappid"></a>CWinApp::m_pszAppID

응용 프로그램 사용자 모델 ID입니다.

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>설명

## <a name="cwinapponcontexthelp"></a><a name="oncontexthelp"></a>CWinApp:::에 컨텍스트 도움말

응용 프로그램 내에서 SHIFT+F1 도움말을 처리합니다.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>설명

이 멤버 `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` 함수를 사용하려면 클래스 메시지 맵에 문을 추가하고 액셀러레이터 테이블 항목(일반적으로 SHIFT+F1)을 추가해야 합니다. `CWinApp`

`OnContextHelp`응용 프로그램을 도움말 모드로 전환합니다. 커서가 화살표와 물음표로 변경되고 사용자는 마우스 포인터를 이동하고 왼쪽 마우스 버튼을 눌러 대화 상자, 창, 메뉴 또는 명령 단추를 선택할 수 있습니다. 이 멤버 함수는 커서 아래의 개체의 도움말 컨텍스트를 검색하고 해당 도움말 컨텍스트를 통해 Windows 함수 WinHelp를 호출합니다.

## <a name="cwinapponddecommand"></a><a name="onddecommand"></a>CWinApp:::OnDDECommand

기본 프레임 창DDE 실행 메시지를 수신 하는 경우 프레임 워크에 의해 호출 됩니다.

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>매개 변수

*lpszCommand*<br/>
응용 프로그램에서 수신한 DDE 명령 문자열을 가리킵니다.

### <a name="return-value"></a>Return Value

명령이 처리되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

기본 구현은 명령이 문서를 여는 요청인지 여부를 확인하고, 이 경우 지정된 문서를 엽니다. Windows 파일 관리자는 일반적으로 사용자가 데이터 파일을 두 번 클릭할 때 이러한 DDE 명령 문자열을 보냅니다. 인쇄 명령과 같은 다른 DDE 실행 명령을 처리하려면 이 함수를 재정의합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

## <a name="cwinapponfilenew"></a><a name="onfilenew"></a>CWinApp::온파일뉴

ID_FILE_NEW 명령을 구현합니다.

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>설명

이 멤버 `ON_COMMAND( ID_FILE_NEW, OnFileNew )` 함수를 `CWinApp` 사용하려면 클래스 메시지 맵에 문을 추가해야 합니다. 이 기능을 사용하면 새 파일 명령의 실행을 처리합니다.

기본 동작 및 이 멤버 함수를 재정의하는 방법에 대한 지침은 [기술 참고 22를](../../mfc/tn022-standard-commands-implementation.md) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponfileopen"></a><a name="onfileopen"></a>CWinApp::온파일 열기

ID_FILE_OPEN 명령을 구현합니다.

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>설명

이 멤버 `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` 함수를 `CWinApp` 사용하려면 클래스 메시지 맵에 문을 추가해야 합니다. 이 기능을 사용하면 파일 열기 명령의 실행을 처리합니다.

기본 동작 및 이 멤버 함수를 재정의하는 방법에 대한 지침은 [기술 참고 22를](../../mfc/tn022-standard-commands-implementation.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponfileprintsetup"></a><a name="onfileprintsetup"></a>CWinApp::온파일 프린트셋업

ID_FILE_PRINT_SETUP 명령을 구현합니다.

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>설명

이 멤버 `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` 함수를 `CWinApp` 사용하려면 클래스 메시지 맵에 문을 추가해야 합니다. 이 기능을 사용하면 파일 인쇄 명령의 실행을 처리합니다.

기본 동작 및 이 멤버 함수를 재정의하는 방법에 대한 지침은 [기술 참고 22를](../../mfc/tn022-standard-commands-implementation.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponhelp"></a><a name="onhelp"></a>CWinApp:::에 도움

현재 컨텍스트를 사용하여 애플리케이션 내에서 F1 도움말을 처리합니다.

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>설명

일반적으로 F1 키에 대한 가속기 키 항목도 추가됩니다. F1 키를 사용하도록 설정하는 것은 요구 사항이 아닌 규칙일 뿐입니다.

이 멤버 `ON_COMMAND( ID_HELP, OnHelp )` 함수를 `CWinApp` 사용하려면 클래스 메시지 맵에 문을 추가해야 합니다. 활성화된 경우 사용자가 F1 키를 누를 때 프레임워크에서 호출합니다.

이 메시지 처리기 함수의 기본 구현은 현재 창, 대화 상자 또는 메뉴 항목에 해당하는 도움말 컨텍스트를 결정한 다음 WINHELP를 호출합니다. Exe. 현재 사용할 수 있는 컨텍스트가 없는 경우 함수는 기본 컨텍스트를 사용합니다.

이 멤버 함수를 재정의하여 도움말 컨텍스트를 현재 포커스가 있는 창, 대화 상자, 메뉴 항목 또는 도구 모음 단추 이외의 것으로 설정합니다. 원하는 `WinHelp` 도움말 컨텍스트 ID로 호출합니다.

## <a name="cwinapponhelpfinder"></a><a name="onhelpfinder"></a>CWinApp:::에 도움말 파인더

ID_HELP_FINDER 및 ID_DEFAULT_HELP 명령을 처리합니다.

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>설명

이 멤버 `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` 함수를 `CWinApp` 사용하려면 클래스 메시지 맵에 문을 추가해야 합니다. 활성화된 경우 프레임워크는 응용 프로그램의 사용자가 표준 `WinHelp` **HELP_FINDER** 항목으로 호출할 도움말 찾기 명령을 선택할 때 이 메시지 처리기 함수를 호출합니다.

## <a name="cwinapponhelpindex"></a><a name="onhelpindex"></a>CWinApp:::온헬드 인덱스

ID_HELP_INDEX 명령을 처리하고 기본 도움말 항목을 제공합니다.

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>설명

이 멤버 `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` 함수를 `CWinApp` 사용하려면 클래스 메시지 맵에 문을 추가해야 합니다. 활성화된 경우 프레임워크는 응용 프로그램의 사용자가 표준 `WinHelp` **HELP_INDEX** 항목으로 호출할 도움말 Index 명령을 선택할 때 이 메시지 처리기 함수를 호출합니다.

## <a name="cwinapponhelpusing"></a><a name="onhelpusing"></a>CWinApp::에 도움 사용

ID_HELP_USING 명령을 처리합니다.

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>설명

이 멤버 `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` 함수를 `CWinApp` 사용하려면 클래스 메시지 맵에 문을 추가해야 합니다. 프레임워크는 응용 프로그램의 사용자가 표준 `WinHelp` **HELP_HELPONHELP** 항목으로 응용 프로그램을 호출하는 도움말 사용 명령을 선택하면 이 메시지 처리기 함수를 호출합니다.

## <a name="cwinapponidle"></a><a name="onidle"></a>CWinApp ::: 온들

유휴 시간 처리를 수행하려면 이 멤버 함수를 재정의합니다.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>매개 변수

*l카운트*<br/>
응용 프로그램의 메시지 큐가 `OnIdle` 비어 있을 때 매번 증가하는 카운터가 호출됩니다. 이 개수는 새 메시지가 처리될 때마다 0으로 재설정됩니다. *lCount* 매개 변수를 사용하여 메시지를 처리하지 않고 응용 프로그램이 유휴 상태였던 상대적인 기간을 확인할 수 있습니다.

### <a name="return-value"></a>Return Value

비영제로 더 많은 유휴 처리 시간을 수신; 더 이상 유휴 시간이 필요하지 않은 경우 0입니다.

### <a name="remarks"></a>설명

`OnIdle`응용 프로그램의 메시지 큐가 비어 있을 때 기본 메시지 루프에서 호출됩니다. 재정의를 사용하여 사용자 고유의 백그라운드 유휴 처리기 작업을 호출합니다.

`OnIdle`유휴 처리 시간이 필요하지 않다는 것을 나타내기 위해 0을 반환해야 합니다. *lCount* 매개 변수는 메시지 큐가 비어 있고 새 메시지가 처리될 때마다 0으로 재설정될 때마다 호출될 때마다 증가됩니다. `OnIdle` 이 개수에 따라 다른 유휴 루틴을 호출할 수 있습니다.

다음은 유휴 루프 처리를 요약합니다.

1. Microsoft Foundation 클래스 라이브러리의 메시지 루프가 메시지 큐를 검사하고 `OnIdle` 보류 중인 메시지를 찾지 못하면 응용 프로그램 개체를 호출하고 *0을 lCount* 인수로 제공합니다.

2. `OnIdle`은 일부 처리를 수행하고 추가 처리를 수행하기 위해 다시 호출해야 함을 나타내기 위해 0이 아닌 값을 반환합니다.

3. 메시지 루프는 메시지 큐를 다시 확인합니다. 보류 중인 메시지가 없는 `OnIdle` 경우 다시 호출되어 *lCount* 인수를 증가시입니다.

4. 결국 `OnIdle` 모든 유휴 작업 처리를 완료하고 0을 반환합니다. 이렇게 하면 메시지 루프가 `OnIdle` 메시지 큐에서 다음 메시지가 수신될 때까지 호출을 중지하도록 지시하며, 이 때 인수가 0으로 설정된 상태로 유휴 주기가 다시 시작됩니다.

응용 프로그램이 반환될 `OnIdle` 때까지 `OnIdle` 사용자 입력을 처리할 수 없으므로 긴 작업을 수행하지 마십시오.

> [!NOTE]
> 업데이트의 `OnIdle` 기본 구현은 메뉴 항목 및 도구 모음 단추와 같은 사용자 인터페이스 개체를 명령하고 내부 데이터 구조 정리를 수행합니다. 따라서 재정의하는 `OnIdle`경우 재정의한 `lCount` 버전에서 호출해야 `CWinApp::OnIdle` 합니다. 먼저 모든 기본 클래스 유휴 처리(즉, `OnIdle` 기본 클래스가 0을 반환할 때까지)를 호출합니다. 기본 클래스 처리가 완료되기 전에 작업을 수행해야 하는 경우 기본 클래스 구현을 검토하여 작업을 수행할 적절한 *lCount를* 선택합니다.

메시지 큐에서 `OnIdle` 메시지를 검색할 때마다 호출하지 않으려면 [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage)을 재정의할 수 있습니다. 응용 프로그램이 매우 짧은 타이머를 설정했거나 시스템에서 WM_SYSTIMER 메시지를 보내는 `OnIdle` 경우 반복적으로 호출되어 성능이 저하됩니다.

### <a name="example"></a>예제

다음 두 예제에서 를 `OnIdle`사용하는 방법을 보여 주십습니다. 첫 번째 예제는 *lCount* 인수를 사용하여 두 개의 유휴 작업을 처리하여 작업의 우선 순위를 지정합니다. 첫 번째 작업은 우선 순위가 높으며 가능하면 수행해야 합니다. 두 번째 작업은 덜 중요하며 사용자 입력이 오래 일시 중지된 경우에만 수행해야 합니다. `OnIdle`의 기본 클래스 버전에 대한 호출을 기록합니다. 두 번째 예제는 우선 순위가 다른 유휴 작업 그룹을 관리합니다.

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

## <a name="cwinappopendocumentfile"></a><a name="opendocumentfile"></a>CWinApp::오픈 문서파일

프레임워크는 이 메서드를 호출하여 응용 프로그램에 대해 명명된 [CDocument](../../mfc/reference/cdocument-class.md) 파일을 엽니다.

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpsz파일이름*<br/>
【인】 열 파일의 이름입니다.

*bAddToMRU*<br/>
【인】 TRUE는 문서가 가장 최근 파일 중 하나임을 나타냅니다. FALSE는 문서가 최신 파일 중 하나가 아님을 나타냅니다.

### <a name="return-value"></a>Return Value

성공하는 `CDocument` 경우에 대한 포인터; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

해당 이름이 있는 문서가 이미 열려 있는 경우 해당 문서가 포함된 첫 번째 프레임 창에 포커스가 표시됩니다. 응용 프로그램이 여러 문서 템플릿을 지원하는 경우 프레임워크는 파일 이름 확장명을 사용하여 문서를 로드하는 데 적합한 문서 템플릿을 찾습니다. 성공하면 문서 템플릿은 프레임 창과 문서에 대한 보기를 만듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

## <a name="cwinappparsecommandline"></a><a name="parsecommandline"></a>CWinApp::P거칠은 커맨드라인

이 멤버 함수를 호출하여 명령줄을 구문 분석하고 매개 변수를 한 번에 하나씩 [CCommandLineInfo::ParseParam로](../../mfc/reference/ccommandlineinfo-class.md#parseparam)보냅니다.

```cpp
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>매개 변수

*rCmdInfo*<br/>
[CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

응용 프로그램 마법사를 사용하여 새 MFC 프로젝트를 시작하면 응용 프로그램 `CCommandLineInfo`마법사에서 의 `ProcessShellCommand` `ParseCommandLine` 로컬 인스턴스를 만든 다음 [InitInstance](#initinstance) 멤버 함수를 호출합니다. 명령줄은 아래에 설명된 경로를 따릅니다.

1. `InitInstance`에서 생성된 후 `CCommandLineInfo` 개체가 `ParseCommandLine`로 전달됩니다.

2. `ParseCommandLine`그런 `CCommandLineInfo::ParseParam` 다음 각 매개 변수에 대해 한 번 반복적으로 호출합니다.

3. `ParseParam`개체를 `CCommandLineInfo` 채웁니다. [ProcessShellCommand](#processshellcommand)

4. `ProcessShellCommand`은 명령줄 인수 와 플래그를 처리합니다.

필요에 따라 직접 `ParseCommandLine` 전화할 수 있습니다.

명령줄 플래그에 대한 설명은 [CCommandLineInfo:m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)를 참조하십시오.

## <a name="cwinapppretranslatemessage"></a><a name="pretranslatemessage"></a>CWinApp::P다시 번역 메시지

Windows 함수 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage에](/windows/win32/api/winuser/nf-winuser-dispatchmessage) 전달되기 전에 창 메시지를 필터링하기 위해 이 함수를 재정의하는 기본 구현은 `CWinApp::PreTranslateMessage` 가속기 키 번역을 수행하므로 재정의된 버전에서 멤버 함수를 호출해야 합니다.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
처리할 메시지가 포함된 [MSG](/windows/win32/api/winuser/ns-winuser-msg) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메시지가 완전히 처리되고 `PreTranslateMessage` 더 이상 처리되지 않아야 하는 경우 Nonzero입니다. 메시지가 정상적인 방식으로 처리되어야 하는 경우 0입니다.

## <a name="cwinappprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinApp::P로케이션메시지필터

프레임워크의 후크 함수는 이 멤버 함수를 호출하여 특정 Windows 메시지를 필터링하고 응답합니다.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>매개 변수

*code*<br/>
후크 코드를 지정합니다. 이 멤버 함수는 코드를 사용하여 *lpMsg를* 처리하는 방법을 결정합니다.

*lpMsg*<br/>
윈도우 [MSG](/windows/win32/api/winuser/ns-winuser-msg)트러처에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메시지가 처리되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

후크 함수는 이벤트를 응용 프로그램의 일반 메시지 처리로 보내기 전에 처리합니다.

이 고급 기능을 재정의하는 경우 기본 클래스 버전을 호출하여 프레임워크의 후크 처리를 유지관리해야 합니다.

## <a name="cwinappprocessshellcommand"></a><a name="processshellcommand"></a>CWinApp::P로키스셸커맨드

이 멤버 함수는 [InitInstance에서](#initinstance) `CCommandLineInfo` *rCmdInfo로*식별된 개체에서 전달된 매개 변수를 수락하고 표시된 작업을 수행하기 위해 호출됩니다.

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>매개 변수

*rCmdInfo*<br/>
[CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

셸 명령이 성공적으로 처리되는 경우 0이 아닙니다. 0이면 InitInstance 에서 FALSE를 [반환합니다.](#initinstance)

### <a name="remarks"></a>설명

응용 프로그램 마법사를 사용하여 새 MFC 프로젝트를 시작하면 응용 프로그램 `CCommandLineInfo`마법사에서 의 `ProcessShellCommand` 로컬 인스턴스를 만든 `InitInstance` 다음 멤버 함수에서 호출 및 [ParseCommandLine을](#parsecommandline) 호출합니다. 명령줄은 아래에 설명된 경로를 따릅니다.

1. `InitInstance`에서 생성된 후 `CCommandLineInfo` 개체가 `ParseCommandLine`로 전달됩니다.

2. `ParseCommandLine`그런 다음 [CCommandLineInfo::ParseParam을](../../mfc/reference/ccommandlineinfo-class.md#parseparam) 반복적으로 호출하여 각 매개 변수에 대해 한 번씩 호출합니다.

3. `ParseParam``CCommandLineInfo` 다음에 전달되는 개체를 `ProcessShellCommand`채웁니다.

4. `ProcessShellCommand`은 명령줄 인수 와 플래그를 처리합니다.

[CCommandLineInfo:m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)식별된 `CCommandLineInfo` `CCommandLineInfo` 개체의 데이터 멤버는 클래스 내에서 정의된 다음 줄임마이드 형식입니다.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };
```

이러한 각 값에 대한 간략한 `CCommandLineInfo::m_nShellCommand`설명은 을 참조하십시오.

## <a name="cwinappprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinApp::P로스WndProc예외

프레임워크는 처리기가 응용 프로그램의 메시지 또는 명령 처리기 중 하나에서 throw된 예외를 catch하지 않을 때마다 이 멤버 함수를 호출합니다.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*전자*<br/>
catch되지 않은 예외에 대한 포인터입니다.

*pMsg*<br/>
프레임워크가 예외를 throw하게 한 Windows 메시지에 대한 정보가 포함된 [MSG](/windows/win32/api/winuser/ns-winuser-msg)트러처입니다.

### <a name="return-value"></a>Return Value

Windows로 반환해야 하는 값입니다. 일반적으로 이것은 창 메시지에 대한 0L, 명령 메시지에 대한 1L (TRUE)입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 직접 호출하지 마십시오.

이 멤버 함수의 기본 구현은 메시지 상자를 만듭니다. catch되지 않은 예외가 메뉴, 도구 모음 또는 가속기 명령 실패로 시작된 경우 메시지 상자에 "Command failed" 메시지가 표시됩니다. 그렇지 않으면 "내부 응용 프로그램 오류" 메시지가 표시 됩니다.

이 멤버 함수를 재정의하여 예외를 전역으로 처리합니다. 메시지 상자를 표시하려는 경우에만 기본 기능을 호출합니다.

## <a name="cwinappregister"></a><a name="register"></a>CWinApp::등록

에서 처리되지 않는 `RegisterShellFileTypes`모든 등록 작업을 수행합니다.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

기본 구현은 TRUE를 반환합니다. 이 함수를 재정의하여 사용자 지정된 등록 단계를 제공합니다.

## <a name="cwinappregistershellfiletypes"></a><a name="registershellfiletypes"></a>CWinApp::레지스터쉘파일타입

이 멤버 함수를 호출하여 응용 프로그램의 모든 문서 유형을 Windows 파일 관리자에 등록합니다.

```cpp
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>매개 변수

*b컴파트 (것)들*<br/>
【인】 TRUE는 셸 명령에 대한 등록 항목을 추가하여 사용자가 셸에서 직접 파일을 인쇄하거나 파일을 프린터 개체로 드래그하여 인쇄할 수 있도록 합니다. 또한 기본 아이콘 키를 추가합니다. 기본적으로 이 매개 변수는 이전 버전과의 호환성을 위해 FALSE입니다.

### <a name="remarks"></a>설명

이렇게 하면 사용자가 파일 관리자 내에서 응용 프로그램에서 만든 데이터 파일을 두 번 클릭하여 열 수 있습니다. 응용 `RegisterShellFileTypes` 프로그램의 각 문서 템플릿에 대해 [AddDocTemplate를](#adddoctemplate) 호출한 후 호출합니다. 또한 호출할 때 [EnableShellOpen](#enableshellopen) `RegisterShellFileTypes`멤버 함수를 호출합니다.

`RegisterShellFileTypes`응용 프로그램이 유지 관리하는 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체 목록을 거치며 각 문서 템플릿에 대해 Windows가 파일 연결을 위해 유지 관리하는 등록 데이터베이스에 항목을 추가합니다. 파일 관리자는 사용자가 데이터 파일을 두 번 클릭할 때 이러한 항목을 사용하여 데이터 파일을 엽니다. 이렇게 하면 을 발송할 필요가 없습니다. 응용 프로그램과 함께 REG 파일.

> [!NOTE]
> `RegisterShellFileTypes`사용자가 관리자 권한으로 프로그램을 실행하는 경우에만 작동합니다. 프로그램에 관리자 권한이 없는 경우 레지스트리 키를 변경할 수 없습니다.

등록 데이터베이스가 이미 지정된 파일 이름 확장명을 다른 파일 형식과 연결하면 새 연결이 만들어지지 않습니다. 이 `CDocTemplate` 정보를 등록하는 데 필요한 문자열 형식은 클래스를 참조하십시오.

## <a name="cwinappregisterwithrestartmanager"></a><a name="registerwithrestartmanager"></a>CWinApp::레지스터위드리스타트매니저

응용 프로그램을 다시 시작 관리자에 등록합니다.

```
virtual HRESULT RegisterWithRestartManager(
    BOOL bRegisterRecoveryCallback,
    const CString& strRestartIdentifier);

virtual HRESULT RegisterWithRestartManager(
    LPCWSTR pwzCommandLineArgs,
    DWORD dwRestartFlags,
    APPLICATION_RECOVERY_CALLBACK pRecoveryCallback,
    LPVOID lpvParam,
    DWORD dwPingInterval,
    DWORD dwCallbackFlags);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*b레지스터리커버콜백*|【인】 TRUE는 응용 프로그램의 이 인스턴스가 복구 콜백 함수를 사용했음을 나타냅니다. FALSE는 그렇지 않음을 나타냅니다. 프레임워크는 응용 프로그램이 예기치 않게 종료될 때 복구 콜백 함수를 호출합니다. 자세한 내용은 [CWinApp:::응용 프로그램 복구호출](#applicationrecoverycallback)을 참조하십시오.|
|*strRestart식별자*|【인】 다시 시작 관리자의 이 인스턴스를 식별하는 고유 문자열입니다. 다시 시작 관리자 식별자는 응용 프로그램의 각 인스턴스에 대해 고유합니다.|
|*pwzCommandLineArgs*|【인】 명령줄에서 추가 인수를 포함 하는 문자열입니다.|
|*dwRestart플래그*|【인】 다시 시작 관리자에 대한 선택적 플래그입니다. 자세한 내용은 주의 섹션을 참조하세요.|
|*p리복구콜백*|【인】 복구 콜백 기능입니다. 이 함수는 LPVOID 매개 변수를 입력으로 가져 와서 DWORD를 반환해야 합니다. 기본 복구 콜백 `CWinApp::ApplicationRecoveryCallback`함수는 .|
|*lpvParam*|【인】 복구 콜백 함수의 입력 매개 변수입니다. 자세한 내용은 [CWinApp:::응용 프로그램 복구호출](#applicationrecoverycallback)을 참조하십시오.|
|*dwPing 간격*|【인】 다시 시작 관리자가 복구 콜백 함수가 반환될 때까지 기다리는 시간입니다. 이 매개 변수는 밀리초 단위입니다.|
|*dwCallbackFlags*|【인】 복구 콜백 함수에 전달된 플래그입니다. 다음에 사용하도록 예약됩니다.|

### <a name="return-value"></a>Return Value

메서드가 성공했는지 S_OK. 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

응용 프로그램에서 파일 자동 저장에 대한 기본 MFC 구현을 `RegisterWithRestartManager`사용하는 경우 의 간단한 버전을 사용해야 합니다. 응용 프로그램의 `RegisterWithRestartManager` 자동 저장 동작을 사용자 지정하려는 경우 복잡한 버전을 사용합니다.

*strRestartIdentifier에*대 한 빈 문자열로이 `RegisterWithRestartManager` 메서드를 호출 하는 경우 다시 시작 관리자의이 인스턴스에 대 한 고유 식별자 문자열을 만듭니다.

응용 프로그램이 예기치 않게 종료되면 다시 시작 관리자는 명령줄에서 응용 프로그램을 다시 시작하고 고유한 다시 시작 식별자를 선택적 인수로 제공합니다. 이 시나리오에서는 프레임 `RegisterWithRestartManager` 워크는 두 번 호출 합니다. 첫 번째 호출은 문자열 식별자에 대한 빈 문자열이 있는 [CWinApp::InitInstance에서](#initinstance) 제공됩니다. 그런 다음 [CWinApp::ProcessShellCommand는](#processshellcommand) 고유한 다시 시작 식별자를 호출합니다. `RegisterWithRestartManager`

다시 시작 관리자에 응용 프로그램을 등록하면 다시 시작 관리자가 응용 프로그램을 모니터링합니다. 응용 프로그램이 예기치 않게 종료되면 다시 시작 관리자는 종료 프로세스 중에 복구 콜백 함수를 호출합니다. 다시 시작 관리자는 복구 콜백 함수의 응답을 위해 *dwPingInterval을* 기다립니다. 이 시간 내에 복구 콜백 함수가 응답하지 않으면 응용 프로그램은 복구 콜백 기능을 실행하지 않고 종료됩니다.

기본적으로 dwRestartFlags는 지원되지 않지만 나중에 사용할 수 있습니다. *dwRestartFlags에* 대 한 가능한 값은 다음과 같습니다.

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

## <a name="cwinappreopenpreviousfilesatrestart"></a><a name="reopenpreviousfilesatrestart"></a>CWinApp::다시 열기이전파일다시 시작

다시 시작 관리자가 응용 프로그램이 예기치 않게 종료될 때 열려 있던 파일을 다시 열지 여부를 결정합니다.

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>Return Value

TRUE는 다시 시작 관리자가 이전에 열려 있는 파일을 다시 연다는 것을 나타냅니다. FALSE는 다시 시작 관리자가 하지 않음을 나타냅니다.

## <a name="cwinapprestartinstance"></a><a name="restartinstance"></a>CWinApp::다시 시작 인스턴스

다시 시작 관리자에 의해 시작 된 응용 프로그램을 다시 시작 처리 합니다.

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>Return Value

TRUE 데이터 복구 처리기가 이전에 열린 문서를 여는 경우; 데이터 복구 처리기에 오류가 있거나 이전에 열려 있는 문서가 없는 경우 FALSE입니다.

### <a name="remarks"></a>설명

다시 시작 관리자가 응용 프로그램을 다시 시작하면 프레임워크에서 이 메서드를 호출합니다. 이 메서드는 데이터 복구 처리기를 검색 하 고 자동 저장 된 파일을 복원 합니다. 이 메서드호출 [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) 사용자가 자동 저장 된 파일을 복원 하려는 여부를 확인 합니다.

이 메서드는 [CDataRecoveryHandler에서](../../mfc/reference/cdatarecoveryhandler-class.md) 열려 있는 문서가 없다고 판단하는 경우 FALSE를 반환합니다. 열려 있는 문서가 없는 경우 응용 프로그램이 일반적으로 시작됩니다.

## <a name="cwinapprestoreautosavedfilesatrestart"></a><a name="restoreautosavedfilesatrestart"></a>CWinApp::복원자동 저장파일다시 시작

다시 시작 관리자가 응용 프로그램을 다시 시작할 때 자동 저장된 파일을 복원하는지 여부를 결정합니다.

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>Return Value

TRUE는 다시 시작 관리자가 자동 저장된 파일을 복원했음을 나타냅니다. FALSE는 다시 시작 관리자가 하지 않음을 나타냅니다.

## <a name="cwinapprun"></a><a name="run"></a>CWinApp :: 실행

기본 메시지 루프를 제공합니다.

```
virtual int Run();
```

### <a name="return-value"></a>Return Value

`WinMain`에서 반환되는 **int** 값입니다.

### <a name="remarks"></a>설명

`Run`응용 프로그램이 WM_QUIT 메시지를 받을 때까지 Windows 메시지를 획득하고 디스패치합니다. 응용 프로그램의 메시지 큐에 현재 메시지가 `Run` 없는 경우 [OnIdle을](#onidle) 호출하여 유휴 시간 처리를 수행합니다. 들어오는 메시지는 특수 처리를 위해 [PreTranslateMessage](#pretranslatemessage) 멤버 함수로 이동한 다음 표준 키보드 번역을 위한 Windows 함수로 `TranslateMessage` 이동합니다. 마지막으로 Windows `DispatchMessage` 함수가 호출됩니다.

`Run`재정의된 경우는 거의 없지만 특수 한 동작을 제공하기 위해 재정의할 수 있습니다.

## <a name="cwinapprunautomated"></a><a name="runautomated"></a>CWinApp::실행 자동화

이 함수를 호출하여 클라이언트 응용 프로그램에서 서버 응용 프로그램이 시작되었는지 여부를 나타내는 **"/Automation"** 또는 **"자동화"** 옵션이 있는지 확인합니다.

```
BOOL RunAutomated();
```

### <a name="return-value"></a>Return Value

옵션이 발견되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

있는 경우 명령줄에서 옵션이 제거됩니다. OLE 자동화에 대한 자세한 내용은 [자동화 서버](../../mfc/automation-servers.md)문서를 참조하십시오.

## <a name="cwinapprunembedded"></a><a name="runembedded"></a>CWinApp:::실행 임베디드

이 함수를 호출하여 **"/포함"** 또는 **"-포함"** 옵션이 있는지 여부를 확인합니다.

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>Return Value

옵션이 발견되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

있는 경우 명령줄에서 옵션이 제거됩니다. 포함에 대한 자세한 내용은 [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)문서를 참조하십시오.

## <a name="cwinappsaveallmodified"></a><a name="saveallmodified"></a>CWinApp:::SaveAll수정

응용 프로그램의 주 프레임 창을 닫을 때 또는 WM_QUERYENDSESSION 메시지를 통해 모든 문서를 저장 하기 위해 프레임 워크에 의해 호출 됩니다.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Return Value

응용 프로그램을 종료하는 것이 안전한 경우 비제로; 0이 안전하지 않은 경우 응용 프로그램을 종료합니다.

### <a name="remarks"></a>설명

이 멤버 함수의 기본 구현은 응용 프로그램 내의 모든 수정된 문서에 대해 [CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified) 멤버 함수를 차례로 호출합니다.

## <a name="cwinappselectprinter"></a><a name="selectprinter"></a>CWinApp::선택 프린터

이 멤버 함수를 호출하여 특정 프린터를 선택하고 인쇄 대화 상자에서 이전에 선택한 프린터를 놓습니다.

```cpp
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>매개 변수

*h데브 네임스*<br/>
특정 프린터의 드라이버, 장치 및 출력 포트 이름을 식별하는 [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)트러크에 대한 핸들입니다.

*h데브 모드*<br/>
프린터의 장치 초기화 및 환경에 대한 정보를 지정하는 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 구조에 대한 핸들입니다.

*b프리올드*<br/>
이전에 선택한 프린터를 해제합니다.

### <a name="remarks"></a>설명

*hDevMode* 및 *hDevNames가* 모두 `SelectPrinter` NULL인 경우 현재 기본 프린터를 사용합니다.

## <a name="cwinappsethelpmode"></a><a name="sethelpmode"></a>CWinApp:::세트헬프 모드

응용 프로그램의 도움말 유형을 설정합니다.

```cpp
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>매개 변수

*e도움말 유형*<br/>
사용할 도움말 유형을 지정합니다. 자세한 내용은 [CWinApp:m_eHelpType](#m_ehelptype) 를 참조하십시오.

### <a name="remarks"></a>설명

응용 프로그램의 도움말 유형을 설정합니다.

응용 프로그램의 도움말 유형을 HTML도움말로 설정하려면 [EnableHTMLHelp](#enablehtmlhelp)를 호출할 수 있습니다. 호출하면 `EnableHTMLHelp`응용 프로그램에서 HTML도움말을 도움말 응용 프로그램으로 사용해야 합니다. WinHelp를 사용하도록 변경하려면 `SetHelpMode` *eHelpType을* `afxWinHelp`로 호출하고 설정할 수 있습니다.

## <a name="cwinappsetregistrykey"></a><a name="setregistrykey"></a>CWinApp:::세트레지스트리키

응용 프로그램 설정을 INI 파일 대신 레지스트리에 저장합니다.

```cpp
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>매개 변수

*lpsz레지스트리키*<br/>
키 의 이름을 포함하는 문자열에 대한 포인터입니다.

*니디레지스트리키*<br/>
레지스트리 키의 이름을 포함하는 문자열 리소스의 ID입니다.

### <a name="remarks"></a>설명

이 함수는 *m_pszRegistryKey*을 `GetProfileInt`설정합니다. `GetProfileString` `WriteProfileInt` `WriteProfileString` `CWinApp` 이 함수가 호출된 경우 가장 최근에 사용한(MRU) 파일 목록도 레지스트리에 저장됩니다. 레지스트리 키는 일반적으로 회사의 이름입니다. \\ HKEY_CURRENT_USER\Software<회사 이름\> \\<응용\> \\ 프로그램 이름<섹션 이름\> \\<\>값 이름의 키에 저장됩니다.

## <a name="cwinappsupportsapplicationrecovery"></a><a name="supportsapplicationrecovery"></a>CWinApp::지원응용 프로그램 복구

다시 시작 관리자가 예기치 않게 종료된 응용 프로그램을 복구하는지 여부를 결정합니다.

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>Return Value

TRUE는 다시 시작 관리자가 응용 프로그램을 복구했음을 나타냅니다. FALSE는 다시 시작 관리자가 하지 않음을 나타냅니다.

## <a name="cwinappsupportsautosaveatinterval"></a><a name="supportsautosaveatinterval"></a>CWinApp::지원자동 저장간격

다시 시작 관리자가 정기적으로 열려 있는 문서를 자동으로 저장하는지 여부를 결정합니다.

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>Return Value

TRUE는 다시 시작 관리자가 열려 있는 문서를 자동으로 저장했음을 나타냅니다. FALSE는 다시 시작 관리자가 하지 않음을 나타냅니다.

## <a name="cwinappsupportsautosaveatrestart"></a><a name="supportsautosaveatrestart"></a>CWinApp::지원자동 저장다시 시작

다시 시작 관리자가 응용 프로그램을 다시 시작할 때 열려 있는 문서를 자동으로 저장하는지 여부를 결정합니다.

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>Return Value

TRUE는 응용 프로그램이 다시 시작될 때 다시 시작 관리자가 열려 있는 문서를 자동으로 저장했음을 나타냅니다. FALSE는 다시 시작 관리자가 하지 않음을 나타냅니다.

## <a name="cwinappsupportsrestartmanager"></a><a name="supportsrestartmanager"></a>CWinApp::지원 다시 시작 관리자

응용 프로그램이 다시 시작 관리자를 지원하는지 여부를 결정합니다.

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>Return Value

TRUE는 응용 프로그램이 다시 시작 관리자를 지원했음을 나타냅니다. FALSE는 응용 프로그램이 그렇지 않음을 나타냅니다.

## <a name="cwinappunregister"></a><a name="unregister"></a>CWinApp::등록 취소

응용 프로그램 개체에 의해 등록된 모든 파일등록을 취소합니다.

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

이 `Unregister` 함수는 응용 프로그램 개체및 등록 함수에 의해 수행되는 [등록을](#register) 취소합니다. 일반적으로 두 함수는 MFC에서 암시적으로 호출되므로 코드에 나타나지 않습니다.

이 함수를 재정의하여 사용자 지정 등록 취소 단계를 수행합니다.

## <a name="cwinappunregistershellfiletypes"></a><a name="unregistershellfiletypes"></a>CWinApp::레지스터 쉘파일 형식

이 멤버 함수를 호출하여 Windows 파일 관리자를 사용하여 응용 프로그램의 모든 문서 유형을 등록 취소합니다.

```cpp
void UnregisterShellFileTypes();
```

## <a name="cwinappwinhelp"></a><a name="winhelp"></a>CWinApp:::윈헬프

WinHelp 응용 프로그램을 호출 하려면이 멤버 함수를 호출 합니다.

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>매개 변수

*dwData*<br/>
추가 데이터를 지정합니다. 사용되는 값은 *nCmd* 매개 변수의 값에 따라 다릅니다.

*nCmd*<br/>
요청한 도움말의 형식을 지정합니다. 가능한 값 목록과 *dwData* 매개 변수에 미치는 영향은 [WinHelp](/windows/win32/api/winuser/nf-winuser-winhelpw) Windows 함수를 참조하십시오.

### <a name="remarks"></a>설명

또한 프레임워크는 이 함수를 호출하여 WinHelp 응용 프로그램을 호출합니다.

응용 프로그램이 종료되면 프레임워크가 WinHelp 응용 프로그램을 자동으로 닫습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

## <a name="cwinappwriteprofilebinary"></a><a name="writeprofilebinary"></a>CWinApp::쓰기 프로필 바이너리

이 멤버 함수를 호출하여 이진 데이터를 응용 프로그램 레지스트리 또는 의 지정된 섹션에 작성합니다. INI 파일입니다.

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다. 단면이 없으면 만들어집니다. 섹션의 이름은 대/소문자 독립적입니다. 문자열은 대문자와 소문자의 조합일 수 있습니다.

*lpsz항목*<br/>
값을 쓸 항목을 포함하는 null 종료 된 문자열을 가리킵니다. 지정된 섹션에 항목이 없으면 항목이 만들어집니다.

*Pdata*<br/>
기록할 데이터를 가리킵니다.

*n바이트*<br/>
쓸 바이트 수를 포함합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

이 예제에서는 MFC 응용 프로그램의 모든 함수에서 `WriteProfileBinary` 사용할 `GetProfileBinary` 수 있는 방법을 설명하는 CWinApp 클래스를 사용하는 데 사용합니다. `CWinApp* pApp = AfxGetApp();`

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

또 다른 예는 [CWinApp::GetProfileBinary](#getprofilebinary)에 대한 예제를 참조하십시오.

## <a name="cwinappwriteprofileint"></a><a name="writeprofileint"></a>CWinApp::쓰기 프로필인트

이 멤버 함수를 호출하여 지정된 값을 응용 프로그램 레지스트리 또는 의 지정된 섹션에 작성합니다. INI 파일입니다.

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다. 단면이 없으면 만들어집니다. 섹션의 이름은 대/소문자 독립적입니다. 문자열은 대문자와 소문자의 조합일 수 있습니다.

*lpsz항목*<br/>
값을 쓸 항목을 포함하는 null 종료 된 문자열을 가리킵니다. 지정된 섹션에 항목이 없으면 항목이 만들어집니다.

*n값*<br/>
쓸 값을 포함합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

이 `CWinApp* pApp = AfxGetApp();` 예제에서는 CWinApp 클래스에서 MFC 응용 `WriteProfileString`프로그램의 `WriteProfileInt` `GetProfileString`모든 `GetProfileInt` 함수에서 사용할 수 있는 방법을 예제로 사용합니다.

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

또 다른 예는 [CWinApp::GetProfileInt](#getprofileint)에 대한 예제를 참조하십시오.

## <a name="cwinappwriteprofilestring"></a><a name="writeprofilestring"></a>CWinApp::쓰기 프로필 스트링

이 멤버 함수를 호출하여 지정된 문자열을 응용 프로그램 레지스트리 또는 의 지정된 섹션에 작성합니다. INI 파일입니다.

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다. 단면이 없으면 만들어집니다. 섹션의 이름은 대/소문자 독립적입니다. 문자열은 대문자와 소문자의 조합일 수 있습니다.

*lpsz항목*<br/>
값을 쓸 항목을 포함하는 null 종료 된 문자열을 가리킵니다. 지정된 섹션에 항목이 없으면 항목이 만들어집니다. 이 매개 변수가 NULL이면 *lpszSection에서* 지정한 섹션이 삭제됩니다.

*lpsz값*<br/>
쓸 문자열을 가리킵니다. 이 매개 변수가 NULL이면 *lpszEntry* 매개 변수에서 지정한 항목이 삭제됩니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

또 다른 예는 [CWinApp::GetProfileInt](#getprofileint)에 대한 예제를 참조하십시오.

## <a name="cwinappsetappid"></a><a name="setappid"></a>CWinApp ::SetAppID

응용 프로그램에 대한 응용 프로그램 사용자 모델 ID를 명시적으로 설정합니다. 이 메서드는 사용자에게 사용자 인터페이스가 표시되기 전에 호출해야 합니다(가장 좋은 장소는 응용 프로그램 생성자).

```cpp
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>매개 변수

*lpcszAppID*<br/>
응용 프로그램 사용자 모델 ID를 지정합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[CWinThread 클래스](../../mfc/reference/cwinthread-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)
