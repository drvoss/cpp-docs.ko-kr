---
title: runtime_exception 클래스
ms.date: 03/27/2019
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
ms.openlocfilehash: 6ad784720833d2ae5de7d653d132ba144aec2677
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126382"
---
# <a name="runtime_exception-class"></a>runtime_exception 클래스

C++ AMP(C++ Accelerated Massive Parallelism) 라이브러리의 예외에 대한 기본 형식입니다.

### <a name="syntax"></a>구문

```cpp
class runtime_exception : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[runtime_exception 생성자](#ctor)|`runtime_exception` 클래스의 새 인스턴스를 초기화합니다.|
|[~ runtime_exception 소멸자](#dtor)|`runtime_exception` 개체를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[get_error_code](#get_error_code)|예외를 발생 시킨 오류 코드를 반환 합니다.|

### <a name="public-operators"></a>Public 연산자

|name|설명|
|----------|-----------------|
|[operator=](#operator_eq)|지정 된 `runtime_exception` 개체의 내용을이 개체에 복사 합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`exception`

`runtime_exception`

## <a name="requirements"></a>요구 사항

**헤더:** amprt. h

**네임스페이스:** 동시성

## <a name="ctor"></a>runtime_exception 생성자

클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
runtime_exception(
    const char * _Message,
    HRESULT _Hresult ) throw();

explicit runtime_exception(
    HRESULT _Hresult ) throw();

runtime_exception(
    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
예외를 발생 시킨 오류에 대 한 설명입니다.

*_Hresult*<br/>
예외의 원인인 오류의 HRESULT입니다.

*_Other*<br/>
복사할 `runtime_exception` 개체입니다.

### <a name="return-value"></a>Return Value

`runtime_exception` 개체

## <a name="dtor"></a>~ runtime_exception 소멸자

개체를 소멸 시킵니다.

### <a name="syntax"></a>구문

```cpp
virtual ~runtime_exception() throw();
```

## <a name="get_error_code"></a>get_error_code

예외를 발생 시킨 오류 코드를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Return Value

예외의 원인인 오류의 HRESULT입니다.

## <a name="operator_eq"></a>  operator=
  지정 된 `runtime_exception` 개체의 내용을이 개체에 복사 합니다.

### <a name="syntax"></a>구문

```cpp
runtime_exception & operator= (    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
복사할 `runtime_exception` 개체입니다.

### <a name="return-value"></a>Return Value

이 `runtime_exception` 개체에 대 한 참조입니다.

## <a name="see-also"></a>참고 항목

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
