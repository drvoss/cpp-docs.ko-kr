---
title: hash 구조체
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::hash
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
ms.openlocfilehash: 4f73d1bfe7f3370d76b39b95f740a4d3a759b908
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426926"
---
# <a name="hash-structure"></a>hash 구조체

클래스 템플릿은 `val.hash_code()`반환 하는 메서드를 정의 합니다. 메서드는 [type_index](../standard-library/type-index-class.md) 형식의 맵 값을 인덱스 값의 분포로 매핑하는 데 사용하는 해시 함수를 정의합니다.

## <a name="syntax"></a>구문

```cpp
template <> struct hash<type_index>
: public unary_function<type_index, size_t>
{ // hashes a typeinfo object
    size_t operator()(type_index val) const;
};
```

## <a name="specialized-types"></a>특수 형식

### <a name="system_error"></a>\<system_error >

```cpp
template <class T> struct hash;
template <> struct hash<error_code>;
template <> struct hash<error_condition>;
```

## <a name="see-also"></a>참고 항목

[\<typeindex>](../standard-library/typeindex.md)
