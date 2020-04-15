---
title: scheduler_ptr 구조
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 60d71a26e5dffcadfb900ef15c26a6d9dc6d6f8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358778"
---
# <a name="scheduler_ptr-structure"></a>scheduler_ptr 구조

스케줄러에 대한 포인터를 나타냅니다. 이 클래스는 원시 포인터를 사용하여 shared_ptr 또는 일반 참조만 사용하여 공유 수명의 사양을 허용하기 위해 존재합니다.

## <a name="syntax"></a>구문

```cpp
struct scheduler_ptr;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[scheduler_ptr:scheduler_ptr](#ctor)|오버로드되었습니다. shared_ptr에서 스케줄러에 대한 스케줄러 포인터를 만듭니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[scheduler_ptr::get](#get)|스케줄러에 대한 원시 포인터를 반환합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[scheduler_ptr::연산자 불](#operator_bool)|스케줄러 포인터가 null이 아닌지 여부를 테스트합니다.|
|[scheduler_ptr::연산자-&gt;](#operator_ptr)|포인터처럼 작동합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`scheduler_ptr`

## <a name="requirements"></a>요구 사항

**헤더:** pplinterface.h

**네임스페이스:** 동시성

## <a name="scheduler_ptrget-method"></a><a name="get"></a>scheduler_ptr::get 방법

원시 포인터를 스케줄러로 반환합니다.

```cpp
scheduler_interface* get() const;
```

### <a name="return-value"></a>Return Value

## <a name="scheduler_ptroperator-bool"></a><a name="operator_bool"></a>scheduler_ptr::연산자 불

스케줄러 포인터가 null이 아닌지 테스트합니다.

```cpp
operator bool() const;
```

## <a name="scheduler_ptroperator-gt"></a><a name="operator_ptr"></a>scheduler_ptr::연산자-&gt;

포인터처럼 행동합니다.

```cpp
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>Return Value

## <a name="scheduler_ptrscheduler_ptr-constructor"></a><a name="ctor"></a>scheduler_ptr::scheduler_ptr 생성자

shared_ptr 스케줄러까지 스케줄러 포인터를 만듭니다.

```cpp
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>매개 변수

*스케줄러*<br/>
변환할 스케줄러입니다.

*p스케줄러*<br/>
변환할 스케줄러 포인터입니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)
