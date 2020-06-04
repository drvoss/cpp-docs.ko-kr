---
title: wstring_convert 클래스
ms.date: 11/04/2016
f1_keywords:
- wstring/stdext::cvt::wstring_convert
- locale/std::wstring_convert::byte_string
- locale/std::wstring_convert::wide_string
- locale/std::wstring_convert::state_type
- locale/std::wstring_convert::int_type
- locale/std::wstring_convert::from_bytes
- locale/std::wstring_convert::to_bytes
- locale/std::wstring_convert::converted
- locale/std::wstring_convert::state
helpviewer_keywords:
- stdext::cvt [C++], wstring_convert
- std::wstring_convert [C++], byte_string
- std::wstring_convert [C++], wide_string
- std::wstring_convert [C++], state_type
- std::wstring_convert [C++], int_type
- std::wstring_convert [C++], from_bytes
- std::wstring_convert [C++], to_bytes
- std::wstring_convert [C++], converted
- std::wstring_convert [C++], state
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
ms.openlocfilehash: f09f12d9100e9faad849de608a9124f457da23df
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366362"
---
# <a name="wstring_convert-class"></a>wstring_convert 클래스

클래스 템플릿은 `wstring_convert` 넓은 문자열과 바이트 문자열 간의 변환을 수행합니다.

## <a name="syntax"></a>구문

```cpp
template <class Codecvt, class Elem = wchar_t>
class wstring_convert
```

### <a name="parameters"></a>매개 변수

*코덱트*\
변환 개체를 나타내는 [locale](../standard-library/locale-class.md) 패싯입니다.

*Elem*\
와이드 문자 요소 형식입니다.

## <a name="remarks"></a>설명

클래스 템플릿은 클래스의 `std::basic_string<Elem>` 넓은 문자열 개체와 클래스의 `std::basic_string<char>` 바이트 문자열 개체(라고도 함)간의 변환을 제어하는 개체를 `std::string`설명합니다. 클래스 템플릿은 형식을 `wide_string` 정의하고 `byte_string` 이러한 두 형식의 동의어로 정의합니다. `Elem` 값(`wide_string` 개체에 저장) 시퀀스와 멀티바이트 시퀀스(`byte_string` 개체에 저장) 간의 변환은 표준 코드 변환 패싯 `std::codecvt<Elem, char, std::mbstate_t>`의 요구 사항을 충족하는 `Codecvt<Elem, char, std::mbstate_t>` 클래스의 개체에 의해 수행됩니다.

이 클래스 템플릿의 개체는 다음을 저장합니다.

- 오류 발생 시 표시할 바이트 문자열

- 오류 발생 시 표시할 와이드 문자열

- 할당된 변환 개체에 대한 포인터(wbuffer_convert 개체가 제거될 때 해제됨)

- [state_type](#state_type) 형식의 변환 상태 개체

- 변환 개수

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[wstring_convert](#wstring_convert)|`wstring_convert` 형식의 개체를 생성합니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[byte_string](#byte_string)|바이트 문자열을 나타내는 형식입니다.|
|[wide_string](#wide_string)|와이드 문자열을 나타내는 형식입니다.|
|[state_type](#state_type)|변환 상태를 나타내는 형식입니다.|
|[int_type](#int_type)|정수를 나타내는 형식입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[from_bytes](#from_bytes)|바이트 문자열을 와이드 문자열로 변환합니다.|
|[to_bytes](#to_bytes)|와이드 문자열을 바이트 문자열로 변환합니다.|
|[converted](#converted)|성공적인 변환 수를 반환합니다.|
|[상태](#state)|변환의 상태를 나타내는 개체를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="wstring_convertbyte_string"></a><a name="byte_string"></a>wstring_convert:byte_string

바이트 문자열을 나타내는 형식입니다.

```cpp
typedef std::basic_string<char> byte_string;
```

### <a name="remarks"></a>설명

이 형식은 `std::basic_string<char>`의 동의어입니다.

## <a name="wstring_convertconverted"></a><a name="converted"></a>wstring_convert::변환

성공적인 변환 수를 반환합니다.

```cpp
size_t converted() const;
```

### <a name="return-value"></a>Return Value

성공적인 변환 수입니다.

### <a name="remarks"></a>설명

성공적인 변환 수가 변환 개수 개체에 저장됩니다.

## <a name="wstring_convertfrom_bytes"></a><a name="from_bytes"></a>wstring_convert:from_bytes

바이트 문자열을 와이드 문자열로 변환합니다.

```cpp
wide_string from_bytes(char Byte);
wide_string from_bytes(const char* ptr);
wide_string from_bytes(const byte_string& Bstr);
wide_string from_bytes(const char* first, const char* last);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Byte*|변환할 단일 요소 바이트 시퀀스입니다.|
|*Ptr*|변환할 C 스타일의 null 종료 문자 시퀀스입니다.|
|*Bstr*|변환할 [byte_string](#byte_string)입니다.|
|*첫 번째*|변환할 문자 범위의 첫 문자입니다.|
|*마지막*|변환할 문자 범위의 마지막 문자입니다.|

### <a name="return-value"></a>Return Value

변환에서 생성되는 와이드 문자열 개체입니다.

### <a name="remarks"></a>설명

전환 [상태](../standard-library/wstring-convert-class.md) 개체가 명시적 값으로 *생성되지 않은* 경우 변환이 시작되기 전에 기본값(초기 전환 상태)으로 설정됩니다. 그렇지 않으면 변경되지 않습니다.

성공적으로 변환된 입력 요소 수는 변환 개수 개체에 저장됩니다. 변환 오류가 발생하지 않는 경우 멤버 함수는 변환된 와이드 문자열을 반환합니다. 오류가 발생하는 경우, 와이드 문자열 오류 메시지에 대한 이니셜라이저를 사용하여 생성된 개체라면 멤버 함수는 와이드 문자열 오류 메시지 개체를 반환합니다. 그렇지 않으면 구성원 함수가 [range_error](../standard-library/range-error-class.md) 클래스의 개체를 발생시킵니다.

## <a name="wstring_convertint_type"></a><a name="int_type"></a>wstring_convert:int_type

정수를 나타내는 형식입니다.

```cpp
typedef typename wide_string::traits_type::int_type int_type;
```

### <a name="remarks"></a>설명

이 형식은 `wide_string::traits_type::int_type`의 동의어입니다.

## <a name="wstring_convertstate"></a><a name="state"></a>wstring_convert::상태

변환의 상태를 나타내는 개체를 반환합니다.

```cpp
state_type state() const;
```

### <a name="return-value"></a>Return Value

변환 상태를 나타내는 [변환 상태](../standard-library/wstring-convert-class.md) 개체입니다.

### <a name="remarks"></a>설명

## <a name="wstring_convertstate_type"></a><a name="state_type"></a>wstring_convert:state_type

변환 상태를 나타내는 형식입니다.

```cpp
typedef typename Codecvt::state_type state_type;
```

### <a name="remarks"></a>설명

형식은 변환 상태를 나타낼 수 있는 개체에 대해 설명합니다. 이 형식은 `Codecvt::state_type`의 동의어입니다.

## <a name="wstring_convertto_bytes"></a><a name="to_bytes"></a>wstring_convert:to_bytes

와이드 문자열을 바이트 문자열로 변환합니다.

```cpp
byte_string to_bytes(Elem Char);
byte_string to_bytes(const Elem* Wptr);
byte_string to_bytes(const wide_string& Wstr);
byte_string to_bytes(const Elem* first, const Elem* last);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Char*|변환할 와이드 문자입니다.|
|*Wptr*|변환할 null로 끝나는 시퀀스로, `wptr`에서 시작되며 C 스타일입니다.|
|*스트레 (Wstr)*|변환할 [wide_string](#wide_string)입니다.|
|*첫 번째*|변환할 요소의 범위에서 첫 번째 요소입니다.|
|*마지막*|변환할 요소의 범위에서 마지막 요소입니다.|

### <a name="remarks"></a>설명

전환 [상태](../standard-library/wstring-convert-class.md) 개체가 명시적 값으로 *생성되지 않은* 경우 변환이 시작되기 전에 기본값(초기 전환 상태)으로 설정됩니다. 그렇지 않으면 변경되지 않습니다.

성공적으로 변환된 입력 요소 수는 변환 개수 개체에 저장됩니다. 변환 오류가 발생하지 않는 경우 멤버 함수는 변환된 바이트 문자열을 반환합니다. 오류가 발생하는 경우, 바이트 문자열 오류 메시지에 대한 이니셜라이저를 사용하여 생성된 개체라면 멤버 함수는 바이트 문자열 오류 메시지 개체를 반환합니다. 그렇지 않으면 구성원 함수가 [range_error](../standard-library/range-error-class.md) 클래스의 개체를 발생시킵니다.

## <a name="wstring_convertwide_string"></a><a name="wide_string"></a>wstring_convert:wide_string

와이드 문자열을 나타내는 형식입니다.

```cpp
typedef std::basic_string<Elem> wide_string;
```

### <a name="remarks"></a>설명

이 형식은 `std::basic_string<Elem>`의 동의어입니다.

## <a name="wstring_convertwstring_convert"></a><a name="wstring_convert"></a>wstring_convert:wstring_convert

`wstring_convert` 형식의 개체를 생성합니다.

```cpp
wstring_convert(Codecvt *Pcvt = new Codecvt);
wstring_convert(Codecvt *Pcvt, state_type _State);
wstring_convert(const byte_string& _Berr, const wide_string& Werr = wide_string());
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*\*PCVt*|변환을 수행할 `Codecvt` 형식의 개체입니다.|
|*_state*|변환 상태를 나타내는 [state_type](#state_type) 형식의 개체입니다.|
|*_Berr*|오류 시에 표시할 [byte_string](#byte_string)입니다.|
|*웨르 (동음이의)*|오류 시에 표시할 [wide_string](#wide_string)입니다.|

### <a name="remarks"></a>설명

첫 번째 생성자는 [변환 개체](../standard-library/wstring-convert-class.md)에 *Pcvt_arg*를 저장합니다.
