---
title: CWinThread 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinThread
- AFXWIN/CWinThread
- AFXWIN/CWinThread::CWinThread
- AFXWIN/CWinThread::CreateThread
- AFXWIN/CWinThread::ExitInstance
- AFXWIN/CWinThread::GetMainWnd
- AFXWIN/CWinThread::GetThreadPriority
- AFXWIN/CWinThread::InitInstance
- AFXWIN/CWinThread::IsIdleMessage
- AFXWIN/CWinThread::OnIdle
- AFXWIN/CWinThread::PostThreadMessage
- AFXWIN/CWinThread::PreTranslateMessage
- AFXWIN/CWinThread::ProcessMessageFilter
- AFXWIN/CWinThread::ProcessWndProcException
- AFXWIN/CWinThread::PumpMessage
- AFXWIN/CWinThread::ResumeThread
- AFXWIN/CWinThread::Run
- AFXWIN/CWinThread::SetThreadPriority
- AFXWIN/CWinThread::SuspendThread
- AFXWIN/CWinThread::m_bAutoDelete
- AFXWIN/CWinThread::m_hThread
- AFXWIN/CWinThread::m_nThreadID
- AFXWIN/CWinThread::m_pActiveWnd
- AFXWIN/CWinThread::m_pMainWnd
helpviewer_keywords:
- CWinThread [MFC], CWinThread
- CWinThread [MFC], CreateThread
- CWinThread [MFC], ExitInstance
- CWinThread [MFC], GetMainWnd
- CWinThread [MFC], GetThreadPriority
- CWinThread [MFC], InitInstance
- CWinThread [MFC], IsIdleMessage
- CWinThread [MFC], OnIdle
- CWinThread [MFC], PostThreadMessage
- CWinThread [MFC], PreTranslateMessage
- CWinThread [MFC], ProcessMessageFilter
- CWinThread [MFC], ProcessWndProcException
- CWinThread [MFC], PumpMessage
- CWinThread [MFC], ResumeThread
- CWinThread [MFC], Run
- CWinThread [MFC], SetThreadPriority
- CWinThread [MFC], SuspendThread
- CWinThread [MFC], m_bAutoDelete
- CWinThread [MFC], m_hThread
- CWinThread [MFC], m_nThreadID
- CWinThread [MFC], m_pActiveWnd
- CWinThread [MFC], m_pMainWnd
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
ms.openlocfilehash: f2e95dd3ba8be31633590e37d95dedc8749ebdd8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367414"
---
# <a name="cwinthread-class"></a>CWinThread 클래스

애플리케이션 내의 실행 스레드를 나타냅니다.

## <a name="syntax"></a>구문

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CWinThread::CWinThread](#cwinthread)|`CWinThread` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CWinThread::만들기 스레드](#createthread)|`CWinThread` 개체 실행을 시작합니다.|
|[CWinThread::종료 인스턴스](#exitinstance)|스레드가 종료될 때 정리하려면 재정의합니다.|
|[CWinThread::GetMainWnd](#getmainwnd)|스레드의 주 창에 대한 포인터를 검색합니다.|
|[CWinThread::GetThread 우선 순위](#getthreadpriority)|현재 스레드의 우선 순위를 가져옵니다.|
|[CWinThread::InitInstance](#initinstance)|스레드 인스턴스 초기화를 수행하기 위해 재정의합니다.|
|[CWinThread::IsidleMessage](#isidlemessage)|특수 메시지를 확인합니다.|
|[CWinThread::에유공](#onidle)|스레드별 유휴 시간 처리를 수행하려면 재정의합니다.|
|[CWinThread::P스트스레드메시지](#postthreadmessage)|다른 `CWinThread` 개체에 메시지를 게시합니다.|
|[CWinThread::P다시 번역 메시지](#pretranslatemessage)|메시지가 Windows [함수TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage로](/windows/win32/api/winuser/nf-winuser-dispatchmessage)전달되기 전에 메시지를 필터링합니다.|
|[CWinThread::P로세스메시지필터](#processmessagefilter)|응용 프로그램에 도달하기 전에 특정 메시지를 가로채는 것입니다.|
|[CWinThread::P로스네이션드프로크예외](#processwndprocexception)|스레드의 메시지 및 명령 처리기에 의해 throw된 처리되지 않은 모든 예외를 차단합니다.|
|[CWinThread::PumpMessage](#pumpmessage)|스레드의 메시지 루프를 포함합니다.|
|[CWinThread::다시 시작 스레드](#resumethread)|스레드의 일시 중단 수를 감소시입니다.|
|[CWinThread::실행](#run)|메시지 펌프를 통해 스레드에 대한 기능 제어. 재정의하여 기본 메시지 루프를 사용자 지정합니다.|
|[CWinThread::설정 스레드 우선 순위](#setthreadpriority)|현재 스레드의 우선 순위를 설정합니다.|
|[CWinThread::서스펜드 스레드](#suspendthread)|스레드의 일시 중단 수를 증가시입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CWinThread::연산자 핸들](#operator_handle)|개체의 핸들을 `CWinThread` 검색합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CWinThread::m_bAutoDelete](#m_bautodelete)|스레드 종료 시 개체를 삭제할지 여부를 지정합니다.|
|[CWinThread::m_hThread](#m_hthread)|현재 스레드를 처리합니다.|
|[CWinThread::m_nThreadID](#m_nthreadid)|현재 스레드의 ID입니다.|
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|OLE 서버가 활성 상태일 때 컨테이너 응용 프로그램의 기본 창에 대한 포인터입니다.|
|[CWinThread::m_pMainWnd](#m_pmainwnd)|응용 프로그램의 주 창에 대한 포인터를 보유합니다.|

## <a name="remarks"></a>설명

실행의 주 스레드는 일반적으로 에서 `CWinApp`파생 된 개체에 의해 제공 됩니다. `CWinApp` `CWinThread` 추가 `CWinThread` 개체는 지정된 응용 프로그램 내에서 여러 스레드를 허용합니다.

지원 되는 `CWinThread` 스레드에는 두 가지 일반적인 유형의 작업자 스레드 와 사용자 인터페이스 스레드가 있습니다. 작업자 스레드에는 메시지 펌프가 없습니다. 사용자 인터페이스 스레드에는 메시지 펌프가 있고 시스템에서 받은 메시지를 처리합니다. [CWinApp](../../mfc/reference/cwinapp-class.md) 및 그것에서 파생 된 클래스는 사용자 인터페이스 스레드의 예입니다. 다른 사용자 인터페이스 스레드는 에서 `CWinThread`직접 파생될 수도 있습니다.

클래스의 `CWinThread` 개체는 일반적으로 스레드의 기간 동안 존재 합니다. 이 동작을 수정하려면 [false로 m_bAutoDelete](#m_bautodelete) 설정합니다.

`CWinThread` 클래스는 코드와 MFC를 완전히 스레드로 안전하게 만드는 데 필요합니다. 스레드 관련 정보를 유지 관리하는 데 프레임워크에서 사용하는 `CWinThread` 스레드 로컬 데이터는 개체에서 관리합니다. 스레드 로컬 데이터를 `CWinThread` 처리하기 위한 이러한 종속성 때문에 MFC를 사용하는 모든 스레드는 MFC에서 만들어야 합니다. 예를 들어 런타임 함수에 의해 생성된 스레드는 [_beginthread _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) MFC API를 사용할 수 없습니다.

스레드를 만들려면 [AfxBeginThread](application-information-and-management.md#afxbeginthread)를 호출합니다. 작업자 또는 사용자 인터페이스 스레드를 원하는지 여부에 따라 두 가지 양식이 있습니다. 사용자 인터페이스 스레드를 원하는 경우 `AfxBeginThread` -derive된 `CRuntimeClass` 클래스의 `CWinThread`포인터에 전달합니다. 작업자 스레드를 만들려면 제어 함수에 `AfxBeginThread` 대한 포인터와 제어 함수에 대한 매개 변수를 전달합니다. 작업자 스레드와 사용자 인터페이스 스레드 모두에 대해 우선 순위, 스택 크기, 생성 플래그 및 보안 특성을 수정하는 선택적 매개 변수를 지정할 수 있습니다. `AfxBeginThread`포인터를 새 `CWinThread` 개체에 반환합니다.

호출하는 `AfxBeginThread`대신 -derived `CWinThread`개체를 생성한 `CreateThread`다음 을 호출할 수 있습니다. 이 2단계 구성 방법은 스레드 실행의 연속적인 생성과 종료 사이에 `CWinThread` 개체를 재사용하려는 경우에 유용합니다.

`CWinThread`자세한 내용은 [C++ 및 MFC,](../../parallel/multithreading-with-cpp-and-mfc.md) [멀티스레딩을](../../parallel/multithreading-creating-user-interface-threads.md)사용한 다중 스레딩 문서: 사용자 인터페이스 스레드 만들기, [다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md)및 [다중 스레딩: 동기화 클래스 를 사용하는 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)참조.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cwinthreadcreatethread"></a><a name="createthread"></a>CWinThread::만들기 스레드

호출 프로세스의 주소 공간 내에서 실행할 스레드를 만듭니다.

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>매개 변수

*dwCreateFlags*<br/>
스레드 생성을 제어하는 추가 플래그를 지정합니다. 이 플래그에는 다음 두 값 중 하나가 포함될 수 있습니다.

- CREATE_SUSPENDED 일시 중단 개수로 스레드를 시작합니다. 스레드가 실행되기 전에 [m_bAutoDelete](#m_bautodelete) 또는 파생 `CWinThread` 클래스의 멤버와 같은 개체의 멤버 데이터를 초기화하려면 CREATE_SUSPENDED 사용합니다. 초기화가 완료되면 [CWinThread::ResumeThread를](#resumethread) 사용하여 스레드 실행을 시작합니다. 스레드가 호출될 `CWinThread::ResumeThread` 때까지 실행되지 않습니다.

- **0** 생성 직후 스레드를 시작합니다.

*n스택 크기*<br/>
새 스레드에 대한 스택의 바이트 크기를 지정합니다. **0이면**스택 크기는 프로세스의 기본 스레드와 동일한 크기로 기본설정됩니다.

*lp보안트르*<br/>
스레드에 대한 보안 특성을 지정하는 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

스레드가 성공적으로 생성되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

스레드 `AfxBeginThread` 개체를 만들고 한 단계에서 실행하는 데 사용합니다. 스레드 `CreateThread` 실행의 연속적인 생성과 종료 사이에 스레드 개체를 다시 사용하려는 경우 사용합니다.

## <a name="cwinthreadcwinthread"></a><a name="cwinthread"></a>CWinThread::CWinThread

`CWinThread` 개체를 생성합니다.

```
CWinThread();
```

### <a name="remarks"></a>설명

스레드의 실행을 시작 하려면 [CreateThread](#createthread) 멤버 함수를 호출 합니다. 일반적으로 이 생성자 및 `CreateThread`을 호출하는 [AfxBeginThread를](application-information-and-management.md#afxbeginthread)호출하여 스레드를 만듭니다.

## <a name="cwinthreadexitinstance"></a><a name="exitinstance"></a>CWinThread::종료 인스턴스

거의 재정의된 [Run](#run) 멤버 함수 내에서 프레임워크에서 호출되어 스레드의 이 인스턴스를 종료하거나 [InitInstance](#initinstance) 에 대한 호출이 실패하는 경우

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Return Value

스레드의 종료 코드; 0은 오류가 없음을 나타내고 값이 0보다 큰 값은 오류를 나타냅니다. 이 값은 [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)를 호출하여 검색할 수 있습니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하지 말고 `Run` 멤버 함수 내에서 호출하지 마십시오. 이 멤버 함수는 사용자 인터페이스 스레드에서만 사용됩니다.

이 함수의 기본 구현은 `CWinThread` [true인](#m_bautodelete) 경우 m_bAutoDelete 개체를 삭제합니다. 스레드가 종료될 때 추가 정리를 수행하려면 이 함수를 재정의합니다. `ExitInstance` 구현은 코드가 실행된 후 기본 클래스의 버전을 호출해야 합니다.

## <a name="cwinthreadgetmainwnd"></a><a name="getmainwnd"></a>CWinThread::GetMainWnd

응용 프로그램이 OLE 서버인 경우 이 함수를 호출하여 응용 프로그램 개체의 `m_pMainWnd` 멤버를 직접 참조하는 대신 응용 프로그램의 활성 주 창에 대한 포인터를 검색합니다.

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>Return Value

이 함수는 두 가지 유형의 창 중 하나에 대한 포인터를 반환합니다. 스레드가 OLE 서버의 일부이고 활성 컨테이너 내에서 활성 상태인 개체가 있는 경우 이 함수는 [개체의 CWinApp:m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) 데이터 멤버를 반환합니다. `CWinThread`

컨테이너 내에 활성 상태인 개체가 없거나 응용 프로그램이 OLE 서버가 아닌 경우 이 함수는 스레드 개체의 [m_pMainWnd](#m_pmainwnd) 데이터 멤버를 반환합니다.

### <a name="remarks"></a>설명

사용자 인터페이스 스레드의 경우 이는 응용 프로그램 `m_pActiveWnd` 개체의 멤버를 직접 참조하는 것과 같습니다.

애플리케이션이 OLE 서버가 아닌 경우 이 함수의 호출은 애플리케이션 개체의 `m_pMainWnd` 멤버를 직접 참조하는 것과 동일합니다.

이 함수를 재정의하여 기본 동작을 수정합니다.

## <a name="cwinthreadgetthreadpriority"></a><a name="getthreadpriority"></a>CWinThread::GetThread 우선 순위

이 스레드의 현재 스레드 우선 순위 수준을 가져옵니다.

```
int GetThreadPriority();
```

### <a name="return-value"></a>Return Value

우선 순위 클래스 내의 현재 스레드 우선 순위 수준입니다. 반환되는 값은 우선 순위가 가장 높은 값에서 가장 낮은 값으로 나열된 다음 중 하나입니다.

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

이러한 우선 순위에 대한 자세한 내용은 Windows SDK의 [SetThreadPriority를](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 참조하십시오.

## <a name="cwinthreadinitinstance"></a><a name="initinstance"></a>CWinThread::InitInstance

`InitInstance`사용자 인터페이스 스레드의 각 새 인스턴스를 초기화하려면 재정의해야 합니다.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Return Value

초기화가 성공하면 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

일반적으로 스레드를 `InitInstance` 처음 만들 때 완료해야 하는 작업을 수행하도록 재정의합니다.

이 멤버 함수는 사용자 인터페이스 스레드에서만 사용됩니다. [AfxBeginThread에](application-information-and-management.md#afxbeginthread)전달 된 제어 함수에서 작업자 스레드의 초기화를 수행 합니다.

## <a name="cwinthreadisidlemessage"></a><a name="isidlemessage"></a>CWinThread::IsidleMessage

특정 메시지가 생성된 `OnIdle` 후 호출되지 않도록 이 함수를 재정의합니다.

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
처리 중인 현재 메시지를 가리킵니다.

### <a name="return-value"></a>Return Value

메시지를 처리 `OnIdle` 한 후 호출해야하는 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

기본 구현은 캐리지 트 에 의해 생성 된 중복 마우스 메시지 및 메시지 후 호출 `OnIdle` 하지 않습니다.

응용 프로그램이 짧은 타이머를 만든 `OnIdle` 경우 자주 호출되어 성능 문제가 발생합니다. 이러한 응용 프로그램의 성능을 향상 시키기 `IsIdleMessage` 위해 다음과 `CWinApp`같이 WM_TIMER 메시지를 확인 하려면 응용 프로그램의 -derived 클래스에서 재정의:

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

이러한 방식으로 WM_TIMER 처리하면 짧은 타이머를 사용하는 응용 프로그램의 성능이 향상됩니다.

## <a name="cwinthreadm_bautodelete"></a><a name="m_bautodelete"></a>CWinThread::m_bAutoDelete

스레드 종료 시 `CWinThread` 개체를 자동으로 삭제할지 여부를 지정합니다.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>설명

`m_bAutoDelete` 데이터 멤버는 BOOL 형식의 공용 변수입니다.

값은 `m_bAutoDelete` 기본 스레드 핸들이 닫히는 방식에는 영향을 주지 않지만 핸들을 닫는 타이밍에는 영향을 미칩니다. 스레드 핸들은 항상 `CWinThread` 개체가 제거될 때 닫힙니다.

## <a name="cwinthreadm_hthread"></a><a name="m_hthread"></a>CWinThread::m_hThread

이 `CWinThread`에 첨부 된 스레드에 핸들 .

```
HANDLE m_hThread;
```

### <a name="remarks"></a>설명

`m_hThread` 데이터 멤버는 HANDLE 형식의 공용 변수입니다. 기본 커널 스레드 개체가 현재 존재하고 핸들이 아직 닫히지 않은 경우에만 유효합니다.

CWinThread 소멸자는 에서 `m_hThread`CloseHandle을 호출합니다. 스레드가 종료될 때 [m_bAutoDelete](#m_bautodelete) TRUE인 경우 CWinThread 개체가 소멸되어 CWinThread 개체 및 해당 멤버 변수에 대한 포인터가 무효화됩니다. `m_hThread` 스레드 종료 값을 확인하거나 신호를 기다리려면 멤버가 필요할 수 있습니다. 스레드 실행 중 및 종료 `m_hThread` 후 CWinThread 개체와 해당 `m_bAutoDelete` 멤버를 유지하려면 스레드 실행을 계속하려면 FALSE로 설정합니다. 그렇지 않으면 스레드가 종료되고 CWinThread 개체를 소멸하고 핸들을 사용하기 전에 닫을 수 있습니다. 이 기술을 사용하는 경우 CWinThread 개체를 삭제해야 합니다.

## <a name="cwinthreadm_nthreadid"></a><a name="m_nthreadid"></a>CWinThread::m_nThreadID

이에 `CWinThread`첨부 된 스레드의 ID .

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>설명

`m_nThreadID` 데이터 멤버는 DWORD 형식의 공용 변수입니다. 기본 커널 스레드 개체가 현재 존재하는 경우에만 유효합니다.
또한 [m_hThread](#m_hthread) 일생에 대한 발언을 참조하십시오.

### <a name="example"></a>예제

  [AfxGetThread에](application-information-and-management.md#afxgetthread)대한 예제를 참조하십시오.

## <a name="cwinthreadm_pactivewnd"></a><a name="m_pactivewnd"></a>CWinThread::m_pActiveWnd

이 데이터 멤버를 사용하여 스레드의 활성 창 개체에 대한 포인터를 저장합니다.

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>설명

참조된 창이 닫히면 Microsoft Foundation 클래스 `m_pActiveWnd` 라이브러리가 스레드를 자동으로 종료합니다. 이 스레드가 응용 프로그램의 기본 스레드인 경우 응용 프로그램도 종료됩니다. 이 데이터 멤버가 NULL이면 응용 프로그램의 `CWinApp` 개체에 대한 활성 창이 상속됩니다. `m_pActiveWnd`는 형식의 `CWnd*`공용 변수입니다.

일반적으로 재정의할 `InitInstance`때 이 멤버 변수를 설정합니다. 작업자 스레드에서 이 데이터 멤버의 값은 상위 스레드에서 상속됩니다.

## <a name="cwinthreadm_pmainwnd"></a><a name="m_pmainwnd"></a>CWinThread::m_pMainWnd

이 데이터 멤버를 사용하여 스레드의 기본 창 개체에 대한 포인터를 저장합니다.

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>설명

참조된 창이 닫히면 Microsoft Foundation 클래스 `m_pMainWnd` 라이브러리가 스레드를 자동으로 종료합니다. 이 스레드가 응용 프로그램의 기본 스레드인 경우 응용 프로그램도 종료됩니다. 이 데이터 멤버가 NULL이면 응용 프로그램의 `CWinApp` 개체에 대한 기본 창이 스레드를 종료할 시기를 결정하는 데 사용됩니다. `m_pMainWnd`는 형식의 `CWnd*`공용 변수입니다.

일반적으로 재정의할 `InitInstance`때 이 멤버 변수를 설정합니다. 작업자 스레드에서 이 데이터 멤버의 값은 상위 스레드에서 상속됩니다.

## <a name="cwinthreadonidle"></a><a name="onidle"></a>CWinThread::에유공

유휴 시간 처리를 수행하려면 이 멤버 함수를 재정의합니다.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>매개 변수

*l카운트*<br/>
스레드의 메시지 큐가 `OnIdle` 비어 있을 때 매번 증가하는 카운터가 호출됩니다. 이 개수는 새 메시지가 처리될 때마다 0으로 재설정됩니다. *lCount* 매개 변수를 사용하여 메시지를 처리하지 않고 스레드가 유휴 상태였던 상대적인 시간을 확인할 수 있습니다.

### <a name="return-value"></a>Return Value

비영제로 더 많은 유휴 처리 시간을 수신; 유휴 처리 시간이 더 이상 필요하지 않은 경우 0입니다.

### <a name="remarks"></a>설명

`OnIdle`스레드의 메시지 큐가 비어 있을 때 기본 메시지 루프에서 호출됩니다. 재정의를 사용하여 사용자 고유의 백그라운드 유휴 처리기 작업을 호출합니다.

`OnIdle`0을 반환하여 추가 유휴 처리 시간이 필요하지 없음을 나타냅니다. *lCount* 매개 변수는 메시지 큐가 비어 있고 새 메시지가 처리될 때마다 0으로 재설정될 때마다 호출될 때마다 증가됩니다. `OnIdle` 이 개수에 따라 다른 유휴 루틴을 호출할 수 있습니다.

이 멤버 함수의 기본 구현은 임시 개체와 사용되지 않는 동적 링크 라이브러리를 메모리에서 해제합니다.

이 멤버 함수는 사용자 인터페이스 스레드에서만 사용됩니다.

응용 프로그램이 반환될 `OnIdle` 때까지 메시지를 처리할 수 없으므로 이 함수에서 긴 작업을 수행하지 마십시오.

## <a name="cwinthreadoperator-handle"></a><a name="operator_handle"></a>CWinThread::연산자 핸들

개체의 핸들을 `CWinThread` 검색합니다.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Return Value

성공하면 스레드 개체의 핸들; 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

핸들을 사용하여 Windows API를 직접 호출합니다.

## <a name="cwinthreadpostthreadmessage"></a><a name="postthreadmessage"></a>CWinThread::P스트스레드메시지

사용자 정의 메시지를 다른 `CWinThread` 개체에 게시하도록 호출됩니다.

```
BOOL PostThreadMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*메시지*<br/>
사용자 정의 메시지의 ID입니다.

*wParam*<br/>
첫 번째 메시지 매개 변수입니다.

*lParam*<br/>
두 번째 메시지 매개 변수입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

게시된 메시지는 메시지 맵 매크로 ON_THREAD_MESSAGE 의해 적절한 메시지 처리기에 매핑됩니다.

> [!NOTE]
> [PostThreadMessage를](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)호출하면 메시지가 스레드의 메시지 큐에 배치됩니다. 그러나 이 방법으로 게시된 메시지는 창과 연결되지 않으므로 MFC는 메시지 또는 명령 처리기로 메시지를 전달하지 않습니다. 이러한 메시지를 처리하려면 CWinApp `PreTranslateMessage()` 파생 클래스의 기능을 재정의하고 메시지를 수동으로 처리합니다.

## <a name="cwinthreadpretranslatemessage"></a><a name="pretranslatemessage"></a>CWinThread::P다시 번역 메시지

이 함수를 재정의하여 Windows 함수 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage로](/windows/win32/api/winuser/nf-winuser-dispatchmessage)디스패치하기 전에 창 메시지를 필터링합니다.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
처리할 메시지가 포함된 [MSG 구조를](/windows/win32/api/winuser/ns-winuser-msg) 가리킵니다.

### <a name="return-value"></a>Return Value

메시지가 완전히 처리되고 `PreTranslateMessage` 더 이상 처리되지 않아야 하는 경우 Nonzero입니다. 메시지가 정상적인 방식으로 처리되어야 하는 경우 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 사용자 인터페이스 스레드에서만 사용됩니다.

## <a name="cwinthreadprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinThread::P로세스메시지필터

프레임워크의 후크 함수는 이 멤버 함수를 호출하여 특정 Windows 메시지를 필터링하고 응답합니다.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>매개 변수

*코드*<br/>
후크 코드를 지정합니다. 이 멤버 함수는 코드를 사용하여 *lpMsg를* 처리하는 방법을 결정합니다.

*lpMsg*<br/>
윈도우 [MSG 구조에](/windows/win32/api/winuser/ns-winuser-msg)대한 포인터 .

### <a name="return-value"></a>Return Value

메시지가 처리되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

후크 함수는 이벤트를 응용 프로그램의 일반 메시지 처리로 보내기 전에 처리합니다.

이 고급 기능을 재정의하는 경우 기본 클래스 버전을 호출하여 프레임워크의 후크 처리를 유지관리해야 합니다.

## <a name="cwinthreadprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinThread::P로스네이션드프로크예외

프레임워크는 처리기가 스레드의 메시지 또는 명령 처리기 중 하나에서 throw된 예외를 catch하지 않을 때마다 이 멤버 함수를 호출합니다.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*전자*<br/>
처리되지 않은 예외를 가리킵니다.

*pMsg*<br/>
프레임워크가 예외를 throw하게 한 Windows 메시지에 대한 정보가 포함된 [MSG 구조를](/windows/win32/api/winuser/ns-winuser-msg) 가리킵니다.

### <a name="return-value"></a>Return Value

WM_CREATE 예외가 생성되는 경우 -1; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수를 직접 호출하지 마십시오.

이 멤버 함수의 기본 구현은 다음 메시지에서 생성된 예외만 처리합니다.

|명령|작업|
|-------------|------------|
|Wm_create|실패|
|Wm_paint|영향을 받는 창의 유효성을 검사하여 다른 WM_PAINT 메시지가 생성되지 않도록 합니다.|

이 멤버 함수를 재정의하여 예외를 전역으로 처리합니다. 기본 동작을 표시하려는 경우에만 기본 기능을 호출합니다.

이 멤버 함수는 메시지 펌프가 있는 스레드에서만 사용됩니다.

## <a name="cwinthreadpumpmessage"></a><a name="pumpmessage"></a>CWinThread::PumpMessage

스레드의 메시지 루프를 포함합니다.

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>설명

`PumpMessage`여기에는 스레드의 메시지 루프가 포함되어 있습니다. `PumpMessage`스레드의 `CWinThread` 메시지를 펌핑하기 위해 호출됩니다. 직접 호출하여 `PumpMessage` 메시지를 강제로 처리하거나 재정의하여 `PumpMessage` 기본 동작을 변경할 수 있습니다.

직접 `PumpMessage` 호출하고 기본 동작을 재정의하는 것은 고급 사용자에게만 권장됩니다.

## <a name="cwinthreadresumethread"></a><a name="resumethread"></a>CWinThread::다시 시작 스레드

[SuspendThread](#suspendthread) 멤버 함수에 의해 일시 중단된 스레드 또는 CREATE_SUSPENDED 플래그로 만든 스레드의 실행을 다시 시작하려면 호출됩니다.

```
DWORD ResumeThread();
```

### <a name="return-value"></a>Return Value

스레드의 이전 일시 중단이 성공하면 계산됩니다. `0xFFFFFFFF` 그렇지 않으면. 반환 값이 0이면 현재 스레드가 일시 중단되지 않았습니다. 반환 값이 1인 경우 스레드가 일시 중단되었지만 이제 다시 시작됩니다. 반환 값이 1보다 크면 스레드가 일시 중단된 상태로 유지됩니다.

### <a name="remarks"></a>설명

현재 스레드의 일시 중단 수가 하나씩 줄어듭니다. 일시 중단 수가 0으로 줄어들면 스레드는 실행을 다시 시작합니다. 그렇지 않으면 스레드가 일시 중단된 상태로 유지됩니다.

## <a name="cwinthreadrun"></a><a name="run"></a>CWinThread::실행

사용자 인터페이스 스레드에 대한 기본 메시지 루프를 제공합니다.

```
virtual int Run();
```

### <a name="return-value"></a>Return Value

스레드에서 반환되는 **int** 값입니다. 이 값은 [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)를 호출하여 검색할 수 있습니다.

### <a name="remarks"></a>설명

`Run`응용 프로그램이 [WM_QUIT](/windows/win32/winmsg/wm-quit) 메시지를 받을 때까지 Windows 메시지를 획득하고 디스패치합니다. 스레드의 메시지 큐에 현재 메시지가 `Run` 없는 `OnIdle` 경우 유휴 시간 처리를 수행 하기 위한 호출입니다. 들어오는 메시지는 특수 처리를 위해 [PreTranslateMessage](#pretranslatemessage) 멤버 기능으로 이동한 다음 표준 키보드 번역을 위해 Windows 기능 [TranslateMessage로](/windows/win32/api/winuser/nf-winuser-translatemessage) 이동합니다. 마지막으로 [디스패치메시지](/windows/win32/api/winuser/nf-winuser-dispatchmessage) 윈도우 함수가 호출됩니다.

`Run`재정의된 경우는 거의 없지만 특수 동작을 구현하기 위해 재정의할 수 있습니다.

이 멤버 함수는 사용자 인터페이스 스레드에서만 사용됩니다.

## <a name="cwinthreadsetthreadpriority"></a><a name="setthreadpriority"></a>CWinThread::설정 스레드 우선 순위

이 함수는 우선 순위 클래스 내에서 현재 스레드의 우선 순위 수준을 설정합니다.

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>매개 변수

*n우선 순위*<br/>
우선 순위 클래스 내에서 새 스레드 우선 순위 수준을 지정합니다. 이 매개 변수는 우선 순위가 가장 높은 값에서 가장 낮은 값으로 나열된 다음 값 중 하나여야 합니다.

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

이러한 우선 순위에 대한 자세한 내용은 Windows SDK의 [SetThreadPriority를](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 참조하십시오.

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닌 경우; 그렇지 않으면 0.

### <a name="remarks"></a>설명

[CreateThread가](#createthread) 성공적으로 반환된 후에만 호출할 수 있습니다.

## <a name="cwinthreadsuspendthread"></a><a name="suspendthread"></a>CWinThread::서스펜드 스레드

현재 스레드의 일시 중단 수를 증가합니다.

```
DWORD SuspendThread();
```

### <a name="return-value"></a>Return Value

스레드의 이전 일시 중단이 성공하면 계산됩니다. `0xFFFFFFFF` 그렇지 않으면.

### <a name="remarks"></a>설명

스레드에 일시 중단 수가 0보다 초과하면 해당 스레드가 실행되지 않습니다. [ResumeThread](#resumethread) 멤버 함수를 호출하여 스레드를 다시 시작할 수 있습니다.

## <a name="see-also"></a>참고 항목

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWinApp 클래스](../../mfc/reference/cwinapp-class.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)
