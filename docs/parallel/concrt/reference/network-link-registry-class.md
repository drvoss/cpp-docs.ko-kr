---
title: network_link_registry 클래스
ms.date: 11/04/2016
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
ms.openlocfilehash: 430190c11ec06a4f26eb9d8c4237552848420ad7
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138882"
---
# <a name="network_link_registry-class"></a>network_link_registry 클래스

`network_link_registry` 추상 기본 클래스는 소스 및 대상 블록 간의 연결을 관리합니다.

## <a name="syntax"></a>구문

```cpp
template<class _Block>
class network_link_registry;
```

### <a name="parameters"></a>매개 변수

*_Block*<br/>
`network_link_registry`에 저장 되는 블록 데이터 형식입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|name|설명|
|----------|-----------------|
|`const_pointer`|`network_link_registry` 개체의 `const` 요소에 대 한 포인터를 제공 하는 형식입니다.|
|`const_reference`|Const 작업을 읽고 수행 하기 위해 `network_link_registry` 개체에 저장 된 `const` 요소에 대 한 참조를 제공 하는 형식입니다.|
|`iterator`|`network_link_registry` 개체의 모든 요소를 읽거나 수정할 수 있는 반복기를 제공 하는 형식입니다.|
|`type`|`network_link_registry` 개체에 저장 된 블록 형식을 나타내는 형식입니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[add](#add)|파생 클래스에서 재정의 되는 경우 `network_link_registry` 개체에 대 한 링크를 추가 합니다.|
|[begin](#begin)|파생 클래스에서 재정의 되는 경우 `network_link_registry` 개체의 첫 번째 요소에 반복기를 반환 합니다.|
|[contains](#contains)|파생 클래스에서 재정의 되는 경우 지정 된 블록에 대 한 `network_link_registry` 개체를 검색 합니다.|
|[count](#count)|파생 클래스에서 재정의 되는 경우 `network_link_registry` 개체의 항목 수를 반환 합니다.|
|[remove](#remove)|파생 클래스에서 재정의 되는 경우 `network_link_registry` 개체에서 지정 된 블록을 제거 합니다.|

## <a name="remarks"></a>설명

`network link registry`은 동시 액세스에 안전 하지 않습니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`network_link_registry`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

## <a name="add"></a>추가

파생 클래스에서 재정의 되는 경우 `network_link_registry` 개체에 대 한 링크를 추가 합니다.

```cpp
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
추가할 블록에 대 한 포인터입니다.

## <a name="begin"></a>시작

파생 클래스에서 재정의 되는 경우 `network_link_registry` 개체의 첫 번째 요소에 반복기를 반환 합니다.

```cpp
virtual iterator begin() = 0;
```

### <a name="return-value"></a>Return Value

`network_link_registry` 개체에서 첫 번째 요소를 주소 지정 하는 반복기입니다.

### <a name="remarks"></a>설명

반복기의 종료 상태는 `NULL` 링크로 표시 됩니다.

## <a name="contains"></a>에서는

파생 클래스에서 재정의 되는 경우 지정 된 블록에 대 한 `network_link_registry` 개체를 검색 합니다.

```cpp
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
`network_link_registry` 개체에서 검색 되는 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

블록이 있으면 **true** 이 고, 그렇지 않으면 **false** 입니다.

## <a name="count"></a>수

파생 클래스에서 재정의 되는 경우 `network_link_registry` 개체의 항목 수를 반환 합니다.

```cpp
virtual size_t count() = 0;
```

### <a name="return-value"></a>Return Value

`network_link_registry` 개체에 있는 항목 수입니다.

## <a name="remove"></a>삭제

파생 클래스에서 재정의 되는 경우 `network_link_registry` 개체에서 지정 된 블록을 제거 합니다.

```cpp
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
제거 될 블록에 대 한 포인터입니다 (있는 경우).

### <a name="return-value"></a>Return Value

링크를 찾아 제거 했으면 **true** 이 고, 그렇지 않으면 **false** 입니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[single_link_registry 클래스](single-link-registry-class.md)<br/>
[multi_link_registry 클래스](multi-link-registry-class.md)
