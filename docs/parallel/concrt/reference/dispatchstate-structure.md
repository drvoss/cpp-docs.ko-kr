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
ms.openlocfilehash: 69e00893373ccca6e2ed676fbb7f5a109c49efdf
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143052"
---
# <a name="dispatchstate-structure"></a>DispatchState 구조체

`DispatchState` 구조체는 `IExecutionContext::Dispatch` 메서드에 상태를 전송하는 데 사용됩니다. `Dispatch` 인터페이스에 대해 `IExecutionContext` 메서드가 호출되는 상황을 설명합니다.

## <a name="syntax"></a>구문

```cpp
struct DispatchState;
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[DispatchState::D ispatchState](#ctor)|새 `DispatchState` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[DispatchState:: m_dispatchStateSize](#m_dispatchstatesize)|버전 관리에 사용 되는이 구조체의 크기입니다.|
|[DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|이전 컨텍스트가 비동기 방식으로 차단 되어이 컨텍스트가 `Dispatch` 메서드를 입력 했는지 여부를 나타냅니다. 이는 UMS 일정 컨텍스트에서만 사용 되며 다른 모든 실행 컨텍스트의 `0` 값으로 설정 됩니다.|
|[DispatchState:: m_reserved](#m_reserved)|향후 정보 전달을 위해 예약 된 비트입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`DispatchState`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm. h

**네임스페이스:** 동시성

## <a name="ctor"></a>DispatchState::D ispatchState 생성자

새 `DispatchState` 개체를 생성합니다.

```cpp
DispatchState();
```

## <a name="m_dispatchstatesize"></a>DispatchState:: m_dispatchStateSize 데이터 멤버

버전 관리에 사용 되는이 구조체의 크기입니다.

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="m_fispreviouscontextasynchronouslyblocked"></a>DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked 데이터 멤버

이전 컨텍스트가 비동기 방식으로 차단 되어이 컨텍스트가 `Dispatch` 메서드를 입력 했는지 여부를 나타냅니다. 이는 UMS 일정 컨텍스트에서만 사용 되며 다른 모든 실행 컨텍스트의 `0` 값으로 설정 됩니다.

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="m_reserved"></a>DispatchState:: m_reserved 데이터 멤버

향후 정보 전달을 위해 예약 된 비트입니다.

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
