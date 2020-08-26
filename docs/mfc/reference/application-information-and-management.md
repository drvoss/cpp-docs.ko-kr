---
title: 애플리케이션 정보 및 관리
description: MFC (Microsoft Foundation Class library) 응용 프로그램 정보 및 관리 함수에 대 한 참조입니다.
ms.date: 01/27/2020
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: 3412ed3f02e93d3e8c947d4f730355c219493a77
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832309"
---
# <a name="application-information-and-management"></a>애플리케이션 정보 및 관리

응용 프로그램을 작성 하는 경우 단일 [CWinApp](../../mfc/reference/cwinapp-class.md)파생 개체를 만듭니다. 때때로 파생 개체 외부에서이 개체에 대 한 정보를 가져올 수 있습니다 `CWinApp` . 또는 다른 전역 "관리자" 개체에 대 한 액세스 권한이 필요할 수 있습니다.

MFC 라이브러리는 이러한 작업을 수행 하는 데 도움이 되는 다음과 같은 전역 함수를 제공 합니다.

## <a name="application-information-and-management-functions"></a>응용 프로그램 정보 및 관리 기능

| Name | 설명 |
|-|-|
|[AfxBeginThread](#afxbeginthread)|새 스레드를 만듭니다.|
|[AfxContextMenuManager](#afxcontextmenumanager)|전역 [상황에 맞는 메뉴 관리자](ccontextmenumanager-class.md)에 대 한 포인터입니다.|
|[AfxEndThread](#afxendthread)|현재 스레드를 종료 합니다.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|리소스 체인을 안내 하 고 리소스 ID 및 리소스 유형별로 특정 리소스를 찾습니다. |
|[AfxFreeLibrary](#afxfreelibrary)|로드 된 DLL (동적 연결 라이브러리) 모듈의 참조 횟수를 감소 시킵니다. 참조 횟수가 0에 도달 하면 모듈은 매핑되지 않습니다.|
|[AfxGetApp](#afxgetapp)|응용 프로그램의 단일 개체에 대 한 포인터를 반환 합니다 `CWinApp` .|
|[AfxGetAppName](#afxgetappname)|응용 프로그램의 이름을 포함 하는 문자열을 반환 합니다.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|응용 프로그램의이 인스턴스를 나타내는 HINSTANCE를 반환 합니다.|
|[AfxGetMainWnd](#afxgetmainwnd)|비 OLE 응용 프로그램의 현재 "주" 창이 나 서버 응용 프로그램의 내부 프레임 창에 대 한 포인터를 반환 합니다.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|이 함수를 사용 하 여 응용 프로그램이 레지스트리 액세스를 **HKEY_CURRENT_USER** (**HKCU**) 노드로 리디렉션하는 지 여부를 확인 합니다.|
|[AfxGetResourceHandle](#afxgetresourcehandle)|응용 프로그램의 기본 리소스의 원본에 대 한 HINSTANCE를 반환 합니다. 를 사용 하 여 응용 프로그램의 리소스에 직접 액세스 합니다.|
|[AfxGetThread](#afxgetthread)|현재 [CWinThread](../../mfc/reference/cwinthread-class.md) 개체에 대 한 포인터를 검색 합니다.|
|[AfxInitRichEdit](#afxinitrichedit)|응용 프로그램에 대 한 버전 1.0 rich edit 컨트롤을 초기화 합니다.|
|[AfxInitRichEdit2](#afxinitrichedit2)|응용 프로그램에 대 한 버전 2.0 이상 rich edit 컨트롤을 초기화 합니다.|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|지정된 창이 확장된 프레임 개체인지 여부를 확인합니다.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|지정 된 창이 toolbar 개체 인지 여부를 확인 합니다.|
|[AfxKeyboardManager](#afxkeyboardmanager)|전역 [키보드 관리자](ckeyboardmanager-class.md)에 대 한 포인터입니다.|
|[AfxLoadLibrary](#afxloadlibrary)|DLL 모듈을 매핑하고 DLL 함수의 주소를 가져오는 데 사용할 수 있는 핸들을 반환 합니다.|
|[AfxLoadLibraryEx](#afxloadlibraryex)|지정 된 옵션을 사용 하 여 DLL 모듈을 매핑하고 DLL 함수의 주소를 가져오는 데 사용할 수 있는 핸들을 반환 합니다.|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|전역 [분리 메뉴 관리자](cmenutearoffmanager-class.md)에 대 한 포인터입니다.|
|[AfxMouseManager](#afxmousemanager)|전역 [마우스 관리자](cmousemanager-class.md)에 대 한 포인터입니다.|
|[AfxRegisterClass](#afxregisterclass)|MFC를 사용 하는 DLL에 창 클래스를 등록 합니다.|
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC에서 자동으로 등록 된 클래스를 보완 하기 위해 Windows 창 클래스를 등록 합니다.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|응용 프로그램이 레지스트리 액세스를 **HKEY_CURRENT_USER** (**HKCU**) 노드로 리디렉션하는 지 여부를 설정 합니다.|
|[AfxSetResourceHandle](#afxsetresourcehandle)|응용 프로그램의 기본 리소스가 로드 되는 HINSTANCE 핸들을 설정 합니다.|
|[AfxShellManager](#afxshellmanager)|전역 [셸 관리자](cshellmanager-class.md)에 대 한 포인터입니다. |
|[AfxSocketInit](#afxsocketinit)|`CWinApp::InitInstance`Windows 소켓을 초기화 하기 위해 재정의에서 호출 됩니다.|
|[AfxUserToolsManager](#afxusertoolsmanager)|전역 [사용자 도구 관리자](cusertoolsmanager-class.md)에 대 한 포인터입니다.|
|[AfxWinInit](#afxwininit)|Mfc 제공 `WinMain` 함수에서 GUI 기반 응용 프로그램의 [CWinApp](../../mfc/reference/cwinapp-class.md) 초기화의 일부로 호출 되어 mfc를 초기화 합니다. 는 MFC를 사용 하는 콘솔 응용 프로그램에 대해 직접 호출 해야 합니다.|

## <a name="afxbeginthread"></a><a name="afxbeginthread"></a> AfxBeginThread

이 함수를 호출 하 여 새 스레드를 만듭니다.

```cpp
CWinThread* AfxBeginThread(
    AFX_THREADPROC pfnThreadProc,
    LPVOID pParam,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);

CWinThread* AfxBeginThread(
    CRuntimeClass* pThreadClass,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>매개 변수

*pfnThreadProc*\
작업자 스레드의 제어 함수를 가리킵니다. 포인터는 NULL 일 수 없습니다. 이 함수는 다음과 같이 선언 해야 합니다.

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*\
[CWinThread](../../mfc/reference/cwinthread-class.md)에서 파생 된 개체의 RUNTIME_CLASS입니다.

*pParam*\
제어 함수에 전달할 매개 변수입니다.

*n 우선 순위*\
스레드에 대해 설정할 우선 순위입니다. 사용 가능한 우선 순위에 대 한 전체 목록과 설명은 Windows SDK의 [Setthreadpriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 를 참조 하십시오.

*nStackSize*\
새 스레드에 대 한 스택의 크기 (바이트)를 지정 합니다. 0 인 경우 스택 크기는 생성 스레드와 동일한 크기의 스택으로 기본 설정 됩니다.

*dwCreateFlags*\
스레드의 생성을 제어 하는 추가 플래그를 지정 합니다. 이 플래그는 다음 두 값 중 하나를 포함할 수 있습니다.

- 일시 중단 횟수가 1 인 스레드를 시작 CREATE_SUSPENDED 합니다. `CWinThread`스레드의 실행을 시작 하기 전에 [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) 또는 파생 클래스의 멤버와 같은 개체의 멤버 데이터를 초기화 하려면 CREATE_SUSPENDED를 사용 합니다. 초기화가 완료 되 면 [CWinThread:: ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) 를 사용 하 여 실행 스레드를 시작 합니다. 스레드는가 호출 될 때까지 실행 되지 않습니다 `CWinThread::ResumeThread` .

- **0** 생성 후 즉시 스레드를 시작 합니다.

*lpSecurityAttrs*\
스레드에 대 한 보안 특성을 지정 하는 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 구조체를 가리킵니다. NULL 인 경우에는 만들기 스레드와 동일한 보안 특성이 사용 됩니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

### <a name="return-value"></a>반환 값

새로 만든 스레드 개체에 대 한 포인터 이거나, 오류가 발생 하는 경우 NULL입니다.

### <a name="remarks"></a>설명

의 첫 번째 형태는 `AfxBeginThread` 작업자 스레드를 만듭니다. 두 번째 폼은 사용자 인터페이스 스레드 또는 작업자 스레드로 작동할 수 있는 스레드를 만듭니다.

`AfxBeginThread` 새 개체를 만들고 `CWinThread` [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) 함수를 호출 하 여 스레드 실행을 시작 하 고 스레드에 대 한 포인터를 반환 합니다. 모든 개체를 생성 하는 데 실패 하는 경우 모든 개체의 할당이 제대로 취소 되는지 확인 하기 위해 전체 절차를 수행 합니다. 스레드를 종료 하려면 스레드 내에서 [AfxEndThread](#afxendthread) 를 호출 하거나 작업자 스레드의 제어 함수에서를 반환 합니다.

다중 스레딩을 응용 프로그램에서 사용 하도록 설정 해야 합니다. 그렇지 않으면이 함수는 실패 합니다. 다중 스레딩을 사용 하는 방법에 대 한 자세한 내용은 [/md,/mt,/LD (런타임 라이브러리 사용)](../../build/reference/md-mt-ld-use-run-time-library.md)를 참조 하세요.

에 대 한 자세한 내용은 `AfxBeginThread` [다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md) 및 [다중 스레딩: 사용자 인터페이스 스레드 만들기](../../parallel/multithreading-creating-user-interface-threads.md)문서를 참조 하세요.

### <a name="example"></a>예제

[CSocket:: Attach](../../mfc/reference/csocket-class.md#attach)의 예제를 참조 하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxcontextmenumanager"></a><a name="afxcontextmenumanager"></a> AfxContextMenuManager

전역 [상황에 맞는 메뉴 관리자](ccontextmenumanager-class.md)에 대 한 포인터입니다.

### <a name="syntax"></a>구문

```cpp
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxcontextmenumanager

## <a name="afxendthread"></a><a name="afxendthread"></a> AfxEndThread

현재 실행 중인 스레드를 종료 하려면이 함수를 호출 합니다.

```cpp
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>매개 변수

*nExitCode*\
스레드의 종료 코드를 지정 합니다.

*bDelete*\
메모리에서 스레드 개체를 삭제 합니다.

### <a name="remarks"></a>설명

종료 될 스레드 내에서를 호출 해야 합니다.

에 대 한 자세한 내용은 `AfxEndThread` [다중 스레딩: 스레드 종료](../../parallel/multithreading-terminating-threads.md)문서를 참조 하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxfindresourcehandle"></a><a name="afxfindresourcehandle"></a> AfxFindResourceHandle

를 사용 하 여 리소스 `AfxFindResourceHandle` 체인을 탐색 하 고 리소스 ID 및 리소스 유형별로 특정 리소스를 찾습니다.

### <a name="syntax"></a>구문

```cpp
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>매개 변수

*lpszName*\
리소스 ID를 포함 하는 문자열에 대 한 포인터입니다.
*lpszType*\
리소스 형식에 대 한 포인터입니다. 리소스 종류 목록은 Windows SDK의 [Findresource](/windows/win32/api/winbase/nf-winbase-findresourcea) 를 참조 하세요.

### <a name="return-value"></a>반환 값

리소스를 포함 하는 모듈에 대 한 핸들입니다.

### <a name="remarks"></a>설명

`AfxFindResourceHandle` 특정 리소스를 찾고 리소스를 포함 하는 모듈에 대 한 핸들을 반환 합니다. 리소스는 로드 된 모든 MFC 확장명 DLL에 있을 수 있습니다. `AfxFindResourceHandle` 리소스를 포함 하는 항목을 알려 줍니다.

모듈은 다음과 같은 순서로 검색 됩니다.

1. MFC 확장 DLL 인 경우 주 모듈입니다.

1. 비시스템 모듈.

1. 언어별 모듈.

1. 시스템 DLL 인 경우 주 모듈입니다.

1. 시스템 모듈.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="afxfreelibrary"></a><a name="afxfreelibrary"></a> AfxFreeLibrary

`AfxFreeLibrary` 및 `AfxLoadLibrary`는 각 코딩된 라이브러리 모듈에 대한 참조 횟수를 유지 관리합니다.

```cpp
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>매개 변수

*Hin Lib*\
로드된 라이브러리 모듈의 핸들입니다. [AfxLoadLibrary](#afxloadlibrary) 는이 핸들을 반환 합니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 TRUE이고 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

`AfxFreeLibrary`는 로드된 DLL(동적 연결 라이브러리) 모듈의 참조 횟수를 감소시킵니다. 참조 횟수가 0에 도달하면, 호출 프로세스의 주소 공간에서 모듈이 매핑 해제되고 핸들이 더 이상 유효하지 않습니다. 이 참조 카운트는 `AfxLoadLibrary`가 호출될 때마다 매번 증가합니다.

라이브러리 모듈을 매핑 해제하기 전에 시스템은 DLL이 이를 사용하는 프로세스에서 분리할 수 있게 해줍니다. 이렇게 하면 DLL에 현재 프로세스에 할당 된 리소스를 정리할 수 있는 기회가 제공 됩니다. 진입점 함수가 반환된 다음 라이브러리 모듈은 현재 프로세스의 주소 공간에서 제거됩니다.

`AfxLoadLibrary`를 사용해서 DLL 모듈을 매핑합니다.

`AfxFreeLibrary` `AfxLoadLibrary` `FreeLibrary` 응용 프로그램에서 여러 스레드를 사용 하는 경우 및 (Win32 함수 대신)를 사용 해야 `LoadLibrary` 합니다. `AfxLoadLibrary`및를 사용 하면 `AfxFreeLibrary` MFC 확장 DLL을 로드 하 고 언로드할 때 실행 되는 시작 및 종료 코드가 전역 mfc 상태를 손상 하지 않습니다.

### <a name="example"></a>예제

[AfxLoadLibrary](#afxloadlibrary)의 예제를 참조 하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdll_ .h

## <a name="afxgetapp"></a><a name="afxgetapp"></a> AfxGetApp

이 함수에서 반환 된 포인터를 사용 하 여 기본 메시지 디스패치 코드 또는 맨 위 창과 같은 응용 프로그램 정보에 액세스할 수 있습니다.

```cpp
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>반환 값

`CWinApp`응용 프로그램의 단일 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드가 NULL을 반환 하는 경우 응용 프로그램 주 창이 아직 완전히 초기화 되지 않았음을 나타낼 수 있습니다. 문제를 나타낼 수도 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxgetappname"></a><a name="afxgetappname"></a> AfxGetAppName

반환 된 문자열은 진단 메시지에 사용할 수도 있고 임시 문자열 이름의 루트로 사용할 수도 있습니다.

```cpp
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>반환 값

응용 프로그램의 이름을 포함 하는 null로 끝나는 문자열입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a> AfxGetInstanceHandle

이 함수를 사용 하면 현재 응용 프로그램의 인스턴스 핸들을 검색할 수 있습니다.

```cpp
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>반환 값

응용 프로그램의 현재 인스턴스에 대 한 HINSTANCE입니다. USRDLL 버전의 MFC와 연결 된 DLL 내에서 호출 되는 경우 해당 DLL에 대 한 HINSTANCE가 반환 됩니다.

### <a name="remarks"></a>설명

`AfxGetInstanceHandle` 항상 실행 파일 ()의 HINSTANCE를 반환 합니다. EXE)를 사용 하는 경우를 제외 하 고 USRDLL 버전의 MFC로 연결 된 DLL에서 호출 되지 않습니다. 이 경우 HINSTANCE를 DLL로 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxgetmainwnd"></a><a name="afxgetmainwnd"></a> AfxGetMainWnd

응용 프로그램이 OLE 서버인 경우이 함수를 호출 하 여 응용 프로그램의 활성 주 창에 대 한 포인터를 검색 합니다. 응용 프로그램 개체의 [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) 멤버를 직접 참조 하는 대신이 결과를 사용 합니다.

```cpp
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>반환 값

서버에 활성 컨테이너 내부에서 활성화 된 개체가 있는 경우 내부 활성 문서를 포함 하는 프레임 창 개체에 대 한 포인터를 반환 합니다.

컨테이너 내에서 활성 상태인 개체가 없거나 응용 프로그램이 OLE 서버가 아닌 경우이 함수는 응용 프로그램 개체의 *m_pMainWnd* 을 반환 합니다.

애플리케이션의 기본 스레드에서 `AfxGetMainWnd`가 호출되는 경우 위의 규칙에 따라 애플리케이션의 주 창이 반환됩니다. 함수가 애플리케이션의 보조 스레드에서 호출되면 함수는 호출한 스레드에 연결된 주 창을 반환합니다.

### <a name="remarks"></a>설명

응용 프로그램이 OLE 서버가 아닌 경우이 함수를 호출 하는 것은 응용 프로그램 개체의 *m_pMainWnd* 멤버를 직접 참조 하는 것과 같습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a> AfxGetPerUserRegistration

이 함수를 사용 하 여 응용 프로그램이 레지스트리 액세스를 **HKEY_CURRENT_USER** (**HKCU**) 노드로 리디렉션하는 지 여부를 확인 합니다.

```cpp
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>반환 값

TRUE는 레지스트리 정보가 HKCU 노드에 전달 됨을 나타냅니다. FALSE는 응용 프로그램이 레지스트리 정보를 기본 노드에 쓰도록 지정 합니다. 기본 노드는 **HKEY_CLASSES_ROOT** (**HKCR**)입니다.

### <a name="remarks"></a>설명

레지스트리 리디렉션을 사용 하도록 설정 하는 경우 프레임 워크는 **HKCR** 에서 **HKEY_CURRENT_USER \\C\\cc\c\\c\c\** MFC 및 ATL 프레임 워크도 리디렉션의 영향을 받습니다.

응용 프로그램이 레지스트리 액세스를 리디렉션하는 지 여부를 변경 하려면 [AfxSetPerUserRegistration](#afxsetperuserregistration)를 사용 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxstat_ .h

## <a name="afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a> AfxGetResourceHandle

이 함수에서 반환 하는 HINSTANCE 핸들을 사용 하 여 응용 프로그램의 리소스 (예: Windows 함수 호출)에 직접 액세스 합니다 `FindResource` .

```cpp
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>반환 값

응용 프로그램의 기본 리소스가 로드 되는 HINSTANCE 핸들입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxgetthread"></a><a name="afxgetthread"></a> AfxGetThread

현재 실행 중인 스레드를 나타내는 [CWinThread](../../mfc/reference/cwinthread-class.md) 개체에 대 한 포인터를 가져오려면이 함수를 호출 합니다.

```cpp
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>반환 값

현재 실행 중인 스레드에 대 한 포인터입니다. 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

는 스레드 내에서 호출 해야 합니다.

> [!NOTE]
> `AfxGetThread`Visual C++ 버전 4.2, 5.0 또는 6.0에서 호출 하는 MFC 프로젝트를 이식 하는 경우 `AfxGetThread` 스레드가 없으면 [AfxGetApp](#afxgetapp) 를 호출 합니다. 최신 버전의 컴파일러에서는 `AfxGetThread` 스레드를 찾을 수 없는 경우 NULL을 반환 합니다. 응용 프로그램 스레드를 원하는 경우을 호출 해야 `AfxGetApp` 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxinitrichedit"></a><a name="afxinitrichedit"></a> AfxInitRichEdit

응용 프로그램에 대 한 rich edit 컨트롤 (버전 1.0)을 초기화 하려면이 함수를 호출 합니다.

```cpp
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>설명

이 함수는 이전 버전과의 호환성을 위해 제공 됩니다. 새 응용 프로그램은 [AfxInitRichEdit2](#afxinitrichedit2)를 사용 해야 합니다.

`AfxInitRichEdit` rich edit 컨트롤의 1.0 버전을 초기화 하 RICHED32.DLL를 로드 합니다. Rich edit 컨트롤의 버전 2.0 및 3.0을 사용 하려면 RICHED20.DLL를 로드 해야 합니다. [AfxInitRichEdit2](#afxinitrichedit2)을 호출 하 여 로드 됩니다.

기존 Visual C++ 응용 프로그램의 rich edit 컨트롤을 버전 2.0으로 업데이트 하려면를 엽니다. RC 파일 텍스트, 각 서식 있는 편집 컨트롤의 클래스 이름을 "RICHEDIT"에서 "RichEdit20a"로 변경 합니다. 그런 다음 호출을로 `AfxInitRichEdit` 바꿉니다 `AfxInitRichEdit2` .

이 함수는 라이브러리가 프로세스에 대해 아직 초기화 되지 않은 경우에도 공용 컨트롤 라이브러리를 초기화 합니다. MFC 응용 프로그램에서 직접 rich edit 컨트롤을 사용 하는 경우이 함수를 호출 하 여 MFC가 rich edit 컨트롤 런타임을 올바르게 초기화 했는지를 확인할 수 있습니다. `Create` [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md)또는 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)의 메서드를 호출 하는 경우 일반적으로이 함수를 호출할 필요가 없지만 경우에 따라 필요할 수 있습니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxinitrichedit2"></a><a name="afxinitrichedit2"></a> AfxInitRichEdit2

응용 프로그램에 대 한 rich edit 컨트롤 (버전 2.0 이상)을 초기화 하려면이 함수를 호출 합니다.

```cpp
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>설명

RICHED20.DLL를 로드 하 고 rich edit 컨트롤의 2.0 버전을 초기화 하려면이 함수를 호출 합니다. `Create` [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md)또는 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)의 메서드를 호출 하는 경우 일반적으로이 함수를 호출할 필요가 없지만 경우에 따라 필요할 수 있습니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxisextendedframeclass"></a><a name="afxisextendedframeclass"></a> AfxIsExtendedFrameClass

지정된 창이 확장된 프레임 개체인지 여부를 확인합니다.

### <a name="syntax"></a>구문

```cpp
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>매개 변수

*pWnd*\
진행 에서 파생 된 개체에 대 한 포인터 `CWnd` 입니다.

### <a name="return-value"></a>반환 값

제공 된 창이 확장 된 프레임 개체 이면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

*PWnd* 가 다음 클래스 중 하나에서 파생 되는 경우이 메서드는 TRUE를 반환 합니다.

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

이 메서드는 함수 또는 메서드 매개 변수가 확장된 프레임 창인지 확인해야 하는 경우에 유용합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxismfctoolbar"></a><a name="afxismfctoolbar"></a> AfxIsMFCToolBar

지정 된 창이 toolbar 개체 인지 여부를 확인 합니다.

### <a name="syntax"></a>구문

```cpp
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*\
진행 에서 파생 된 개체에 대 한 포인터 `CWnd` 입니다.

### <a name="return-value"></a>반환 값

제공 된 창이 도구 모음 개체 이면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

`TRUE` *PWnd* 가에서 파생 되는 경우이 메서드는를 반환 `CMFCToolBar` 합니다. 이 메서드는 함수 또는 메서드 매개 변수가 개체 인지 확인 해야 하는 경우에 유용 `CMFCToolBar` 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxkeyboardmanager"></a><a name="afxkeyboardmanager"></a> AfxKeyboardManager

전역 [키보드 관리자](ckeyboardmanager-class.md)에 대 한 포인터입니다.

### <a name="syntax"></a>구문

```cpp
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxkeyboardmanager

## <a name="afxloadlibrary"></a><a name="afxloadlibrary"></a> AfxLoadLibrary

`AfxLoadLibrary`를 사용해서 DLL 모듈을 매핑합니다.

```cpp
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>매개 변수

*lpszModuleName*\
은 (는) 모듈의 이름을 포함 하는 null로 끝나는 문자열을 가리킵니다. DLL 또는. EXE 파일). 지정 된 이름은 모듈의 파일 이름입니다.

문자열이 경로를 지정 하지만 파일이 지정 된 디렉터리에 없으면 함수가 실패 합니다.

경로를 지정 하지 않고 파일 이름 확장명을 생략 하면 기본 확장명이 지정 됩니다. DLL이 추가 됩니다. 그러나 파일 이름 문자열에는 모듈 이름에 확장명이 없음을 나타내는 후행 점 문자 (.)가 포함 될 수 있습니다. 경로를 지정 하지 않으면 함수는 [데스크톱 응용 프로그램의 검색 순서](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)를 사용 합니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 반환 값은 모듈에 대 한 핸들입니다. 오류가 발생 하면 반환 값은 NULL입니다.

### <a name="remarks"></a>설명

이 클래스는 [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) 에서 DLL 함수의 주소를 가져오는 데 사용할 수 있는 핸들을 반환 합니다. `AfxLoadLibrary` 를 사용 하 여 다른 실행 모듈을 매핑할 수도 있습니다.

각 프로세스는 로드 된 각 라이브러리 모듈에 대 한 참조 횟수를 유지 관리 합니다. 이 참조 횟수는가 호출 될 때마다 증가 `AfxLoadLibrary` 하 고가 호출 될 때마다 감소 `AfxFreeLibrary` 합니다. 참조 횟수가 0에 도달하면, 호출 프로세스의 주소 공간에서 모듈이 매핑 해제되고 핸들이 더 이상 유효하지 않습니다.

`AfxLoadLibrary` `AfxFreeLibrary` `LoadLibrary` `FreeLibrary` 응용 프로그램에서 여러 스레드를 사용 하 고 동적으로 MFC 확장명 DLL을 로드 하는 경우 및 (Win32 함수 대신)를 사용 해야 합니다. `AfxLoadLibrary`및를 사용 하면 `AfxFreeLibrary` MFC 확장 DLL을 로드 하 고 언로드할 때 실행 되는 시작 및 종료 코드가 전역 mfc 상태를 손상 하지 않습니다.

`AfxLoadLibrary`응용 프로그램에서를 사용 하려면 MFC의 DLL 버전에 동적으로 연결 해야 합니다. , Afxdll_에 대 한 헤더 파일은 `AfxLoadLibrary` MFC가 응용 프로그램에 DLL로 연결 된 경우에만 포함 됩니다. Mfc 확장명 Dll을 사용 하거나 만들려면 MFC의 DLL 버전에 연결 해야 하기 때문에이 요구 사항은 의도 된 것입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdll_ .h

## <a name="afxloadlibraryex"></a><a name="afxloadlibraryex"></a> AfxLoadLibraryEx

`AfxLoadLibraryEx`를 사용해서 DLL 모듈을 매핑합니다.

```cpp
HINSTANCE AFXAPI AfxLoadLibraryEx(LPCTSTR lpFileName, HANDLE hFile, DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*lpFileName*\
은 (는) 모듈의 이름을 포함 하는 null로 끝나는 문자열을 가리킵니다. DLL 또는. EXE 파일). 지정 된 이름은 모듈의 파일 이름입니다.

문자열이 경로를 지정 하지만 파일이 지정 된 디렉터리에 없으면 함수가 실패 합니다.

경로를 지정 하지 않고 파일 이름 확장명을 생략 하면 기본 확장명이 지정 됩니다. DLL이 추가 됩니다. 그러나 파일 이름 문자열에는 모듈 이름에 확장명이 없음을 나타내는 후행 점 문자 (.)가 포함 될 수 있습니다. 경로를 지정 하지 않으면 함수는 [데스크톱 응용 프로그램의 검색 순서](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)를 사용 합니다.

*hFile*\
이 매개 변수는 나중에 사용하도록 예약되어 있습니다. NULL 이어야 합니다.

*dwFlags*\
모듈을 로드할 때 수행할 동작입니다. 플래그가 지정 되지 않은 경우이 함수의 동작은 `AfxLoadLibrary` 함수와 동일 합니다. 이 매개 변수의 가능한 값은 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) 설명서에 설명 되어 있습니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 반환 값은 모듈에 대 한 핸들입니다. 오류가 발생 하면 반환 값은 NULL입니다.

### <a name="remarks"></a>설명

`AfxLoadLibraryEx`[GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) 에서 DLL 함수의 주소를 가져오는 데 사용할 수 있는 핸들을 반환 합니다. `AfxLoadLibraryEx` 를 사용 하 여 다른 실행 모듈을 매핑할 수도 있습니다.

각 프로세스는 로드 된 각 라이브러리 모듈에 대 한 참조 횟수를 유지 관리 합니다. 이 참조 횟수는가 호출 될 때마다 증가 `AfxLoadLibraryEx` 하 고가 호출 될 때마다 감소 `AfxFreeLibrary` 합니다. 참조 횟수가 0에 도달하면, 호출 프로세스의 주소 공간에서 모듈이 매핑 해제되고 핸들이 더 이상 유효하지 않습니다.

`AfxLoadLibraryEx` `AfxFreeLibrary` `LoadLibraryEx` `FreeLibrary` 응용 프로그램에서 여러 스레드를 사용 하 고 MFC 확장명 DLL을 동적으로 로드 하는 경우 및 (Win32 함수 대신)를 사용 해야 합니다. `AfxLoadLibraryEx`및를 사용 하면 `AfxFreeLibrary` MFC 확장 DLL을 로드 하 고 언로드할 때 실행 되는 시작 및 종료 코드가 전역 mfc 상태를 손상 하지 않습니다.

`AfxLoadLibraryEx`응용 프로그램에서를 사용 하려면 MFC의 DLL 버전에 동적으로 연결 해야 합니다. , Afxdll_에 대 한 헤더 파일은 `AfxLoadLibraryEx` MFC가 응용 프로그램에 DLL로 연결 된 경우에만 포함 됩니다. Mfc 확장명 Dll을 사용 하거나 만들려면 MFC의 DLL 버전에 연결 해야 하기 때문에이 요구 사항은 의도 된 것입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdll_ .h

## <a name="afxmenutearoffmanager"></a><a name="afxmenutearoffmanager"></a> AfxMenuTearOffManager

전역 [분리 메뉴 관리자](cmenutearoffmanager-class.md)에 대 한 포인터입니다.

### <a name="syntax"></a>구문

```cpp
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxmenutearoffmanager

## <a name="afxmousemanager"></a><a name="afxmousemanager"></a> AfxMouseManager

전역 [마우스 관리자](cmousemanager-class.md)에 대 한 포인터입니다.

### <a name="syntax"></a>구문

```cpp
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxmousemanager

## <a name="afxregisterclass"></a><a name="afxregisterclass"></a> AfxRegisterClass

이 함수를 사용 하 여 MFC를 사용 하는 DLL에 창 클래스를 등록 합니다.

```cpp
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>매개 변수

*lpWndClass*\
등록할 창 클래스에 대 한 정보를 포함 하는 [예: wndclassa](/windows/win32/api/winuser/ns-winuser-wndclassw) 구조체에 대 한 포인터입니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

### <a name="return-value"></a>반환 값

클래스가 성공적으로 등록 되 면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 함수를 사용 하면 DLL이 언로드될 때 클래스의 등록이 자동으로 취소 됩니다.

DLL이 아닌 빌드에서는 `AfxRegisterClass` `RegisterClass` 응용 프로그램에 등록 된 클래스가 자동으로 등록 취소 되기 때문에 식별자는 Windows 함수에 매핑되는 매크로로 정의 됩니다. 대신를 사용 하는 경우 `AfxRegisterClass` `RegisterClass` 응용 프로그램과 DLL 모두에서 코드를 변경 하지 않고 코드를 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxregisterwndclass"></a><a name="afxregisterwndclass"></a> AfxRegisterWndClass

사용자 고유의 창 클래스를 등록할 수 있습니다.

```cpp
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>매개 변수

*nClassStyle*\
창 클래스에 대해 비트 or (**&#124;**) 연산자를 사용 하 여 만든 Windows 클래스 스타일 또는 스타일의 조합을 지정 합니다. 클래스 스타일의 목록은 Windows SDK [예: wndclassa](/windows/win32/api/winuser/ns-winuser-wndclassw) 구조체를 참조 하세요. NULL 인 경우 기본값은 다음과 같이 설정 됩니다.

- 마우스 스타일을 CS_DBLCLKS 설정 합니다. 그러면 사용자가 마우스를 두 번 클릭 하면 창 프로시저에 두 번 클릭 메시지가 전송 됩니다.

- 화살표 커서 스타일을 Windows 표준 IDC_ARROW 설정 합니다.

- 배경 브러시를 NULL로 설정 하므로 창이 배경을 지우지 않습니다.

- 아이콘을 표준 대기가 없어 Windows 로고 아이콘으로 설정 합니다.

*hCursor*\
Window 클래스에서 만든 각 창에 설치할 커서 리소스에 대 한 핸들을 지정 합니다. 기본값인 **0**을 사용 하는 경우 표준 IDC_ARROW 커서를 받게 됩니다.

*hbrBackground*\
Window 클래스에서 만든 각 창에 설치할 브러시 리소스에 대 한 핸들을 지정 합니다. 기본값인 **0**을 사용 하는 경우 NULL 배경 브러시를 갖게 되며 기본적으로 [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)처리 하는 동안 창이 배경을 지우지 않습니다.

*hIcon*\
Window 클래스에서 만든 각 창에 설치할 아이콘 리소스에 대 한 핸들을 지정 합니다. 기본값인 **0**을 사용 하는 경우 표준 대기가 없어 Windows 로고 아이콘이 표시 됩니다.

### <a name="return-value"></a>반환 값

클래스 이름을 포함 하는 null로 끝나는 문자열입니다. `Create` `CWnd` 또는 다른 **CWnd**파생 클래스의 멤버 함수에이 클래스 이름을 전달 하 여 창을 만들 수 있습니다. 이름은 MFC 라이브러리에서 생성 됩니다.

> [!NOTE]
> 반환 값은 정적 버퍼에 대 한 포인터입니다. 이 문자열을 저장 하려면 `CString` 변수에 할당 합니다.

### <a name="remarks"></a>설명

MFC 라이브러리는 자동으로 여러 표준 창 클래스를 등록 합니다. 사용자 고유의 창 클래스를 등록 하려면이 함수를 호출 합니다.

에 의해 클래스에 대해 등록 된 이름은 `AfxRegisterWndClass` 매개 변수에 따라서만 달라 집니다. 동일한 매개 변수를 사용 하 여를 여러 번 호출 하는 경우에 `AfxRegisterWndClass` 는 첫 번째 호출에만 클래스를 등록 합니다. 이후에 동일한 매개 변수를 사용 하 여를 호출 `AfxRegisterWndClass` 하면 이미 등록 된 classname이 반환 됩니다.

`AfxRegisterWndClass`동일한 매개 변수를 사용 하는 여러 CWnd 파생 클래스에 대해를 호출 하는 경우 각 클래스에 대해 별도의 창 클래스를 가져오는 대신 각 클래스는 동일한 창 클래스를 공유 합니다. CS_CLASSDC 클래스 스타일이 사용 되는 경우이 공유에서 문제가 발생할 수 있습니다. 여러 CS_CLASSDC 창 클래스 대신 CS_CLASSDC 창 클래스를 하나만 사용 합니다. 해당 클래스를 사용 하는 모든 c + + 창은 동일한 DC를 공유 합니다. 이 문제를 방지 하려면 [AfxRegisterClass](#afxregisterclass) 를 호출 하 여 클래스를 등록 합니다.

창 클래스 등록 및 함수에 대 한 자세한 내용은 Technical Note [TN001: Window 클래스 등록](../../mfc/tn001-window-class-registration.md) 을 참조 하세요 `AfxRegisterWndClass` .

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a> AfxSetPerUserRegistration

응용 프로그램이 레지스트리 액세스를 **HKEY_CURRENT_USER** (**HKCU**) 노드로 리디렉션하는 지 여부를 설정 합니다.

```cpp
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*\
진행 TRUE는 레지스트리 정보가 HKCU 노드에 전달 됨을 나타냅니다. FALSE는 응용 프로그램이 레지스트리 정보를 기본 노드에 쓰도록 지정 합니다. 기본 노드는 **HKEY_CLASSES_ROOT** (**HKCR**)입니다.

### <a name="remarks"></a>설명

Windows Vista 이전에는 레지스트리에 액세스 한 응용 프로그램이 일반적으로 **HKEY_CLASSES_ROOT** 노드를 사용 했습니다. 그러나 Windows Vista 이상 운영 체제를 사용 하는 경우에는 응용 프로그램을 관리자 모드로 실행 하 여 HKCR에 써야 합니다.

이 메서드를 사용 하면 관리자 모드에서 실행 하지 않고 응용 프로그램에서 레지스트리를 읽고 쓸 수 있습니다. HKCR에서 HKCU로 레지스트리 액세스를 리디렉션하여 작동 합니다. 자세한 내용은 [Linker Property Pages](../../build/reference/linker-property-pages.md)을 참조하세요.

레지스트리 리디렉션을 사용 하도록 설정 하는 경우 프레임 워크는 HKCR에서 **HKEY_CURRENT_USER \\C\\cc\c\\c\c\** MFC 및 ATL 프레임 워크도 리디렉션의 영향을 받습니다.

기본 구현은 HKCR에서 레지스트리에 액세스 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxstat_ .h

## <a name="afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a> AfxSetResourceHandle

이 함수를 사용 하 여 응용 프로그램의 기본 리소스가 로드 되는 위치를 결정 하는 HINSTANCE 핸들을 설정 합니다.

```cpp
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>매개 변수

*H명령이 리소스*\
에 대 한 인스턴스 또는 모듈 핸들입니다. 응용 프로그램의 리소스가 로드 되는 EXE 또는 DLL 파일입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxshellmanager"></a><a name="afxshellmanager"></a> AfxShellManager

전역 [셸 관리자](cshellmanager-class.md)에 대 한 포인터입니다.

### <a name="syntax"></a>구문

```cpp
CShellManager* afxShellManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxshellmanager

## <a name="afxsocketinit"></a><a name="afxsocketinit"></a> AfxSocketInit

재정의에서이 함수 `CWinApp::InitInstance` 를 호출 하 여 Windows 소켓을 초기화 합니다.

```cpp
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>매개 변수

*lpwsaData*\
[WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) 구조체에 대 한 포인터입니다. *LpwsaData* 가 NULL이 아닌 경우 `WSADATA` 에는에 대 한 호출에 의해 구조체의 주소가 채워집니다 `WSAStartup` . 또한이 함수를 `WSACleanup` 사용 하면 응용 프로그램이 종료 되기 전에가 호출 됩니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

정적으로 연결 된 MFC 응용 프로그램의 보조 스레드에서 MFC 소켓을 사용 하는 경우 소켓 `AfxSocketInit` 라이브러리를 초기화 하는 데 소켓을 사용 하는 각 스레드에서를 호출 해야 합니다. 기본적으로 `AfxSocketInit` 는 주 스레드에서만 호출 됩니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxsock

## <a name="afxusertoolsmanager"></a><a name="afxusertoolsmanager"></a> AfxUserToolsManager

전역 [사용자 도구 관리자](cusertoolsmanager-class.md)에 대 한 포인터입니다.

### <a name="syntax"></a>구문

```cpp
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxusertoolsmanager

## <a name="afxwininit"></a><a name="afxwininit"></a> AfxWinInit

이 함수는 mfc 제공 `WinMain` 함수에서 GUI 기반 응용 프로그램의 [CWinApp](../../mfc/reference/cwinapp-class.md) 초기화의 일부로 호출 되어 mfc를 초기화 합니다.

```cpp
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>매개 변수

*hInstance*\
현재 실행 중인 모듈의 핸들입니다.

*hPrevInstance*\
응용 프로그램의 이전 인스턴스에 대 한 핸들입니다. Win32 기반 응용 프로그램의 경우이 매개 변수는 항상 **NULL**입니다.

*lpCmdLine*\
응용 프로그램에 대 한 명령줄을 지정 하는 null로 끝나는 문자열을 가리킵니다.

*nCmdShow*\
GUI 응용 프로그램의 주 창이 표시 되는 방식을 지정 합니다.

### <a name="remarks"></a>설명

MFC 제공 함수를 사용 하지 않는 콘솔 응용 프로그램의 경우에는 `WinMain` `AfxWinInit` 를 직접 호출 하 여 mfc를 초기화 해야 합니다.

자신을 호출 하는 경우 `AfxWinInit` 클래스의 인스턴스를 선언 해야 합니다 `CWinApp` . 콘솔 응용 프로그램의 경우에서 고유한 클래스를 파생 하지 않고 인스턴스를 직접 사용 하도록 선택할 수 있습니다 `CWinApp` `CWinApp` . 이 기법은 응용 프로그램에 대 한 모든 기능을 **기본**구현에서 유지 하려는 경우에 적합 합니다.

> [!NOTE]
> 어셈블리에 대 한 활성화 컨텍스트를 만들 때 MFC는 사용자 모듈에서 제공 하는 매니페스트 리소스를 사용 합니다. 활성화 컨텍스트는 `AfxWinInit`에서 만듭니다. 자세한 내용은 [MFC 모듈 상태의 활성화 컨텍스트 지원](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)을 참조 하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](mfc-macros-and-globals.md)\
[CWinApp 클래스](cwinapp-class.md)\
[CContextMenuManager 클래스](ccontextmenumanager-class.md)\
[CWnd 클래스](cwnd-class.md)\
[CFrameWndEx 클래스](cframewndex-class.md)\
[CMFCToolBar 클래스](cmfctoolbar-class.md)\
[CKeyboardManager 클래스](ckeyboardmanager-class.md)\
[CMenuTearOffManager 클래스](cmenutearoffmanager-class.md)\
[CMouseManager 클래스](cmousemanager-class.md)\
[CShellManager 클래스](cshellmanager-class.md)\
[CUserToolsManager 클래스](cusertoolsmanager-class.md)
