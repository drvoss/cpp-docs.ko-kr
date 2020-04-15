---
title: '&lt;string_view&gt; 타입데프'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 0ec278484b7c1c9887771f6cbe7e5d0b05205dd7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376670"
---
# <a name="ltstring_viewgt-typedefs"></a>&lt;string_view&gt; 타입데프

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a><a name="string_view"></a>string_view

클래스 템플릿의 특수화를 설명하는 형식은 **char**형식의 요소와 [basic_string_view.](../standard-library/basic-string-view-class.md)

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>설명

아래의 코드 두 줄은 동일한 선언입니다.

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u16string_view"></a><a name="u16string_view"></a>u16string_view

클래스 템플릿의 특수화를 설명하는 형식은 형식의 `char16_t`요소와 [basic_string_view.](../standard-library/basic-string-view-class.md)

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u32string_view"></a><a name="u32string_view"></a>u32string_view

클래스 템플릿의 특수화를 설명하는 형식은 형식의 `char32_t`요소와 [basic_string_view.](../standard-library/basic-string-view-class.md)

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="wstring_view"></a><a name="wstring_view"></a>wstring_view

클래스 템플릿의 특수화를 설명하는 형식은 **wchar_t**요소로 [basic_string_view.](../standard-library/basic-string-view-class.md)

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>설명

아래의 코드 두 줄은 동일한 선언입니다.

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

> [!NOTE]
> **wchar_t** 크기는 Windows에서 2바이트이지만 모든 플랫폼의 경우는 아닙니다. 모든 플랫폼에서 동일하게 유지되도록 보장되는 너비가 string_view 넓은 문자 유형이 필요한 경우 [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) 또는 [u32string_view.](../standard-library/string-view-typedefs.md#u32string_view)

## <a name="see-also"></a>참고 항목

[\<string_view>](../standard-library/string-view.md)
