---
title: C스레드풀 클래스
ms.date: 11/04/2016
f1_keywords:
- CThreadPool
- ATLUTIL/ATL::CThreadPool
- ATLUTIL/ATL::CThreadPool::CThreadPool
- ATLUTIL/ATL::CThreadPool::AddRef
- ATLUTIL/ATL::CThreadPool::GetNumThreads
- ATLUTIL/ATL::CThreadPool::GetQueueHandle
- ATLUTIL/ATL::CThreadPool::GetSize
- ATLUTIL/ATL::CThreadPool::GetTimeout
- ATLUTIL/ATL::CThreadPool::Initialize
- ATLUTIL/ATL::CThreadPool::QueryInterface
- ATLUTIL/ATL::CThreadPool::QueueRequest
- ATLUTIL/ATL::CThreadPool::Release
- ATLUTIL/ATL::CThreadPool::SetSize
- ATLUTIL/ATL::CThreadPool::SetTimeout
- ATLUTIL/ATL::CThreadPool::Shutdown
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
ms.openlocfilehash: 5e52868f23883836919b96be9aec1815bc1c17b3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747455"
---
# <a name="cthreadpool-class"></a>C스레드풀 클래스

이 클래스는 작업 항목의 큐를 처리하는 작업자 스레드 풀을 제공합니다.

## <a name="syntax"></a>구문

```
template <class Worker, class ThreadTraits = DefaultThreadTraits>
class CThreadPool : public IThreadPoolConfig
```

#### <a name="parameters"></a>매개 변수

*작업자*<br/>
스레드 풀에 큐에 대기하는 작업 항목을 처리하는 데 사용되는 코드를 제공하는 [작업자 아키타입을](../../atl/reference/worker-archetype.md) 준수하는 클래스입니다.

*스레드 특성*<br/>
풀에서 스레드를 만드는 데 사용되는 함수를 제공하는 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C스레드 풀::C스레드풀](#cthreadpool)|스레드 풀의 생성자입니다.|
|[C스레드 풀::~CThread풀](#dtor)|스레드 풀의 소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C스레드풀::애드레프](#addref)|`IUnknown::AddRef`의 구현입니다.|
|[C스레드 풀::겟넘스레드](#getnumthreads)|풀의 스레드 수를 얻으려면 이 메서드를 호출합니다.|
|[C스레드 풀::GetQueue핸들](#getqueuehandle)|작업 항목을 큐에 사용하는 IO 완료 포트의 핸들을 얻으려면 이 메서드를 호출합니다.|
|[C스레드 풀::겟사이즈](#getsize)|풀의 스레드 수를 얻으려면 이 메서드를 호출합니다.|
|[C스레드 풀::GetTimeout](#gettimeout)|스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 최대 시간을 밀리초 단위로 얻으려면 이 메서드를 호출합니다.|
|[C스레드 풀::초기화](#initialize)|스레드 풀을 초기화하려면 이 메서드를 호출합니다.|
|[C스레드풀::쿼리 인터페이스](#queryinterface)|`IUnknown::QueryInterface`의 구현입니다.|
|[C스레드풀::큐요청](#queuerequest)|풀의 스레드가 처리할 작업 항목을 큐에 대기하도록 이 메서드를 호출합니다.|
|[C스레드풀::릴리스](#release)|`IUnknown::Release`의 구현입니다.|
|[C스레드 풀::세트크기](#setsize)|풀의 스레드 수를 설정하려면 이 메서드를 호출합니다.|
|[C스레드 풀::설정 시간 설정](#settimeout)|스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 최대 시간을 밀리초 단위로 설정하려면 이 메서드를 호출합니다.|
|[C스레드 풀::종료](#shutdown)|스레드 풀을 종료 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

풀의 스레드는 풀을 초기화, 크기 조정 또는 종료할 때 생성되고 소멸됩니다. 클래스 *Worker의* 인스턴스는 풀의 각 작업자 스레드의 스택에 만들어집니다. 각 인스턴스는 스레드의 수명 동안 유지됩니다.

스레드를 만든 직후 *Worker*::`Initialize` 해당 스레드와 연결된 개체에서 호출됩니다. 스레드가 파괴되기 직전에 *Worker*`Terminate` :: 호출됩니다. 두 메서드 모두 **void** <strong>\*</strong> 인수를 수락해야 합니다. 이 인수의 값은 [CThreadPool::초기화의](#initialize) *pvWorkerParam* 매개 변수를 통해 스레드 풀에 전달됩니다.

큐에 작업 항목과 작업에 사용할 수 있는 작업자 스레드가 있는 경우 작업자 스레드는 `Execute` 큐에서 항목을 끌어와서 해당 스레드에 대한 *Worker* 개체의 메서드를 호출합니다. 그런 다음 세 개의 항목이 메서드에 전달됩니다: `pvWorkerParam` 큐의 항목, 동일한 `Terminate` *워커*:: `Initialize` 및 *Worker*:: 및 IO 완료 포트 큐에 사용되는 [OVERLAPPED](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) 구조에 대한 포인터입니다.

*Worker* 클래스는 typedef, *Worker*:: `RequestType`를 제공하여 스레드 풀에서 큐에 대기할 항목의 유형을 선언합니다. 이 유형은 ULONG_PTR 캐스팅할 수 있어야 합니다.

*Worker* 클래스의 예로는 [CNonStatelessWorker 클래스입니다.](../../atl/reference/cnonstatelessworker-class.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IUnknown`

[아이스레드풀콘피그](../../atl/reference/ithreadpoolconfig-interface.md)

`CThreadPool`

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="cthreadpooladdref"></a><a name="addref"></a>C스레드풀::애드레프

`IUnknown::AddRef`의 구현입니다.

```
ULONG STDMETHODCALLTYPE AddRef() throw();
```

### <a name="return-value"></a>Return Value

항상 1을 반환합니다.

### <a name="remarks"></a>설명

이 클래스는 참조 카운트를 사용하여 수명 제어를 구현하지 않습니다.

## <a name="cthreadpoolcthreadpool"></a><a name="cthreadpool"></a>C스레드 풀::C스레드풀

스레드 풀의 생성자입니다.

```
CThreadPool() throw();
```

### <a name="remarks"></a>설명

시간 시간 값을 ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT 초기화합니다. 기본 시간은 36초입니다. 필요한 경우 atlutil.h를 포함하기 전에 이 기호에 대해 고유한 양수 정수 값을 정의할 수 있습니다.

## <a name="cthreadpoolcthreadpool"></a><a name="dtor"></a>C스레드 풀::~CThread풀

스레드 풀의 소멸자입니다.

```
~CThreadPool() throw();
```

### <a name="remarks"></a>설명

[CThreadPool::종료를](#shutdown)호출합니다.

## <a name="cthreadpoolgetnumthreads"></a><a name="getnumthreads"></a>C스레드 풀::겟넘스레드

풀의 스레드 수를 얻으려면 이 메서드를 호출합니다.

```
int GetNumThreads() throw();
```

### <a name="return-value"></a>Return Value

풀의 스레드 수를 반환합니다.

## <a name="cthreadpoolgetqueuehandle"></a><a name="getqueuehandle"></a>C스레드 풀::GetQueue핸들

작업 항목을 큐에 사용하는 IO 완료 포트의 핸들을 얻으려면 이 메서드를 호출합니다.

```
HANDLE GetQueueHandle() throw();
```

### <a name="return-value"></a>Return Value

스레드 풀이 초기화되지 않은 경우 큐 핸들 또는 NULL을 반환합니다.

## <a name="cthreadpoolgetsize"></a><a name="getsize"></a>C스레드 풀::겟사이즈

풀의 스레드 수를 얻으려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```

### <a name="parameters"></a>매개 변수

*pnNum스레드*<br/>
【아웃】 성공 시 풀의 스레드 수를 받는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cthreadpoolgettimeout"></a><a name="gettimeout"></a>C스레드 풀::GetTimeout

스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 최대 시간을 밀리초 단위로 얻으려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```

### <a name="parameters"></a>매개 변수

*pdwMaxWait*<br/>
【아웃】 성공 시 스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 최대 시간을 밀리초 단위로 받는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 시간 시간 값은 [CThreadPool::Shutdown에서](#shutdown) 다른 값이 해당 메서드에 제공되지 않는 경우에 사용됩니다.

## <a name="cthreadpoolinitialize"></a><a name="initialize"></a>C스레드 풀::초기화

스레드 풀을 초기화하려면 이 메서드를 호출합니다.

```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```

### <a name="parameters"></a>매개 변수

*pvworkerParam*<br/>
worker 스레드 개체의 및 `Initialize` `Execute` `Terminate` 메서드에 전달할 worker 매개 변수입니다.

*nNumThreads*<br/>
풀에서 요청된 스레드 수입니다.

*nNumThreads가* 음수이면 절대 값에 총 스레드 수를 얻기 위해 컴퓨터의 프로세서 수를 곱합니다.

*nNumThreads가* 0이면 ATLS_DEFAULT_THREADSPERPROC 컴퓨터의 프로세서 수에 총 스레드 수를 곱합니다.  기본값은 프로세서당 2개의 스레드입니다. 필요한 경우 atlutil.h를 포함하기 전에 이 기호에 대해 고유한 양수 정수 값을 정의할 수 있습니다.

*dw스택사이즈*<br/>
풀의 각 스레드에 대한 스택 크기입니다.

*h완성*<br/>
완료 포트와 연결할 개체의 핸들입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cthreadpoolqueryinterface"></a><a name="queryinterface"></a>C스레드풀::쿼리 인터페이스

`IUnknown::QueryInterface`의 구현입니다.

```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```

### <a name="remarks"></a>설명

이 클래스의 개체는 `IUnknown` 및 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) 인터페이스에 대해 성공적으로 쿼리할 수 있습니다.

## <a name="cthreadpoolqueuerequest"></a><a name="queuerequest"></a>C스레드풀::큐요청

풀의 스레드가 처리할 작업 항목을 큐에 대기하도록 이 메서드를 호출합니다.

```
BOOL QueueRequest(Worker::RequestType request) throw();
```

### <a name="parameters"></a>매개 변수

*요청*<br/>
큐에 대기할 요청입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 메서드는 큐에 작업 항목을 추가합니다. 풀의 스레드는 수신된 순서대로 큐에서 항목을 선택합니다.

## <a name="cthreadpoolrelease"></a><a name="release"></a>C스레드풀::릴리스

`IUnknown::Release`의 구현입니다.

```
ULONG STDMETHODCALLTYPE Release() throw();
```

### <a name="return-value"></a>Return Value

항상 1을 반환합니다.

### <a name="remarks"></a>설명

이 클래스는 참조 카운트를 사용하여 수명 제어를 구현하지 않습니다.

## <a name="cthreadpoolsetsize"></a><a name="setsize"></a>C스레드 풀::세트크기

풀의 스레드 수를 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```

### <a name="parameters"></a>매개 변수

*nNumThreads*<br/>
풀에서 요청된 스레드 수입니다.

*nNumThreads가* 음수이면 절대 값에 총 스레드 수를 얻기 위해 컴퓨터의 프로세서 수를 곱합니다.

*nNumThreads가* 0이면 ATLS_DEFAULT_THREADSPERPROC 컴퓨터의 프로세서 수에 총 스레드 수를 곱합니다. 기본값은 프로세서당 2개의 스레드입니다. 필요한 경우 atlutil.h를 포함하기 전에 이 기호에 대해 고유한 양수 정수 값을 정의할 수 있습니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

지정된 스레드 수가 현재 풀에 있는 스레드 수보다 작은 경우 개체는 대기 중인 스레드에서 픽업할 큐에 종료 메시지를 넣습니다. 대기 스레드가 큐에서 메시지를 가져오면 스레드 풀에 대해 통보하고 스레드 프로시저를 종료합니다. 이 프로세스는 풀의 스레드 수가 지정된 수에 도달할 때까지 또는 [GetTimeout](#gettimeout)/ [SetTimeout에서](#settimeout)지정한 기간 내에 스레드가 종료되지 않은 때까지 반복됩니다. 이 경우 메서드는 WAIT_TIMEOUT 해당하는 HRESULT를 반환 하 고 보류 중인 종료 메시지가 취소 됩니다.

## <a name="cthreadpoolsettimeout"></a><a name="settimeout"></a>C스레드 풀::설정 시간 설정

스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 최대 시간을 밀리초 단위로 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```

### <a name="parameters"></a>매개 변수

*드맥스웨이트*<br/>
스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 요청된 최대 시간(밀리초)입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

시간 아웃은 ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT 초기화됩니다. 기본 시간은 36초입니다. 필요한 경우 atlutil.h를 포함하기 전에 이 기호에 대해 고유한 양수 정수 값을 정의할 수 있습니다.

*dwMaxWait는* 풀이 단일 스레드가 종료될 때까지 기다리는 시간입니다. 풀에서 여러 스레드를 제거하는 데 사용할 수 있는 최대 시간은 *dwMaxWait에* 스레드 수를 곱한 값보다 약간 적을 수 있습니다.

## <a name="cthreadpoolshutdown"></a><a name="shutdown"></a>C스레드 풀::종료

스레드 풀을 종료 하려면이 메서드를 호출 합니다.

```cpp
void Shutdown(DWORD dwMaxWait = 0) throw();
```

### <a name="parameters"></a>매개 변수

*드맥스웨이트*<br/>
스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 요청된 최대 시간(밀리초)입니다. 값이 0 또는 제공되지 않으면 이 메서드는 [CThreadPool::SetTimeout](#settimeout)에서 설정한 시간 지정을 사용합니다.

### <a name="remarks"></a>설명

이 메서드는 풀의 모든 스레드에 종료 요청을 게시합니다. 시간 지정이 만료되면 이 메서드는 종료되지 않은 모든 스레드에서 [TerminateThread를](/windows/win32/api/processthreadsapi/nf-processthreadsapi-terminatethread) 호출합니다. 이 메서드는 클래스의 소멸자에서 자동으로 호출 됩니다.

## <a name="see-also"></a>참조

[IThreadPool구성 인터페이스](../../atl/reference/ithreadpoolconfig-interface.md)<br/>
[기본 스레드 특성](atl-typedefs.md#defaultthreadtraits)<br/>
[클래스](../../atl/reference/atl-classes.md)
