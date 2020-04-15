---
title: regex_error 클래스
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
ms.openlocfilehash: f8f3c88c1b203ed7fcea148843fa99590e27b888
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331865"
---
# <a name="regex_error-class"></a>regex_error 클래스

잘못된 basic_regex 개체를 보고합니다.

## <a name="syntax"></a>구문

```cpp
class regex_error
: public std::runtime_error
```

## <a name="remarks"></a>설명

클래스는 `basic_regex` 개체의 사용 또는 생성 중 오류를 보고하기 위해 throw된 예외 개체를 설명합니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[regex_error](#regex_error)|개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[코드](#code)|오류 코드를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<regex>

**네임스페이스:** std

## <a name="example"></a>예제

```cpp
// std__regex__regex_error.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code() ? "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }
```

```Output
regex error: unbalanced parentheses
```

## <a name="regex_errorcode"></a><a name="code"></a>regex_error::코드

오류 코드를 반환합니다.

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>설명

멤버 함수는 개체의 생성자에 전달된 값을 반환합니다.

## <a name="regex_errorregex_error"></a><a name="regex_error"></a>regex_error:regex_error

개체를 생성합니다.

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>매개 변수

*오류*\
오류 코드입니다.

### <a name="remarks"></a>설명

생성자는 값 *오류를*보유 하는 개체를 생성 합니다.

## <a name="see-also"></a>참고 항목

[\<정규식>](../standard-library/regex.md)\
[regex_constants 클래스](../standard-library/regex-constants-class.md)\
[\<정규식> 함수](../standard-library/regex-functions.md)\
[regex_iterator 클래스](../standard-library/regex-iterator-class.md)\
[\<정규식> 연산자](../standard-library/regex-operators.md)\
[regex_token_iterator 클래스](../standard-library/regex-token-iterator-class.md)\
[regex_traits 클래스](../standard-library/regex-traits-class.md)\
[\<정규식> 타입defs](../standard-library/regex-typedefs.md)
