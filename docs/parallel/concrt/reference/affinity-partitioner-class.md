---
title: affinity_partitioner 클래스
ms.date: 11/04/2016
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
ms.openlocfilehash: 0ae6bbee49d1b8873190a7054e55f65b40b31b13
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142884"
---
# <a name="affinity_partitioner-class"></a>affinity_partitioner 클래스

`affinity_partitioner` 클래스는 `static_partitioner` 클래스와 비슷하지만 하위 범위를 작업자 스레드로 매핑하는 선택을 통해 캐시 선호도를 향상시킵니다. 동일한 데이터 집합에서 루프를 다시 실행하고 데이터가 캐시에 맞는 경우 성능을 훨씬 향상시킬 수 있습니다. 데이터 집약성을 활용하려면 특정 데이터 집합에 대해 실행되는 병렬 루프의 후속 반복과 함께 동일한 `affinity_partitioner` 개체를 사용해야 합니다.

## <a name="syntax"></a>구문

```cpp
class affinity_partitioner;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[affinity_partitioner](#ctor)|`affinity_partitioner` 개체를 생성합니다.|
|[~ affinity_partitioner 소멸자](#dtor)|`affinity_partitioner` 개체를 소멸 시킵니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`affinity_partitioner`

## <a name="requirements"></a>요구 사항

**헤더:** ppl. h

**네임스페이스:** 동시성

## <a name="dtor"></a>~ affinity_partitioner

`affinity_partitioner` 개체를 소멸 시킵니다.

```cpp
~affinity_partitioner();
```

## <a name="ctor"></a>affinity_partitioner

`affinity_partitioner` 개체를 생성합니다.

```cpp
affinity_partitioner();
```

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
