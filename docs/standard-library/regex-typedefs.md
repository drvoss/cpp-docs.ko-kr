---
title: '&lt;regex&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- regex/std::cmatch
- regex/std::cregex_iterator
- regex/std::cregex_token_iterator
- regex/std::csub_match
- regex/std::regex
- regex/std::smatch
- regex/std::sregex_iterator
- regex/std::sregex_token_iterator
- regex/std::ssub_match
- regex/std::wcmatch
- regex/std::wcregex_iterator
- regex/std::wcregex_token_iterator
- regex/std::wcsub_match
- regex/std::wregex
- regex/std::wsmatch
- regex/std::wsregex_iterator
- regex/std::wsregex_token_iterator
- regex/std::wssub_match
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
ms.openlocfilehash: 5dbda2df4877da7594dd633e9f203a3780b4adb1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368553"
---
# <a name="ltregexgt-typedefs"></a>&lt;regex&gt; 형식 정의

||||
|-|-|-|
|[cmatch](#cmatch)|[cregex_iterator](#cregex_iterator)|[cregex_token_iterator](#cregex_token_iterator)|
|[csub_match](#csub_match)|[Regex](#regex)|[smatch](#smatch)|
|[sregex_iterator](#sregex_iterator)|[sregex_token_iterator](#sregex_token_iterator)|[ssub_match](#ssub_match)|
|[wcmatch](#wcmatch)|[wcregex_iterator](#wcregex_iterator)|[wcregex_token_iterator](#wcregex_token_iterator)|
|[wcsub_match](#wcsub_match)|[wregex](#wregex)|[wsmatch](#wsmatch)|
|[wsregex_iterator](#wsregex_iterator)|[wsregex_token_iterator](#wsregex_token_iterator)|[wssub_match](#wssub_match)|

## <a name="cmatch-typedef"></a><a name="cmatch"></a>cmatch 유형 def

char match_results에 대한 형식 정의입니다.

```cpp
typedef match_results<const char*> cmatch;
```

### <a name="remarks"></a>설명

형식은 형식의 거리터에 대한 클래스 템플릿 match_results `const char*` [클래스의](../standard-library/match-results-class.md) 전문화에 대해 설명합니다.

## <a name="cregex_iterator-typedef"></a><a name="cregex_iterator"></a>cregex_iterator 타이프

char regex_iterator에 대한 형식 정의입니다.

```cpp
typedef regex_iterator<const char*> cregex_iterator;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 regex_iterator `const char*` [클래스의](../standard-library/regex-iterator-class.md) 전문화에 대해 설명합니다.

## <a name="cregex_token_iterator-typedef"></a><a name="cregex_token_iterator"></a>cregex_token_iterator 타이프

char regex_token_iterator에 대한 형식 정의

```cpp
typedef regex_token_iterator<const char*> cregex_token_iterator;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 regex_token_iterator `const char*` [클래스의](../standard-library/regex-token-iterator-class.md) 전문화에 대해 설명합니다.

## <a name="csub_match-typedef"></a><a name="csub_match"></a>csub_match 타이프

char sub_match에 대한 형식 정의입니다.

```cpp
typedef sub_match<const char*> csub_match;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 sub_match `const char*` [클래스의](../standard-library/sub-match-class.md) 전문화에 대해 설명합니다.

## <a name="regex-typedef"></a><a name="regex"></a>정규어 유형 def

char basic_regex에 대한 형식 정의입ㄴ니다.

```cpp
typedef basic_regex<char> regex;
```

### <a name="remarks"></a>설명

형식은 **문자 char의**요소에 대한 클래스 템플릿 [basic_regex 클래스의](../standard-library/basic-regex-class.md) 특수화를 설명합니다.

> [!NOTE]
> 높은 비트 문자의 경우 `regex`에서 예기치 않은 결과가 반환됩니다. 0~127 범위를 벗어나는 값을 사용하는 경우 정의되지 않은 동작이 발생할 수 있습니다.

## <a name="smatch-typedef"></a><a name="smatch"></a>스매치 타이프데프

string match_results에 대한 형식 정의입니다.

```cpp
typedef match_results<string::const_iterator> smatch;
```

### <a name="remarks"></a>설명

형식은 형식의 거리터에 대한 클래스 템플릿 match_results `string::const_iterator` [클래스의](../standard-library/match-results-class.md) 전문화에 대해 설명합니다.

## <a name="sregex_iterator-typedef"></a><a name="sregex_iterator"></a>sregex_iterator 타이프

regex_iterator 문자열에 대한 형식 정의입니다.

```cpp
typedef regex_iterator<string::const_iterator> sregex_iterator;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 regex_iterator `string::const_iterator` [클래스의](../standard-library/regex-iterator-class.md) 전문화에 대해 설명합니다.

## <a name="sregex_token_iterator-typedef"></a><a name="sregex_token_iterator"></a>sregex_token_iterator 타이프

string regex_token_iterator에 대한 형식 정의입니다.

```cpp
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 regex_token_iterator `string::const_iterator` [클래스의](../standard-library/regex-token-iterator-class.md) 전문화에 대해 설명합니다.

## <a name="ssub_match-typedef"></a><a name="ssub_match"></a>ssub_match 타이프

string sub_match에 대한 형식 정의입니다.

```cpp
typedef sub_match<string::const_iterator> ssub_match;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 sub_match `string::const_iterator` [클래스의](../standard-library/sub-match-class.md) 전문화에 대해 설명합니다.

## <a name="wcmatch-typedef"></a><a name="wcmatch"></a>wcmatch 타입데프

wchar_t match_results에 대한 형식 정의입니다.

```cpp
typedef match_results<const wchar_t *> wcmatch;
```

### <a name="remarks"></a>설명

형식은 형식의 거리터에 대한 클래스 템플릿 match_results `const wchar_t*` [클래스의](../standard-library/match-results-class.md) 전문화에 대해 설명합니다.

## <a name="wcregex_iterator-typedef"></a><a name="wcregex_iterator"></a>wcregex_iterator 타이프

wchar_t regex_iterator에 대한 형식 정의입니다.

```cpp
typedef regex_iterator<const wchar_t*> wcregex_iterator;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 regex_iterator `const wchar_t*` [클래스의](../standard-library/regex-iterator-class.md) 전문화에 대해 설명합니다.

## <a name="wcregex_token_iterator-typedef"></a><a name="wcregex_token_iterator"></a>wcregex_token_iterator 타이프

wchar_t regex_token_iterator에 대한 형식 정의입니다.

```cpp
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 regex_token_iterator `const wchar_t*` [클래스의](../standard-library/regex-token-iterator-class.md) 전문화에 대해 설명합니다.

## <a name="wcsub_match-typedef"></a><a name="wcsub_match"></a>wcsub_match 타이프

wchar_t sub_match에 대한 형식 정의입니다.

```cpp
typedef sub_match<const wchar_t*> wcsub_match;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 sub_match `const wchar_t*` [클래스의](../standard-library/sub-match-class.md) 전문화에 대해 설명합니다.

## <a name="wregex-typedef"></a><a name="wregex"></a>레그렉스 타이프

wchar_t basic_regex에 대한 형식 정의입니다.

```cpp
typedef basic_regex<wchar_t> wregex;
```

### <a name="remarks"></a>설명

형식은 **형식 wchar_t**요소에 대한 클래스 템플릿 [basic_regex 클래스의](../standard-library/basic-regex-class.md) 전문화에 대해 설명합니다.

## <a name="wsmatch-typedef"></a><a name="wsmatch"></a>와스매치 타입데프

wstring match_results에 대한 형식 정의입니다.

```cpp
typedef match_results<wstring::const_iterator> wsmatch;
```

### <a name="remarks"></a>설명

형식은 형식의 거리터에 대한 클래스 템플릿 match_results `wstring::const_iterator` [클래스의](../standard-library/match-results-class.md) 전문화에 대해 설명합니다.

## <a name="wsregex_iterator-typedef"></a><a name="wsregex_iterator"></a>wsregex_iterator 타이프

regex_iterator에 대한 형식 정의입니다.

```cpp
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 regex_iterator `wstring::const_iterator` [클래스의](../standard-library/regex-iterator-class.md) 전문화에 대해 설명합니다.

## <a name="wsregex_token_iterator-typedef"></a><a name="wsregex_token_iterator"></a>wsregex_token_iterator 타이프

regex_token_iterator에 대한 형식 정의입니다.

```cpp
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 regex_token_iterator `wstring::const_iterator` [클래스의](../standard-library/regex-token-iterator-class.md) 전문화에 대해 설명합니다.

## <a name="wssub_match-typedef"></a><a name="wssub_match"></a>wssub_match 타이프

wstring sub_match에 대한 형식 정의입니다.

```cpp
typedef sub_match<wstring::const_iterator> wssub_match;
```

### <a name="remarks"></a>설명

형식은 형식의 거처에 대한 클래스 템플릿 sub_match `wstring::const_iterator` [클래스의](../standard-library/sub-match-class.md) 전문화에 대해 설명합니다.

## <a name="see-also"></a>참고 항목

[\<정규식>](../standard-library/regex.md)\
[regex_constants 클래스](../standard-library/regex-constants-class.md)\
[regex_error 클래스](../standard-library/regex-error-class.md)\
[\<정규식> 함수](../standard-library/regex-functions.md)\
[regex_iterator 클래스](../standard-library/regex-iterator-class.md)\
[\<정규식> 연산자](../standard-library/regex-operators.md)\
[regex_token_iterator 클래스](../standard-library/regex-token-iterator-class.md)\
[regex_traits 클래스](../standard-library/regex-traits-class.md)
