---
title: '&lt;string&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
ms.openlocfilehash: 1ee36d67d137c74e17fff845f9d412b2673f311e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376634"
---
# <a name="ltstringgt-typedefs"></a>&lt;string&gt; 형식 정의

||||
|-|-|-|
|[string](#string)|[u16스트링](#u16string)|[u32스트링](#u32string)|
|[스트링](#wstring)|

## <a name="string"></a><a name="string"></a> 문자열

클래스 템플릿의 특수화를 설명하는 형식은 **문자 char의**요소와 [basic_string.](../standard-library/basic-string-class.md)

`basic_string`을 특수화하는 기타 형식 정의에는 [wstring](../standard-library/string-typedefs.md#wstring), [u16string](../standard-library/string-typedefs.md#u16string), [u32string](../standard-library/string-typedefs.md#u32string) 등이 있습니다.

```cpp
typedef basic_string<char, char_traits<char>, allocator<char>> string;
```

### <a name="remarks"></a>설명

아래의 코드 두 줄은 동일한 선언입니다.

```cpp
string str("");

basic_string<char> str("");
```

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u16string"></a><a name="u16string"></a>u16스트링

클래스 템플릿의 특수화를 설명하는 형식은 형식의 `char16_t`요소와 [basic_string.](../standard-library/basic-string-class.md)

`basic_string`을 특수화하는 기타 형식 정의에는 [wstring](../standard-library/string-typedefs.md#wstring), [string](../standard-library/string-typedefs.md#string), [u32string](../standard-library/string-typedefs.md#u32string) 등이 있습니다.

```cpp
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u32string"></a><a name="u32string"></a>u32스트링

클래스 템플릿의 특수화를 설명하는 형식은 형식의 `char32_t`요소와 [basic_string.](../standard-library/basic-string-class.md)

`basic_string`을 특수화하는 기타 형식 정의에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string), [wstring](../standard-library/string-typedefs.md#wstring) 등이 있습니다.

```cpp
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="wstring"></a><a name="wstring"></a>스트링

**wchar_t**형식의 요소와 함께 클래스 템플릿 [basic_string](../standard-library/basic-string-class.md) 특성화를 설명하는 형식입니다.

`basic_string`을 특수화하는 기타 형식 정의에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string), [u32string](../standard-library/string-typedefs.md#u32string) 등이 있습니다.

```cpp
typedef basic_string<wchar_t, char_traits<wchar_t>, allocator<wchar_t>> wstring;
```

### <a name="remarks"></a>설명

아래의 코드 두 줄은 동일한 선언입니다.

```cpp
wstring wstr(L"");

basic_string<wchar_t> wstr(L"");
```

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

> [!NOTE]
> **wchar_t** 크기는 구현 정의입니다. 코드가 특정 크기로 **wchar_t** 의존하는 경우 플랫폼의 구현(예: 사용)을 `sizeof(wchar_t)`확인합니다. 모든 플랫폼에서 너비가 동일하게 유지되도록 보장되는 문자열 문자 형식이 필요한 경우에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string) 또는 [u32string](../standard-library/string-typedefs.md#u32string)을 사용합니다.

## <a name="see-also"></a>참고 항목

[\<문자열>](../standard-library/string.md)
