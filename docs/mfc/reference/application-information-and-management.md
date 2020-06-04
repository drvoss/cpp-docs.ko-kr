---
title: 애플리케이션 정보 및 관리
description: Microsoft 재단 클래스 라이브러리(MFC) 응용 프로그램 정보 및 관리 기능에 대한 참조입니다.
ms.date: 01/27/2020
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: fc0b4b09f6c48da68bebe4a2825f49bcf6ab7e23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372496"
---
# <a name="application-information-and-management"></a>애플리케이션 정보 및 관리

응용 프로그램을 작성할 때 단일 [CWinApp-파생](../../mfc/reference/cwinapp-class.md)개체를 만듭니다. 경우에 따라 -derived 개체 외부에서 이 개체에 `CWinApp`대한 정보를 얻을 수 있습니다. 또는 다른 전역 "관리자" 개체에 액세스해야 할 수 있습니다.

Microsoft 재단 클래스 라이브러리는 이러한 작업을 수행하는 데 도움이 되는 다음과 같은 전역 기능을 제공합니다.

## <a name="application-information-and-management-functions"></a>응용 프로그램 정보 및 관리 기능

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|새 스레드를 만듭니다.|
|[Afx컨텍스트메뉴관리자](#afxcontextmenumanager)|전역 컨텍스트 [메뉴 관리자에](ccontextmenumanager-class.md)대한 포인터입니다.|
|[AfxEndThread](#afxendthread)|현재 스레드를 종료합니다.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|리소스 체인을 안내하고 리소스 ID 및 리소스 유형별로 특정 리소스를 찾습니다. |
|[AfxFreeLibrary](#afxfreelibrary)|로드된 동적 링크 라이브러리(DLL) 모듈의 참조 수를 줄입니다. 참조 수가 0에 도달하면 모듈이 매핑되지 않습니다.|
|[AfxGetApp](#afxgetapp)|응용 프로그램의 단일 `CWinApp` 개체에 대한 포인터를 반환합니다.|
|[AfxGetAppName](#afxgetappname)|응용 프로그램의 이름이 포함된 문자열을 반환합니다.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|응용 프로그램의 이 인스턴스를 나타내는 HINSTANCE를 반환합니다.|
|[AfxGetMainWnd](#afxgetmainwnd)|OLE가 아닌 응용 프로그램의 현재 "주" 창 또는 서버 응용 프로그램의 현재 프레임 창에 대한 포인터를 반환합니다.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|이 함수를 사용하여 응용 프로그램이 레지스트리 액세스를**HKEY_CURRENT_USER(HKCU)** 노드로 리디렉션하는지 여부를 확인합니다. **HKEY_CURRENT_USER**|
|[AfxGetResourceHandle](#afxgetresourcehandle)|HINSTANCE를 응용 프로그램의 기본 리소스의 원본으로 반환합니다. 응용 프로그램의 리소스에 직접 액세스하는 데 사용합니다.|
|[AfxGetThread](#afxgetthread)|현재 [CWinThread](../../mfc/reference/cwinthread-class.md) 개체에 대한 포인터를 검색합니다.|
|[AfxInitRichEdit](#afxinitrichedit)|응용 프로그램에 대한 버전 1.0 리치 편집 컨트롤을 초기화합니다.|
|[AfxInitRichEdit2](#afxinitrichedit2)|버전 2.0 및 응용 프로그램에 대한 이후의 풍부한 편집 컨트롤을 초기화합니다.|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|지정된 창이 확장된 프레임 개체인지 여부를 확인합니다.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|지정된 창이 도구 모음 개체인지 여부를 결정합니다.|
|[Afx키보드매니저](#afxkeyboardmanager)|글로벌 키보드 [관리자에](ckeyboardmanager-class.md)대한 포인터 .|
|[AfxLoadLibrary](#afxloadlibrary)|DLL 모듈을 매핑하고 DLL 함수의 주소를 가져오는 데 사용할 수 있는 핸들을 반환합니다.|
|[아프로드라이브러리텍스](#afxloadlibraryex)|지정된 옵션을 사용하여 DLL 모듈을 매핑하고 DLL 함수의 주소를 가져오는 데 사용할 수 있는 핸들을 반환합니다.|
|[아프메뉴티어오프매니저](#afxmenutearoffmanager)|글로벌 [찢어짐 메뉴 관리자에](cmenutearoffmanager-class.md)대한 포인터 .|
|[아fx마우스매니저](#afxmousemanager)|글로벌 마우스 [관리자에](cmousemanager-class.md)대한 포인터 .|
|[AfxRegisterClass](#afxregisterclass)|MFC를 사용하는 DLL에 창 클래스를 등록합니다.|
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC에서 자동으로 등록된 클래스를 보완하기 위해 Windows 창 클래스를 등록합니다.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|응용 프로그램이 레지스트리 액세스를**HKEY_CURRENT_USER(HKCU)** 노드로 리디렉션할지 여부를 설정합니다. **HKEY_CURRENT_USER**|
|[AfxSetResourceHandle](#afxsetresourcehandle)|응용 프로그램의 기본 리소스가 로드되는 HINSTANCE 핸들을 설정합니다.|
|[아프쉘매니저](#afxshellmanager)|전역 셸 [관리자에](cshellmanager-class.md)대한 포인터입니다. |
|[AfxSocketInit](#afxsocketinit)|Windows 소켓을 `CWinApp::InitInstance` 초기화하기 위해 재정의에서 호출됩니다.|
|[AfxUserTools매니저](#afxusertoolsmanager)|글로벌 사용자 [도구 관리자에](cusertoolsmanager-class.md)대한 포인터 .|
|[AfxWinInit](#afxwininit)|MFC 기반 응용 `WinMain` 프로그램의 [CWinApp](../../mfc/reference/cwinapp-class.md) 초기화의 일부로 MFC 제공 함수에 의해 호출되어 MFC를 초기화합니다. MFC를 사용하는 콘솔 응용 프로그램에 대해 직접 호출해야 합니다.|

## <a name="afxbeginthread"></a><a name="afxbeginthread"></a>아fx비긴스레드

이 함수를 호출하여 새 스레드를 만듭니다.

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

*pfn스레드프로크*\
작업자 스레드의 제어 함수를 가리킵니다. 포인터는 NULL일 수 없습니다. 이 함수는 다음과 같이 선언해야 합니다.

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThread클래스*\
[CWinThread에서](../../mfc/reference/cwinthread-class.md)파생 된 개체의 RUNTIME_CLASS .

*p파라름*\
제어 함수에 전달할 매개 변수입니다.

*n우선 순위*\
스레드에 대해 설정할 우선 순위입니다. 사용 가능한 우선 순위에 대한 전체 목록 및 설명은 Windows SDK의 [SetThreadPriority를](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 참조하십시오.

*n스택 크기*\
새 스레드에 대한 스택의 바이트 크기를 지정합니다. 이 경우 스택 크기는 생성 스레드와 동일한 크기 스택으로 기본설정됩니다.

*dwCreateFlags*\
스레드 생성을 제어하는 추가 플래그를 지정합니다. 이 플래그에는 다음 두 값 중 하나가 포함될 수 있습니다.

- CREATE_SUSPENDED 일시 중단 개수로 스레드를 시작합니다. 스레드가 실행되기 전에 [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) 또는 파생 `CWinThread` 클래스의 멤버와 같은 개체의 멤버 데이터를 초기화하려면 CREATE_SUSPENDED 사용합니다. 초기화가 완료되면 [CWinThread::ResumeThread를](../../mfc/reference/cwinthread-class.md#resumethread) 사용하여 스레드 실행을 시작합니다. 스레드가 호출될 때까지 `CWinThread::ResumeThread` 실행되지 않습니다.

- **0** 생성 직후 스레드를 시작합니다.

*lp보안트르*\
스레드에 대한 보안 특성을 지정하는 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 구조를 가리킵니다. NULL인 경우 만드는 스레드와 동일한 보안 특성이 사용됩니다. 이 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

### <a name="return-value"></a>Return Value

새로 생성된 스레드 개체 또는 오류가 발생할 경우 NULL에 대한 포인터입니다.

### <a name="remarks"></a>설명

첫 번째 `AfxBeginThread` 형식의 작업자 스레드를 만듭니다. 두 번째 양식은 사용자 인터페이스 스레드 또는 작업자 스레드로 사용될 수 있는 스레드를 만듭니다.

`AfxBeginThread`새 `CWinThread` 개체를 만들고 [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) 함수를 호출하여 스레드 실행을 시작하고 스레드에 대한 포인터를 반환합니다. 만들기의 일부가 실패할 경우 모든 개체가 제대로 할당 할당되었는지 확인하기 위해 프로시저 전체에서 검사가 수행됩니다. 스레드를 종료하려면 스레드 내에서 [AfxEndThread를](#afxendthread) 호출하거나 작업자 스레드의 제어 함수에서 반환합니다.

응용 프로그램에서 다중 스레딩을 사용하도록 설정해야 합니다. 그렇지 않으면 이 함수가 실패합니다. 다중 스레딩 사용에 대한 자세한 내용은 [/MD, /MT, /LD(런타임 라이브러리 사용)를](../../build/reference/md-mt-ld-use-run-time-library.md)참조하십시오.

자세한 내용은 `AfxBeginThread` [다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md) 및 [다중 스레딩: 사용자 인터페이스 스레드 만들기](../../parallel/multithreading-creating-user-interface-threads.md)에 대한 자세한 내용은 문서를 참조하십시오.

### <a name="example"></a>예제

[CSocket::연결](../../mfc/reference/csocket-class.md#attach)에 대한 예제를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxcontextmenumanager"></a><a name="afxcontextmenumanager"></a>Afx컨텍스트메뉴관리자

전역 컨텍스트 [메뉴 관리자에](ccontextmenumanager-class.md)대한 포인터입니다.

### <a name="syntax"></a>구문

```cpp
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxcontextmenumanager.h

## <a name="afxendthread"></a><a name="afxendthread"></a>아fx엔드스레드

이 함수를 호출하여 현재 실행 중인 스레드를 종료합니다.

```cpp
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>매개 변수

*n엑시트 코드*\
스레드의 종료 코드를 지정합니다.

*b삭제*\
메모리에서 스레드 개체를 삭제합니다.

### <a name="remarks"></a>설명

종료하려면 스레드 내에서 호출해야 합니다.

자세한 내용은 `AfxEndThread` [다중 스레딩: 스레드 종료](../../parallel/multithreading-terminating-threads.md)에 대한 도움말을 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxfindresourcehandle"></a><a name="afxfindresourcehandle"></a>AfxFind리소스핸들

리소스 `AfxFindResourceHandle` 체인을 걷고 리소스 ID 및 리소스 유형별로 특정 리소스를 찾는 데 사용합니다.

### <a name="syntax"></a>구문

```cpp
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>매개 변수

*Lpszname*\
리소스 ID를 포함하는 문자열에 대한 포인터입니다.
*lpszType*\
리소스 유형에 대한 포인터입니다. 리소스 유형 목록은 Windows SDK의 [FindResource를](/windows/win32/api/winbase/nf-winbase-findresourcea) 참조하십시오.

### <a name="return-value"></a>Return Value

리소스를 포함하는 모듈에 대한 핸들입니다.

### <a name="remarks"></a>설명

`AfxFindResourceHandle`에서는 특정 리소스를 찾아 리소스가 포함된 모듈에 핸들을 반환합니다. 리소스가 로드된 모든 MFC 확장 DLL에 있을 수 있습니다. `AfxFindResourceHandle`리소스가 있는 것을 알려줍니다.

모듈은 다음 순서로 검색됩니다.

1. 메인 모듈, 그것은 MFC 확장 DLL의 경우.

1. 비시스템 모듈.

1. 언어별 모듈.

1. 메인 모듈, 그것은 시스템 DLL의 경우.

1. 시스템 모듈.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="afxfreelibrary"></a><a name="afxfreelibrary"></a>아fx프리라이브러리

`AfxFreeLibrary` 및 `AfxLoadLibrary`는 각 코딩된 라이브러리 모듈에 대한 참조 횟수를 유지 관리합니다.

```cpp
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>매개 변수

*힌스트리브*\
로드된 라이브러리 모듈의 핸들입니다. [AfxLoadLibrary는](#afxloadlibrary) 이 핸들을 반환합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 TRUE이고 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

`AfxFreeLibrary`는 로드된 DLL(동적 연결 라이브러리) 모듈의 참조 횟수를 감소시킵니다. 참조 횟수가 0에 도달하면, 호출 프로세스의 주소 공간에서 모듈이 매핑 해제되고 핸들이 더 이상 유효하지 않습니다. 이 참조 카운트는 `AfxLoadLibrary`가 호출될 때마다 매번 증가합니다.

라이브러리 모듈을 매핑 해제하기 전에 시스템은 DLL이 이를 사용하는 프로세스에서 분리할 수 있게 해줍니다. 이렇게 하면 DLL에서 현재 프로세스에 할당된 리소스를 정리할 수 있습니다. 진입점 함수가 반환된 다음 라이브러리 모듈은 현재 프로세스의 주소 공간에서 제거됩니다.

`AfxLoadLibrary`를 사용해서 DLL 모듈을 매핑합니다.

응용 프로그램에서 `AfxFreeLibrary` 여러 `AfxLoadLibrary` 스레드를 사용하는 경우 Win32 함수 `FreeLibrary` 및(Win32 `LoadLibrary`함수 대신)을 사용해야 합니다. MFC 확장 DLL을 로드하고 언로드할 때 실행되는 시작 및 종료 코드가 전역 MFC 상태를 손상시키지 않도록 합니다. `AfxLoadLibrary` `AfxFreeLibrary`

### <a name="example"></a>예제

[AfxLoadLibrary에](#afxloadlibrary)대한 예제를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdll_.h

## <a name="afxgetapp"></a><a name="afxgetapp"></a>아fxGetApp

이 함수에서 반환되는 포인터를 사용하여 기본 메시지 디스패치 코드 또는 최상위 창과 같은 응용 프로그램 정보에 액세스할 수 있습니다.

```cpp
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>Return Value

응용 프로그램의 단일 `CWinApp` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드가 NULL을 반환하는 경우 응용 프로그램 주 창이 아직 완전히 초기화되지 않았음을 나타낼 수 있습니다. 또한 문제를 나타낼 수도 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxgetappname"></a><a name="afxgetappname"></a>AfxGetApp네임

반환된 문자열은 진단 메시지 또는 임시 문자열 이름의 루트로 사용할 수 있습니다.

```cpp
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>Return Value

응용 프로그램의 이름을 포함하는 null 종료 문자열입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a>AfxGet인스턴스핸들

이 함수를 사용하면 현재 응용 프로그램의 인스턴스 핸들을 검색할 수 있습니다.

```cpp
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>Return Value

응용 프로그램의 현재 인스턴스에 대한 HINSTANCE입니다. UsRDLL 버전의 MFC와 연결된 DLL 내에서 호출하면 DLL에 대한 HINSTANCE가 반환됩니다.

### <a name="remarks"></a>설명

`AfxGetInstanceHandle`항상 실행 파일의 HINSTANCE를 반환합니다() EXE) MFC의 USRDLL 버전과 연결된 DLL 내에서 호출되지 않는 한. 이 경우 HINSTANCE를 DLL에 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxgetmainwnd"></a><a name="afxgetmainwnd"></a>아fxGet메인드

응용 프로그램이 OLE 서버인 경우 이 함수를 호출하여 응용 프로그램의 활성 주 창에 대한 포인터를 검색합니다. 응용 프로그램 개체의 [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) 멤버를 직접 참조하는 대신 이 결과를 사용합니다.

```cpp
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>Return Value

서버에 활성 컨테이너 내에서 활성 상태인 개체가 있는 경우 내부 활성 문서가 포함된 프레임 창 개체에 대한 포인터를 반환합니다.

컨테이너 내에 활성 상태인 개체가 없거나 응용 프로그램이 OLE 서버가 아닌 경우 이 함수는 응용 프로그램 개체의 *m_pMainWnd* 반환합니다.

애플리케이션의 기본 스레드에서 `AfxGetMainWnd`가 호출되는 경우 위의 규칙에 따라 애플리케이션의 주 창이 반환됩니다. 함수가 애플리케이션의 보조 스레드에서 호출되면 함수는 호출한 스레드에 연결된 주 창을 반환합니다.

### <a name="remarks"></a>설명

응용 프로그램이 OLE 서버가 아닌 경우 이 함수를 호출하는 것은 응용 프로그램 개체의 *m_pMainWnd* 멤버를 직접 참조하는 것과 같습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a>AfxGetPer사용자 등록

이 함수를 사용하여 응용 프로그램이 레지스트리 액세스를**HKEY_CURRENT_USER(HKCU)** 노드로 리디렉션하는지 여부를 확인합니다. **HKEY_CURRENT_USER**

```cpp
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>Return Value

TRUE는 레지스트리 정보가 HKCU 노드로 전달됨을 나타냅니다. FALSE는 응용 프로그램이 레지스트리 정보를 기본 노드에 기록했음을 나타냅니다. 기본 노드는 **HKEY_CLASSES_ROOT** **HKEY_CLASSES_ROOT(HKCR)입니다.**

### <a name="remarks"></a>설명

레지스트리 리디렉션을 사용하도록 설정하면 프레임워크가 **HKCR에서** **HKEY_CURRENT_USER\Software\Class로**액세스를 리디렉션합니다. MFC 및 ATL 프레임워크만 리디렉션의 영향을 받습니다.

응용 프로그램이 레지스트리 액세스를 리디렉션하는지 여부를 변경하려면 [AfxSetPerUser등록을](#afxsetperuserregistration)사용합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxstat_.h

## <a name="afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a>AfxGet리소스핸들

이 함수에서 반환되는 HINSTANCE 핸들을 사용하여 Windows 함수를 `FindResource`호출할 때 응용 프로그램의 리소스에 직접 액세스합니다.

```cpp
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>Return Value

응용 프로그램의 기본 리소스가 로드되는 HINSTANCE 핸들입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxgetthread"></a><a name="afxgetthread"></a>아fxGet스레드

현재 실행 중인 스레드를 나타내는 [CWinThread](../../mfc/reference/cwinthread-class.md) 개체에 대한 포인터를 얻으려면 이 함수를 호출합니다.

```cpp
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>Return Value

현재 실행 중인 스레드에 대한 포인터; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

스레드 내에서 호출해야 합니다.

> [!NOTE]
> Visual C++ 버전 4.2, 5.0 또는 6.0에서 호출하는 `AfxGetThread` MFC `AfxGetThread` 프로젝트를 이식하는 경우 스레드가 없는 경우 [AfxGetApp을](#afxgetapp) 호출합니다. 최신 버전의 컴파일러에서는 스레드가 없는 경우 NULL을 `AfxGetThread` 반환합니다. 응용 프로그램 스레드를 원하는 경우 `AfxGetApp`을 호출해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxinitrichedit"></a><a name="afxinitrichedit"></a>아프시니티리치에이트

이 함수를 호출하여 응용 프로그램의 리치 편집 컨트롤(버전 1.0)을 초기화합니다.

```cpp
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>설명

이 함수는 이전 버전과의 호환성을 위해 제공됩니다. 새 응용 프로그램은 [AfxInitRichEdit2](#afxinitrichedit2).

`AfxInitRichEdit`부하 RICHED32. DLL은 리치 편집 컨트롤의 버전 1.0을 초기화합니다. 리치 편집 컨트롤의 버전 2.0 및 3.0을 사용하려면 RICHED20입니다. DLL을 로드해야 합니다. [AfxInitRichEdit2에](#afxinitrichedit2)전화를 걸어 로드됩니다.

기존 Visual C++ 응용 프로그램의 풍부한 편집 컨트롤을 버전 2.0으로 업데이트하려면 을 엽니다. 텍스트로 RC 파일, "RICHEDIT"에서 "RichEdit20a"로 각 풍부한 편집 컨트롤의 클래스 이름을 변경합니다. 그런 다음 `AfxInitRichEdit` 호출을 `AfxInitRichEdit2`로 바꿉꿉습니다.

또한 이 함수는 프로세스에 대해 라이브러리가 아직 초기화되지 않은 경우 공통 컨트롤 라이브러리를 초기화합니다. MFC 응용 프로그램에서 직접 리치 편집 컨트롤을 사용하는 경우 이 함수를 호출하여 MFC가 리치 편집 컨트롤 런타임을 올바르게 초기화했는지 확인합니다. `Create` [CRichEditCtrl,](../../mfc/reference/cricheditctrl-class.md) [CRichEditView](../../mfc/reference/cricheditview-class.md)또는 [CRichEditDoc의](../../mfc/reference/cricheditdoc-class.md)메서드를 호출하는 경우 일반적으로 이 함수를 호출할 필요가 없지만 경우에 따라 필요할 수 있습니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxinitrichedit2"></a><a name="afxinitrichedit2"></a>아프시니티리치리치2

이 함수를 호출하여 응용 프로그램의 리치 편집 컨트롤(버전 2.0 이상)을 초기화합니다.

```cpp
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>설명

이 함수를 호출하여 RICHED20을 로드합니다. 풍부한 편집 컨트롤의 버전 2.0을 DLL 및 초기화합니다. `Create` [CRichEditCtrl,](../../mfc/reference/cricheditctrl-class.md) [CRichEditView](../../mfc/reference/cricheditview-class.md)또는 [CRichEditDoc의](../../mfc/reference/cricheditdoc-class.md)메서드를 호출하는 경우 일반적으로 이 함수를 호출할 필요가 없지만 경우에 따라 필요할 수 있습니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxisextendedframeclass"></a><a name="afxisextendedframeclass"></a>AfxIs확장프레임클래스

지정된 창이 확장된 프레임 개체인지 여부를 확인합니다.

### <a name="syntax"></a>구문

```cpp
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>매개 변수

*Pwnd*\
【인】 `CWnd`에서 파생된 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

제공된 창이 확장프레임 객체인 경우 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

*pWnd다음* 클래스 중 하나에서 파생 되는 경우이 메서드는 TRUE를 반환 합니다.

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

이 메서드는 함수 또는 메서드 매개 변수가 확장된 프레임 창인지 확인해야 하는 경우에 유용합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxismfctoolbar"></a><a name="afxismfctoolbar"></a>아프시스엠FC툴바

지정된 창이 도구 모음 개체인지 여부를 결정합니다.

### <a name="syntax"></a>구문

```cpp
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*Pwnd*\
【인】 `CWnd`에서 파생된 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 제공된 창이 도구 모음 개체인 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 `TRUE` *pWnd에서* `CMFCToolBar`파생 되는 경우 반환 합니다. 이 메서드는 함수 또는 메서드 매개 변수가 `CMFCToolBar` 개체인지 확인해야 하는 경우에 유용합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxkeyboardmanager"></a><a name="afxkeyboardmanager"></a>Afx키보드매니저

글로벌 키보드 [관리자에](ckeyboardmanager-class.md)대한 포인터 .

### <a name="syntax"></a>구문

```cpp
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afx키보드매니저.h

## <a name="afxloadlibrary"></a><a name="afxloadlibrary"></a>아프로드라이브러리

`AfxLoadLibrary`를 사용해서 DLL 모듈을 매핑합니다.

```cpp
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>매개 변수

*lpsz모듈이름*\
모듈의 이름을 포함하는 null 종료 된 문자열을 가리킵니다(. DLL 또는 . EXE 파일)을 참조하십시오. 지정된 이름은 모듈의 파일 이름입니다.

문자열에서 경로를 지정하지만 파일이 지정된 디렉터리에 없으면 함수가 실패합니다.

경로를 지정하지 않고 파일 이름 확장명을 생략하면 기본 확장명 . DLL이 추가됩니다. 그러나 파일 이름 문자열에는 모듈 이름에 확장이 없음을 나타내는 후행 지점 문자(.)가 포함될 수 있습니다. 경로를 지정하지 않은 경우 이 함수는 [데스크톱 응용 프로그램에 대한 검색 순서를](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)사용합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값은 모듈에 대한 핸들입니다. 실패시 반환 값은 NULL입니다.

### <a name="remarks"></a>설명

[GetProcAddress에서](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) DLL 함수의 주소를 얻는 데 사용할 수 있는 핸들을 반환합니다. `AfxLoadLibrary`다른 실행 모듈을 매핑하는 데 사용할 수도 있습니다.

각 프로세스는 로드된 각 라이브러리 모듈에 대한 참조 수를 유지 관리합니다. 이 참조 수는 `AfxLoadLibrary` 호출될 때마다 증가하며 `AfxFreeLibrary` 호출될 때마다 감소됩니다. 참조 횟수가 0에 도달하면, 호출 프로세스의 주소 공간에서 모듈이 매핑 해제되고 핸들이 더 이상 유효하지 않습니다.

응용 프로그램이 `AfxLoadLibrary` 여러 `AfxFreeLibrary` 스레드를 `LoadLibrary` 사용하고 MFC 확장 `FreeLibrary`DLL을 동적으로 로드하는 경우 Win32 함수 및 대신 사용하고 사용해야 합니다. MFC `AfxFreeLibrary` 확장 DLL을 로드하고 언로드할 때 실행되는 시작 및 종료 코드가 전역 MFC 상태를 손상시키지 않도록 합니다. `AfxLoadLibrary`

응용 `AfxLoadLibrary` 프로그램에서 사용하려면 DLL 버전의 MFC에 동적으로 연결해야 합니다. Afxdll_.h에 `AfxLoadLibrary`대한 헤더 파일은 MFC가 응용 프로그램에 DLL로 연결된 경우에만 포함됩니다. MFC 확장 DLL을 사용하거나 만들려면 MFC의 DLL 버전에 연결해야 하기 때문에 이 요구 사항은 의도적으로 사용됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdll_.h

## <a name="afxloadlibraryex"></a><a name="afxloadlibraryex"></a>아프로드라이브러리텍스

`AfxLoadLibraryEx`를 사용해서 DLL 모듈을 매핑합니다.

```cpp
HINSTANCE AFXAPI AfxLoadLibraryEx(LPCTSTR lpFileName, HANDLE hFile, DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*lpFileName*\
모듈의 이름을 포함하는 null 종료 된 문자열을 가리킵니다(. DLL 또는 . EXE 파일)을 참조하십시오. 지정된 이름은 모듈의 파일 이름입니다.

문자열에서 경로를 지정하지만 파일이 지정된 디렉터리에 없으면 함수가 실패합니다.

경로를 지정하지 않고 파일 이름 확장명을 생략하면 기본 확장명 . DLL이 추가됩니다. 그러나 파일 이름 문자열에는 모듈 이름에 확장이 없음을 나타내는 후행 지점 문자(.)가 포함될 수 있습니다. 경로를 지정하지 않은 경우 이 함수는 [데스크톱 응용 프로그램에 대한 검색 순서를](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)사용합니다.

*hFile*\
이 매개 변수는 나중에 사용하도록 예약되어 있습니다. NULL이어야 합니다.

*dwFlags*\
모듈을 로드할 때 수행해야 하는 작업입니다. 플래그를 지정하지 않으면 이 함수의 동작이 `AfxLoadLibrary` 함수와 동일합니다. 이 매개 변수의 가능한 값은 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) 설명서에 설명되어 있습니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값은 모듈에 대한 핸들입니다. 실패시 반환 값은 NULL입니다.

### <a name="remarks"></a>설명

`AfxLoadLibraryEx`은 [GetProcAddress에서](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) 사용할 수 있는 핸들을 반환하여 DLL 함수의 주소를 가져옵니다. `AfxLoadLibraryEx`다른 실행 모듈을 매핑하는 데 사용할 수도 있습니다.

각 프로세스는 로드된 각 라이브러리 모듈에 대한 참조 수를 유지 관리합니다. 이 참조 수는 `AfxLoadLibraryEx` 호출될 때마다 증가하며 `AfxFreeLibrary` 호출될 때마다 감소됩니다. 참조 횟수가 0에 도달하면, 호출 프로세스의 주소 공간에서 모듈이 매핑 해제되고 핸들이 더 이상 유효하지 않습니다.

응용 프로그램이 `AfxLoadLibraryEx` 여러 `AfxFreeLibrary` 스레드를 `LoadLibraryEx` 사용하고 MFC 확장 `FreeLibrary`DLL을 동적으로 로드하는 경우 Win32 함수 및 대신 사용하고 사용해야 합니다. MFC 확장 DLL을 로드하고 언로드할 때 실행되는 시작 및 종료 코드가 전역 MFC 상태를 손상시키지 않도록 합니다. `AfxLoadLibraryEx` `AfxFreeLibrary`

응용 `AfxLoadLibraryEx` 프로그램에서 사용하려면 DLL 버전의 MFC에 동적으로 연결해야 합니다. Afxdll_.h에 `AfxLoadLibraryEx`대한 헤더 파일은 MFC가 응용 프로그램에 DLL로 연결된 경우에만 포함됩니다. MFC 확장 DLL을 사용하거나 만들려면 MFC의 DLL 버전에 연결해야 하기 때문에 이 요구 사항은 의도적으로 사용됩니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdll_.h

## <a name="afxmenutearoffmanager"></a><a name="afxmenutearoffmanager"></a>아프메뉴티어오프매니저

글로벌 [찢어짐 메뉴 관리자에](cmenutearoffmanager-class.md)대한 포인터 .

### <a name="syntax"></a>구문

```cpp
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxmenutearoffmanager.h

## <a name="afxmousemanager"></a><a name="afxmousemanager"></a>아fx마우스매니저

글로벌 마우스 [관리자에](cmousemanager-class.md)대한 포인터 .

### <a name="syntax"></a>구문

```cpp
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxmousemanager.h

## <a name="afxregisterclass"></a><a name="afxregisterclass"></a>Afx레지스터 클래스

이 함수를 사용하여 MFC를 사용하는 DLL에서 창 클래스를 등록합니다.

```cpp
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>매개 변수

*lpWndClass*\
등록할 창 클래스에 대한 정보가 포함된 [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) 구조에 대한 포인터입니다. 이 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

### <a name="return-value"></a>Return Value

TRUE 클래스가 성공적으로 등록된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 함수를 사용하면 DLL이 언로드될 때 클래스가 자동으로 등록 취소됩니다.

DLL이 아닌 빌드에서 `AfxRegisterClass` 식별자는 응용 프로그램에 등록된 클래스가 자동으로 `RegisterClass`등록 취소되므로 Windows 함수에 매핑되는 매크로로 정의됩니다. 을 대신 `AfxRegisterClass` 사용하는 경우 응용 프로그램과 DLL에서 모두 변경하지 않고 코드를 사용할 수 있습니다. `RegisterClass`

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxregisterwndclass"></a><a name="afxregisterwndclass"></a>AfxRegisterWndClass

사용자 고유의 창 클래스를 등록할 수 있습니다.

```cpp
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>매개 변수

*n클래스스타일*\
창 클래스에 대해 비트와이즈** OR(&#124;) **연산자를 사용하여 만든 Windows 클래스 스타일 또는 스타일 조합을 지정합니다. 클래스 스타일 목록은 Windows [SDK의 WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) 구조를 참조하십시오. NULL이면 기본값은 다음과 같이 설정됩니다.

- 사용자가 마우스를 두 번 클릭할 때 창 프로시저로 두 번 클릭 메시지를 보내는 CS_DBLCLKS 마우스 스타일을 설정합니다.

- 화살표 커서 스타일을 Windows 표준 IDC_ARROW 설정합니다.

- 배경 브러시를 NULL로 설정하여 창이 배경을 지우지 않도록 합니다.

- 아이콘을 표준, 흔들기 플래그 Windows 로고 아이콘으로 설정합니다.

*h커서*\
창 클래스에서 만든 각 창에 설치할 커서 리소스에 대한 핸들을 지정합니다. 기본값 **0을**사용하면 표준 IDC_ARROW 커서를 받게 됩니다.

*hbr배경*\
창 클래스에서 만든 각 창에 설치할 브러시 리소스에 대한 핸들을 지정합니다. 기본값 **0을**사용하는 경우 NULL 백그라운드 브러시가 있으며 기본적으로 [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)처리하는 동안 창이 배경을 지우지 않습니다.

*히콘 (것)이 많은*\
창 클래스에서 만든 각 창에 설치할 아이콘 리소스에 대한 핸들을 지정합니다. 기본값 **0을**사용하는 경우 표준 물결 모양의 Windows 로고 아이콘이 표시됩니다.

### <a name="return-value"></a>Return Value

클래스 이름을 포함하는 null 종료 된 문자열입니다. 이 클래스 이름을 `Create` 멤버 함수 `CWnd` 또는 다른 **CWnd-파생**클래스에 전달하여 창을 만들 수 있습니다. 이름은 Microsoft 재단 클래스 라이브러리에서 생성됩니다.

> [!NOTE]
> 반환 값은 정적 버퍼에 대한 포인터입니다. 이 문자열을 저장하려면 변수에 `CString` 할당합니다.

### <a name="remarks"></a>설명

Microsoft 재단 클래스 라이브러리는 자동으로 여러 표준 창 클래스를 등록합니다. 사용자 고유의 창 클래스를 등록하려면 이 함수를 호출합니다.

클래스에 `AfxRegisterWndClass` 등록된 이름은 매개 변수에만 따라 다릅니다. 동일한 매개 `AfxRegisterWndClass` 변수를 사용하여 여러 번 호출하는 경우 첫 번째 호출에서만 클래스를 등록합니다. 나중에 동일한 `AfxRegisterWndClass` 매개 변수를 사용하여 호출하여 이미 등록된 클래스 이름을 반환합니다.

각 클래스에 대해 별도의 창 클래스를 가져오는 대신 동일한 매개 변수를 가진 여러 CWnd 파생 클래스를 호출하는 `AfxRegisterWndClass` 경우 각 클래스는 동일한 창 클래스를 공유합니다. 이 공유는 CS_CLASSDC 클래스 스타일을 사용하는 경우 문제가 발생할 수 있습니다. 여러 CS_CLASSDC 창 클래스 대신 하나의 CS_CLASSDC 창 클래스만 종료됩니다. 해당 클래스를 사용하는 모든 C++ 창은 동일한 DC를 공유합니다. 이 문제를 방지하려면 [AfxRegisterClass에](#afxregisterclass) 전화하여 클래스를 등록하십시오.

윈도우 클래스 등록 및 기능에 대한 자세한 내용은 기술 노트 [TN001: 창 클래스 등록을](../../mfc/tn001-window-class-registration.md) `AfxRegisterWndClass` 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a>AfxSetPer사용자 등록

응용 프로그램이 레지스트리 액세스를**HKEY_CURRENT_USER(HKCU)** 노드로 리디렉션할지 여부를 설정합니다. **HKEY_CURRENT_USER**

```cpp
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*\
【인】 TRUE는 레지스트리 정보가 HKCU 노드로 전달됨을 나타냅니다. FALSE는 응용 프로그램이 레지스트리 정보를 기본 노드에 기록했음을 나타냅니다. 기본 노드는 **HKEY_CLASSES_ROOT** **HKEY_CLASSES_ROOT(HKCR)입니다.**

### <a name="remarks"></a>설명

Windows Vista 이전에는 레지스트리에 액세스한 응용 프로그램이 **일반적으로 HKEY_CLASSES_ROOT** 노드를 사용했습니다. 그러나 Windows Vista 또는 이후 운영 체제에서는 HKCR에 쓸 수 있도록 상승 모드에서 응용 프로그램을 실행해야 합니다.

이 방법을 사용하면 응용 프로그램이 상승 된 모드에서 실행되지 않고 레지스트리를 읽고 쓸 수 있습니다. 그것은 HKCR에서 HKCU로 레지스트리 액세스를 리디렉션하여 작동합니다. 자세한 내용은 [링커 속성 페이지를](../../build/reference/linker-property-pages.md)참조하십시오.

레지스트리 리디렉션을 사용하도록 설정하면 프레임워크가 HKCR에서 **HKEY_CURRENT_USER\Software\Class로**액세스를 리디렉션합니다. MFC 및 ATL 프레임워크만 리디렉션의 영향을 받습니다.

기본 구현은 HKCR 아래의 레지스트리에 액세스합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxstat_.h

## <a name="afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a>AfxSet리소스핸들

이 함수를 사용하여 응용 프로그램의 기본 리소스가 로드되는 위치를 결정하는 HINSTANCE 핸들을 설정합니다.

```cpp
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>매개 변수

*힌스트리소스*\
에 대한 인스턴스 또는 모듈 핸들입니다. 응용 프로그램의 리소스가 로드되는 EXE 또는 DLL 파일입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxshellmanager"></a><a name="afxshellmanager"></a>아프쉘매니저

전역 셸 [관리자에](cshellmanager-class.md)대한 포인터입니다.

### <a name="syntax"></a>구문

```cpp
CShellManager* afxShellManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxshellmanager.h

## <a name="afxsocketinit"></a><a name="afxsocketinit"></a>아fx소켓이니트

`CWinApp::InitInstance` 재정의에서 이 함수를 호출하여 Windows 소켓을 초기화합니다.

```cpp
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>매개 변수

*lpwsaData*\
[WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) 구조에 대한 포인터입니다. *lpwsaData* NULL과 같지 않은 경우 `WSADATA` 구조의 주소는 `WSAStartup`에 대한 호출로 채워집니다. 또한 이 함수는 `WSACleanup` 응용 프로그램이 종료되기 전에 호출되도록 합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

정적으로 연결된 MFC 응용 프로그램에서 보조 스레드에서 MFC 소켓을 `AfxSocketInit` 사용하는 경우 소켓을 사용하여 소켓 라이브러리를 초기화하는 각 스레드를 호출해야 합니다. 기본적으로 기본 `AfxSocketInit` 스레드에서만 호출됩니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxsock.h

## <a name="afxusertoolsmanager"></a><a name="afxusertoolsmanager"></a>AfxUserTools매니저

글로벌 사용자 [도구 관리자에](cusertoolsmanager-class.md)대한 포인터 .

### <a name="syntax"></a>구문

```cpp
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxusertoolsmanager.h

## <a name="afxwininit"></a><a name="afxwininit"></a>아프스위니트

이 함수는 Gui 기반 응용 `WinMain` 프로그램의 [CWinApp](../../mfc/reference/cwinapp-class.md) 초기화의 일부로 MFC 제공 함수에 의해 호출되어 MFC를 초기화합니다.

```cpp
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>매개 변수

*h인스턴스*\
현재 실행 중인 모듈의 핸들입니다.

*hPrevInstance*\
응용 프로그램의 이전 인스턴스에 대한 핸들입니다. Win32 기반 응용 프로그램의 경우 이 매개 변수는 항상 **NULL입니다.**

*lpCmdLine*\
응용 프로그램에 대 한 명령줄을 지정 하는 null 종료 된 문자열을 가리킵니다.

*nCmdShow*\
GUI 응용 프로그램의 기본 창이 표시되는 방법을 지정합니다.

### <a name="remarks"></a>설명

MFC에서 제공된 `WinMain` 기능을 사용하지 않는 콘솔 응용 프로그램의 경우 `AfxWinInit` MFC를 초기화하기 위해 직접 호출해야 합니다.

자신을 호출하는 `AfxWinInit` 경우 클래스의 인스턴스를 `CWinApp` 선언해야 합니다. 콘솔 응용 프로그램의 경우 고유한 클래스를 `CWinApp` 파생하지 않고 `CWinApp` 직접 인스턴스를 사용하도록 선택할 수 있습니다. 이 기술은 **기본**을 구현할 때 응용 프로그램에 대한 모든 기능을 그대로 두려는 경우에 적합합니다.

> [!NOTE]
> 어셈블리에 대한 활성화 컨텍스트를 만들 때 MFC는 사용자 모듈에서 제공하는 매니페스트 리소스를 사용합니다. 활성화 컨텍스트는 `AfxWinInit`에서 만듭니다. 자세한 내용은 [MFC 모듈 상태의 활성화 컨텍스트 지원을](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="see-also"></a>참고 항목

[매크로 및 글로벌](mfc-macros-and-globals.md)\
[CWinApp 클래스](cwinapp-class.md)\
[C컨텍스트 메뉴관리자 클래스](ccontextmenumanager-class.md)\
[CWnd 클래스](cwnd-class.md)\
[CFrameWndEx 클래스](cframewndex-class.md)\
[CMFC툴바 클래스](cmfctoolbar-class.md)\
[C키보드관리자 클래스](ckeyboardmanager-class.md)\
[CMenuTearOff관리자 클래스](cmenutearoffmanager-class.md)\
[C마우스관리자 클래스](cmousemanager-class.md)\
[CShellManager 클래스](cshellmanager-class.md)\
[CUserToolsManager 클래스](cusertoolsmanager-class.md)
