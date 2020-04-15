---
title: money_put 클래스
ms.date: 11/01/2018
f1_keywords:
- xlocmon/std::money_put
- xlocmon/std::money_put::char_type
- xlocmon/std::money_put::iter_type
- xlocmon/std::money_put::string_type
- xlocmon/std::money_put::do_put
- xlocmon/std::money_put::put
helpviewer_keywords:
- std::money_put [C++]
- std::money_put [C++], char_type
- std::money_put [C++], iter_type
- std::money_put [C++], string_type
- std::money_put [C++], do_put
- std::money_put [C++], put
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
ms.openlocfilehash: 035cc4e7b9cfac262979509bf7b4570e2c55336c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377424"
---
# <a name="money_put-class"></a>money_put 클래스

클래스 템플릿은 금전적 값의 변환을 형식의 `CharType`시퀀스로 제어하는 로캘 면역할을 할 수 있는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class money_put : public locale::facet;
```

### <a name="parameters"></a>매개 변수

*Chartype*\
로캘의 문자를 인코딩하기 위해 프로그램 내 사용하는 형식입니다.

*출력이터*\
통화 put 함수가 출력을 쓰는 반복기의 형식입니다.

## <a name="remarks"></a>설명

모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 저장된 값에 액세스를 처음 시도하면 **id**에 고유한 양수 값이 저장됩니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[money_put](#money_put)|`money_put` 형식의 개체에 대한 생성자입니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[char_type](#char_type)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|
|[iter_type](#iter_type)|출력 반복기에 대해 설명하는 형식입니다.|
|[string_type](#string_type)|`CharType` 형식의 문자가 포함된 문자열을 설명하는 형식입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[do_put](#do_put)|숫자 또는 문자열을 통화 값을 나타내는 문자 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|
|[넣어](#put)|숫자 또는 문자열을 통화 값을 나타내는 문자 시퀀스로 변환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="money_putchar_type"></a><a name="char_type"></a>money_put:char_type

로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수 **CharType의**동의어입니다.

## <a name="money_putdo_put"></a><a name="do_put"></a>money_put::do_put

숫자 또는 문자열을 통화 값을 나타내는 문자 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.

```cpp
virtual iter_type do_put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    const string_type& val) const;

virtual iter_type do_put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

### <a name="parameters"></a>매개 변수

*다음*\
삽입된 문자열의 첫 번째 요소 주소를 지정하는 반복기입니다.

*_Intl*\
시퀀스에서 필요한 통화 기호 유형을 나타내는 부울 값입니다. 국제의 경우 **true**이고 국내의 경우 **false**입니다.

*_Iosbase*\
집합이 통화 기호가 선택 사항임을 나타낼 때 사용하는 형식 플래그입니다. 그 외의 경우 통화 기호는 필수 항목입니다.

*_Fill*\
간격에 사용되는 문자입니다.

*발*\
변환할 문자열 개체입니다.

### <a name="return-value"></a>Return Value

생성된 마지막 요소에서 한 위치 다음의 위치 주소를 지정하는 출력 반복기입니다.

### <a name="remarks"></a>설명

첫 번째 가상 보호 멤버 함수는 [string_type](#string_type) 개체 *val에서*통화 출력 필드를 생성하기 위해 *옆에서* 시작하는 순차 적 요소를 생성합니다. *val으로* 제어되는 시퀀스는 소수자릿수 중 하나 이상으로 시작해야 하며, 선택적으로 양을 나타내는 마이너스 부호(-)가 앞에 옵니다. 함수는 생성된 통화 출력 필드를 벗어난 범위에 있는 첫 번째 요소를 지정하는 반복기를 반환합니다.

두 번째 가상 보호 멤버 함수는 val을 소수 자릿수 시퀀스로 *val* 효과적으로 변환하고 선택적으로 빼기 기호앞에 오는 다음 위와 같이 해당 시퀀스를 변환한다는 점을 제외하면 첫 번째 함수와 동일하게 작동합니다.

통화 출력 필드의 형식은 [locale facet](../standard-library/locale-class.md#facet_class) fac에 의해 결정됩니다. 이 항목은 유효 호출 [use_facet](../standard-library/locale-functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **intl**> >( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc))에서 반환됩니다.

특히 다음에 대한 내용을 설명합니다.

- **fac**. [pos_format](../standard-library/moneypunct-class.md#pos_format)은 음수가 아닌 값에 대해 필드 구성 요소가 생성되는 순서를 결정합니다.

- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format)은 음수 값에 대해 필드 구성 요소가 생성되는 순서를 결정합니다.

- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol)은 통화 기호에 대해 생성할 요소 시퀀스를 결정합니다.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign)은 양수 기호에 대해 생성할 요소 시퀀스를 결정합니다.

- **fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign)은 음수 기호에 대해 생성할 요소 시퀀스를 결정합니다.

- **fac**. [grouping](../standard-library/moneypunct-class.md#grouping)은 숫자가 소수점 왼쪽으로 그룹화되는 방법을 결정합니다.

- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep)는 소수점 왼쪽의 숫자 그룹을 구분하는 요소를 결정합니다.

- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point)는 소수 자릿수와 정수 자릿수를 구분하는 요소를 결정합니다.

- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits)는 소수점 오른쪽에 있는 유효 소수 자릿수의 수를 결정합니다.

부호 문자열 ( **fac**. `negative_sign` 또는 **fac**. `positive_sign`)에 요소가 두 개 이상 있으면 첫 번째 요소만 생성되며, **money_base::sign**과 동일한 요소가 형식 패턴 ( **fac**. `neg_format` 또는 **fac**. `pos_format`). 나머지 요소는 통화 출력 필드의 끝에 생성됩니다.

**iosbase**. [플래그](../standard-library/ios-base-class.md#flags) & [쇼베이스는](../standard-library/ios-functions.md#showbase) 영하지 않은 문자열 **fac입니다.** `curr_symbol`이 생성되며, **money_base::symbol**과 동일한 요소가 형식 패턴에 나타납니다. 그렇지 않은 경우에는 통화 기호가 생성되지 않습니다.

**fac**, **grouping**에 의해 그룹화 제약 조건이 적용되지 않는 경우(해당 첫 번째 요소값이 CHAR_MAX임) **fac**. `thousands_sep`의 인스턴스가 통화 출력 필드의 값 부분에 생성되지 않습니다. 이 필드에는 **money_base::value**와 동일한 요소가 형식 패턴에 나타납니다. **fac**. `frac_digits`가 0이면 소수 자릿수 뒤에 **fac**. `decimal_point`의 인스턴스가 생성되지 않습니다. 그렇지 않은 경우 결과 통화 출력 필드에서 하위 순서 **fac**. `frac_digits` 소수 자릿수가 소수점 오른쪽에 배치됩니다.

모든 숫자 출력 필드에 대해서는 채우기가 수행됩니다. 단, **iosbase**. **플래그** & **iosbase**. [internal](../standard-library/ios-functions.md#internal)이 0이 아니면 내부 채우기가 생성되며 **money_base::space**와 동일한 요소가 형식 패턴에 나타납니다(나타나는 경우). 그렇지 않으면 생성된 시퀀스 앞에서 내부 채우기가 수행됩니다. 채우기 문자는 **fill**입니다.

함수는 **iosbase**. **width**(0)을 호출하여 필드 너비를 0으로 다시 설정합니다.

### <a name="example"></a>예제

**put**에 의해 가상 구성원 함수가 호출되는 [put](#put)의 예제를 참조하세요.

## <a name="money_putiter_type"></a><a name="iter_type"></a>money_put:iter_type

출력 반복기에 대해 설명하는 형식입니다.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 **OutputIterator**와 동일한 의미입니다.

## <a name="money_putmoney_put"></a><a name="money_put"></a>money_put:money_put

`money_put` 형식의 개체에 대한 생성자입니다.

```cpp
explicit money_put(size_t _Refs = 0);
```

### <a name="parameters"></a>매개 변수

*_Refs*\
개체에 대한 메모리 관리 형식을 지정하는 데 사용하는 정수값입니다.

### <a name="remarks"></a>설명

*_Refs* 매개 변수와 그 중요성에 대한 가능한 값은 다음과 같습니다.

- 0: 개체가 포함된 로캘에서 개체의 수명을 관리합니다.

- 1: 개체의 수명을 수동으로 관리해야 합니다.

- \>1: 이러한 값은 정의되지 않습니다.

소멸자는 보호되므로 직접적인 예제는 확인할 수 없습니다.

생성자는 기본 개체를 **로캘::**[facet](../standard-library/locale-class.md#facet_class)()로 `_Refs`초기화합니다.

## <a name="money_putput"></a><a name="put"></a>money_put::put

숫자 또는 문자열을 통화 값을 나타내는 문자 시퀀스로 변환합니다.

```cpp
iter_type put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    const string_type& val) const;

iter_type put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

### <a name="parameters"></a>매개 변수

*다음*\
삽입된 문자열의 첫 번째 요소 주소를 지정하는 반복기입니다.

*_Intl*\
시퀀스에서 필요한 통화 기호 유형을 나타내는 부울 값입니다. 국제의 경우 **true**이고 국내의 경우 **false**입니다.

*_Iosbase*\
집합이 통화 기호가 선택 사항임을 나타낼 때 사용하는 형식 플래그입니다. 그 외의 경우 통화 기호는 필수 항목입니다.

*_Fill*\
간격에 사용되는 문자입니다.

*발*\
변환할 문자열 개체입니다.

### <a name="return-value"></a>Return Value

생성된 마지막 요소에서 한 위치 다음의 위치 주소를 지정하는 출력 반복기입니다.

### <a name="remarks"></a>설명

두 멤버 함수 [do_put](#do_put)모두 `next` `_Intl`do_put `_Iosbase` `_Fill`반환합니다. `val`

### <a name="example"></a>예제

```cpp
// money_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

int main()
{
    std::locale loc( "german_germany" );
    std::basic_stringstream<char> psz;

    psz.imbue(loc);
    psz.flags(psz.flags() | std::ios_base::showbase); // force the printing of the currency symbol
    std::use_facet<std::money_put<char> >(loc).put(std::basic_ostream<char>::_Iter(psz.rdbuf()), true, psz, ' ', 100012);
    if (psz.fail())
        std::cout << "money_put() FAILED" << std::endl;
    else
        std::cout << "money_put() = \"" << psz.rdbuf()->str() << "\"" << std::endl;
}
```

```Output
money_put() = "EUR1.000,12"
```

## <a name="money_putstring_type"></a><a name="string_type"></a>money_put:string_type

`CharType` 형식의 문자가 포함된 문자열을 설명하는 형식입니다.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>설명

형식은 개체가 소스 시퀀스의 요소 시퀀스를 저장할 수 [basic_string](../standard-library/basic-string-class.md) 클래스 템플릿의 전문화에 대해 설명합니다.

## <a name="see-also"></a>참고 항목

[\<로캘>](../standard-library/locale.md)\
[페이스트 클래스](../standard-library/locale-class.md#facet_class)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
