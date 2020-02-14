---
title: auto_partitioner 클래스
ms.date: 11/04/2016
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
ms.openlocfilehash: 4d1d8f19069412240de8e9d69cdcfb34618f2796
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142860"
---
# <a name="auto_partitioner-class"></a>auto_partitioner 클래스

`auto_partitioner` 클래스는 `parallel_for`, `parallel_for_each` 및 `parallel_transform`이 반복하는 범위를 분할하는 데 사용하는 기본 방법을 나타냅니다. 이 분할 방법은 부하 분산 및 반복 별 취소에 대해 범위 가로채기를 채택 합니다.

## <a name="syntax"></a>구문

```cpp
class auto_partitioner;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[auto_partitioner](#ctor)|`auto_partitioner` 개체를 생성합니다.|
|[~ auto_partitioner 소멸자](#dtor)|`auto_partitioner` 개체를 제거합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`auto_partitioner`

## <a name="requirements"></a>요구 사항

**헤더:** ppl. h

**네임스페이스:** 동시성

## <a name="dtor"></a>~ auto_partitioner

`auto_partitioner` 개체를 제거합니다.

```cpp
~auto_partitioner();
```

## <a name="ctor"></a>auto_partitioner

`auto_partitioner` 개체를 생성합니다.

```cpp
auto_partitioner();
```

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
