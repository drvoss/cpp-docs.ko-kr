---
title: SafeInt 함수
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeInt functions
- SafeAdd
- SafeCast
- SafeDivide
- SafeEquals
- SafeGreaterThan
- SafeGreaterThanEquals
- SafeLessThan
- SafeLessThanEquals
- SafeModulus
- SafeMultiply
- SafeNotEquals
- SafeSubtract
helpviewer_keywords:
- functions, SafeInt
- SafeAdd function
- SafeCast function
- SafeDivide function
- SafeEquals function
- SafeGreaterThan function
- SafeGreaterThanEquals function
- SafeLessThan function
- SafeLessThanEquals function
- SafeModulus function
- SafeMultiply function
- SafeNotEquals function
- SafeSubtract function
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
ms.openlocfilehash: 0cf1418e3bf00c037faaa67de2bc76ad2b7cc5e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578401"
---
# <a name="safeint-functions"></a>SafeInt 함수

SafeInt 라이브러리의 인스턴스를 만들지 않고도 사용할 수 있는 여러 기능을 제공 합니다 [SafeInt 클래스](../windows/safeint-class.md)합니다. 정수 오버플로에서 단일 수학 연산을 보호 하려는 경우 이러한 함수를 사용할 수 있습니다. 여러 개의 산술 연산을 보호 하려는 경우 만든 `SafeInt` 개체입니다. 것이 보다 효과적으로 만들 `SafeInt` 를 이러한 함수를 여러 번 사용 보다는 개체입니다.

이러한 함수를 사용 하면 먼저 동일한 형식으로 변환 하지 않고도 두 가지 유형의 매개 변수에서 수학 작업을 수행 하거나 비교할 수 있습니다.

이러한 각 함수는 두 가지 서식 파일 형식: `T` 고 `U`입니다. 이러한 각 유형의 부울, 문자 또는 정수 계열 형식 수 있습니다. 정수 계열 형식 수 서명 되거나 서명 되지 않은 및 8 비트에서 64 비트 크기입니다.

> [!NOTE]
> 이 라이브러리의 최신 버전은 [ https://github.com/dcleblanc/SafeInt ](https://github.com/dcleblanc/SafeInt)에 있습니다.

## <a name="in-this-section"></a>섹션 내용

기능                      | 설명
----------------------------- | --------------------------------------------------------------
[SafeAdd](#safeadd)           | 두 숫자를 더하고 오버플로 방지 합니다.
[SafeCast](#safecast)         | 한 가지 유형의 다른 형식으로 매개 변수를 캐스팅합니다.
[SafeDivide](#safedivide)     | 두 숫자를 나누고를 0으로 나눈 으로부터 보호 합니다.
[SafeEquals](#safeequals), [SafeGreaterThan](#safegreaterthan), [SafeGreaterThanEquals](#safegreaterthanequals)를 [SafeLessThan](#safelessthan)를 [SafeLessThanEquals](#safelessthanequals)합니다 [ SafeNotEquals](#safenotequals) | 두 숫자를 비교합니다. 이러한 함수를 사용 하면 해당 유형을 변경 하지 않고 두 개의 서로 다른 형식의 숫자를 비교할 수 있습니다.
[SafeModulus](#safemodulus)   | 두 숫자에 대 한 나머지 작업을 수행합니다.
[SafeMultiply](#safemultiply) | 두 숫자를 함께 곱하고 오버플로 방지 합니다.
[SafeSubtract](#safesubtract) | 두 숫자를 빼고 오버플로 방지 합니다.

## <a name="related-sections"></a>관련 단원

단원                                                  | 설명
-------------------------------------------------------- | ----------------------------------------------------
[SafeInt](../windows/safeint-class.md)                   | `SafeInt` 클래스
[SafeIntException](../windows/safeintexception-class.md) | SafeInt 라이브러리 관련 예외 클래스입니다.

## <a name="safeadd"></a>SafeAdd

오버플로 방지 하는 방식으로 두 숫자를 추가 합니다.

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 추가할 첫 번째 숫자입니다. T 형식이어야 합니다.

*u*<br/>
[in] 추가할 두 번째 숫자입니다. U 형식이어야 합니다.

*결과*<br/>
[out] 매개 변수가 있는 `SafeAdd` 결과 저장 합니다.

### <a name="return-value"></a>반환 값

**true** 오류가 발생 하지 않으면; **false** 오류가 발생 합니다.

## <a name="safecast"></a>SafeCast

한 가지 형식의 숫자를 다른 형식으로 캐스팅합니다.

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>매개 변수

*From*<br/>
[in] 변환할 원본 숫자입니다. 이 형식 이어야 합니다 `T`합니다.

*대상*<br/>
[out] 새 숫자 형식에 대 한 참조입니다. 이 형식 이어야 합니다 `U`합니다.

### <a name="return-value"></a>반환 값

**true** 오류가 발생 하지 않으면; **false** 오류가 발생 합니다.

## <a name="safedivide"></a>SafeDivide

두 숫자를 0으로 나눈 으로부터 보호 하는 방식으로 나눕니다.

```cpp
template<typename T, typename U>
inline bool SafeDivide (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 제 수입니다. T 형식이어야 합니다.

*u*<br/>
[in] 피제수입니다. U 형식이어야 합니다.

*결과*<br/>
[out] 매개 변수가 있는 `SafeDivide` 결과 저장 합니다.

### <a name="return-value"></a>반환 값

**true** 오류가 발생 하지 않으면; **false** 오류가 발생 합니다.

## <a name="safeequals"></a>SafeEquals

같은지 여부를 확인 하려면 두 숫자를 비교 합니다.

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 비교할 첫 번째 숫자입니다. T 형식이어야 합니다.

*u*<br/>
[in] 비교할 두 번째 숫자입니다. U 형식이어야 합니다.

### <a name="return-value"></a>반환 값

**true 이면** 하는 경우 *t* 하 고 *u* 같고, 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

`==`가 두 가지 다른 형식의 숫자를 비교할 수 있게 해주기 때문에 이 메서드는 `SafeEquals`을 향상시켜 줍니다.

## <a name="safegreaterthan"></a>SafeGreaterThan

두 숫자를 비교합니다.

```cpp
template<typename T, typename U>
inline bool SafeGreaterThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 비교할 첫 번째 숫자입니다. 이 형식 이어야 합니다 `T`합니다.

*u*<br/>
[in] 비교할 두 번째 숫자입니다. 이 형식 이어야 합니다 `U`합니다.

### <a name="return-value"></a>반환 값

**true** 하는 경우 *t* 보다 크면 *u*이 고 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

`SafeGreaterThan` 두 가지 유형의 숫자를 비교할 수 있도록 하 여 일반 비교 연산자를 확장 합니다.

## <a name="safegreaterthanequals"></a>SafeGreaterThanEquals

두 숫자를 비교합니다.

```cpp
template <typename T, typename U>
inline bool SafeGreaterThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 비교할 첫 번째 숫자입니다. 이 형식 이어야 합니다 `T`합니다.

*u*<br/>
[in] 비교할 두 번째 숫자입니다. 이 형식 이어야 합니다 `U`합니다.

### <a name="return-value"></a>반환 값

**true 이면** 하는 경우 *t* 보다 크거나 같음 *u*이 고 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

`SafeGreaterThanEquals` 두 가지 유형의 숫자를 비교할 수 있기 때문에 표준 비교 연산자를 향상 시킵니다.

## <a name="safelessthan"></a>SafeLessThan

1 개의 숫자 다른 노드보다 작은지 여부를 결정 합니다.

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 첫 번째 숫자입니다. 이 형식 이어야 합니다 `T`합니다.

*u*<br/>
[in] 두 번째 필드가 됩니다. 이 형식 이어야 합니다 `U`합니다.

### <a name="return-value"></a>반환 값

**true** 하는 경우 *t* 는 미만 *u*이 고 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

이 메서드는 때문에 표준 비교 연산자를 향상 `SafeLessThan` 을 두 가지 유형의 수를 비교할 수 있습니다.

## <a name="safelessthanequals"></a>SafeLessThanEquals

두 숫자를 비교합니다.

```cpp
template <typename T, typename U>
inline bool SafeLessThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 비교할 첫 번째 숫자입니다. 이 형식 이어야 합니다 `T`합니다.

*u*<br/>
[in] 비교할 두 번째 숫자입니다. 이 형식 이어야 합니다 `U`합니다.

### <a name="return-value"></a>반환 값

**true 이면** 하는 경우 *t* 보다 작거나 같음 *u*이 고 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

`SafeLessThanEquals` 두 가지 유형의 숫자를 비교할 수 있도록 하 여 일반 비교 연산자를 확장 합니다.

## <a name="safemodulus"></a>SafeModulus

두 숫자에 대 한 나머지 작업을 수행합니다.

```cpp
template<typename T, typename U>
inline bool SafeModulus (
   const T t,
   const U u,
   T& result
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 제 수입니다. 이 형식 이어야 합니다 `T`합니다.

*u*<br/>
[in] 피제수입니다. 이 형식 이어야 합니다 `U`합니다.

*결과*<br/>
[out] 매개 변수가 있는 `SafeModulus` 결과 저장 합니다.

### <a name="return-value"></a>반환 값

**true** 오류가 발생 하지 않으면; **false** 오류가 발생 합니다.

## <a name="safemultiply"></a>SafeMultiply

오버플로 으로부터 보호 하는 방식으로 두 개의 숫자를 곱합니다.

```cpp
template<typename T, typename U>
inline bool SafeMultiply (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 곱할 첫 번째 숫자입니다. 이 형식 이어야 합니다 `T`합니다.

*u*<br/>
[in] 곱할 두 번째 숫자입니다. 이 형식 이어야 합니다 `U`합니다.

*결과*<br/>
[out] 매개 변수가 있는 `SafeMultiply` 결과 저장 합니다.

### <a name="return-value"></a>반환 값

`true` 오류가 발생 하지 않으면; `false` 오류가 발생 합니다.

## <a name="safenotequals"></a>SafeNotEquals

두 개의 숫자가 같지 않은지 확인합니다.

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 비교할 첫 번째 숫자입니다. 이 형식 이어야 합니다 `T`합니다.

*u*<br/>
[in] 비교할 두 번째 숫자입니다. 이 형식 이어야 합니다 `U`합니다.

### <a name="return-value"></a>반환 값

**true** 하는 경우 *t* 하 고 *u* 같지 않으면이 고 그렇지 **false**합니다.

### <a name="remarks"></a>설명

`!=`가 두 가지 다른 형식의 숫자를 비교할 수 있게 해주기 때문에 이 메서드는 `SafeNotEquals`을 향상시켜 줍니다.

## <a name="safesubtract"></a>SafeSubtract

오버플로 방지 하는 방식으로 두 개의 숫자를 뺍니다.

```cpp
template<typename T, typename U>
inline bool SafeSubtract (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>매개 변수

*t*<br/>
[in] 빼기의 첫 번째 숫자입니다. 이 형식 이어야 합니다 `T`합니다.

*u*<br/>
[in] 뺄 숫자입니다 *t*합니다. 이 형식 이어야 합니다 `U`합니다.

*결과*<br/>
[out] 매개 변수가 있는 `SafeSubtract` 결과 저장 합니다.

### <a name="return-value"></a>반환 값

**true** 오류가 발생 하지 않으면; **false** 오류가 발생 합니다.
