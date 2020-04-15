---
title: IResourceManager 구조체
ms.date: 03/27/2019
f1_keywords:
- IResourceManager
- CONCRTRM/concurrency::IResourceManager
- CONCRTRM/concurrency::IResourceManager::IResourceManager::OSVersion
- CONCRTRM/concurrency::IResourceManager::IResourceManager::CreateNodeTopology
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetAvailableNodeCount
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetFirstNode
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Reference
- CONCRTRM/concurrency::IResourceManager::IResourceManager::RegisterScheduler
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Release
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
ms.openlocfilehash: 15e27a586fc039791255c01a053f6a1109183f90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368181"
---
# <a name="iresourcemanager-structure"></a>IResourceManager 구조체

동시성 런타임의 리소스 관리자에 대한 인터페이스입니다. 스케줄러가 리소스 관리자와 통신하는 데 사용되는 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
struct IResourceManager;
```

## <a name="members"></a>멤버

### <a name="public-enumerations"></a>public 열거형

|속성|Description|
|----------|-----------------|
|[IResourceManager::OSVersion](#osversion)|운영 체제 버전을 나타내는 열거 형식입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IResourceManager::만들기노드토폴로지](#createnodetopology)|런타임의 디버그 빌드에서만 존재하는 이 메서드는 구성과 일치하는 실제 하드웨어없이 다양한 하드웨어 토폴로지에 대한 리소스 관리자의 테스트를 용이하게 하도록 설계된 테스트 후크입니다. 런타임의 소매 빌드를 사용하면 이 메서드는 아무 작업도 수행하지 않고 반환됩니다.|
|[IResourceManager:::사용 가능 노드 카운트](#getavailablenodecount)|리소스 관리자에서 사용할 수 있는 노드의 수를 반환합니다.|
|[IResourceManager::GetFirstNode](#getfirstnode)|리소스 관리자를 통해 정의된 열거 순서에서 첫 번째 노드를 반환합니다.|
|[IResourceManager::참조](#reference)|리소스 관리자 인스턴스의 참조 수를 증가시입니다.|
|[IResourceManager::레지스터스케줄러](#registerscheduler)|리소스 관리자에 스케줄러를 등록합니다. 스케줄러가 등록되면 반환되는 `ISchedulerProxy` 인터페이스를 사용하여 리소스 관리자와 통신해야 합니다.|
|[IResourceManager::릴리스](#release)|리소스 관리자 인스턴스의 참조 수를 감소시입니다. 리소스 관리자는 참조 수가 로 이동하면 `0`소멸됩니다.|

## <a name="remarks"></a>설명

[CreateResourceManager](concurrency-namespace-functions.md) 함수를 사용하여 단일 리소스 관리자 인스턴스에 대한 인터페이스를 가져옵니다. 메서드는 리소스 관리자에 대 한 참조 수를 증가 하 고 리소스 관리자를 완료 하는 경우 참조를 해제 하는 [IResourceManager::Release](#release) 메서드를 호출 해야 합니다. 일반적으로 만드는 각 스케줄러는 만드는 동안 이 메서드를 호출하고 종료된 후 리소스 관리자에 대한 참조를 해제합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IResourceManager`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="iresourcemanagercreatenodetopology-method"></a><a name="createnodetopology"></a>IResourceManager::만들기Node토폴로지 방법

런타임의 디버그 빌드에서만 존재하는 이 메서드는 구성과 일치하는 실제 하드웨어없이 다양한 하드웨어 토폴로지에 대한 리소스 관리자의 테스트를 용이하게 하도록 설계된 테스트 후크입니다. 런타임의 소매 빌드를 사용하면 이 메서드는 아무 작업도 수행하지 않고 반환됩니다.

```cpp
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>매개 변수

*노드 카운트*<br/>
시뮬레이션할 프로세서 노드 수입니다.

*pCoreCount*<br/>
각 노드의 코어 수를 지정하는 배열입니다.

*pNode거리*<br/>
두 노드 사이의 노드 거리를 지정하는 행렬입니다. 이 매개 변수는 `NULL`값을 가질 수 있습니다.

*p프로세서 그룹*<br/>
각 노드가 속한 프로세서 그룹을 지정하는 배열입니다.

### <a name="remarks"></a>설명

[매개](../../../standard-library/invalid-argument-class.md) 변수에 `nodeCount` 값이 `0` 전달된 경우 또는 매개 변수에 `pCoreCount` 값이 `NULL`있는 경우 invalid_argument throw됩니다.

프로세스에 다른 스케줄러가 있는 동안 이 메서드가 호출되면 [invalid_operation](invalid-operation-class.md) throw됩니다.

## <a name="iresourcemanagergetavailablenodecount-method"></a><a name="getavailablenodecount"></a>IResourceManager::GetAvailableNodeCount 방법

리소스 관리자에서 사용할 수 있는 노드의 수를 반환합니다.

```cpp
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>Return Value

리소스 관리자에서 사용할 수 있는 노드 수입니다.

## <a name="iresourcemanagergetfirstnode-method"></a><a name="getfirstnode"></a>IResourceManager::GetFirstNode 방법

리소스 관리자를 통해 정의된 열거 순서에서 첫 번째 노드를 반환합니다.

```cpp
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>Return Value

리소스 관리자에서 정의한 열거 순서의 첫 번째 노드입니다.

## <a name="iresourcemanagerosversion-enumeration"></a><a name="osversion"></a>IResourceManager::OS버전 열거

운영 체제 버전을 나타내는 열거 형식입니다.

```cpp
enum OSVersion;
```

## <a name="iresourcemanagerreference-method"></a><a name="reference"></a>IResourceManager::참조 방법

리소스 관리자 인스턴스의 참조 수를 증가시입니다.

```cpp
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Return Value

결과 참조 수입니다.

## <a name="iresourcemanagerregisterscheduler-method"></a><a name="registerscheduler"></a>IResourceManager::레지스터스케줄러 방법

리소스 관리자에 스케줄러를 등록합니다. 스케줄러가 등록되면 반환되는 `ISchedulerProxy` 인터페이스를 사용하여 리소스 관리자와 통신해야 합니다.

```cpp
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>매개 변수

*p스케줄러*<br/>
등록할 스케줄러에 대한 `IScheduler` 인터페이스입니다.

*version*<br/>
스케줄러가 리소스 관리자와 통신하는 데 사용하는 통신 인터페이스 버전입니다. 버전을 사용하면 리소스 관리자가 통신 인터페이스를 발전시키면서 스케줄러가 이전 기능에 대한 액세스 권한을 얻을 수 있습니다. Visual Studio 2010에 있는 리소스 관리자 기능을 사용하려는 `CONCRT_RM_VERSION_1`스케줄러는 버전을 사용해야 합니다.

### <a name="return-value"></a>Return Value

리소스 `ISchedulerProxy` 관리자가 스케줄러와 연결한 인터페이스입니다. 스케줄러는 이 인터페이스를 사용하여 이 시점부터 리소스 관리자와 통신해야 합니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 리소스 관리자와 통신을 시작합니다. 이 메서드는 `IScheduler` 스케줄러의 인터페이스를 `ISchedulerProxy` 인터페이스와 연결하여 다시 건네줍니다. 반환된 인터페이스를 사용하여 스케줄러에서 사용할 실행 리소스를 요청하거나 리소스 관리자를 사용하여 스레드를 구독할 수 있습니다. 리소스 관리자는 [IScheduler::GetPolicy](ischeduler-structure.md#getpolicy) 메서드에서 반환하는 스케줄러 정책의 정책 요소를 사용하여 스케줄러가 작업을 실행하는 데 필요한 스레드 유형을 결정합니다. `SchedulerKind` `UmsThreadDefault` 정책 키에 값이 있고 값이 정책에서 값으로 `UmsThreadDefault`다시 읽혀지는 `IScheduler` 경우 메서드에 전달된 `IUMSScheduler` 인터페이스는 인터페이스여야 합니다.

이 메서드는 `invalid_argument` 매개 변수에 `pScheduler` 값이 `NULL` 있거나 매개 `version` 변수가 통신 인터페이스에 대한 유효한 버전이 아닌 경우 예외를 throw합니다.

## <a name="iresourcemanagerrelease-method"></a><a name="release"></a>IResourceManager::릴리스 방법

리소스 관리자 인스턴스의 참조 수를 감소시입니다. 리소스 관리자는 참조 수가 로 이동하면 `0`소멸됩니다.

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Return Value

결과 참조 수입니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[ISchedulerProxy 구조체](ischedulerproxy-structure.md)<br/>
[IScheduler 구조체](ischeduler-structure.md)
