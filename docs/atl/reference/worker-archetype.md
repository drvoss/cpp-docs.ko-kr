---
title: 작업자 아키타입
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: c9ed9b30b94a8debe133bc213c12063750bfb15a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747349"
---
# <a name="worker-archetype"></a>작업자 아키타입

*작업자* 아키타입을 준수하는 클래스는 스레드 풀에 큐에 대기된 작업 항목을 처리하는 코드를 제공합니다.

**구현**

이 아키타입에 맞는 클래스를 구현하려면 클래스는 다음 기능을 제공해야 합니다.

|방법|Description|
|------------|-----------------|
|[Initialize](#initialize)|요청이 [Execute로](#execute)전달되기 전에 worker 개체를 초기화하기 위해 호출됩니다.|
|[실행](#execute)|작업 항목을 처리하기 위해 호출됩니다.|
|[Terminate](#terminate)|모든 요청이 [Execute로](#execute)전달된 후 worker 개체를 초기화하기 위해 호출됩니다.|

|형식 정의|Description|
|-------------|-----------------|
|[RequestType](#requesttype)|작업자 클래스에서 처리할 수 있는 작업 항목 의 형식에 대 한 형식 def입니다.|

일반적인 *작업자* 클래스는 다음과 같습니다.

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**기존 구현**

이러한 클래스는 다음 의 전형을 준수합니다.

|클래스|Description|
|-----------|-----------------|
|[CNonStateless워커](../../atl/reference/cnonstatelessworker-class.md)|스레드 풀에서 요청을 수신 하 고 각 요청에 대 한 생성 되 고 삭제 되는 작업자 개체에 전달 합니다.|

**사용**

이러한 템플릿 매개 변수는 클래스가 이 아키타입을 준수할 것으로 예상합니다.

|매개 변수 이름|사용 대상|
|--------------------|-------------|
|*작업자*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*작업자*|[CNonStateless워커](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="workerarchetypeexecute"></a><a name="execute"></a>작업자아키유형::실행

작업 항목을 처리하기 위해 호출됩니다.

```cpp
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>매개 변수

*요청*<br/>
처리할 작업 항목입니다. 작업 항목은 `RequestType`와 동일한 형식입니다.

*pvworkerParam*<br/>
worker 클래스에서 이해하는 사용자 지정 매개 변수입니다. 또한 에 `WorkerArchetype::Initialize` `Terminate`전달 하 고 .

*겹쳐있는*<br/>
작업 항목이 큐에 대기된 큐를 만드는 데 사용되는 [OverLAPPED](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) 구조에 대한 포인터입니다.

## <a name="workerarchetypeinitialize"></a><a name="initialize"></a>작업자아키유형::초기화

요청이 로 전달되기 전에 worker 개체를 초기화하기 위해 `WorkerArchetype::Execute`호출됩니다.

```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>매개 변수

*pvParam*<br/>
worker 클래스에서 이해하는 사용자 지정 매개 변수입니다. 또한 에 `WorkerArchetype::Terminate` `WorkerArchetype::Execute`전달 하 고 .

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="workerarchetyperequesttype"></a><a name="requesttype"></a>작업자아키유형::요청 유형

작업자 클래스에서 처리할 수 있는 작업 항목 의 형식에 대 한 형식 def입니다.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>설명

이 형식은 `WorkerArchetype::Execute` 첫 번째 매개 변수로 사용해야 하며 ULONG_PTR 캐스팅할 수 있어야 합니다.

## <a name="workerarchetypeterminate"></a><a name="terminate"></a>작업자아키유형::종료

모든 요청이 )로 전달된 후 worker `WorkerArchetype::Execute`개체를 초기화하기 위해 호출됩니다.

```cpp
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>매개 변수

*pvParam*<br/>
worker 클래스에서 이해하는 사용자 지정 매개 변수입니다. 또한 에 `WorkerArchetype::Initialize` `WorkerArchetype::Execute`전달 하 고 .

## <a name="see-also"></a>참조

[개념](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)
