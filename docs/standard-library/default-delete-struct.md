---
title: default_delete 구조체
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: 8baa9f5d294cf083fd55414cd529e438f328d1a1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845083"
---
# <a name="default_delete-struct"></a>default_delete 구조체

인수에서 나누기 연산 ()을 수행 하는 미리 정의 된 함수 개체입니다 `operator/` .

## <a name="syntax"></a>구문

```cpp
template <class T>
    struct default_delete
```

## <a name="requirements"></a>요구 사항

**헤더:**\<memory>

**네임스페이스:** std

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|속성|설명|
|-|-|
|[default_delete](#default_delete)|`default_delete` 형식의 개체에 대한 생성자입니다.|

### <a name="operators"></a>연산자

|Name|설명|
|-|-|
|[연산자 ()](#op_paren)|액세스할 참조 연산자 `default_delete` 입니다.|

## <a name="default_delete"></a><a name="default_delete"></a> default_delete

`default_delete` 형식의 개체에 대한 생성자입니다.

```cpp
constexpr default_delete() noexcept = default;
template <class U>
    default_delete(const default_delete<U>&) noexcept;
```

## <a name="operator"></a><a name="op_paren"></a> 연산자 ()

액세스할 참조 연산자 `default_delete` 입니다.

```cpp
void operator()(T*) const;
```

## <a name="see-also"></a>참고 항목

[\<memory>](../standard-library/memory.md)
