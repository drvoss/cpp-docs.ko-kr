---
title: ITopologyNode 구조체
ms.date: 11/04/2016
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
ms.openlocfilehash: 7cb815c4f7dc5ad09e8d352abc3f3375b8d9e205
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368111"
---
# <a name="itopologynode-structure"></a>ITopologyNode 구조체

리소스 관리자에 의해 정의된 토폴로지 노드에 대한 인터페이스입니다. 노드는 하나 이상의 실행 리소스를 포함합니다.

## <a name="syntax"></a>구문

```cpp
struct ITopologyNode;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[itopologyNode::GetExecutionResourceCount](#getexecutionresourcecount)|이 노드 아래에 함께 그룹화된 실행 리소스의 수를 반환합니다.|
|[i토폴로지노드::GetFirst실행리소스](#getfirstexecutionresource)|열거 순서에서 이 노드 아래에 그룹화된 첫 번째 실행 리소스를 반환합니다.|
|[이토폴로지노드::GetId](#getid)|이 노드에 대한 리소스 관리자의 고유 식별자를 반환합니다.|
|[이토폴로지노드::GetNext](#getnext)|열거 순서에 따라 다음 토폴로지 노드로 인터페이스를 반환합니다.|
|[이토폴로지노드::겟누마노드](#getnumanode)|이 리소스 Maanger 노드가 속한 Windows 할당된 NUMA 노드 번호를 반환합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 일반적으로 리소스 관리자에서 관찰한 대로 시스템의 토폴로지 이동에 사용됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ITopologyNode`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="itopologynodegetexecutionresourcecount-method"></a><a name="getexecutionresourcecount"></a>itopologyNode::GetExecutionResourceCount 방법

이 노드 아래에 함께 그룹화된 실행 리소스의 수를 반환합니다.

```cpp
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Return Value

이 노드 아래에 함께 그룹화된 실행 리소스의 수입니다.

## <a name="itopologynodegetfirstexecutionresource-method"></a><a name="getfirstexecutionresource"></a>itopologyNode::GetFirst실행리소스 방법

열거 순서에서 이 노드 아래에 그룹화된 첫 번째 실행 리소스를 반환합니다.

```cpp
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Return Value

열거 순서에서 이 노드 아래에 그룹화된 첫 번째 실행 리소스입니다.

## <a name="itopologynodegetid-method"></a><a name="getid"></a>itopologyNode::GetId 방법

이 노드에 대한 리소스 관리자의 고유 식별자를 반환합니다.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Return Value

이 노드에 대한 리소스 관리자의 고유 식별자입니다.

### <a name="remarks"></a>설명

동시성 런타임은 프로세서 노드 그룹에서 시스템의 하드웨어 스레드를 나타냅니다. 노드는 일반적으로 시스템의 하드웨어 토폴로지에서 파생됩니다. 예를 들어 특정 소켓 또는 특정 NUMA 노드의 모든 프로세서가 동일한 프로세서 노드에 속할 수 있습니다. 리소스 관리자는 시스템의 총 프로세서 노드 수를 `0` `nodeCount` 나타내는 최대 `nodeCount - 1`및 포함부터 이러한 노드에 고유 식별자를 할당합니다.

노드 의 수는 [함수 GetProcessorNodeCount에서](concurrency-namespace-functions.md)얻을 수 있습니다.

## <a name="itopologynodegetnext-method"></a><a name="getnext"></a>itopologyNode::GetNext 방법

열거 순서에 따라 다음 토폴로지 노드로 인터페이스를 반환합니다.

```cpp
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Return Value

열거 순서에서 다음 노드에 대한 인터페이스입니다. 시스템 토폴로지의 열거 순서에 노드가 더 이상 없을 경우 이 메서드는 `NULL` 값을 반환합니다.

## <a name="itopologynodegetnumanode-method"></a><a name="getnumanode"></a>itopology노드::겟넘마노드 방법

이 리소스 Maanger 노드가 속한 Windows 할당된 NUMA 노드 번호를 반환합니다.

```cpp
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Return Value

Windows에서 이 리소스 관리자 노드가 속한 NUMA 노드 번호를 할당했습니다.

### <a name="remarks"></a>설명

이 노드에 속한 가상 프로세서 루트에서 실행되는 스레드 프록시는 이 메서드에서 반환되는 NUMA 노드에 대한 최소 한도의 NUMA 노드 수준에 대한 선호도를 갖습니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)
