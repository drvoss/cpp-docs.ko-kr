---
title: DispatchState 구조체
ms.date: 11/04/2016
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
ms.openlocfilehash: 2c4103f89f7fc74c5368bafac3c82685ff9b6e03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372692"
---
# <a name="dispatchstate-structure"></a>DispatchState 구조체

`DispatchState` 구조체는 `IExecutionContext::Dispatch` 메서드에 상태를 전송하는 데 사용됩니다. `IExecutionContext` 인터페이스에 대해 `Dispatch` 메서드가 호출되는 상황을 설명합니다.

## <a name="syntax"></a>구문

```cpp
struct DispatchState;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[디스패치상태::DispatchState](#ctor)|새 `DispatchState` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[디스패치 상태:m_dispatchStateSize](#m_dispatchstatesize)|버전 조정에 사용되는 이 구조의 크기입니다.|
|[디스패치상태:m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|이전 컨텍스트가 비동기적으로 차단되어 이 컨텍스트가 메서드에 `Dispatch` 입력되었는지 여부를 알려줍니다. UMS 스케줄링 컨텍스트에서만 사용되며 다른 모든 실행 `0` 컨텍스트에 대한 값으로 설정됩니다.|
|[디스패치상태:m_reserved](#m_reserved)|향후 정보 전달을 위해 예약된 비트입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`DispatchState`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="dispatchstatedispatchstate-constructor"></a><a name="ctor"></a>디스패치상태::DispatchState 생성자

새 `DispatchState` 개체를 생성합니다.

```cpp
DispatchState();
```

## <a name="dispatchstatem_dispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a>디스패치상태::m_dispatchStateSize 데이터 멤버

버전 조정에 사용되는 이 구조의 크기입니다.

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="dispatchstatem_fispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a>디스패치상태::m_fIsPreviousContextAsynchronouslyBlocked 데이터 멤버

이전 컨텍스트가 비동기적으로 차단되어 이 컨텍스트가 메서드에 `Dispatch` 입력되었는지 여부를 알려줍니다. UMS 스케줄링 컨텍스트에서만 사용되며 다른 모든 실행 `0` 컨텍스트에 대한 값으로 설정됩니다.

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="dispatchstatem_reserved-data-member"></a><a name="m_reserved"></a>디스패치상태::m_reserved 데이터 멤버

향후 정보 전달을 위해 예약된 비트입니다.

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)
