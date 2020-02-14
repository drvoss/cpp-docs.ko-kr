---
title: source_link_manager 클래스
ms.date: 11/04/2016
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
ms.openlocfilehash: 35c7cc72520cdb0675abf9c15574a49e33741d0b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142690"
---
# <a name="source_link_manager-class"></a>source_link_manager 클래스

`source_link_manager` 개체는 `ISource` 블록에 대한 메시징 블록 네트워크 연결을 관리합니다.

## <a name="syntax"></a>구문

```cpp
template<class _LinkRegistry>
class source_link_manager;
```

### <a name="parameters"></a>매개 변수

*_LinkRegistry*<br/>
네트워크 링크 레지스트리

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|name|설명|
|----------|-----------------|
|`const_pointer`|`source_link_manager` 개체의 `const` 요소에 대 한 포인터를 제공 하는 형식입니다.|
|`const_reference`|Const 작업을 읽고 수행 하기 위해 `source_link_manager` 개체에 저장 된 `const` 요소에 대 한 참조를 제공 하는 형식입니다.|
|`iterator`|`source_link_manager` 개체의 모든 요소를 읽거나 수정할 수 있는 반복기를 제공 하는 형식입니다.|
|`type`|`source_link_manager` 개체에서 관리 하는 링크 레지스트리의 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[source_link_manager](#ctor)|`source_link_manager` 개체를 생성합니다.|
|[~ source_link_manager 소멸자](#dtor)|`source_link_manager` 개체를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[add](#add)|`source_link_manager` 개체에 소스 링크를 추가 합니다.|
|[begin](#begin)|`source_link_manager` 개체의 첫 번째 요소에 대 한 반복기를 반환 합니다.|
|[contains](#contains)|이 `source_link_manager` 개체 내에서 지정 된 블록에 대 한 `network_link_registry`를 검색 합니다.|
|[count](#count)|`source_link_manager` 개체의 연결 된 블록 수를 셉니다.|
|[reference](#reference)|`source_link_manager` 개체에 대 한 참조를 가져옵니다.|
|[register_target_block](#register_target_block)|이 `source_link_manager` 개체를 보유 하는 대상 블록을 등록 합니다.|
|[release](#release)|`source_link_manager` 개체에 대 한 참조를 해제 합니다.|
|[remove](#remove)|`source_link_manager` 개체에서 링크를 제거 합니다.|
|[set_bound](#set_bound)|이 `source_link_manager` 개체에 추가할 수 있는 최대 소스 링크 수를 설정 합니다.|

## <a name="remarks"></a>설명

현재 소스 블록은 참조 횟수가 계산 됩니다. 이는 링크에 대 한 동시 액세스를 허용 하 고 콜백을 통해 링크를 참조 하는 기능을 제공 하는 `network_link_registry` 개체의 래퍼입니다. 메시지 블록 (`target_block`s 또는 `propagator_block`s)은 소스 링크에 대해이 클래스를 사용 해야 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`source_link_manager`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

## <a name="add"></a>추가

`source_link_manager` 개체에 소스 링크를 추가 합니다.

```cpp
void add(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
추가할 블록에 대 한 포인터입니다.

## <a name="begin"></a>시작

`source_link_manager` 개체의 첫 번째 요소에 대 한 반복기를 반환 합니다.

```cpp
iterator begin();
```

### <a name="return-value"></a>Return Value

`source_link_manager` 개체에서 첫 번째 요소를 주소 지정 하는 반복기입니다.

### <a name="remarks"></a>설명

반복기의 종료 상태는 `NULL` 링크로 표시 됩니다.

## <a name="contains"></a>에서는

이 `source_link_manager` 개체 내에서 지정 된 블록에 대 한 `network_link_registry`를 검색 합니다.

```cpp
bool contains(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
`source_link_manager` 개체에서 검색할 블록에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

지정 된 블록이 발견 되 면 **true** 이 고, 그렇지 않으면 **false** 입니다.

## <a name="count"></a>수

`source_link_manager` 개체의 연결 된 블록 수를 셉니다.

```cpp
size_t count();
```

### <a name="return-value"></a>Return Value

`source_link_manager` 개체의 연결 된 블록 수입니다.

## <a name="reference"></a>참조일

`source_link_manager` 개체에 대 한 참조를 가져옵니다.

```cpp
void reference();
```

## <a name="register_target_block"></a>register_target_block

이 `source_link_manager` 개체를 보유 하는 대상 블록을 등록 합니다.

```cpp
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 `source_link_manager` 개체를 보유 하는 대상 블록입니다.

## <a name="release"></a>릴리스

`source_link_manager` 개체에 대 한 참조를 해제 합니다.

```cpp
void release();
```

## <a name="remove"></a>삭제

`source_link_manager` 개체에서 링크를 제거 합니다.

```cpp
bool remove(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
제거 될 블록에 대 한 포인터입니다 (있는 경우).

### <a name="return-value"></a>Return Value

링크를 찾아 제거 했으면 **true** 이 고, 그렇지 않으면 **false** 입니다.

## <a name="set_bound"></a>set_bound

이 `source_link_manager` 개체에 추가할 수 있는 최대 소스 링크 수를 설정 합니다.

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>매개 변수

*_MaxLinks*<br/>
최대 링크 수입니다.

## <a name="ctor"></a>source_link_manager

`source_link_manager` 개체를 생성합니다.

```cpp
source_link_manager();
```

## <a name="dtor"></a>~ source_link_manager

`source_link_manager` 개체를 소멸 시킵니다.

```cpp
~source_link_manager();
```

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[single_link_registry 클래스](single-link-registry-class.md)<br/>
[multi_link_registry 클래스](multi-link-registry-class.md)
