---
title: CNoWorker스레드 클래스
ms.date: 11/04/2016
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
ms.openlocfilehash: 90056e648a53218ac06083d43ca34870e1ca72fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326702"
---
# <a name="cnoworkerthread-class"></a>CNoWorker스레드 클래스

동적 캐시 유지 관리를 `MonitorClass` 사용하지 않으려면 이 클래스를 템플릿 매개 변수에 대한 인수로 사용하여 클래스를 캐시합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CNoWorkerThread
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CNoWorker스레드::추가 핸들](#addhandle)|[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)의 비기능적 동일|
|[CNoWorker스레드::추가 타이머](#addtimer)|[CWorkerThread::AddTimer의](../../atl/reference/cworkerthread-class.md#addtimer)비기능적 동일|
|[CNoWorker스레드::GetThread핸들](#getthreadhandle)|[CWorkerThread::GetThreadHandle.](../../atl/reference/cworkerthread-class.md#getthreadhandle)|
|[CNoWorker스레드::GetThreadId](#getthreadid)|[CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|
|[CNoWorkerThread::초기화](#initialize)|[CWorkerThread::초기화.](../../atl/reference/cworkerthread-class.md#initialize)|
|[CNoWorker스레드::제거 핸들](#removehandle)|[CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)의 비기능적 동일|
|[CNoWorker스레드::종료](#shutdown)|[CWorkerThread::Shutdown의](../../atl/reference/cworkerthread-class.md#shutdown)비기능적 동일.|

## <a name="remarks"></a>설명

이 클래스는 [CWorkerThread](../../atl/reference/cworkerthread-class.md)와 동일한 공용 인터페이스를 제공합니다. 이 인터페이스는 템플릿 매개 `MonitorClass` 변수에서 캐시 클래스에 제공할 것으로 예상됩니다.

이 클래스의 메서드는 아무 것도 수행하지 않고 구현됩니다. HRESULT를 반환하는 메서드는 항상 S_OK 반환하고 HANDLE 또는 스레드 ID를 반환하는 메서드는 항상 0을 반환합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="cnoworkerthreadaddhandle"></a><a name="addhandle"></a>CNoWorker스레드::추가 핸들

[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)의 비기능적 동일

```
HRESULT AddHandle(HANDLE /* hObject */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */) throw();
```

### <a name="return-value"></a>Return Value

항상 S_OK 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공하는 구현은 아무 것도 수행하지 않습니다.

## <a name="cnoworkerthreadaddtimer"></a><a name="addtimer"></a>CNoWorker스레드::추가 타이머

[CWorkerThread::AddTimer의](../../atl/reference/cworkerthread-class.md#addtimer)비기능적 동일

```
HRESULT AddTimer(DWORD /* dwInterval */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */,
    HANDLE* /* phTimer */) throw();
```

### <a name="return-value"></a>Return Value

항상 S_OK 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공하는 구현은 아무 것도 수행하지 않습니다.

## <a name="cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CNoWorker스레드::GetThread핸들

[CWorkerThread::GetThreadHandle.](../../atl/reference/cworkerthread-class.md#getthreadhandle)

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Return Value

항상 NULL을 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공하는 구현은 아무 것도 수행하지 않습니다.

## <a name="cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a>CNoWorker스레드::GetThreadId

[CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Return Value

항상 0을 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공하는 구현은 아무 것도 수행하지 않습니다.

## <a name="cnoworkerthreadinitialize"></a><a name="initialize"></a>CNoWorkerThread::초기화

[CWorkerThread::초기화.](../../atl/reference/cworkerthread-class.md#initialize)

```
HRESULT Initialize() throw();
```

### <a name="return-value"></a>Return Value

항상 S_OK 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공하는 구현은 아무 것도 수행하지 않습니다.

## <a name="cnoworkerthreadremovehandle"></a><a name="removehandle"></a>CNoWorker스레드::제거 핸들

[CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)의 비기능적 동일

```
HRESULT RemoveHandle(HANDLE /* hObject */) throw();
```

### <a name="return-value"></a>Return Value

항상 S_OK 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공하는 구현은 아무 것도 수행하지 않습니다.

## <a name="cnoworkerthreadshutdown"></a><a name="shutdown"></a>CNoWorker스레드::종료

[CWorkerThread::Shutdown의](../../atl/reference/cworkerthread-class.md#shutdown)비기능적 동일.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="return-value"></a>Return Value

항상 S_OK 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공하는 구현은 아무 것도 수행하지 않습니다.
