---
title: '&lt;string_view&gt; typedef'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: c3367afe1353ac70abb74a59658a255614ac8470
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865849"
---
# <a name="ltstring_viewgt-typedefs"></a>&lt;string_view&gt; typedef

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a>string_view

**Char**형식의 요소를 사용 하 여 [basic_string_view](../standard-library/basic-string-view-class.md) 클래스 템플릿의 특수화를 설명 하는 형식입니다.

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

## <a name="u16string_view"></a>u16string_view

`char16_t`형식의 요소를 사용 하 여 [basic_string_view](../standard-library/basic-string-view-class.md) 클래스 템플릿의 특수화를 설명 하는 형식입니다.

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u32string_view"></a>u32string_view

`char32_t`형식의 요소를 사용 하 여 [basic_string_view](../standard-library/basic-string-view-class.md) 클래스 템플릿의 특수화를 설명 하는 형식입니다.

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="wstring_view"></a>wstring_view

**Wchar_t**형식의 요소를 사용 하 여 [basic_string_view](../standard-library/basic-string-view-class.md) 클래스 템플릿의 특수화를 설명 하는 형식입니다.

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
> **Wchar_t** 크기는 Windows에서 2 바이트 이지만 모든 플랫폼에서 반드시 필요한 것은 아닙니다. 모든 플랫폼에서 너비가 동일 하 게 유지 되도록 보장 되는 string_view 와이드 문자 형식이 필요한 경우 [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) 또는 [u32string_view](../standard-library/string-view-typedefs.md#u32string_view)를 사용 합니다.

## <a name="see-also"></a>참고 항목

[\<string_view >](../standard-library/string-view.md)
