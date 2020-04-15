---
title: ITopologyExecutionResource 구조체
ms.date: 11/04/2016
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
ms.openlocfilehash: 2c9221cab1ac2d48bd099a769188e4bee797823c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368141"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource 구조체

리소스 관리자에 의해 정의된 실행 리소스에 대한 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
struct ITopologyExecutionResource;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[이토폴로지실행리소스::GetId](#getid)|이 실행 리소스에 대한 리소스 관리자의 고유 식별자를 반환합니다.|
|[i토폴로지실행리소스::GetNext](#getnext)|열거 순서에서 다음 실행 리소스에 대한 인터페이스를 반환합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 일반적으로 리소스 관리자에서 관찰한 대로 시스템의 토폴로지 이동에 사용됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ITopologyExecutionResource`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="itopologyexecutionresourcegetid-method"></a><a name="getid"></a>itopology실행리소스::GetId 방법

이 실행 리소스에 대한 리소스 관리자의 고유 식별자를 반환합니다.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Return Value

이 실행 리소스에 대한 리소스 관리자의 고유 식별자입니다.

## <a name="itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a>itopology실행리소스::GetNext 방법

열거 순서에서 다음 실행 리소스에 대한 인터페이스를 반환합니다.

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Return Value

열거 순서에서 다음 실행 리소스에 대한 인터페이스입니다. 이 실행 리소스가 속한 노드의 열거 순서에 노드가 더 이상 없을 경우 이 메서드는 `NULL` 값을 반환합니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)
