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
ms.openlocfilehash: c1c5593aee19254d4348d4e8658ffe9c3f0cf1b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368246"
---
# <a name="safeint-functions"></a>SafeInt 함수

SafeInt 라이브러리는 [SafeInt 클래스](../safeint/safeint-class.md) 인스턴스를 만들지 않고도 사용할 수 있는 여러 함수를 제공합니다. 단일 수학 연산을 정수 오버플로에서 보호하려는 경우 이 함수를 사용할 수 있습니다. 여러 개의 수학 연산을 보호하려면 `SafeInt` 개체를 만들어야 합니다. 이 함수를 여러 번 사용하는 것보다 `SafeInt` 개체를 만드는 것이 더 효율적입니다.

이 함수를 사용하면 먼저 동일한 형식으로 변환하지 않고도 서로 다른 두 형식의 매개 변수를 비교하거나 수학 연산을 수행할 수 있습니다.

각 함수에 `T`와 `U`라는 두 가지 템플릿 형식이 있습니다. 두 형식은 각각 부울, 문자 또는 정수 형식일 수 있습니다. 정수 형식은 부호 있는 형식이나 부호 없는 형식으로, 8비트에서 64비트의 임의 크기일 수 있습니다.

> [!NOTE]
> 이 라이브러리의 최신 버전은 [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt)에 있습니다.

## <a name="in-this-section"></a>섹션 내용

함수                      | Description
----------------------------- | --------------------------------------------------------------
[SafeAdd](#safeadd)           | 두 숫자를 더하고 오버플로를 방지합니다.
[세이프 캐스트](#safecast)         | 한 형식의 매개 변수를 다른 형식으로 캐스팅합니다.
[세이프 바이바이드](#safedivide)     | 두 숫자를 나누고 0으로 나누기를 방지합니다.
[SafeEquals](#safeequals), [SafeGreaterThan](#safegreaterthan), [SafeGreaterThanEquals](#safegreaterthanequals), [SafeLessThan](#safelessthan), [SafeLessThanEquals](#safelessthanequals), [SafeNotEquals](#safenotequals) | 두 숫자를 비교합니다. 이 함수를 사용하면 형식을 변경하지 않고도 서로 다른 두 형식의 숫자를 비교할 수 있습니다.
[SafeModulus](#safemodulus)   | 두 숫자의 모듈러스 연산을 수행합니다.
[SafeMultiply](#safemultiply) | 두 숫자를 곱하고 오버플로를 방지합니다.
[SafeSubtract](#safesubtract) | 두 숫자를 빼고 오버플로를 방지합니다.

## <a name="related-sections"></a>관련 단원

섹션                                                  | Description
-------------------------------------------------------- | ----------------------------------------------------
[SafeInt](../safeint/safeint-class.md)                   | `SafeInt` 클래스입니다.
[SafeIntException](../safeint/safeintexception-class.md) | SafeInt 라이브러리와 관련된 예외 클래스입니다.

## <a name="safeadd"></a><a name="safeadd"></a>세이프애드

오버플로를 방지하는 방식으로 두 숫자를 더합니다.

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 더할 첫 번째 숫자입니다. T 형식이어야 합니다.

*U*<br/>
[in] 더할 두 번째 숫자입니다. U 형식이어야 합니다.

*result*<br/>
[out] `SafeAdd`에서 결과를 저장하는 매개 변수입니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 **true**이고, 오류가 발생하면 **false**입니다.

## <a name="safecast"></a><a name="safecast"></a>세이프 캐스트

한 형식의 숫자를 다른 형식으로 캐스팅합니다.

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>매개 변수

*보낸 사람*<br/>
[in] 변환할 소스 숫자입니다. `T` 형식이어야 합니다.

*받는 사람*<br/>
[out] 새 숫자 형식에 대한 참조입니다. `U` 형식이어야 합니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 **true**이고, 오류가 발생하면 **false**입니다.

## <a name="safedivide"></a><a name="safedivide"></a>세이프 바이바이드

0으로 나누기를 방지하는 방식으로 두 숫자를 나눕니다.

```cpp
template<typename T, typename U>
inline bool SafeDivide (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 제수입니다. T 형식이어야 합니다.

*U*<br/>
[in] 피제수입니다. U 형식이어야 합니다.

*result*<br/>
[out] `SafeDivide`에서 결과를 저장하는 매개 변수입니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 **true**이고, 오류가 발생하면 **false**입니다.

## <a name="safeequals"></a><a name="safeequals"></a>안전 동등성

두 숫자를 비교하여 같은지 확인합니다.

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 비교할 첫 번째 숫자입니다. T 형식이어야 합니다.

*U*<br/>
[in] 비교할 두 번째 숫자입니다. U 형식이어야 합니다.

### <a name="return-value"></a>Return Value

*t*와 *u*가 같으면 **true**이고, 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

`==`가 두 가지 다른 형식의 숫자를 비교할 수 있게 해주기 때문에 이 메서드는 `SafeEquals`을 향상시켜 줍니다.

## <a name="safegreaterthan"></a><a name="safegreaterthan"></a>세이프그레이터탄

두 숫자를 비교합니다.

```cpp
template<typename T, typename U>
inline bool SafeGreaterThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 비교할 첫 번째 숫자입니다. `T` 형식이어야 합니다.

*U*<br/>
[in] 비교할 두 번째 숫자입니다. `U` 형식이어야 합니다.

### <a name="return-value"></a>Return Value

*t*가 *u*보다 크면 **true**이고, 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

`SafeGreaterThan`는 서로 다른 두 형식의 숫자를 비교할 수 있도록 하여 일반 비교 연산자를 확장합니다.

## <a name="safegreaterthanequals"></a><a name="safegreaterthanequals"></a>세이프그레이터이상동등한

두 숫자를 비교합니다.

```cpp
template <typename T, typename U>
inline bool SafeGreaterThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 비교할 첫 번째 숫자입니다. `T` 형식이어야 합니다.

*U*<br/>
[in] 비교할 두 번째 숫자입니다. `U` 형식이어야 합니다.

### <a name="return-value"></a>Return Value

*t*가 *u*보다 크거나 같으면 **true**이고, 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

`SafeGreaterThanEquals`는 서로 다른 두 형식의 숫자를 비교할 수 있기 때문에 표준 비교 연산자를 개선합니다.

## <a name="safelessthan"></a><a name="safelessthan"></a>세이프리스탄

한 숫자가 다른 숫자보다 작은지 여부를 확인합니다.

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 첫 번째 숫자입니다. `T` 형식이어야 합니다.

*U*<br/>
[in] 두 번째 숫자입니다. `U` 형식이어야 합니다.

### <a name="return-value"></a>Return Value

*t*가 *u*보다 작으면 **true**이고, 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 메서드는 `SafeLessThan`을 사용하여 서로 다른 두 형식의 숫자를 비교할 수 있기 때문에 표준 비교 연산자를 개선합니다.

## <a name="safelessthanequals"></a><a name="safelessthanequals"></a>세이프리스탄이 동등성

두 숫자를 비교합니다.

```cpp
template <typename T, typename U>
inline bool SafeLessThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 비교할 첫 번째 숫자입니다. `T` 형식이어야 합니다.

*U*<br/>
[in] 비교할 두 번째 숫자입니다. `U` 형식이어야 합니다.

### <a name="return-value"></a>Return Value

*t*가 *u*보다 작거나 같으면 **true**이고, 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

`SafeLessThanEquals`는 서로 다른 두 형식의 숫자를 비교할 수 있도록 하여 일반 비교 연산자를 확장합니다.

## <a name="safemodulus"></a><a name="safemodulus"></a>세이프모둘루스

두 숫자의 모듈러스 연산을 수행합니다.

```cpp
template<typename T, typename U>
inline bool SafeModulus (
   const T t,
   const U u,
   T& result
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 제수입니다. `T` 형식이어야 합니다.

*U*<br/>
[in] 피제수입니다. `U` 형식이어야 합니다.

*result*<br/>
[out] `SafeModulus`에서 결과를 저장하는 매개 변수입니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 **true**이고, 오류가 발생하면 **false**입니다.

## <a name="safemultiply"></a><a name="safemultiply"></a>안전 배수

두 숫자를 곱하고 오버플로를 방지합니다.

```cpp
template<typename T, typename U>
inline bool SafeMultiply (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 곱할 첫 번째 숫자입니다. `T` 형식이어야 합니다.

*U*<br/>
[in] 곱할 두 번째 숫자입니다. `U` 형식이어야 합니다.

*result*<br/>
[out] `SafeMultiply`에서 결과를 저장하는 매개 변수입니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 `true`이고, 오류가 발생하면 `false`입니다.

## <a name="safenotequals"></a><a name="safenotequals"></a>세이프노이퀄등

두 개의 숫자가 같지 않은지 확인합니다.

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 비교할 첫 번째 숫자입니다. `T` 형식이어야 합니다.

*U*<br/>
[in] 비교할 두 번째 숫자입니다. `U` 형식이어야 합니다.

### <a name="return-value"></a>Return Value

*t*와 *u*가 같지 않으면 **true**이고, 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

`!=`가 두 가지 다른 형식의 숫자를 비교할 수 있게 해주기 때문에 이 메서드는 `SafeNotEquals`을 향상시켜 줍니다.

## <a name="safesubtract"></a><a name="safesubtract"></a>안전 감산

오버플로를 방지하는 방식으로 두 숫자를 뺍니다.

```cpp
template<typename T, typename U>
inline bool SafeSubtract (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
[in] 빼기의 첫 번째 숫자입니다. `T` 형식이어야 합니다.

*U*<br/>
[in] *t*에서 뺄 숫자입니다. `U` 형식이어야 합니다.

*result*<br/>
[out] `SafeSubtract`에서 결과를 저장하는 매개 변수입니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 **true**이고, 오류가 발생하면 **false**입니다.
