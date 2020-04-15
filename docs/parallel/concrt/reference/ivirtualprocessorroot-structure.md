---
title: IVirtualProcessorRoot 구조체
ms.date: 11/04/2016
f1_keywords:
- IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Activate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Deactivate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::EnsureAllTasksVisible
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::GetId
helpviewer_keywords:
- IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
ms.openlocfilehash: f642a29d0a80568f7a5f2a5e89f6951d4819243e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364254"
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot 구조체

스레드 프록시가 실행될 수 있는 하드웨어 스레드의 추상화입니다.

## <a name="syntax"></a>구문

```cpp
struct IVirtualProcessorRoot : public IExecutionResource;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[아이 버추얼 프로세서 루트 ::활성화](#activate)|실행 컨텍스트 인터페이스와 `pContext` 연결된 스레드 프록시가 이 가상 프로세서 루트에서 실행을 시작하게 합니다.|
|[아이 버추얼 프로세서루트::D활성화](#deactivate)|현재 이 가상 프로세서 루트에서 실행 중인 스레드 프록시가 실행 컨텍스트 디스패치를 중지하도록 합니다. 스레드 프록시는 `Activate` 메서드에 대한 호출시 실행이 다시 시작됩니다.|
|[아이 버추얼 프로세서 루트 ::보장모든 작업볼 수](#ensurealltasksvisible)|개별 프로세서의 메모리 계층 구조에 저장된 데이터가 시스템의 모든 프로세서에 표시되도록 합니다. 메서드가 반환되기 전에 모든 프로세서에서 전체 메모리 울타리가 실행되었는지 확인합니다.|
|[아이 버추얼 프로세서 루트 ::GetId](#getid)|가상 프로세서 루트에 대한 고유 식별자를 반환합니다.|

## <a name="remarks"></a>설명

모든 가상 프로세서 루트에는 연결된 실행 리소스가 있습니다. 인터페이스는 `IVirtualProcessorRoot` [IExecutionResource](iexecutionresource-structure.md) 인터페이스에서 상속됩니다. 여러 가상 프로세서 루트는 동일한 기본 하드웨어 스레드에 해당할 수 있습니다.

리소스 관리자는 리소스 요청에 대한 응답으로 스케줄러에 가상 프로세서 루트를 부여합니다. 스케줄러는 가상 프로세서 루트를 사용하여 실행 컨텍스트로 활성화하여 작업을 수행할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[I실행리소스](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="ivirtualprocessorrootactivate-method"></a><a name="activate"></a>IVirtualProcessor루트::활성화 방법

실행 컨텍스트 인터페이스와 `pContext` 연결된 스레드 프록시가 이 가상 프로세서 루트에서 실행을 시작하게 합니다.

```cpp
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
이 가상 프로세서 루트에서 전달될 실행 컨텍스트에 대한 인터페이스입니다.

### <a name="remarks"></a>설명

리소스 관리자는 실행 컨텍스트 인터페이스와 연결 되지 않은 경우 스레드 프록시를 제공 합니다.`pContext`

이 `Activate` 메서드는 Resource Manager에서 반환하는 새 가상 프로세서 루트에서 작업을 실행하거나 비활성화되거나 비활성화하려는 가상 프로세서 루트에서 스레드 프록시를 다시 시작하는 데 사용할 수 있습니다. 비활성화에 대한 자세한 내용은 [IVirtualProcessorRoot::D활성화를](#deactivate) 참조하십시오. 비활성화된 가상 프로세서 루트를 다시 시작하려면 `pContext` 매개 변수가 가상 프로세서 루트를 비활성화하는 데 사용되는 매개 변수와 같아야 합니다.

가상 프로세서 루트가 처음으로 활성화되면 후속 호출 쌍이 `Deactivate` 서로 `Activate` 경합할 수 있습니다. 즉, 리소스 관리자가 의도한 호출을 `Activate` 받기 전에 `Deactivate` 호출을 받을 수 있습니다.

가상 프로세서 루트를 활성화하면 리소스 관리자에게 이 가상 프로세서 루트가 현재 작업 중임을 나타냅니다. 스케줄러가 이 루트에서 실행할 작업을 찾을 수 없는 경우 가상 `Deactivate` 프로세서 루트가 유휴 상태임을 리소스 관리자에 알리는 메서드를 호출해야 합니다. 리소스 관리자는 이 데이터를 사용하여 시스템 분산을 로드합니다.

`invalid_argument`인수에 `pContext` 값이 `NULL`있으면 throw됩니다.

`invalid_operation`인수가 `pContext` 이 가상 프로세서 루트에서 가장 최근에 디스패치된 실행 컨텍스트를 나타내지 않으면 throw됩니다.

가상 프로세서 루트를 활성화하면 기본 하드웨어 스레드의 구독 수준이 하나씩 증가합니다. 구독 수준에 대한 자세한 내용은 [IExecutionResource::현재 구독 수준](iexecutionresource-structure.md#currentsubscriptionlevel)을 참조하십시오.

## <a name="ivirtualprocessorrootdeactivate-method"></a><a name="deactivate"></a>IVirtualProcessor루트::D활성화 방법

현재 이 가상 프로세서 루트에서 실행 중인 스레드 프록시가 실행 컨텍스트 디스패치를 중지하도록 합니다. 스레드 프록시는 `Activate` 메서드에 대한 호출시 실행이 다시 시작됩니다.

```cpp
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
현재 이 루트에서 디스패치중인 컨텍스트입니다.

### <a name="return-value"></a>Return Value

부울 값입니다. **true** 값은 메서드 호출에 대한 `Deactivate` 응답으로 메서드에서 스레드 프록시가 반환됨을 `Activate` 나타냅니다. 값은 `false` 리소스 관리자의 알림 이벤트에 대한 응답으로 메서드에서 스레드 프록시가 반환됨을 나타냅니다. UMS(사용자 모드) 스레드 스케줄러에서 이는 항목이 스케줄러의 완료 목록에 나타나고 스케줄러가 이를 처리해야 한다는 것을 나타냅니다.

### <a name="remarks"></a>설명

스케줄러에서 작업을 찾을 수 없는 경우 이 메서드를 사용하여 가상 프로세서 루트 실행을 일시적으로 중지합니다. 메서드에 `Deactivate` 대한 호출은 가상 프로세서 `Dispatch` 루트가 마지막으로 활성화된 실행 컨텍스트의 메서드 내에서 시작되어야 합니다. 즉, 메서드를 `Deactivate` 호출하는 스레드 프록시는 현재 가상 프로세서 루트에서 실행 중인 스레드 프록시여야 합니다. 실행하지 않는 가상 프로세서 루트에서 메서드를 호출하면 정의되지 않은 동작이 발생할 수 있습니다.

비활성화된 가상 프로세서 루트는 메서드에 `Activate` 전달된 것과 동일한 인수를 사용하여 메서드를 호출하여 `Deactivate` 깨어날 수 있습니다. 스케줄러는 `Activate` 메서드 및 `Deactivate` 메서드에 대한 호출이 쌍을 이루도록 할 책임이 있지만 특정 순서로 수신할 필요는 없습니다. 리소스 관리자는 메서드에 `Activate` 대 한 호출을 수신 하기 `Deactivate` 전에 메서드에 대 한 호출을 받을 수 있습니다.

가상 프로세서 루트가 `Deactivate` 깨어나고 메서드의 반환 값이 **false**값인 경우 스케줄러는 `IUMSCompletionList::GetUnblockNotifications` 메서드를 통해 UMS 완료 목록을 쿼리하고 해당 `Deactivate` 정보에 대해 조치를 한 다음 메서드를 다시 호출해야 합니다. 메서드가 `Deactivate` 값을 `true`반환할 때까지 이 작업을 반복해야 합니다.

`invalid_argument`인수에 `pContext` NULL 값이 있는 경우 throw됩니다.

`invalid_operation`가상 프로세서 루트가 활성화되지 않았거나 인수가 `pContext` 이 가상 프로세서 루트에서 가장 최근에 디스패치된 실행 컨텍스트를 나타내지 않는 경우 throw됩니다.

가상 프로세서 루트를 비활성화하면 기본 하드웨어 스레드의 구독 수준이 하나씩 줄어듭니다. 구독 수준에 대한 자세한 내용은 [IExecutionResource::현재 구독 수준](iexecutionresource-structure.md#currentsubscriptionlevel)을 참조하십시오.

## <a name="ivirtualprocessorrootensurealltasksvisible-method"></a><a name="ensurealltasksvisible"></a>IVirtualProcessor루트:보장모든작업가볼가능한방법

개별 프로세서의 메모리 계층 구조에 저장된 데이터가 시스템의 모든 프로세서에 표시되도록 합니다. 메서드가 반환되기 전에 모든 프로세서에서 전체 메모리 울타리가 실행되었는지 확인합니다.

```cpp
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
이 가상 프로세서 루트에서 현재 디스패치중인 컨텍스트입니다.

### <a name="remarks"></a>설명

이 메서드는 스케줄러에 새 작업을 추가하여 가상 프로세서 루트의 비활성화를 동기화하려는 경우에 유용할 수 있습니다. 성능상의 이유로 메모리 장벽을 실행하지 않고 스케줄러에 작업 항목을 추가하도록 결정할 수 있습니다. 이 메서드와 함께 이 `Deactivate` 메서드를 사용하면 작업 항목이 스케줄러 컬렉션에 있는 동안 스케줄러가 모든 가상 프로세서 루트를 비활성화하지 않도록 할 수 있습니다.

메서드에 `EnsureAllTasksVisibleThe` 대한 호출은 가상 프로세서 `Dispatch` 루트가 마지막으로 활성화된 실행 컨텍스트의 메서드 내에서 시작되어야 합니다. 즉, 메서드를 `EnsureAllTasksVisible` 호출하는 스레드 프록시는 현재 가상 프로세서 루트에서 실행 중인 스레드 프록시여야 합니다. 실행하지 않는 가상 프로세서 루트에서 메서드를 호출하면 정의되지 않은 동작이 발생할 수 있습니다.

`invalid_argument`인수에 `pContext` 값이 `NULL`있으면 throw됩니다.

`invalid_operation`가상 프로세서 루트가 활성화되지 않았거나 인수가 `pContext` 이 가상 프로세서 루트에서 가장 최근에 디스패치된 실행 컨텍스트를 나타내지 않는 경우 throw됩니다.

## <a name="ivirtualprocessorrootgetid-method"></a><a name="getid"></a>아이 버추얼 프로세서 루트 ::GetId 방법

가상 프로세서 루트에 대한 고유 식별자를 반환합니다.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Return Value

정수 식별자입니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)
