---
title: codecvt 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
ms.openlocfilehash: 3dba971b112c23325e0529e53746cbee827df5e9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371958"
---
# <a name="codecvt-class"></a>codecvt 클래스

로캘 면역할을 할 수 있는 개체를 설명하는 클래스 템플릿입니다. 프로그램 내의 문자를 인코딩하는 데 사용하는 값의 시퀀스와 프로그램 밖의 문자를 인코딩하는 데 사용하는 값 사이의 변환을 제어할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>매개 변수

*Chartype*\
문자를 인코딩하기 위해 프로그램 내 사용하는 형식

*바이트*\
프로그램 밖의 문자를 인코딩하는 데 사용되는 형식입니다.

*상태 유형*\
내부 및 외부 문자 표현 형식 사이의 변환의 중간 상태를 나타내는 데 사용할 수 있는 형식입니다.

## <a name="remarks"></a>설명

클래스 템플릿은 *CharType* 형식의 값 시퀀스와 *바이트*형식의 값 시퀀스 간의 변환을 제어하기 위해 [로캘 면역할을](../standard-library/locale-class.md#facet_class)할 수 있는 개체를 설명합니다. 클래스 *StateType* 변환을 특성화 하 고 *클래스 StateType의* 개체 변환 하는 동안 필요한 상태 정보를 저장 합니다.

내부 인코딩은 문자당 고정된 수의 바이트가 있는 표현을 사용합니다(일반적으로 **문자** 문자 또는 **wchar_t**형식 입니다.

모든 로캘 패싯과 마찬가지로, 고정 개체 `id`에는 초기값 0이 저장되어 있습니다. 저장된 값에 액세스를 처음 시도하면 `id`에 고유한 양수 값이 저장됩니다.

[do_in](#do_in) 및 [do_out](#do_out)의 템플릿 버전은 항상 `codecvt_base::noconv`를 반환합니다.

C++ 표준 라이브러리는 여러 명시적 특수화를 정의합니다.

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

**wchar_t** **문자** 시퀀스 사이를 변환합니다.

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

UTF-16으로 인코딩된 시퀀스와 UTF-8로 인코딩된 `char16_t` **char** 시퀀스 간에 변환됩니다.

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

UTF-32(UCS-4)로 인코딩된 시퀀스와 UTF-8로 인코딩된 `char32_t` **char** 시퀀스 간에 변환됩니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[코덱트](#codecvt)|변환을 처리할 로캘 패싯으로 사용할 `codecvt` 클래스 개체의 생성자입니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[extern_type](#extern_type)|외부 표현에 사용되는 문자 형식입니다.|
|[intern_type](#intern_type)|내부 표현에 사용되는 문자 형식입니다.|
|[state_type](#state_type)|내부 및 외부 표현 사이의 변환 중간 상태를 나타내는 데 사용하는 문자 형식입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[always_noconv](#always_noconv)|변환을 수행해야 하는지 여부를 테스트합니다.|
|[do_always_noconv](#do_always_noconv)|변환을 수행해야 하는지 여부를 테스트하기 위해 호출하는 가상 함수입니다.|
|[do_encoding](#do_encoding)|`Byte` 스트림의 인코딩이 상태 종속인지, 사용된 `Byte` 값과 생성된 `CharType` 값 간의 비율이 일정하는지 여부를 테스트하는 가상 함수이며, 이 경우 해당 비율의 값을 결정합니다.|
|[do_in](#do_in)|내부 `Byte` 값의 시퀀스를 외부 `CharType` 값시퀀스로 변환하는 가상 함수입니다.|
|[do_length](#do_length)|지정된 `Byte` 외부 `Byte` 값 시퀀스의 값 수를 결정하는 가상 함수는 지정된 수의 `CharType` 내부 값을 생성하지 않고 해당 `Byte` 값 수를 반환합니다.|
|[do_max_length](#do_max_length)|하나의 내부 `CharType`을 만드는 데 필요한 외부 바이트의 최대 수를 반환하는 가상 함수입니다.|
|[do_out](#do_out)|내부 `CharType` 값의 시퀀스를 외부 바이트 시퀀스로 변환하는 가상 함수입니다.|
|[do_unshift](#do_unshift)|상태 종속 변환에 `Byte` 필요한 값을 제공하여 값 시퀀스의 마지막 문자를 완료하는 `Byte` 데 필요한 값을 제공하는 가상 함수입니다.|
|[인코딩](#encoding)|`Byte` 스트림의 인코딩이 상태 종속적인지, 사용된 `Byte` 값과 생성된 `CharType` 값 간의 비율이 일정한지 여부를 테스트하고, 이 경우 해당 비율의 값을 결정합니다.|
|[in](#in)|`Byte` 값 시퀀스의 외부 표현을 `CharType` 값 시퀀스의 내부 표현으로 변환합니다.|
|[length](#length)|지정된 `Byte` 외부 `Byte` 값 시퀀스의 값 수가 지정된 내부 `CharType` 값 개수보다 많지 않고 `Byte` 해당 값 수를 반환하는 지 결정합니다.|
|[max_length](#max_length)|하나의 내부 `CharType`를 `Byte` 생성하는 데 필요한 최대 외부 값 수를 반환합니다.|
|[밖으로](#out)|내부 `CharType` 값 시퀀스를 외부 `Byte` 값 시퀀스로 변환합니다.|
|[unshift](#unshift)|상태 종속 `Byte` 변환에 필요한 외부 값을 제공하여 `Byte` 값 시퀀스의 마지막 문자를 완료합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="codecvtalways_noconv"></a><a name="always_noconv"></a>코덱트:always_noconv

변환을 수행할 필요가 없는지 여부를 테스트합니다.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>Return Value

변환을 수행할 필요가 없는 경우 **true인** 부울 값입니다. 적어도 하나 이상을 수행해야하는 경우 **false.**

### <a name="remarks"></a>설명

멤버 함수는 [do_always_noconv](#do_always_noconv)를 반환합니다.

### <a name="example"></a>예제

```cpp
// codecvt_always_noconv.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvtcodecvt"></a><a name="codecvt"></a>codecvt::codecvt

변환을 처리할 로캘 패싯으로 사용하는 codecvt 클래스 개체의 생성자입니다.

```cpp
explicit codecvt(size_t refs = 0);
```

### <a name="parameters"></a>매개 변수

*심판*\
개체에 대한 메모리 관리 형식을 지정하는 데 사용하는 정수값입니다.

### <a name="remarks"></a>설명

*refs* 매개 변수와 그 중요성에 대한 가능한 값은 다음과 같습니다.

- 0: 개체를 포함하는 로캘에 의해 개체의 수명이 관리됩니다.

- 1: 개체의 수명을 수동으로 관리해야 합니다.

- 2: 이러한 값은 정의되지 않습니다.

생성자는 `locale::facet` [로캘 ::facet를](../standard-library/locale-class.md#facet_class)`(refs)`통해 기본 개체를 초기화합니다.

## <a name="codecvtdo_always_noconv"></a><a name="do_always_noconv"></a>코덱트::do_항상_noconv

변환을 수행할 필요가 없는지 여부를 테스트하기 위해 호출된 가상 함수입니다.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>Return Value

보호된 가상 멤버 함수는 [do_in](#do_in) 또는 [do_out](#do_out) `noconv`대한 모든 호출이 반환되는 경우에만 **true를** 반환합니다.

템플릿 버전은 항상 **true**를 반환합니다.

### <a name="example"></a>예제

`do_always_noconv`를 호출하는 [always_noconv](#always_noconv)에 대한 예제를 참조하세요.

## <a name="codecvtdo_encoding"></a><a name="do_encoding"></a>codecvt::do_인코딩

`Byte` 스트림의 인코딩이 상태 종속인지, 사용된 `Byte` 값과 생성된 `CharType` 값 간의 비율이 일정하는지 여부를 테스트하는 가상 함수이며, 이 경우 해당 비율의 값을 결정합니다.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>Return Value

보호된 가상 멤버 함수는 다음을 반환합니다.

- -1, 형식의 `extern_type` 시퀀스의 인코딩이 상태에 따라 달라지는 경우.

- 0: 인코딩에 다양한 길이의 시퀀스가 포함된 경우

- *N*, 인코딩에 길이 *N의* 시퀀스만 포함되는 경우

### <a name="example"></a>예제

`do_encoding`을 호출하는 [encoding](#encoding)에 대한 예제를 참조하세요.

## <a name="codecvtdo_in"></a><a name="do_in"></a>코덱트::do_in

외부 `Byte` 값의 시퀀스를 내부 `CharType` 값시퀀스로 변환하는 가상 함수입니다.

```cpp
virtual result do_in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>매개 변수

*상태*\
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*첫 번째 1*\
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*마지막 1*\
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*다음1*\
변환된 시퀀스의 끝 너머에 있는 포인터로, 변환되지 않은 첫 번째 문자에 대한 포인터입니다.

*처음 2*\
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*마지막 2*\
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*다음2*\
`CharType` 대상 시퀀스의 첫 번째 `CharType`변경되지 않은 문자에 대해 마지막으로 변환된 후에 오는 포인터입니다.

### <a name="return-value"></a>Return Value

작업의 성공, 부분적 성공 또는 실패를 나타내는 반환입니다. 함수에서 다음을 반환합니다.

- `codecvt_base::error`소스 서열이 아픈 경우.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- `codecvt_base::ok`변환이 성공하면

- `codecvt_base::partial`원본이 충분하지 않거나 대상이 충분히 크지 않은 경우 변환이 성공할 수 있습니다.

### <a name="remarks"></a>설명

*상태는* 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 저장 값은 달리 지정되지 않습니다.

### <a name="example"></a>예제

`do_in`을 호출하는 [in](#in)에 대한 예제를 참조하세요.

## <a name="codecvtdo_length"></a><a name="do_length"></a>코덱트::do_길이

지정된 `Byte` 외부 `Byte` 값 시퀀스의 값 수를 결정하는 가상 함수는 지정된 수의 `CharType` 내부 값을 생성하지 않고 해당 `Byte` 값 수를 반환합니다.

```cpp
virtual int do_length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>매개 변수

*상태*\
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*첫 번째 1*\
외부 시퀀스의 시작 부분에 대한 포인터입니다.

*마지막 1*\
외부 시퀀스의 끝 부분에 대한 포인터입니다.

*len2*\
멤버 함수에서 `Byte` 반환할 수 있는 최대 값 수입니다.

### <a name="return-value"></a>Return Value

[에서 `first1` `last1`외부 소스 시퀀스에 의해 정의된 *len2보다*크지 않은 최대 변환 수의 수를 나타내는 정수입니다.

### <a name="remarks"></a>설명

보호된 가상 멤버 `do_in( state, first1, last1, next1, buf, buf + len2, next2)` 함수는 *상태(상태의* 복사본), `buf`일부 버퍼 `next1` 및 `next2`포인터 및 를 효과적으로 호출합니다.

그런 다음 `next2` - `buf`를 반환합니다. 따라서, [, `first1` `last1`)에서 소스 시퀀스에 의해 정의된 *len2보다*크지 않은 최대 변환 수를 계산한다.

템플릿 버전은 항상 *last1* - 의 작은*1 및* *len2를*반환합니다.

### <a name="example"></a>예제

을 호출하는 `do_length` [길이에](#length)대한 예제를 참조하십시오.

## <a name="codecvtdo_max_length"></a><a name="do_max_length"></a>코덱트::do_max_length

하나의 내부를 `CharType`생성하는 데 필요한 `Byte` 외부 값의 최대 수를 반환하는 가상 함수입니다.

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>Return Value

하나를 `CharType`생성하는 `Byte` 데 필요한 값의 최대 수입니다.

### <a name="remarks"></a>설명

보호된 가상 멤버 함수는 do_length 의해 [do_length](#do_length) `( first1, last1, 1)` 반환될 수 있는 가장 큰 허용 *last1*값을 *반환합니다.*

### <a name="example"></a>예제

`do_max_length`를 호출하는 [max_length](#max_length)에 대한 예제를 참조하세요.

## <a name="codecvtdo_out"></a><a name="do_out"></a>코덱트::do_out

내부 `CharType` 값의 시퀀스를 외부 `Byte` 값시퀀스로 변환하는 가상 함수입니다.

```cpp
virtual result do_out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*상태*\
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*첫 번째 1*\
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*마지막 1*\
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*다음1*\
마지막으로 `CharType` 변환된 후 첫 번째 `CharType`변환되지 않은 포인터에 대한 참조입니다.

*처음 2*\
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*마지막 2*\
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*다음2*\
마지막으로 `Byte` 변환된 후 첫 번째 `Byte`변환되지 않은 포인터에 대한 참조입니다.

### <a name="return-value"></a>Return Value

함수에서 다음을 반환합니다.

- `codecvt_base::error`소스 서열이 아픈 경우.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- `codecvt_base::ok`변환이 성공하면

- `codecvt_base::partial`원본이 충분하지 않거나 변환이 성공할 수 있을 만큼 큰 대상이 아닌 경우

### <a name="remarks"></a>설명

*상태는* 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 저장 값은 달리 지정되지 않습니다.

### <a name="example"></a>예제

`do_out`을 호출하는 [out](#out)에 대한 예제를 참조하세요.

## <a name="codecvtdo_unshift"></a><a name="do_unshift"></a>코덱트::do_unshift

상태 종속 변환에 `Byte` 필요한 값을 제공하여 값 시퀀스의 마지막 문자를 완료하는 `Byte` 데 필요한 값을 제공하는 가상 함수입니다.

```cpp
virtual result do_unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*상태*\
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*처음 2*\
대상 범위에서 첫 번째 위치에 대한 포인터입니다.

*마지막 2*\
대상 범위에서 마지막 위치에 대한 포인터입니다.

*다음2*\
대상 시퀀스의 변경되지 않은 첫 번째 요소에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수에서 다음을 반환합니다.

- `codecvt_base::error`*상태가* 잘못된 상태를 나타내는 경우

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- `codecvt_base::ok`변환이 성공하는 경우

- `codecvt_base::partial`변환이 성공할 수 있을 만큼 대상이 크지 않은 경우

### <a name="remarks"></a>설명

보호된 가상 멤버 함수는 종료 `CharType` `last2` `Byte`요소(0)를 제외하고 소스 요소(0)를 [, 내에 `first2`저장하는 대상 시퀀스로 변환하려고 합니다. 항상 *next2에* 대상 시퀀스의 첫 번째 변경되지 않은 요소에 대한 포인터를 저장합니다.

_*State*는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 일반적으로 소스 요소(0)를 `CharType`변환하면 초기 변환 상태의 현재 상태가 남습니다.

### <a name="example"></a>예제

`do_unshift`를 호출하는 [unshift](#unshift)에 대한 예제를 참조하세요.

## <a name="codecvtencoding"></a><a name="encoding"></a>codecvt::인코딩

`Byte` 스트림의 인코딩이 상태 종속적인지, 사용된 `Byte` 값과 생성된 `CharType` 값 간의 비율이 일정한지 여부를 테스트하고, 이 경우 해당 비율의 값을 결정합니다.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>Return Value

반환 값이 양수이면 해당 값은 `Byte` 문자를 생성하는 데 `CharType` 필요한 상수 문자 수입니다.

보호된 가상 멤버 함수는 다음을 반환합니다.

- -1, 형식의 `extern_type` 시퀀스의 인코딩이 상태에 따라 달라지는 경우.

- 0: 인코딩에 다양한 길이의 시퀀스가 포함된 경우

- *N*: 인코딩에 *N* 길이의 시퀀스만 포함된 경우

### <a name="remarks"></a>설명

멤버 함수는 [do_encoding](#do_encoding)을 반환합니다.

### <a name="example"></a>예제

```cpp
// codecvt_encoding.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
}
```

```Output
1
1
1
```

## <a name="codecvtextern_type"></a><a name="extern_type"></a>코덱트::extern_type

외부 표현에 사용되는 문자 형식입니다.

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `Byte`의 동의어입니다.

## <a name="codecvtin"></a><a name="in"></a>코덱트::에서

`Byte` 값 시퀀스의 외부 표현을 `CharType` 값 시퀀스의 내부 표현으로 변환합니다.

```cpp
result in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>매개 변수

*상태*\
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*첫 번째 1*\
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*마지막 1*\
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*다음1*\
변환된 시퀀스의 끝 너머에 있는 포인터로, 변환되지 않은 첫 번째 문자에 대한 포인터입니다.

*처음 2*\
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*마지막 2*\
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*다음2*\
`CharType` 대상 시퀀스에서 변경되지 않은 `Chartype` 첫 번째 문자로 마지막으로 변환된 후에 오는 포인터입니다.

### <a name="return-value"></a>Return Value

작업의 성공, 부분적 성공 또는 실패를 나타내는 반환입니다. 함수에서 다음을 반환합니다.

- `codecvt_base::error`소스 서열이 아픈 경우.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- `codecvt_base::ok`변환이 성공하면

- `codecvt_base::partial`원본이 충분하지 않거나 변환이 성공할 수 있을 만큼 큰 대상이 아닌 경우

### <a name="remarks"></a>설명

*상태는* 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 부분 변환 후 새 문자가 도착할 때 변환이 다시 시작될 수 있도록 *상태를* 설정해야 합니다.

멤버 함수는 [do_in](#do_in)`( state, first1,  last1,  next1, first2, last2,  next2)`반환합니다.

### <a name="example"></a>예제

```cpp
// codecvt_in.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )
   << L"The converted string is:\n ["
   << &pwszInt[0]
   << L"]" << endl;
   exit(-1);
}
```

```Output
It worked! The converted string is:
[This is the string to be converted!]
```

## <a name="codecvtintern_type"></a><a name="intern_type"></a>코덱트:intern_type

내부 표현에 사용되는 문자 형식입니다.

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `CharType`의 동의어입니다.

## <a name="codecvtlength"></a><a name="length"></a>코덱트::길이

지정된 `Byte` 외부 `Byte` 값 시퀀스의 값 수가 지정된 내부 `CharType` 값 개수보다 많지 않고 `Byte` 해당 값 수를 반환하는 지 결정합니다.

```cpp
int length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>매개 변수

*상태*\
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*첫 번째 1*\
외부 시퀀스의 시작 부분에 대한 포인터입니다.

*마지막 1*\
외부 시퀀스의 끝 부분에 대한 포인터입니다.

*len2*\
멤버 함수에서 반환할 수 있는 최대 바이트 수입니다.

### <a name="return-value"></a>Return Value

[에서 `first1` `last1`외부 소스 시퀀스에 의해 정의된 *len2보다*크지 않은 최대 변환 수의 수를 나타내는 정수입니다.

### <a name="remarks"></a>설명

멤버 함수는 [do_length](#do_length)`( state, first1, last1, len2)`반환합니다.

### <a name="example"></a>예제

```cpp
// codecvt_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << endl;
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="codecvtmax_length"></a><a name="max_length"></a>코덱트::max_length

하나의 내부 `CharType`를 `Byte` 생성하는 데 필요한 최대 외부 값 수를 반환합니다.

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>Return Value

하나를 `CharType`생성하는 `Byte` 데 필요한 값의 최대 수입니다.

### <a name="remarks"></a>설명

멤버 함수는 [do_max_length](#do_max_length)를 반환합니다.

### <a name="example"></a>예제

```cpp
// codecvt_max_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc( "C");//English_Britain" );//German_Germany
   int res = use_facet<codecvt<char, char, mbstate_t> >
     ( loc ).max_length( );
   wcout << res << endl;
}
```

```Output
1
```

## <a name="codecvtout"></a><a name="out"></a>코덱트::아웃

내부 `CharType` 값 시퀀스를 외부 `Byte` 값 시퀀스로 변환합니다.

```cpp
result out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*상태*\
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*첫 번째 1*\
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*마지막 1*\
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*다음1*\
마지막으로 `CharType` `CharType` 변환된 후 첫 번째 변환되지 않은 포인터에 대한 참조입니다.

*처음 2*\
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*마지막 2*\
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*다음2*\
마지막으로 변환된 `Byte` 후 첫 번째 변환되지 않은 `Byte`포인터에 대한 참조입니다.

### <a name="return-value"></a>Return Value

멤버 함수는 [do_out](#do_out)`( state, first1, last1, next1, first2, last2, next2)`반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [codecvt::do_out](#do_out)을 참조하세요.

### <a name="example"></a>예제

```cpp
// codecvt_out.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
#include <wchar.h>
using namespace std;
#define LEN 90
int main( )
{
   char pszExt[LEN+1];
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );
   char* pszNext;
   const wchar_t* pwszNext;
   mbstate_t state;
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).out( state,
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );
   pszExt[wcslen( pwszInt )] = 0;
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )
   << "The converted string is:\n ["
   << &pszExt[0]
   << "]" << endl;
}
```

```Output
It worked: The converted string is:
[This is the wchar_t string to be converted.]
```

## <a name="codecvtstate_type"></a><a name="state_type"></a>코덱트::state_type

내부 및 외부 표현 사이의 변환 중간 상태를 나타내는 데 사용하는 문자 형식입니다.

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `StateType`의 동의어입니다.

## <a name="codecvtunshift"></a><a name="unshift"></a>codecvt::unshift

상태 `Byte` 종속 변환에 필요한 값을 제공하여 값 시퀀스의 `Byte` 마지막 문자를 완료합니다.

```cpp
result unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*상태*\
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*처음 2*\
대상 범위에서 첫 번째 위치에 대한 포인터입니다.

*마지막 2*\
대상 범위에서 마지막 위치에 대한 포인터입니다.

*다음2*\
대상 시퀀스의 변경되지 않은 첫 번째 요소에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수에서 다음을 반환합니다.

- `codecvt_base::error`상태가 잘못된 상태를 나타내는 경우

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- `codecvt_base::ok`변환이 성공하면

- `codecvt_base::partial`변환이 성공할 수 있을 만큼 크지 않은 경우

### <a name="remarks"></a>설명

보호된 가상 멤버 함수는 종료 `CharType` `last2` `Byte`요소(0)를 제외하고 소스 요소(0)를 [, 내에 `first2`저장하는 대상 시퀀스로 변환하려고 합니다. 항상 *next2에* 대상 시퀀스의 첫 번째 변경되지 않은 요소에 대한 포인터를 저장합니다.

*상태는* 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 일반적으로 소스 요소(0)를 `CharType`변환하면 초기 변환 상태의 현재 상태가 남습니다.

멤버 함수는 [do_unshift](#do_unshift)`( state, first2, last2, next2 )`반환합니다.

## <a name="see-also"></a>참고 항목

[\<로캘>](../standard-library/locale.md)\
[코드 페이지](../c-runtime-library/code-pages.md)\
[로캘 이름, 언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
