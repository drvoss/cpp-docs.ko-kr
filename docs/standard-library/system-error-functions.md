---
title: '&lt;system_error&gt; 함수'
ms.date: 03/15/2019
f1_keywords:
- system_error/std::generic_category
- system_error/std::make_error_code
- system_error/std::make_error_condition
- system_error/std::system_category
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
helpviewer_keywords:
- std::generic_category
- std::make_error_code
- std::make_error_condition
- std::system_category
ms.openlocfilehash: 2ddeb256c974294e2e46d516219a6b5b0cac3ae2
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076357"
---
# <a name="ltsystem_errorgt-functions"></a>&lt;system_error&gt; 함수

## <a name="generic_category"></a><a name="generic_category"></a>generic_category

일반 오류의 범주를 나타냅니다.

```cpp
const error_category& generic_category() noexcept;
```

### <a name="remarks"></a>주의

`generic_category` 개체는 [error_category](../standard-library/error-category-class.md)의 구현입니다.

## <a name="is_error_code_enum_v"></a><a name="is_error_code_enum_v"></a>is_error_code_enum_v

```cpp
template <class T>
    inline constexpr bool is_error_code_enum_v = is_error_code_enum<T>::value;
```

## <a name="is_error_condition_enum_v"></a><a name="is_error_condition_enum_v"></a>is_error_condition_enum_v

```cpp
template <class T>
    inline constexpr bool is_error_condition_enum_v = is_error_condition_enum<T>::value;
```

## <a name="make_error_code"></a><a name="make_error_code"></a>make_error_code

오류 코드 개체를 만듭니다.

```cpp
error_code make_error_code(std::errc error) noexcept;
```

### <a name="parameters"></a>매개 변수

*오류*\
오류 코드 개체에 저장할 `std::errc` 열거형 값입니다.

### <a name="return-value"></a>반환 값

오류 코드 개체입니다.

### <a name="remarks"></a>주의

## <a name="make_error_condition"></a><a name="make_error_condition"></a>make_error_condition

오류 조건 개체를 만듭니다.

```cpp
error_condition make_error_condition(std::errc error) noexcept;
```

### <a name="parameters"></a>매개 변수

*오류*\
오류 코드 개체에 저장할 `std::errc` 열거형 값입니다.

### <a name="return-value"></a>반환 값

오류 조건 개체입니다.

### <a name="remarks"></a>주의

## <a name="system_category"></a><a name="system_category"></a>system_category

하위 수준 시스템 오버플로로 인해 발생하는 오류의 범주를 나타냅니다.

```cpp
const error_category& system_category() noexcept;
```

### <a name="remarks"></a>주의

`system_category` 개체는 [error_category](../standard-library/error-category-class.md)의 구현입니다.
