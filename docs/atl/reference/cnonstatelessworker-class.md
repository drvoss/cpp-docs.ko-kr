---
title: CNonStateless워커 클래스
ms.date: 11/04/2016
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
ms.openlocfilehash: 6264bb6bc9070b5ce170b294f9db0d371e7b6b71
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747675"
---
# <a name="cnonstatelessworker-class"></a>CNonStateless워커 클래스

스레드 풀에서 요청을 수신 하 고 각 요청에 생성 되 고 소멸 하는 작업자 개체에 전달 합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>매개 변수

*작업자*<br/>
[CThreadPool에서](../../atl/reference/cthreadpool-class.md)큐에 대기된 요청을 처리하는 데 적합한 [작업자 아키타입을](../../atl/reference/worker-archetype.md) 준수하는 작업자 스레드 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CNonStateless워커::요청 유형](#requesttype)|[Worker아키 유형 구현::요청 유형](worker-archetype.md#requesttype).|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CNonStateless워커::실행](#execute)|[Worker아키 유형 구현::Execute](worker-archetype.md#execute).|
|[CNonStateless워커::초기화](#initialize)|[Worker아키 유형 구현::초기화](worker-archetype.md#initialize).|
|[CNonStateless워커::종료](#terminate)|[WorkerArchetype 의 구현::종료](worker-archetype.md#terminate).|

## <a name="remarks"></a>설명

이 클래스는 [CThreadPool](../../atl/reference/cthreadpool-class.md)에서 사용할 수 있는 간단한 작업자 스레드입니다. 이 클래스는 자체요청 처리 기능을 제공하지 않습니다. 대신 요청당 한 인스턴스의 *Worker를* 인스턴스화하고 해당 메서드의 구현을 해당 인스턴스에 위임합니다.

이 클래스의 장점은 기존 작업자 스레드 클래스에 대한 상태 모델을 변경하는 편리한 방법을 제공한다는 것입니다. `CThreadPool`스레드의 수명 동안 단일 워커를 만들므로 worker 클래스가 상태를 보유하면 여러 요청에서 해당 워커를 보유합니다. `CNonStatelessWorker` 템플릿을 사용하기 전에 템플릿에서 해당 `CThreadPool`클래스를 래핑하기만 하면 작업자의 수명과 해당 클래스가 보유한 상태는 단일 요청으로 제한됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="cnonstatelessworkerexecute"></a><a name="execute"></a>CNonStateless워커::실행

[Worker아키 유형 구현::Execute](worker-archetype.md#execute).

```cpp
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>설명

이 메서드는 스택에 *Worker* 클래스의 인스턴스를 만들고 해당 개체에 [초기화를](worker-archetype.md#initialize) 호출합니다. 초기화가 성공하면 이 메서드는 동일한 개체에서 [Execute](worker-archetype.md#execute) 및 [Terminate를](worker-archetype.md#terminate) 호출합니다.

## <a name="cnonstatelessworkerinitialize"></a><a name="initialize"></a>CNonStateless워커::초기화

[Worker아키 유형 구현::초기화](worker-archetype.md#initialize).

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>Return Value

항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 클래스는 에서 `Initialize`초기화를 수행하지 않습니다.

## <a name="cnonstatelessworkerrequesttype"></a><a name="requesttype"></a>CNonStateless워커::요청 유형

[Worker아키 유형 구현::요청 유형](worker-archetype.md#requesttype).

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>설명

이 클래스는 *Worker* 템플릿 매개 변수에 사용되는 클래스와 동일한 유형의 작업 항목을 처리합니다. 자세한 내용은 [CNonStatelessWorker 개요를](../../atl/reference/cnonstatelessworker-class.md) 참조하십시오.

## <a name="cnonstatelessworkerterminate"></a><a name="terminate"></a>CNonStateless워커::종료

[WorkerArchetype 의 구현::종료](worker-archetype.md#terminate).

```cpp
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>설명

이 클래스에서는 정리를 수행하지 `Terminate`않습니다.

## <a name="see-also"></a>참조

[C스레드풀 클래스](../../atl/reference/cthreadpool-class.md)<br/>
[작업자 아키타입](../../atl/reference/worker-archetype.md)<br/>
[클래스](../../atl/reference/atl-classes.md)
