---
title: money_get 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_get
- xlocmon/std::money_get::char_type
- xlocmon/std::money_get::iter_type
- xlocmon/std::money_get::string_type
- xlocmon/std::money_get::do_get
- xlocmon/std::money_get::get
helpviewer_keywords:
- std::money_get [C++]
- std::money_get [C++], char_type
- std::money_get [C++], iter_type
- std::money_get [C++], string_type
- std::money_get [C++], do_get
- std::money_get [C++], get
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
ms.openlocfilehash: ac85e99bfb834fd970a804269f25ec9f20960a23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375909"
---
# <a name="money_get-class"></a>money_get 클래스

클래스 템플릿은 형식 `CharType` 시퀀스를 금전적 값으로 변환하는 것을 제어하는 로캘 면역할을 할 수 있는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class money_get : public locale::facet;
```

### <a name="parameters"></a>매개 변수

*Chartype*\
로캘의 문자를 인코딩하기 위해 프로그램 내 사용하는 형식입니다.

*입력이터*\
get 함수가 입력을 읽어올 반복기의 형식입니다.

## <a name="remarks"></a>설명

모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 저장된 값에 액세스를 처음 시도하면 **id**에 고유한 양수 값이 저장됩니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[money_get](#money_get)|통화 값을 나타내는 시퀀스에서 숫자 값을 추출하는 데 사용되는 `money_get` 형식의 개체에 대한 생성자입니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[char_type](#char_type)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|
|[iter_type](#iter_type)|입력 반복기에 대해 설명하는 형식입니다.|
|[string_type](#string_type)|`CharType` 형식의 문자가 포함된 문자열을 설명하는 형식입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[do_get](#do_get)|통화 값을 나타내는 문자 시퀀스에서 숫자 값을 추출하기 위해 호출하는 가상 함수입니다.|
|[get](#get)|통화 값을 나타내는 문자 시퀀스에서 숫자 값을 추출합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="money_getchar_type"></a><a name="char_type"></a>money_get:char_type

로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수 *CharType의*동의어입니다.

## <a name="money_getdo_get"></a><a name="do_get"></a>money_get::do_get

통화 값을 나타내는 문자 시퀀스에서 숫자 값을 추출하기 위해 호출하는 가상 함수입니다.

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const
```

### <a name="parameters"></a>매개 변수

*첫 번째*\
변환할 시퀀스의 시작 부분 주소를 지정하는 입력 반복기입니다.

*마지막*\
변환할 시퀀스의 끝부분 주소를 지정하는 입력 반복기입니다.

*국제공항*\
시퀀스에서 필요한 통화 기호 유형을 나타내는 부울 값입니다. 국제의 경우 **true**이고 국내의 경우 **false**입니다.

*이오스베이스*\
집합이 통화 기호가 선택 사항임을 나타낼 때 사용하는 형식 플래그입니다. 그 외의 경우 통화 기호는 필수 항목입니다.

*상태*\
작업 성공 여부에 따라 스트림 상태에 대해 적절한 비트 마스크 요소를 설정합니다.

*발*\
변환된 시퀀스를 저장하는 문자열입니다.

### <a name="return-value"></a>Return Value

통화 입력 필드를 벗어난 범위에 있는 첫 번째 요소를 주소 지정하는 입력 반복기입니다.

### <a name="remarks"></a>설명

첫 번째 보호된 가상 구성원 함수는 비어 있지 않은 완전한 통화 입력 필드를 인식할 때까지 시퀀스 [ `first`, `last`)에서 처음 시작되는 순차 요소 일치를 시도합니다. 성공하면 이 필드를 하나 이상의 소수자릿수 시퀀스로 변환하고 선택적으로 마이너스 기호() `-`앞에 오는 양을 나타내고 결과를 [string_type](#string_type) 개체 *값으로*저장합니다. 이 함수는 통화 입력 필드를 벗어난 범위에 있는 첫 번째 요소를 지정하는 반복기를 반환합니다. 그렇지 않으면 함수는 빈 시퀀스를 `ios_base::failbit` *val에* 저장하고 *상태를*설정합니다. 그리고 유효한 통화 입력 필드의 접두사를 벗어난 범위에 있는 첫 번째 요소를 지정하는 반복기를 반환합니다. 두 경우 모두 반환 값이 `last`와 같으면 함수는 `State`에서 `ios_base::eofbit`를 설정합니다.

두 번째 가상 보호 멤버 함수는 첫 번째 함수와 동일하게 작동하지만 성공한 경우 선택적으로 서명된 숫자 시퀀스를 형식 **long double** 값으로 변환하고 해당 값을 *val에*저장합니다.

통화 출력 필드의 형식은 [locale facet](../standard-library/locale-class.md#facet_class)**fac**에 의해 결정됩니다. 이 항목은 유효 호출 [use_facet](../standard-library/locale-functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **intl**>>( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc))에서 반환됩니다.

특히 다음에 대한 내용을 설명합니다.

- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format)은 필드 구성 요소가 나타나는 순서를 결정합니다.

- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol)은 통화 기호를 구성하는 요소 시퀀스를 결정합니다.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign)은 양수 기호를 구성하는 요소 시퀀스를 결정합니다.

- **fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign)은 음수 기호를 구성하는 요소 시퀀스를 결정합니다.

- **fac**. [grouping](../standard-library/moneypunct-class.md#grouping)은 숫자가 소수점 왼쪽으로 그룹화되는 방법을 결정합니다.

- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep)는 소수점 왼쪽의 숫자 그룹을 구분하는 요소를 결정합니다.

- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point)는 소수 자릿수와 정수 자릿수를 구분하는 요소를 결정합니다.

- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits)는 소수점 오른쪽에 있는 유효 소수 자릿수의 수를 결정합니다. `frac_digits`에서 호출한 것보다 소수 자릿수가 많은 금액을 구문 분석할 때 `do_get`은 최대 `frac_digits`자를 사용한 후 구문 분석을 중지합니다.

부호 문자열 ( **fac**. `negative_sign` 또는 **fac**. `positive_sign`)에 요소가 두 개 이상 있으면 첫 번째 요소만 일치 여부를 확인하되며, **money_base::sign**과 동일한 요소가 형식 패턴 ( **fac**. `neg_format`). 나머지 요소는 통화 입력 필드의 끝에서 일치 여부를 확인합니다. 어떤 문자열에도 통화 입력 필드의 다음 요소와 일치하는 첫 번째 요소가 없으면 부호 문자열을 빈 문자열로 가져오며 양수 부호를 사용합니다.

**iosbase**. [플래그](../standard-library/ios-base-class.md#flags) & [쇼베이스는](../standard-library/ios-functions.md#showbase) 영하지 않은 문자열 **fac입니다.** `curr_symbol`이 일치해야 하며, **money_base::symbol**과 동일한 요소가 형식 패턴에 나타납니다. 그렇지 않고 **money_base::symbol**이 형식 패턴 끝에 나오며 부호 문자열에서 일치 여부를 확인할 요소가 남아 있지 않으면 통화 기호의 일치 여부를 확인하지 않습니다. 그 외의 경우에는 필요에 따라 통화 기호의 일치 여부를 확인합니다.

숫자 입력 필드에 **fac**. `thousands_sep`의 인스턴스가 나오지 않으면(**money_base::value**와 동일한 요소가 형식 패턴에 나타남) 그룹화 제양ㄱ 조건이 적용되지 않습니다. 그렇지 않으면 **fac**. **grouping**에서 적용하는 모든 그룹화 제약 조건이 적용됩니다. 결과 숫자 시퀀스는 하위 순서 **fac**. `frac_digits` 소수 자릿수가 소수점 오른쪽에 있는 것으로 간주하는 정수를 나타냅니다.

**money_base::space**와 동일한 요소가 형식 패턴에 나타나는 위치(해당 요소가 형식 패턴의 끝이 아닌 위치에 나타나는 경우)에서 임의의 공백 일치 여부를 확인합니다. 그렇지 않으면 내부 공백 일치 여부를 확인하지 않습니다. 요소 *ch*는 [use_facet](../standard-library/locale-functions.md#use_facet) < [ctype](../standard-library/ctype-class.md)\< **CharType**> >( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc))에서 반환됩니다. [is](../standard-library/ctype-class.md#is)( **ctype_base::space**, *ch*)가 **true**이면 공백으로 간주합니다.

### <a name="example"></a>예제

`do_get`을 호출하는 [get](#get)에 대한 예제를 참조하세요.

## <a name="money_getget"></a><a name="get"></a>money_get::get

통화 값을 나타내는 문자 시퀀스에서 숫자 값을 추출합니다.

```cpp
iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const;

iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const;
```

### <a name="parameters"></a>매개 변수

*첫 번째*\
변환할 시퀀스의 시작 부분 주소를 지정하는 입력 반복기입니다.

*마지막*\
변환할 시퀀스의 끝부분 주소를 지정하는 입력 반복기입니다.

*국제공항*\
시퀀스에서 필요한 통화 기호 유형을 나타내는 부울 값입니다. 국제의 경우 **true**이고 국내의 경우 **false**입니다.

*이오스베이스*\
집합이 통화 기호가 선택 사항임을 나타낼 때 사용하는 형식 플래그입니다. 그 외의 경우 통화 기호는 필수 항목입니다.

*상태*\
작업 성공 여부에 따라 스트림 상태에 대해 적절한 비트 마스크 요소를 설정합니다.

*발*\
변환된 시퀀스를 저장하는 문자열입니다.

### <a name="return-value"></a>Return Value

통화 입력 필드를 벗어난 범위에 있는 첫 번째 요소를 주소 지정하는 입력 반복기입니다.

### <a name="remarks"></a>설명

두 멤버 함수 모두 [do_get](#do_get)`(first, last, Intl, Iosbase, State, val)`반환합니다.

### <a name="example"></a>예제

```cpp
// money_get_get.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;

int main( )
{
   locale loc( "german_germany" );

   basic_stringstream< char > psz;
   psz << use_facet<moneypunct<char, 1> >(loc).curr_symbol() << "-1.000,56";
   basic_stringstream< char > psz2;
   psz2 << "-100056" << use_facet<moneypunct<char, 1> >(loc).curr_symbol();

   ios_base::iostate st = 0;
   long double fVal;

   psz.flags( psz.flags( )|ios_base::showbase );
   // Which forced the READING the currency symbol
   psz.imbue(loc);
   use_facet < money_get < char > >( loc ).
      get( basic_istream<char>::_Iter( psz.rdbuf( ) ),
           basic_istream<char>::_Iter( 0 ), true, psz, st, fVal );

   if ( st & ios_base::failbit )
      cout << "money_get(" << psz.str( ) << ", intl = 1) FAILED"
           << endl;
   else
      cout << "money_get(" << psz.str( ) << ", intl = 1) = "
           << fVal/100.0 << endl;

   use_facet < money_get < char > >( loc ).
      get(basic_istream<char>::_Iter(psz2.rdbuf( )),
          basic_istream<char>::_Iter(0), false, psz2, st, fVal);

   if ( st & ios_base::failbit )
      cout << "money_get(" << psz2.str( ) << ", intl = 0) FAILED"
           << endl;
   else
      cout << "money_get(" << psz2.str( ) << ", intl = 0) = "
           << fVal/100.0 << endl;
};
```

## <a name="money_getiter_type"></a><a name="iter_type"></a>money_get:iter_type

입력 반복기에 대해 설명하는 형식입니다.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 **InputIterator**와 동일한 의미입니다.

## <a name="money_getmoney_get"></a><a name="money_get"></a>money_get:money_get

통화 값을 나타내는 시퀀스에서 숫자 값을 추출하는 데 사용되는 `money_get` 형식의 개체에 대한 생성자입니다.

```cpp
explicit money_get(size_t _Refs = 0);
```

### <a name="parameters"></a>매개 변수

*_Refs*\
개체에 대한 메모리 관리 형식을 지정하는 데 사용하는 정수값입니다.

### <a name="remarks"></a>설명

*_Refs* 매개 변수와 그 중요성에 대한 가능한 값은 다음과 같습니다.

- 0: 개체를 포함하는 로캘에 의해 개체의 수명이 관리됩니다.

- 1: 개체의 수명을 수동으로 관리해야 합니다.

- \>1: 이러한 값은 정의되지 않습니다.

소멸자는 보호되므로 직접적인 예제는 확인할 수 없습니다.

생성자는 기본 개체를 **로캘::***면(_Refs)으로*초기화합니다.[facet](../standard-library/locale-class.md#facet_class)

## <a name="money_getstring_type"></a><a name="string_type"></a>money_get:string_type

**CharType** 형식의 문자가 포함된 문자열을 설명하는 형식입니다.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_string](../standard-library/basic-string-class.md)전문화에 대해 설명합니다.

## <a name="see-also"></a>참고 항목

[\<로캘>](../standard-library/locale.md)\
[페이스트 클래스](../standard-library/locale-class.md#facet_class)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
