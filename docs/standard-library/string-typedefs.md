---
title: '&lt;string&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
ms.openlocfilehash: 950ca5ae34b6469c3d79b7297d4fe7b7644d2fcf
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856606"
---
# <a name="ltstringgt-typedefs"></a>&lt;string&gt; 형식 정의

||||
|-|-|-|
|[string](#string)|[u16string](#u16string)|[u32string](#u32string)|
|[wstring](#wstring)|

## <a name="string"></a>  string

**Char**형식의 요소를 사용 하 여 [basic_string](../standard-library/basic-string-class.md) 클래스 템플릿의 특수화를 설명 하는 형식입니다.

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

## <a name="u16string"></a>  u16string

`char16_t`형식의 요소를 사용 하 여 [basic_string](../standard-library/basic-string-class.md) 클래스 템플릿의 특수화를 설명 하는 형식입니다.

`basic_string`을 특수화하는 기타 형식 정의에는 [wstring](../standard-library/string-typedefs.md#wstring), [string](../standard-library/string-typedefs.md#string), [u32string](../standard-library/string-typedefs.md#u32string) 등이 있습니다.

```cpp
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="u32string"></a>  u32string

`char32_t`형식의 요소를 사용 하 여 [basic_string](../standard-library/basic-string-class.md) 클래스 템플릿의 특수화를 설명 하는 형식입니다.

`basic_string`을 특수화하는 기타 형식 정의에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string), [wstring](../standard-library/string-typedefs.md#wstring) 등이 있습니다.

```cpp
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```

### <a name="remarks"></a>설명

문자열 생성자 목록은 [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)을 참조하세요.

## <a name="wstring"></a>  wstring

**Wchar_t**형식의 요소를 사용 하 여 [basic_string](../standard-library/basic-string-class.md) 클래스 템플릿의 특수화를 설명 하는 형식입니다.

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
> **Wchar_t** 크기는 구현에 정의 되어 있습니다. 코드가 특정 크기 **wchar_t** 에 종속 되는 경우 플랫폼의 구현 (예: `sizeof(wchar_t)`)을 확인 합니다. 모든 플랫폼에서 너비가 동일하게 유지되도록 보장되는 문자열 문자 형식이 필요한 경우에는 [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string) 또는 [u32string](../standard-library/string-typedefs.md#u32string)을 사용합니다.

## <a name="see-also"></a>참고 항목

[\<string>](../standard-library/string.md)
