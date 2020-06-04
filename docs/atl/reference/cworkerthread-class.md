---
title: CWorkerThread 클래스
ms.date: 11/04/2016
f1_keywords:
- CWorkerThread
- ATLUTIL/ATL::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::AddHandle
- ATLUTIL/ATL::CWorkerThread::AddTimer
- ATLUTIL/ATL::CWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CWorkerThread::GetThreadId
- ATLUTIL/ATL::CWorkerThread::Initialize
- ATLUTIL/ATL::CWorkerThread::RemoveHandle
- ATLUTIL/ATL::CWorkerThread::Shutdown
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
ms.openlocfilehash: 05e6b432d44927fa7e276792643e29c80c42d822
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330218"
---
# <a name="cworkerthread-class"></a>CWorkerThread 클래스

이 클래스는 작업자 스레드를 만들거나 기존 스레드를 사용하고, 하나 이상의 커널 개체 핸들을 대기하고, 핸들 중 하나가 신호를 받으면 지정된 클라이언트 함수를 실행합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class ThreadTraits = DefaultThreadTraits>
class CWorkerThread
```

### <a name="parameters"></a>매개 변수

*스레드 특성*<br/>
[CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) 또는 [Win32ThreadTraits와](../../atl/reference/win32threadtraits-class.md)같은 스레드 생성 함수를 제공하는 클래스입니다.

## <a name="members"></a>멤버

### <a name="protected-structures"></a>보호된 구조

|속성|Description|
|----------|-----------------|
|`WorkerClientEntry`||

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CWorkerThread:::CWorkerThread](#cworkerthread)|작업자 스레드의 생성자입니다.|
|[CWorkerThread::~CWorkerThread](#dtor)|작업자 스레드의 소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CWorkerThread::추가 핸들](#addhandle)|이 메서드를 호출하여 작업자 스레드에서 유지 관리하는 목록에 대기 가능한 개체의 핸들을 추가합니다.|
|[CWorkerThread::추가 타이머](#addtimer)|이 메서드를 호출하여 작업자 스레드에서 유지 관리하는 목록에 주기적인 대기 가능한 타이머를 추가합니다.|
|[CWorkerThread::GetThread핸들](#getthreadhandle)|이 메서드를 호출하여 작업자 스레드의 스레드 핸들을 가져옵니다.|
|[CWorkerThread::GetThreadId](#getthreadid)|이 메서드를 호출하여 작업자 스레드의 스레드 ID를 가져옵니다.|
|[CWorkerThread::초기화](#initialize)|이 메서드를 호출하여 작업자 스레드를 초기화합니다.|
|[CWorkerThread::제거 핸들](#removehandle)|대기 가능한 개체 목록에서 핸들을 제거하려면 이 메서드를 호출합니다.|
|[CWorkerThread::종료](#shutdown)|이 메서드를 호출하여 작업자 스레드를 종료합니다.|

## <a name="remarks"></a>설명

### <a name="to-use-cworkerthread"></a>CWorkerThread를 사용하려면

1. 이 클래스의 인스턴스를 만듭니다.

1. [CWorkerThread 호출::초기화.](#initialize)

1. [CWorkerThread::AddHandle](#addhandle) 커널 개체의 핸들 및 [IWorkerThreadClient의](../../atl/reference/iworkerthreadclient-interface.md)구현에 대 한 포인터.

   \- 또는-

   [CWorkerThread::AddTimer](#addtimer) [IWorkerThreadClient의](../../atl/reference/iworkerthreadclient-interface.md)구현에 대 한 포인터를 호출 합니다.

1. [IWorkerThreadClient::실행](../../atl/reference/iworkerthreadclient-interface.md#execute) 핸들 또는 타이머 가 신호 될 때 몇 가지 작업을 수행 합니다.

1. 대기 가능한 개체 목록에서 개체를 제거하려면 [CWorkerThread::RemoveHandle](#removehandle)을 호출합니다.

1. 스레드를 종료하려면 [CWorkerThread::Shutdown](#shutdown)을 호출합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="cworkerthreadaddhandle"></a><a name="addhandle"></a>CWorkerThread::추가 핸들

이 메서드를 호출하여 작업자 스레드에서 유지 관리하는 목록에 대기 가능한 개체의 핸들을 추가합니다.

```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
대기 가능한 개체에 대한 핸들입니다.

*p 클라이언트*<br/>
핸들이 신호를 받을 때 호출할 개체의 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) 인터페이스에 대한 포인터입니다.

*dwParam*<br/>
핸들이 신호를 받을 때 [IWorkerThreadClient::Execute에](../../atl/reference/iworkerthreadclient-interface.md#execute) 전달할 매개 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[IWorkerThreadClient::Execute는](../../atl/reference/iworkerthreadclient-interface.md#execute) *핸들, hObject가*신호될 때 *pClient를* 통해 호출됩니다.

## <a name="cworkerthreadaddtimer"></a><a name="addtimer"></a>CWorkerThread::추가 타이머

이 메서드를 호출하여 작업자 스레드에서 유지 관리하는 목록에 주기적인 대기 가능한 타이머를 추가합니다.

```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```

### <a name="parameters"></a>매개 변수

*dw간격*<br/>
타이머 의 기간을 밀리초 단위로 지정합니다.

*p 클라이언트*<br/>
핸들이 신호를 받을 때 호출할 개체의 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) 인터페이스에 대한 포인터입니다.

*dwParam*<br/>
핸들이 신호를 받을 때 [IWorkerThreadClient::Execute에](../../atl/reference/iworkerthreadclient-interface.md#execute) 전달할 매개 변수입니다.

*phTimer*<br/>
【아웃】 성공 시 새로 생성된 타이머에 핸들을 받는 HANDLE 변수의 주소입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[IWorkerThreadClient::실행](../../atl/reference/iworkerthreadclient-interface.md#execute) 타이머가 신호될 때 *pClient를* 통해 호출됩니다.

타이머 핸들을 *phTimer에서* [CWorkerThread::RemoveHandle으로](#removehandle) 전달하여 타이머를 닫습니다.

## <a name="cworkerthreadcworkerthread"></a><a name="cworkerthread"></a>CWorkerThread:::CWorkerThread

생성자입니다.

```
CWorkerThread() throw();
```

## <a name="cworkerthreadcworkerthread"></a><a name="dtor"></a>CWorkerThread::~CWorkerThread

소멸자입니다.

```
~CWorkerThread() throw();
```

### <a name="remarks"></a>설명

[CWorkerThread::종료를](#shutdown)호출합니다.

## <a name="cworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CWorkerThread::GetThread핸들

이 메서드를 호출하여 작업자 스레드의 스레드 핸들을 가져옵니다.

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Return Value

작업자 스레드가 초기화되지 않은 경우 스레드 핸들 또는 NULL을 반환합니다.

## <a name="cworkerthreadgetthreadid"></a><a name="getthreadid"></a>CWorkerThread::GetThreadId

이 메서드를 호출하여 작업자 스레드의 스레드 ID를 가져옵니다.

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Return Value

작업자 스레드가 초기화되지 않은 경우 스레드 ID 또는 NULL을 반환합니다.

## <a name="cworkerthreadinitialize"></a><a name="initialize"></a>CWorkerThread::초기화

이 메서드를 호출하여 작업자 스레드를 초기화합니다.

```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```

### <a name="parameters"></a>매개 변수

*pThread*<br/>
기존 작업자 스레드입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 생성 후 또는 [CWorkerThread::Shutdown](#shutdown)을 호출한 후 개체를 초기화하기 위해 호출되어야 합니다.

둘 이상의 `CWorkerThread` 개체가 동일한 작업자 스레드를 사용하도록 하려면 인수를 전달하지 않고 그 중 하나를 `Initialize` 초기화한 다음 해당 개체에 대한 포인터를 다른 개체의 메서드에 전달합니다. 포인터를 사용하여 초기화된 개체는 초기화하는 데 사용되는 개체전에 종료해야 합니다.

기존 개체에 대한 포인터를 사용하여 초기화할 때 해당 메서드의 동작이 어떻게 변경되는지에 대한 자세한 내용은 [CWorkerThread::Shutdown을](#shutdown) 참조하십시오.

## <a name="cworkerthreadremovehandle"></a><a name="removehandle"></a>CWorkerThread::제거 핸들

대기 가능한 개체 목록에서 핸들을 제거하려면 이 메서드를 호출합니다.

```
HRESULT RemoveHandle(HANDLE hObject) throw();
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
제거할 핸들입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

핸들이 제거되면 [IWorkerThreadClient::CloseHandle은 AddHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) 에 전달된 연결된 [AddHandle](#addhandle)개체에서 호출됩니다. 이 호출에 `CWorkerThread` 실패하면 핸들의 Windows [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) 함수를 호출합니다.

## <a name="cworkerthreadshutdown"></a><a name="shutdown"></a>CWorkerThread::종료

이 메서드를 호출하여 작업자 스레드를 종료합니다.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="parameters"></a>매개 변수

*dwWait*<br/>
작업자 스레드가 종료될 때까지 기다리는 시간(밀리초)입니다. ATL_WORKER_THREAD_WAIT 기본값은 10초입니다. 필요한 경우 atlutil.h를 포함하기 전에 이 기호에 대한 사용자 고유의 값을 정의할 수 있습니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 시간 초과 *값인 dwWait*가 초과된 경우와 같이 오류 HRESULT 오류입니다.

### <a name="remarks"></a>설명

개체를 다시 사용 하려면 [CWorkerThread::이](#initialize) 메서드를 호출 한 후 초기화를 호출 합니다.

다른 `Shutdown` `CWorkerThread` 개체에 대한 포인터로 초기화된 개체를 호출하면 아무런 효과가 없으며 항상 S_OK 반환됩니다.

## <a name="see-also"></a>참고 항목

[기본 스레드 특성](atl-typedefs.md#defaultthreadtraits)<br/>
[클래스](../../atl/reference/atl-classes.md)<br/>
[다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md)<br/>
[IWorker스레드클라이언트 인터페이스](../../atl/reference/iworkerthreadclient-interface.md)
