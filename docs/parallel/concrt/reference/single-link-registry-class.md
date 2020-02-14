---
title: single_link_registry 클래스
ms.date: 11/04/2016
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
ms.openlocfilehash: c29caf6d31df316e80b15fe6827c81e34ece8a18
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142717"
---
# <a name="single_link_registry-class"></a>single_link_registry 클래스

`single_link_registry` 개체는 단일 소스 또는 대상 블록만 관리하는 `network_link_registry`입니다.

## <a name="syntax"></a>구문

```cpp
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>매개 변수

*_Block*<br/>
`single_link_registry` 개체에 저장 되는 블록 데이터 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[single_link_registry](#ctor)|`single_link_registry` 개체를 생성합니다.|
|[~ single_link_registry 소멸자](#dtor)|`single_link_registry` 개체를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[add](#add)|`single_link_registry` 개체에 대 한 링크를 추가 합니다. [Network_link_registry:: add](network-link-registry-class.md#add)를 재정의 합니다.|
|[begin](#begin)|`single_link_registry` 개체의 첫 번째 요소에 대 한 반복기를 반환 합니다. [Network_link_registry:: begin](network-link-registry-class.md#begin)을 재정의 합니다.|
|[contains](#contains)|지정 된 블록에 대 한 `single_link_registry` 개체를 검색 합니다. [Network_link_registry:: contains](network-link-registry-class.md#contains)를 재정의 합니다.|
|[count](#count)|`single_link_registry` 개체의 항목 수를 셉니다. [Network_link_registry:: count](network-link-registry-class.md#count)를 재정의 합니다.|
|[remove](#remove)|`single_link_registry` 개체에서 링크를 제거 합니다. [Network_link_registry:: remove](network-link-registry-class.md#remove)를 재정의 합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

## <a name="add"></a>추가

`single_link_registry` 개체에 대 한 링크를 추가 합니다.

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
추가할 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 레지스트리에 이미 링크가 있는 경우 메서드는 [invalid_link_target](invalid-link-target-class.md) 예외를 throw 합니다.

## <a name="begin"></a>시작

`single_link_registry` 개체의 첫 번째 요소에 대 한 반복기를 반환 합니다.

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Return Value

`single_link_registry` 개체에서 첫 번째 요소를 주소 지정 하는 반복기입니다.

### <a name="remarks"></a>설명

최종 상태는 `NULL` 링크로 표시 됩니다.

## <a name="contains"></a>에서는

지정 된 블록에 대 한 `single_link_registry` 개체를 검색 합니다.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
`single_link_registry` 개체에서 검색할 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

링크가 있으면 **true** 이 고, 그렇지 않으면 **false** 입니다.

## <a name="count"></a>수

`single_link_registry` 개체의 항목 수를 셉니다.

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Return Value

`single_link_registry` 개체에 있는 항목 수입니다.

## <a name="remove"></a>삭제

`single_link_registry` 개체에서 링크를 제거 합니다.

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
제거 될 블록에 대 한 포인터입니다 (있는 경우).

### <a name="return-value"></a>Return Value

링크를 찾아 제거 했으면 **true** 이 고, 그렇지 않으면 **false** 입니다.

## <a name="ctor"></a>single_link_registry

`single_link_registry` 개체를 생성합니다.

```cpp
single_link_registry();
```

## <a name="dtor"></a>~ single_link_registry

`single_link_registry` 개체를 소멸 시킵니다.

```cpp
virtual ~single_link_registry();
```

### <a name="remarks"></a>설명

메서드는 링크가 제거 되기 전에 호출 되는 경우 [invalid_operation](invalid-operation-class.md) 예외를 throw 합니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[multi_link_registry 클래스](multi-link-registry-class.md)
