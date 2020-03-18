---
title: moneypunct 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct
- xlocmon/std::moneypunct::char_type
- xlocmon/std::moneypunct::string_type
- xlocmon/std::moneypunct::curr_symbol
- xlocmon/std::moneypunct::decimal_point
- xlocmon/std::moneypunct::do_curr_symbol
- xlocmon/std::moneypunct::do_decimal_point
- xlocmon/std::moneypunct::do_frac_digits
- xlocmon/std::moneypunct::do_grouping
- xlocmon/std::moneypunct::do_neg_format
- xlocmon/std::moneypunct::do_negative_sign
- xlocmon/std::moneypunct::do_pos_format
- xlocmon/std::moneypunct::do_positive_sign
- xlocmon/std::moneypunct::do_thousands_sep
- xlocmon/std::moneypunct::frac_digits
- xlocmon/std::moneypunct::grouping
- xlocmon/std::moneypunct::neg_format
- xlocmon/std::moneypunct::negative_sign
- xlocmon/std::moneypunct::pos_format
- xlocmon/std::moneypunct::positive_sign
- xlocmon/std::moneypunct::thousands_sep
helpviewer_keywords:
- std::moneypunct [C++]
- std::moneypunct [C++], char_type
- std::moneypunct [C++], string_type
- std::moneypunct [C++], curr_symbol
- std::moneypunct [C++], decimal_point
- std::moneypunct [C++], do_curr_symbol
- std::moneypunct [C++], do_decimal_point
- std::moneypunct [C++], do_frac_digits
- std::moneypunct [C++], do_grouping
- std::moneypunct [C++], do_neg_format
- std::moneypunct [C++], do_negative_sign
- std::moneypunct [C++], do_pos_format
- std::moneypunct [C++], do_positive_sign
- std::moneypunct [C++], do_thousands_sep
- std::moneypunct [C++], frac_digits
- std::moneypunct [C++], grouping
- std::moneypunct [C++], neg_format
- std::moneypunct [C++], negative_sign
- std::moneypunct [C++], pos_format
- std::moneypunct [C++], positive_sign
- std::moneypunct [C++], thousands_sep
ms.assetid: cf2650da-3e6f-491c-95d5-23e57f582ee6
ms.openlocfilehash: 7960ee8b5e9ce6b27494e896e38bbf6b5256fe7e
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425426"
---
# <a name="moneypunct-class"></a>moneypunct 클래스

클래스 템플릿에서는 통화 입력 필드 또는 통화 출력 필드를 나타내는 데 사용 되는 *Chartype* 형식의 시퀀스를 설명 하기 위해 로캘 패싯으로 사용할 수 있는 개체에 대해 설명 합니다. 템플릿 매개 변수 *국제* 이 *true*이면 국제 규칙이 관찰 됩니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType, bool Intl>
class moneypunct;
```

### <a name="parameters"></a>매개 변수

*Chartype*\
문자를 인코딩하기 위해 프로그램 내 사용하는 형식

*국제*\
국제 규약을 준수하는지 여부를 지정하는 플래그입니다.

## <a name="remarks"></a>설명

모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 저장된 값에 액세스를 처음 시도하면 **id**에 고유한 양수 값이 저장됩니다.

상수 정적 개체 intl에는 템플릿 매개 변수 *Intl*의 값이 저장됩니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[moneypunct](#moneypunct)|`moneypunct` 형식의 개체 생성자입니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[char_type](#char_type)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|
|[string_type](#string_type)|`CharType` 형식의 문자가 포함된 문자열을 설명하는 형식입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[curr_symbol](#curr_symbol)|통화 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.|
|[decimal_point](#decimal_point)|소수점 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.|
|[do_curr_symbol](#do_curr_symbol)|통화 기호로 사용할 로캘별 요소 시퀀스를 반환하는 보호된 가상 멤버 함수입니다.|
|[do_decimal_point](#do_decimal_point)|소수점 기호로 사용할 로캘별 요소 시퀀스를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|
|[do_frac_digits](#do_frac_digits)|보호된 가상 멤버 함수가 소수점 오른쪽에 표시할 자릿수를 로캘별로 반환합니다.|
|[do_grouping](#do_grouping)|보호된 가상 멤버 함수가 소수점 자리 왼쪽의 숫자를 그룹화하는 방법을 결정하는 로캘별 규칙을 반환합니다.|
|[do_neg_format](#do_neg_format)|음수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|
|[do_negative_sign](#do_negative_sign)|음수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|
|[do_pos_format](#do_pos_format)|양수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|
|[do_positive_sign](#do_positive_sign)|양수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|
|[do_thousands_sep](#do_thousands_sep)|1000 단위 구분 기호로 사용할 로캘별 요소 시퀀스를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|
|[frac_digits](#frac_digits)|소수점 오른쪽에 표시할 자릿수를 로캘별로 반환합니다.|
|[grouping](#grouping)|소수점 왼쪽의 숫자를 그룹화할 방법을 결정하기 위한 로캘별 규칙을 반환합니다.|
|[neg_format](#neg_format)|음수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환합니다.|
|[negative_sign](#negative_sign)|음수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.|
|[pos_format](#pos_format)|양수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환합니다.|
|[positive_sign](#positive_sign)|양수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.|
|[thousands_sep](#thousands_sep)|1000 단위 구분 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<로캘 >

**네임스페이스:** std

## <a name="char_type"></a>  moneypunct::char_type

로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 **CharType**의 동의어입니다.

## <a name="curr_symbol"></a>  moneypunct::curr_symbol

통화 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.

```cpp
string_type curr_symbol() const;
```

### <a name="return-value"></a>Return Value

통화 기호를 포함하는 문자열입니다.

### <a name="remarks"></a>설명

구성원 함수는 [do_curr_symbol](#do_curr_symbol)을 반환합니다.

### <a name="example"></a>예제

```cpp
// moneypunct_curr_symbol.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct < char, true > &mpunct = use_facet < moneypunct < char, true > >(loc);
   cout << loc.name( ) << " international currency symbol "<<  mpunct.curr_symbol( ) << endl;

   const moneypunct < char, false> &mpunct2 = use_facet < moneypunct < char, false> >(loc);
   cout << loc.name( ) << " domestic currency symbol "<<  mpunct2.curr_symbol( ) << endl;
};
```

## <a name="decimal_point"></a>  moneypunct::decimal_point

소수점 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>Return Value

소수점 기호로 사용할 로캘별 요소 시퀀스입니다.

### <a name="remarks"></a>설명

구성원 함수는 [do_decimal_point](#do_decimal_point)를 반환합니다.

### <a name="example"></a>예제

```cpp
// moneypunct_decimal_pt.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc("german_germany");

   const moneypunct < char, true > &mpunct = use_facet
      < moneypunct < char, true > >(loc);
   cout << loc.name( ) << " international decimal point "
        << mpunct.decimal_point( ) << endl;

   const moneypunct < char, false> &mpunct2 = use_facet
      < moneypunct < char, false> >(loc);
   cout << loc.name( ) << " domestic decimal point "
        << mpunct2.decimal_point( ) << endl;
}
```

```Output
German_Germany.1252 international decimal point ,
German_Germany.1252 domestic decimal point ,
```

## <a name="do_curr_symbol"></a>  moneypunct::do_curr_symbol

통화 기호로 사용할 로캘별 요소 시퀀스를 반환하는 보호된 가상 멤버 함수입니다.

```cpp
virtual string_type do_curr_symbol() const;
```

### <a name="return-value"></a>Return Value

소수점 기호로 사용할 로캘별 요소 시퀀스입니다.

### <a name="example"></a>예제

[에 의해 가상 구성원 함수가 호출되는 ](#curr_symbol)curr_symbol`curr_symbol`의 예제를 참조하세요.

## <a name="do_decimal_point"></a>  moneypunct::do_decimal_point

소수점 기호통화 기호로 사용할 로캘별 요소 시퀀스를 반환하는 보호된 가상 구성원 함수입니다.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Return Value

소수점 기호로 사용할 로캘별 요소 시퀀스입니다.

### <a name="example"></a>예제

[에 의해 가상 구성원 함수가 호출되는 ](#decimal_point)decimal_point`decimal_point`의 예제를 참조하세요.

## <a name="do_frac_digits"></a>  moneypunct::do_frac_digits

소수점 오른쪽에 표시할 자릿수를 로캘별로 반환하는 보호된 가상 구성원 함수입니다.

```cpp
virtual int do_frac_digits() const;
```

### <a name="return-value"></a>Return Value

소수점 오른쪽에 표시할 로캘별 자릿수입니다.

### <a name="example"></a>예제

[에 의해 가상 구성원 함수가 호출되는 ](#frac_digits)frac_digits`frac_digits`의 예제를 참조하세요.

## <a name="do_grouping"></a>  moneypunct::do_grouping

소수점 자리 왼쪽의 숫자를 그룹화하는 방법을 결정하는 로캘별 규칙을 반환하는 보호된 가상 구성원 함수입니다.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Return Value

소수점 왼쪽의 숫자를 그룹화할 방법을 결정하기 위한 로캘별 규칙입니다.

### <a name="example"></a>예제

`grouping`에서 가상 멤버 함수를 호출 하는 [그룹화](#grouping)의 예제를 참조 하세요.

## <a name="do_neg_format"></a>  moneypunct::do_neg_format

음수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.

```cpp
virtual pattern do_neg_format() const;
```

### <a name="return-value"></a>Return Value

보호된 가상 구성원 함수는 음수 값에 대해 통화 출력 필드를 생성하는 방법을 결정하기 위한 로캘별 규칙을 반환합니다. `pattern::field`의 각 4 개 요소에는 다음 값을 사용할 수 있습니다.

- `none`는 0 개 이상의 공백을 찾거나 아무것도 생성 하지 않습니다.

- 양수 또는 음수 기호를 일치 또는 생성 `sign` 합니다.

- 0 개 이상의 공백과 일치 하거나 공백을 생성 하는 `space` 합니다.

- 통화 기호를 일치 또는 생성 `symbol` 합니다.

- 통화 값을 일치 또는 생성 `value` 합니다.

통화 출력 필드의 구성 요소가 생성 되 고 통화 입력 필드의 구성 요소가 `pattern::field`에 표시 되는 순서 대로 일치 합니다. `sign`, `symbol`, `value`, `none` 또는 `space` 값은 모두 정확히 한 번만 나타나야 합니다. `none` 값을 먼저 표시 해서는 안 됩니다. spce 값은 첫 번째나 마지막에 나올 수 **없습니다**. `Intl` true 이면 순서는 `symbol`, `sign`, `none`, `value`입니다.

`moneypunct`\< **Chartype**, **국제**>의 템플릿 버전은 `{`**money_base:: symbol**, **money_base:: sign**, **money_base:: value**, **money_base:: none**`}`를 반환 합니다.

### <a name="example"></a>예제

[에 의해 가상 구성원 함수가 호출되는 ](#neg_format)neg_format`neg_format`의 예제를 참조하세요.

## <a name="do_negative_sign"></a>  moneypunct::do_negative_sign

음수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.

```cpp
virtual string_type do_negative_sign() const;
```

### <a name="return-value"></a>Return Value

음수 부호로 사용할 로캘별 요소 시퀀스입니다.

### <a name="example"></a>예제

[에 의해 가상 구성원 함수가 호출되는 ](#negative_sign)negative_sign`negative_sign`의 예제를 참조하세요.

## <a name="do_pos_format"></a>  moneypunct::do_pos_format

양수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.

```cpp
virtual pattern do_pos_format() const;
```

### <a name="return-value"></a>Return Value

보호된 가상 구성원 함수는 양수 금액에 대해 통화 출력 필드를 생성하는 방법을 결정하기 위한 로캘별 규칙을 반환합니다. 또한 통화 입력 필드의 구성 요소와 일치 하는 방법을 결정 합니다. 인코딩은 [do_neg_format](#do_neg_format)와 동일 합니다.

Moneypunct\< **Chartype**, **inputlterator**의 템플릿 버전은 `{`**money_base:: symbol**, **money_base:: sign**, **money_base:: value**, **money_base:: none**`}`를 반환 합니다.

### <a name="example"></a>예제

[에 의해 가상 구성원 함수가 호출되는 ](#pos_format)pos_format`pos_format`의 예제를 참조하세요.

## <a name="do_positive_sign"></a>  moneypunct::do_positive_sign

양수 부호로 사용할 로캘별 요소 시퀀스를 반환하는 보호된 가상 구성원 함수입니다.

```cpp
virtual string_type do_positive_sign() const;
```

### <a name="return-value"></a>Return Value

양수 부호로 사용할 로캘별 요소 시퀀스입니다.

### <a name="example"></a>예제

[에 의해 가상 구성원 함수가 호출되는 ](#positive_sign)positive_sign`positive_sign`의 예제를 참조하세요.

## <a name="do_thousands_sep"></a>  moneypunct::do_thousands_sep

소수점 왼쪽의 그룹 구분 기호로 사용할 로캘별 요소를 반환하는 보호된 가상 구성원 함수입니다.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Return Value

소스점 왼쪽의 그룹 구분 기호로 사용할 로캘별 요소입니다.

### <a name="example"></a>예제

[에 의해 가상 구성원 함수가 호출되는 ](#thousands_sep)thousands_sep`thousands_sep`의 예제를 참조하세요.

## <a name="frac_digits"></a>  moneypunct::frac_digits

소수점 오른쪽에 표시할 자릿수를 로캘별로 반환합니다.

```cpp
int frac_digits() const;
```

### <a name="return-value"></a>Return Value

소수점 오른쪽에 표시할 로캘별 자릿수입니다.

### <a name="remarks"></a>설명

구성원 함수는 [do_frac_digits](#do_frac_digits)를 반환합니다.

### <a name="example"></a>예제

```cpp
// moneypunct_frac_digits.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
       use_facet <moneypunct <char, true> >(loc);
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " international grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " international frac_digits\n to the right"
        << " of the radix character: "
        << mpunct.frac_digits ( ) << endl << endl;

   const moneypunct <char, false> &mpunct2 =
       use_facet <moneypunct <char, false> >(loc);
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " domestic grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct2.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " domestic frac_digits\n to the right"
        << " of the radix character: "
        << mpunct2.frac_digits ( ) << endl << endl;
}
```

```Output
German_Germany.1252 international grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 international frac_digits
to the right of the radix character: 2

German_Germany.1252 domestic grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 domestic frac_digits
to the right of the radix character: 2
```

## <a name="grouping"></a>  moneypunct::grouping

소수점 왼쪽의 숫자를 그룹화할 방법을 결정하기 위한 로캘별 규칙을 반환합니다.

```cpp
string grouping() const;
```

### <a name="return-value"></a>Return Value

소수점 왼쪽의 숫자를 그룹화할 방법을 결정하기 위한 로캘별 규칙입니다.

### <a name="remarks"></a>설명

구성원 함수는 [do_grouping](#do_grouping)을 반환합니다.

### <a name="example"></a>예제

```cpp
// moneypunct_grouping.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
       use_facet <moneypunct <char, true> >( loc );
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " international grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " international frac_digits\n to the right"
        << " of the radix character: "
        << mpunct.frac_digits ( ) << endl << endl;

   const moneypunct <char, false> &mpunct2 =
       use_facet <moneypunct <char, false> >( loc );
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " domestic grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct2.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " domestic frac_digits\n to the right"
        << " of the radix character: "
        << mpunct2.frac_digits ( ) << endl << endl;
}
```

```Output
German_Germany.1252 international grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 international frac_digits
to the right of the radix character: 2

German_Germany.1252 domestic grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 domestic frac_digits
to the right of the radix character: 2
```

## <a name="moneypunct"></a>  moneypunct::moneypunct

`moneypunct` 형식의 개체 생성자입니다.

```cpp
explicit moneypunct(size_t _Refs = 0);
```

### <a name="parameters"></a>매개 변수

*_Refs*\
개체에 대한 메모리 관리의 유형을 지정하는 데 사용하는 정수 값입니다.

### <a name="remarks"></a>설명

*_Refs* 매개 변수에 사용할 수 있는 값과 해당 의미는 다음과 같습니다.

- 0: 개체를 포함하는 로캘에 의해 개체의 수명이 관리됩니다.

- 1: 개체의 수명을 수동으로 관리해야 합니다.

- \> 1: 이러한 값이 정의 되어 있지 않습니다.

소멸자는 보호되므로 직접적인 예제는 확인할 수 없습니다.

생성자는 [locale::facet](../standard-library/locale-class.md#facet_class)(_ *Refs*)를 통해 해당 기준 개체를 초기화합니다.

## <a name="neg_format"></a>  moneypunct::neg_format

음수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환합니다.

```cpp
pattern neg_format() const;
```

### <a name="return-value"></a>Return Value

음수 금액의 출력 서식을 지정하기 위한 로캘별 규칙입니다.

### <a name="remarks"></a>설명

구성원 함수는 [do_neg_format](#do_neg_format)을 반환합니다.

### <a name="example"></a>예제

```cpp
// moneypunct_neg_format.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main( ) {
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true > >(loc);
   cout << loc.name( ) << " international negative number format: "
        << mpunct.neg_format( ).field[0]
        << mpunct.neg_format( ).field[1]
        << mpunct.neg_format( ).field[2]
        << mpunct.neg_format( ).field[3] << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic negative number format: "
        << mpunct2.neg_format( ).field[0]
        << mpunct2.neg_format( ).field[1]
        << mpunct2.neg_format( ).field[2]
        << mpunct2.neg_format( ).field[3] << endl;
}
```

## <a name="negative_sign"></a>  moneypunct::negative_sign

음수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.

```cpp
string_type negative_sign() const;
```

### <a name="return-value"></a>Return Value

음수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.

### <a name="remarks"></a>설명

구성원 함수는 [do_negative_sign](#do_negative_sign)을 반환합니다.

### <a name="example"></a>예제

```cpp
// moneypunct_neg_sign.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true> >(loc);
   cout << loc.name( ) << " international negative sign: "
        << mpunct.negative_sign( ) << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic negative sign: "
        << mpunct2.negative_sign( ) << endl;

   locale loc2( "French" );

   const moneypunct <char, true> &mpunct3 =
      use_facet <moneypunct <char, true> >(loc2);
   cout << loc2.name( ) << " international negative sign: "
        << mpunct3.negative_sign( ) << endl;

   const moneypunct <char, false> &mpunct4 =
      use_facet <moneypunct <char, false> >(loc2);
   cout << loc2.name( ) << " domestic negative sign: "
        << mpunct4.negative_sign( ) << endl;
};
```

```Output
German_Germany.1252 international negative sign: -
German_Germany.1252 domestic negative sign: -
French_France.1252 international negative sign: -
French_France.1252 domestic negative sign: -
```

## <a name="pos_format"></a>  moneypunct::pos_format

양수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환합니다.

```cpp
pattern pos_format() const;
```

### <a name="return-value"></a>Return Value

양수 금액의 출력 서식을 지정하기 위한 로캘별 규칙입니다.

### <a name="remarks"></a>설명

구성원 함수는 [do_pos_format](#do_pos_format)을 반환합니다.

### <a name="example"></a>예제

```cpp
// moneypunct_pos_format.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main() {
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true> >(loc);
   cout << loc.name( ) << " international positive number format: "
        << mpunct.pos_format( ).field[0]
        << mpunct.pos_format( ).field[1]
        << mpunct.pos_format( ).field[2]
        << mpunct.pos_format( ).field[3] << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic positive number format: "
        << mpunct2.pos_format( ).field[0]
        << mpunct2.pos_format( ).field[1]
        << mpunct2.pos_format( ).field[2]
        << mpunct2.pos_format( ).field[3] << endl;
}
```

## <a name="positive_sign"></a>  moneypunct::positive_sign

양수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.

```cpp
string_type positive_sign() const;
```

### <a name="return-value"></a>Return Value

양수 부호 기호로 사용할 로캘별 요소 시퀀스입니다.

### <a name="remarks"></a>설명

구성원 함수는 [do_positive_sign](#do_positive_sign)을 반환합니다.

### <a name="example"></a>예제

```cpp
// moneypunct_pos_sign.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true > >(loc);
   cout << loc.name( ) << " international positive sign:"
        << mpunct.positive_sign( ) << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic positive sign:"
        << mpunct2.positive_sign( ) << endl;

   locale loc2( "French" );

   const moneypunct <char, true> &mpunct3 =
      use_facet <moneypunct <char, true> >(loc2);
   cout << loc2.name( ) << " international positive sign:"
        << mpunct3.positive_sign( ) << endl;

   const moneypunct <char, false> &mpunct4 =
      use_facet <moneypunct <char, false> >(loc2);
   cout << loc2.name( ) << " domestic positive sign:"
        << mpunct4.positive_sign( ) << endl;
};
```

```Output
German_Germany.1252 international positive sign:
German_Germany.1252 domestic positive sign:
French_France.1252 international positive sign:
French_France.1252 domestic positive sign:
```

## <a name="string_type"></a>  moneypunct::string_type

**CharType** 형식의 문자가 포함된 문자열을 설명하는 형식입니다.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>설명

이 형식은 개체가 문장 부호 시퀀스의 복사본을 저장할 수 있는 클래스 템플릿 [basic_string](../standard-library/basic-string-class.md) 의 특수화를 설명 합니다.

## <a name="thousands_sep"></a>  moneypunct::thousands_sep

1000 단위 구분 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Return Value

1000 단위 구분 기호로 사용할 로캘별 요소 시퀀스입니다.

### <a name="remarks"></a>설명

구성원 함수는 [do_thousands_sep](#do_thousands_sep)를 반환합니다.

### <a name="example"></a>예제

```cpp
// moneypunct_thou_sep.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
       use_facet <moneypunct <char, true > >(loc);
   cout << loc.name( ) << " international thousands separator: "
        << mpunct.thousands_sep( ) << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic thousands separator: "
        << mpunct2.thousands_sep( ) << endl << endl;

   locale loc2( "english_canada" );

   const moneypunct <char, true> &mpunct3 =
       use_facet <moneypunct <char, true> >(loc2);
   cout << loc2.name( ) << " international thousands separator: "
        << mpunct3.thousands_sep( ) << endl;

   const moneypunct <char, false> &mpunct4 =
      use_facet <moneypunct <char, false> >(loc2);
   cout << loc2.name( ) << " domestic thousands separator: "
        << mpunct4.thousands_sep( ) << endl;
}
```

```Output
German_Germany.1252 international thousands separator: .
German_Germany.1252 domestic thousands separator: .

English_Canada.1252 international thousands separator: ,
English_Canada.1252 domestic thousands separator: ,
```

## <a name="see-also"></a>참고 항목

[\<locale>](../standard-library/locale.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
