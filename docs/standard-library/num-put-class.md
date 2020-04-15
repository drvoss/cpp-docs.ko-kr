---
title: num_put 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::num_put
- locale/std::num_put::char_type
- locale/std::num_put::iter_type
- locale/std::num_put::do_put
- locale/std::num_put::put
helpviewer_keywords:
- std::num_put [C++]
- std::num_put [C++], char_type
- std::num_put [C++], iter_type
- std::num_put [C++], do_put
- std::num_put [C++], put
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
ms.openlocfilehash: 3f65d7140bb5c691fa58ec9d74ceda5573280ddb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373642"
---
# <a name="num_put-class"></a>num_put 클래스

숫자 값의 변환을 형식의 `CharType`시퀀스로 제어하는 로캘 면역할을 할 수 있는 개체를 설명하는 클래스 템플릿입니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>매개 변수

*Chartype*\
로캘의 문자를 인코딩하기 위해 프로그램 내 사용하는 형식입니다.

*출력이터*\
숫자 put 함수가 출력을 쓰는 반복기의 형식입니다.

## <a name="remarks"></a>설명

모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 저장된 값에 액세스를 처음 시도하면 **id**에 고유한 양수 값이 저장됩니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[num_put](#num_put)|`num_put` 형식의 개체에 대한 생성자입니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[char_type](#char_type)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|
|[iter_type](#iter_type)|출력 반복기에 대해 설명하는 형식입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[do_put](#do_put)|숫자를 지정된 로캘에 대해 서식이 지정된 숫자를 나타내는 `CharType`의 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|
|[넣어](#put)|숫자를 지정된 로캘에 대해 서식이 지정된 숫자를 나타내는 `CharType`의 시퀀스로 변환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="num_putchar_type"></a><a name="char_type"></a>num_put:char_type

로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `CharType`의 동의어입니다.

## <a name="num_putdo_put"></a><a name="do_put"></a>num_put::do_put

숫자를 지정된 로캘에 대해 서식이 지정된 숫자를 나타내는 `CharType`의 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.

```cpp
virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    bool val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    unsigned long val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    double val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long double val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const void* val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const long long val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const unsigned long long val) const;
```

### <a name="parameters"></a>매개 변수

*다음*\
삽입된 문자열의 첫 번째 요소 주소를 지정하는 반복기입니다.

*_Iosbase*\
출력 및 출력 서식 지정을 위한 플래그에 문장 부호를 적용하는 데 사용되는 numpunct 패싯이 들어 있는 로캘을 포함하는 스트림을 지정합니다.

*_Fill*\
간격에 사용되는 문자입니다.

*발*\
출력할 숫자 또는 부울 형식입니다.

### <a name="return-value"></a>Return Value

생성된 마지막 요소에서 한 위치 다음의 위치 주소를 지정하는 출력 반복기입니다.

### <a name="remarks"></a>설명

첫 번째 가상 보호 멤버 함수는 *val*값에서 정수 출력 필드를 생성하기 위해 *옆에서* 시작하는 순차 적 요소를 생성합니다. 함수는 생성된 정수 출력 필드를 지나 요소를 삽입할 다음 위치를 지정하는 반복기를 반환합니다.

정수 출력 필드는 일련의 **char** 요소를 파일에 생성하는 인쇄 함수에서 사용하는 것과 동일한 규칙에 의해 생성됩니다. 이러한 각 char 요소는 간단한 일대일 매핑을 `CharType` 통해 형식의 동등한 요소에 매핑하는 것으로 가정됩니다. 그러나 인쇄 함수가 공백 또는 숫자 0으로 필드를 `do_put` 패드하는 `fill`경우 대신 을 사용합니다. 동일한 인쇄 변환 사양은 다음과 같이 결정됩니다.

- **iosbase**. [flags](../standard-library/ios-base-class.md#flags) & 플래그`ios_base::basefield` `lo`10 월, 변환 사양은 .[oct](../standard-library/ios-functions.md#oct) == `ios_base::`

- **iosbase.flags** & **ios_base::basefield** == `ios_base::`[육수,](../standard-library/ios-functions.md#hex)변환 `lx`사양은 .

- 그렇지 않으면 변환 사양은 `ld`입니다.

**iosbase**. [width](../standard-library/ios-base-class.md#width)가 0이 아닌 경우 이 값의 필드 너비가 앞에 추가됩니다. 그런 후에 이 함수는 **iosbase**. **width**(0)을 호출하여 필드 너비를 0으로 다시 설정합니다.

출력 필드를 지정하는 데 필요한 최소 요소 수 *N*이 **iosbase**. [너비를 가다.](../standard-library/ios-base-class.md#width) 이러한 패딩은 **채우기의** *N* - **너비** 복사본 시퀀스로 구성됩니다. 그런 후에 다음과 같이 채우기가 수행됩니다.

- **iosbase**. **플래그가** & `ios_base::`[left](../standard-library/ios-functions.md#left) **-** 왼쪽으로, 플래그가 준비됩니다.`ios_base::adjustfield` ==  채우기는 생성된 텍스트 뒤에서 수행됩니다.

- **iosbase.flagsios_base::adjustfield** & **ios_base::adjustfield** == `ios_base::`[내부,](../standard-library/ios-functions.md#internal)플래그 **0** 준비 됩니다. 숫자 출력 필드의 경우에는 print 함수가 0으로 채우는 위치에서 채우기가 수행됩니다.

- 그렇지 않은 경우에는 추가 플래그가 앞에 추가되지 않습니다. 채우기는 생성된 시퀀스 앞에서 수행됩니다.

그리고 마지막으로 다음과 같이 채우기가 수행됩니다.

- **iosbase**. **flags** & 플래그`ios_base::`[쇼포지는](../standard-library/ios-functions.md#showpos) 0이 **+** 아닌 플래그가 변환 사양으로 준비됩니다.

- **iosbase**. **플래그** & **ios_base::**[showbase가](../standard-library/ios-functions.md#showbase) 0이 **#** 아닌 경우 플래그가 변환 사양으로 준비됩니다.

정수 출력 필드의 형식은 [locale facet](../standard-library/locale-class.md#facet_class)**fac**에 의해 추가로 결정됩니다. 이 항목은 [use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md)\< **Elem**>( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc))에서 반환됩니다. 특히 다음에 대한 내용을 설명합니다.

- **fac**. [그룹화는](../standard-library/numpunct-class.md#grouping) 숫자가 소수점의 왼쪽에 그룹화되는 방법을 결정합니다.

- **fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) 소수점의 왼쪽으로 숫자 그룹을 구분하는 시퀀스를 결정합니다.

**fac**, **grouping**에 의해 그룹화 제약 조건이 적용되지 않는 경우(해당 첫 번째 요소값이 CHAR_MAX임) **fac**. `thousands_sep`의 인스턴스가 출력 필드에서 생성되지 않습니다. 그렇지 않은 경우에는 인쇄 변환이 수행된 후에 구분 기호가 삽입됩니다.

두 번째 보호된 가상 구성원 함수는 다음 코드와 같습니다.

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

이 함수는 `ld`의 변환 사양을 `lu`로 대체한다는 점을 제외하면 첫 번째 함수와 동일하게 동작합니다.

세 번째 보호된 가상 구성원 함수는 다음 코드와 같습니다.

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

이 함수는 **val**. **fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point)의 값에서 부동 소수점 출력 필드를 생성하며 정수 자릿수와 소수 자릿수를 구분하는 시퀀스를 결정한다는 점을 제외하면 첫 번째 함수와 동일하게 동작합니다. 동일한 인쇄 변환 사양은 다음과 같이 결정됩니다.

- **iosbase**. **고정 플래그,** & `ios_base::floatfield` == `ios_base::`[fixed](../standard-library/ios-functions.md#fixed)변환 `lf`사양은 .

- **iosbase**. **플래그** & **ios_base ::floatfield** == `ios_base::`[과학,](../standard-library/ios-functions.md#scientific) `le`변환 사양입니다. **iosbase**. **flags** & 플래그`ios_base::`[대문자가](../standard-library/ios-functions.md#uppercase) 0이 아닌 `E`경우로 `e` 대체됩니다.

- 그렇지 않으면 변환 사양은 **lg**입니다. **iosbase**. **플래그** & **ios_base :::대문자가** 0이 아닌 경우 `g` 로 `G`대체됩니다.

**iosbase**. **플래그** & **ios_base ::fixed는** 영하지 않거나 **iosbase인**경우 . [precision](../standard-library/ios-base-class.md#precision)이 0보다 크면 **iosbase**. **precision** 값이 포함된 전체 자릿수가 변환 사양 앞에 추가됩니다. 모든 채우기는 정수 출력 필드에 대해 동일하게 동작합니다. 채우기 문자는 **fill**입니다. 그리고 마지막으로 다음과 같이 채우기가 수행됩니다.

- **iosbase**. **flags** & 플래그`ios_base::`[쇼포지는](../standard-library/ios-functions.md#showpos) 0이 **+** 아닌 플래그가 변환 사양으로 준비됩니다.

- **iosbase**. **flags** & 플래그`ios_base::`[쇼포인트가](../standard-library/ios-functions.md#showpoint) 0이 **#** 아닌 플래그는 변환 사양으로 준비됩니다.

네 번째 보호된 가상 구성원 함수는 다음 코드와 같습니다.

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

변환 사양의 한정자가 `l` 로 `L`대체된다는 점을 제외하면 세 번째 와 동일하게 행동합니다.

다섯 번째 보호된 가상 구성원 함수는 다음 코드와 같습니다.

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

이 함수는 변환 사양이 `p`** 및** 채우기를 지하는 데 필요한 한정자라는 점을 제외하면 첫 번째 함수와 동일하게 동작합니다.

여섯 번째 보호된 가상 구성원 함수는 다음 코드와 같습니다.

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

*val에서*부울 출력 필드를 생성한다는 점을 제외하면 첫 번째 와 동일하게 작동합니다.

부울 출력 필드는 두 가지 형식 중 하나를 사용합니다. `iosbase.flags & ios_base::` [boolalpha가](../standard-library/ios-functions.md#boolalpha) **false이면**멤버 `do_put(_Next, _Iosbase, _Fill, (long)val)`함수는 반환되며 일반적으로 0(false의 **false**경우) 또는 **1(true)의**생성된 시퀀스를 생성합니다. 그렇지 않으면 생성된 시퀀스는 *fac*입니다. [falsename](../standard-library/numpunct-class.md#falsename) **(false)** 또는 *fac*. [truename](../standard-library/numpunct-class.md#truename) (true). **true**

일곱 번째 보호된 가상 구성원 함수는 다음 코드와 같습니다.

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

이 함수는 `ld`의 변환 사양을 `lld`로 대체한다는 점을 제외하면 첫 번째 함수와 동일하게 동작합니다.

여덟 번째 보호된 가상 구성원 함수는 다음 코드와 같습니다.

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    unsigned long long val) const;
```

이 함수는 `ld`의 변환 사양을 `llu`로 대체한다는 점을 제외하면 첫 번째 함수와 동일하게 동작합니다.

### <a name="example"></a>예제

`do_put`을 호출하는 [put](#put)에 대한 예제를 참조하세요.

## <a name="num_putiter_type"></a><a name="iter_type"></a>num_put:iter_type

출력 반복기에 대해 설명하는 형식입니다.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 **OutputIterator**와 동일한 의미입니다.

## <a name="num_putnum_put"></a><a name="num_put"></a>num_put:num_put

`num_put` 형식의 개체에 대한 생성자입니다.

```cpp
explicit num_put(size_t _Refs = 0);
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

생성자는 기본 개체를 **로캘::**[패싯(_](../standard-library/locale-class.md#facet_class) *참조)으로 초기화합니다.*

## <a name="num_putput"></a><a name="put"></a>num_put::put

숫자를 지정된 로캘에 `CharType`대해 서식이 지정된 숫자를 나타내는 s 시퀀스로 변환합니다.

```cpp
iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    bool val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    unsigned long val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    Long long val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    Unsigned long long val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    double val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long double val) const;

iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const void* val) const;
```

### <a name="parameters"></a>매개 변수

*Dest*\
삽입된 문자열의 첫 번째 요소 주소를 지정하는 반복기입니다.

*_Iosbase*\
출력 및 출력 서식 지정을 위한 플래그에 문장 부호를 적용하는 데 사용되는 numpunct 패싯이 들어 있는 로캘을 포함하는 스트림을 지정합니다.

*_Fill*\
간격에 사용되는 문자입니다.

*발*\
출력할 숫자 또는 부울 형식입니다.

### <a name="return-value"></a>Return Value

생성된 마지막 요소에서 한 위치 다음의 위치 주소를 지정하는 출력 반복기입니다.

### <a name="remarks"></a>설명

모든 멤버 함수는 `next` [do_put](#do_put) `_Fill`반환합니다. `val` `_Iosbase`

### <a name="example"></a>예제

```cpp
// num_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );
   basic_stringstream<char> psz2;
   ios_base::iostate st = 0;
   long double fVal;
   cout << "The thousands separator is: "
        << use_facet < numpunct <char> >(loc).thousands_sep( )
        << endl;

   psz2.imbue( loc );
   use_facet < num_put < char > >
      ( loc ).put(basic_ostream<char>::_Iter(psz2.rdbuf( ) ),
                    psz2, ' ', fVal=1000.67);

   if ( st & ios_base::failbit )
      cout << "num_put( ) FAILED" << endl;
   else
      cout << "num_put( ) = " << psz2.rdbuf( )->str( ) << endl;
}
```

```Output
The thousands separator is: .
num_put( ) = 1.000,67
```

## <a name="see-also"></a>참고 항목

[\<로캘>](../standard-library/locale.md)\
[페이스트 클래스](../standard-library/locale-class.md#facet_class)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
