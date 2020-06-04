---
title: Platform::String 클래스
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::String::String
- VCCORLIB/Platform::String::Begin
- VCCORLIB/Platform::String::CompareOrdinal
- VCCORLIB/Platform::String::Concat
- VCCORLIB/Platform::String::Data
- VCCORLIB/Platform::String::Dispose
- VCCORLIB/Platform::String::End
- VCCORLIB/Platform::String::Equals
- VCCORLIB/Platform::String::GetHashCode
- VCCORLIB/Platform::String::IsEmpty
- VCCORLIB/Platform::String::IsFastPass
- VCCORLIB/Platform::String::Length
- VCCORLIB/Platform::String::ToString
helpviewer_keywords:
- Platform::String
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
ms.openlocfilehash: 3f29c60d0d6a4618d97d8f750a048fcc18f976b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322123"
---
# <a name="platformstring-class"></a>Platform::String 클래스

텍스트를 나타내는 데 사용되는 유니코드 문자의 순차적인 컬렉션을 나타냅니다. 자세한 정보 및 예제는 [문자열 을](../cppcx/strings-c-cx.md)참조하십시오.

## <a name="syntax"></a>구문

```cpp
public ref class String sealed : Object,
    IDisposable,
    IEquatable,
    IPrintable
```

## <a name="iterators"></a>반복기

String 클래스의 멤버가 아닌 두 반복기 함수를 `std::for_each` 템플릿 함수와 함께 사용하여 String 개체의 문자를 열거할 수 있습니다.

|멤버|Description|
|------------|-----------------|
|`const char16* begin(String^ s)`|지정된 String 개체의 시작 부분에 대한 포인터를 반환합니다.|
|`const char16* end(String^ s)`|지정된 String 개체의 끝을 지나는 포인터를 반환합니다.|

## <a name="members"></a>멤버

String 클래스는 Object 및 IDisposable, IEquatable 및 IPrintable 인터페이스에서 상속합니다.

String 클래스에는 다음 형식의 멤버도 있습니다.

### <a name="constructors"></a>생성자

|멤버|Description|
|------------|-----------------|
|[문자열 :: 문자열](#ctor)|String 클래스의 새 인스턴스를 초기화합니다.|

### <a name="methods"></a>메서드

String 클래스는 [Platform::Object Class](../cppcx/platform-object-class.md)의 Equals(), Finalize(), GetHashCode(), GetType(), MemberwiseClose() 및 ToString() 메서드를 상속합니다. String에는 다음 메서드도 있습니다.

|메서드|Description|
|------------|-----------------|
|[문자열::시작](#begin)|현재 문자열의 시작 부분에 대한 포인터를 반환합니다.|
|[문자열:비교ordinal](#compareordinal)|개체가 나타내는 두 문자열 값에서 해당 문자의 숫자 값을 계산하여 두 `String` 개체를 비교합니다.|
|[문자열 :: 콘캣](#concat)|두 String 개체의 값을 연결합니다.|
|[문자열::Data](#data)|현재 문자열의 시작 부분에 대한 포인터를 반환합니다.|
|[문자열::D](#dispose)|리소스를 확보하거나 해제합니다.|
|[문자열 ::끝](#end)|현재 문자열의 끝을 지나는 포인터를 반환합니다.|
|[문자열::같음](#equals)|지정된 개체가 현재 개체와 같은지 여부를 나타냅니다.|
|[문자열::GetHashCode](#gethashcode)|이 인스턴스에 대한 해시 코드를 반환합니다.|
|[문자열::비어 있음](#isempty)|현재 String 개체가 비어 있는지 여부를 나타냅니다.|
|[문자열 :: IsFastPass](#isfastpass)|현재 String 개체가 *빠른 패스* 작업에 참여하고 있는지 여부를 나타냅니다. 빠른 전달 작업에서는 참조 횟수가 일시 중단됩니다.|
|[문자열 : 길이 : 길이](#length)|현재 String 개체의 길이를 검색합니다.|
|[문자열 :: 토스트링](#tostring)|현재 문자열과 같은 값을 갖는 String 개체를 반환합니다.|

### <a name="operators"></a>연산자

String 클래스에는 다음 연산자가 있습니다.

|멤버|Description|
|------------|-----------------|
|[문자열::연산자== 연산자](#operator-equality)|지정된 두 String 개체의 값이 동일한지 여부를 나타냅니다.|
|[operator+ Operator](#operator-plus)|두 String 개체를 새 String 개체에 연결합니다.|
|[문자열::연산자> 연산자](#operator-greater-than)|String 개체 값이 두 번째 String 개체 값보다 큰지 여부를 나타냅니다.|
|[문자열::연산자>= 연산자](#operator-greater-than-or-equals)|String 개체 값이 두 번째 String 개체 값보다 크거나 같은지 여부를 나타냅니다.|
|[문자열::연산자!= 연산자](#operator-inequality)|지정된 두 String 개체의 값이 다른지 여부를 나타냅니다.|
|[문자열::연산자< 연산자](#operator-less-than)|String 개체 값이 두 번째 String 개체 값보다 작은지 여부를 나타냅니다.|

### <a name="requirements"></a>요구 사항

**지원되는 최소 클라이언트:** 윈도우 8

**지원되는 최소 서버:** 윈도우 서버 2012

**네임스페이스:** Platform

**헤더** vccorlib.h(기본적으로 포함)

## <a name="stringbegin-method"></a><a name="begin"></a>문자열::시작 메서드

현재 문자열의 시작 부분에 대한 포인터를 반환합니다.

### <a name="syntax"></a>구문

```cpp
char16* Begin();
```

### <a name="return-value"></a>Return Value

현재 문자열의 시작 부분에 대한 포인터입니다.

## <a name="stringcompareordinal-method"></a><a name="compareordinal"></a>문자열 ::비교ordinal 방법

개체로 표시되는 두 `String` 문자열 값에서 해당 문자의 숫자 값을 평가하여 두 개체를 비교하는 정적 메서드입니다.

### <a name="syntax"></a>구문

```cpp
static int CompareOrdinal( String^ str1, String^ str2 );
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 String 개체입니다.

*str2*<br/>
두 번째 String 개체입니다.

### <a name="return-value"></a>Return Value

두 비교 대상 간의 어휘 관계를 나타내는 정수입니다. 다음 표에서는 가능한 반환 값을 보여 줍니다.

|값|조건|
|-----------|---------------|
|-1|`str1`가 `str2`보다 작은 경우|
|0|`str1`이 `str2`와 같은 경우|
|1|`str1`가 `str2`보다 큰 경우|

## <a name="stringconcat-method"></a><a name="concat"></a>문자열 ::Concat 방법

두 String 개체의 값을 연결합니다.

### <a name="syntax"></a>구문

```cpp
String^ Concat( String^ str1, String^ str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 String 개체 또는 `null`입니다.

*str2*<br/>
두 번째 String 개체 또는 `null`입니다.

### <a name="return-value"></a>Return Value

`str1` 값과 `str2` 값의 연결을 값으로 하는 새로운 String^ 개체입니다.

`str1`가 `null`이고 `str2`이l 아니면 `str1`가 반환됩니다. `str2`가 `null`이고 `str1`이l 아니면 `str2`가 반환됩니다. `str1`과 `str2`가 모두 `null`이면 빈 문자열(L"")이 반환됩니다.

## <a name="stringdata-method"></a><a name="data"></a>문자열::Data 방법

개체의 데이터 버퍼 시작에 대한 포인터를 `char16`(`wchar_t`) 요소의 C 스타일 배열로 반환합니다.

### <a name="syntax"></a>구문

```cpp
const char16* Data();
```

### <a name="return-value"></a>Return Value

유니코드 문자 `const char16` 배열의 시작 부분에 대한`char16` 포인터입니다(형식def에 대한 `wchar_t`형식).

### <a name="remarks"></a>설명

이 메서드를 사용하여 `Platform::String^`에서 `wchar_t*`로 변환합니다. `String` 개체가 범위를 벗어나는 경우 데이터 포인터의 유효성이 더 이상 보장되지 않습니다. 원본 `String` 개체의 수명 을 초과하는 데이터를 저장하려면 [wcscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) 사용하여 자신이 할당한 메모리에 배열을 복사합니다.

## <a name="stringdispose-method"></a><a name="dispose"></a>문자열::D체계 메서드

리소스를 확보하거나 해제합니다.

### <a name="syntax"></a>구문

```cpp
virtual override void Dispose();
```

## <a name="stringend-method"></a><a name="end"></a>문자열::끝 방법

현재 문자열의 끝을 지나는 포인터를 반환합니다.

### <a name="syntax"></a>구문

```cpp
char16* End();
```

### <a name="return-value"></a>Return Value

현재 문자열의 끝을 지나는 포인터입니다.

### <a name="remarks"></a>설명

End() 반환 시작() + 길이입니다.

## <a name="stringequals-method"></a><a name="equals"></a>문자열::와이메메

지정된 String의 값이 현재 개체와 동일한지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
bool String::Equals(Object^ str);
bool String::Equals(String^ str);
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
비교할 개체.

### <a name="return-value"></a>Return Value

**true** `str` 는 현재 개체와 같으면 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

이 메서드는 정적 [문자열::CompareOrdinal](#compareordinal). 첫 번째 오버로드에서는 `str` 매개 변수가 String^ 개체로 캐스팅될 수 있어야 합니다.

## <a name="stringgethashcode-method"></a><a name="gethashcode"></a>문자열::GetHashCode 방법

이 인스턴스에 대한 해시 코드를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual override int GetHashCode();
```

### <a name="return-value"></a>Return Value

이 인스턴스의 해시 코드입니다.

## <a name="stringisempty-method"></a><a name="isempty"></a>문자열::IsEmpty 메서드

현재 String 개체가 비어 있는지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
bool IsEmpty();
```

### <a name="return-value"></a>Return Value

현재 `String` 개체가 **null이거나** 빈 문자열(L")인 경우 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="stringisfastpass-method"></a><a name="isfastpass"></a>문자열 ::IsFastPass 방법

현재 String 개체가 *빠른 패스* 작업에 참여하고 있는지 여부를 나타냅니다. 빠른 전달 작업에서는 참조 횟수가 일시 중단됩니다.

### <a name="syntax"></a>구문

```cpp
bool IsFastPass();
```

### <a name="return-value"></a>Return Value

**true** 현재 `String` 개체가 빠른 과거인 경우 true입니다. 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

참조 횟수가 계산된 개체가 매개 변수이고, 호출된 함수가 이 개체만 읽는 함수에 대한 호출인 경우 컴파일러는 참조 횟수를 안전하게 일시 중단하고 호출 성능을 향상시킬 수 있습니다. 코드에서 이 속성으로 할 수 있는 유용한 일은 없습니다. 시스템에서 모든 세부 사항을 처리합니다.

## <a name="stringlength-method"></a><a name="length"></a>문자열 :: 길이 방법

현재 `String` 개체의 문자 수를 검색합니다.

### <a name="syntax"></a>구문

```cpp
unsigned int Length();
```

### <a name="return-value"></a>Return Value

현재 `String` 개체의 문자 수입니다.

### <a name="remarks"></a>설명

문자가 없는 String의 길이는 0입니다. 다음 String의 길이는 5입니다.

```cpp
String^ str = "Hello";
int len = str->Length(); //len = 5
```

[String::Data에서](#data) 반환되는 문자 배열에는 NULL 또는 '\0'을 종료하는 하나의 추가 문자가 있습니다. 이 문자의 길이도 2바이트입니다.

## <a name="stringoperator-operator"></a><a name="operator-plus"></a>문자열::연산자+ 연산자

두 [String](../cppcx/platform-string-class.md) 개체를 새 [String](../cppcx/platform-string-class.md) 개체에 연결합니다.

### <a name="syntax"></a>구문

```cpp
bool String::operator+( String^ str1, String^ str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 `String` 개체입니다.

*str2*<br/>
내용이 `String`에 추가될 두 번째`str1` 개체입니다.

### <a name="return-value"></a>Return Value

**true** *str1이* *str2와*같으면; 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

이 연산자는 두 피연산자의 데이터가 들어 있는 `String^` 개체를 만듭니다. 매우 높은 성능이 중요하지 않은 경우 편의를 위해 이를 사용합니다. 함수에서 "`+`"를 몇 번 호출하는 것은 그렇게 눈에 띄지 않지만 대행 개체나 텍스트 데이터를 연속해서 조작하는 경우 표준 C++ 매커니즘과 형식을 사용하십시오.

## <a name="stringoperator-operator"></a><a name="operator-equality"></a>문자열::연산자== 연산자

지정된 두 String 개체의 텍스트 값이 같은지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
bool String::operator==( String^ str1, String^ str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
비교할 첫 번째 `String` 개체입니다.

*str2*<br/>
비교할 두 번째 `String` 개체입니다.

### <a name="return-value"></a>Return Value

의 내용이 `str1` 같으면 `str2` **true;** 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

이 연산자는 [문자열::비교Ordinal](#compareordinal).

## <a name="stringoperatorgt"></a><a name="operator-greater-than"></a>문자열::연산자&gt;

한 `String` 개체의 값이 두 번째 `String` 개체의 값보다 큰지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
bool String::operator>( String^ str1, String^ str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 `String` 개체입니다.

*str2*<br/>
두 번째 `String` 개체입니다.

### <a name="return-value"></a>Return Value

의 `str1` 값이 의 값보다 큰 `str2`경우 **true;** 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

이 연산자는 [String:::CompareOrdinal을](#compareordinal) 명시적으로 호출하고 0보다 큰 결과를 얻는 것과 같습니다.

## <a name="stringoperatorgt"></a><a name="operator-greater-than-or-equals"></a>문자열::연산자&gt;=

한 `String` 개체의 값이 두 번째 `String` 개체의 값보다 크거나 같는지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
bool String::operator>=( String^ str1, String^ str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 `String` 개체입니다.

*str2*<br/>
두 번째 `String` 개체입니다.

### <a name="return-value"></a>Return Value

의 `str1` 값이 의 값보다 크거나 같으면 `str2` **true;** 그렇지 **않으면, 거짓**.

## <a name="stringoperator"></a><a name="operator-inequality"></a>문자열::연산자!=

지정된 `String` 두 개체의 값이 다른지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
bool String::operator!=( String^ str1, String^ str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
비교할 첫 번째 `String` 개체입니다.

*str2*<br/>
비교할 두 번째 `String` 개체입니다.

### <a name="return-value"></a>Return Value

**true가** 같지 `str1` 않은 `str2`경우; 그렇지 **않으면, 거짓**.

## <a name="stringoperatorlt"></a><a name="operator-less-than"></a>문자열::연산자&lt;

한 `String` 개체의 값이 두 번째 `String` 개체의 값보다 작은지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
bool String::operator<( String^ str1, String^ str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 `String` 개체입니다.

*str2*<br/>
두 번째 `String` 개체입니다.

### <a name="return-value"></a>Return Value

*true str1값이* *str2*의 값보다 **낮으면** 그렇지 **않으면, 거짓**.

## <a name="stringstring-constructor"></a><a name="ctor"></a>문자열::문자열 생성자

입력 문자열 데이터의 복사본으로 `String` 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
String();
String(char16* s);
String(char16* s, unsigned int n);
```

### <a name="parameters"></a>매개 변수

*s*<br/>
문자열을 초기화하는 일련의 와이드 문자입니다. char16

*N*<br/>
문자열의 길이를 지정하는 숫자입니다.

### <a name="remarks"></a>설명

성능이 중요하고 원본 문자열의 수명을 제어하는 경우 문자열 대신 [Platform::StringReference를](../cppcx/platform-stringreference-class.md) 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
String^ s = L"Hello!";
```

## <a name="stringtostring"></a><a name="tostring"></a>문자열 :: 토스트링

값이 `String` 현재 문자열과 동일한 개체를 반환합니다.

### <a name="syntax"></a>구문

```cpp
String^ String::ToString();
```

### <a name="return-value"></a>Return Value

값이 `String` 현재 문자열과 동일한 개체입니다.

## <a name="see-also"></a>참고 항목

[Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)
