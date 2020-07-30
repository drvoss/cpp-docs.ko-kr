---
title: nested_exception 클래스
ms.date: 11/04/2016
f1_keywords:
- exception/std::nested_exception
helpviewer_keywords:
- nested_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 6ae95880f0bc18928ed9bd4f6b6da14722f6ec60
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212191"
---
# <a name="nested_exception-class"></a>nested_exception 클래스

이 클래스는 여러 상속을 사용 하는 예외를 설명 합니다. 현재 처리 된 예외를 캡처하여 나중에 사용할 수 있도록 저장 합니다.

## <a name="syntax"></a>구문

```cpp
class nested_exception {
    public:
        nested_exception();
        nested_exception(const nested_exception&) = default;
        virtual ~nested_exception() = default; // access functions
};
```

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 =](#op_as)||

### <a name="functions"></a>Functions

|||
|-|-|
|[rethrow_nested](#rethrow_nested)|저장 된 예외를 throw 합니다.|
|[nested_ptr](#nested_ptr)|저장 된 예외를 반환 합니다.|

### <a name="operator"></a><a name="op_as"></a>연산자 =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a><a name="nested_ptr"></a>nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>Return Value

이 개체가 캡처한 저장 된 예외 `nested_exception` 입니다.

### <a name="rethrow_nested"></a><a name="rethrow_nested"></a>rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>설명

가 `nested_ptr()` null 포인터를 반환 하면 함수는를 호출 합니다 `std::terminate()` . 그렇지 않으면에서 캡처한 저장 된 예외를 throw 합니다 **`*this`** .

## <a name="requirements"></a>요구 사항

**헤더:**\<exception>

**네임스페이스:** std

## <a name="see-also"></a>참고 항목

[exception 클래스](../standard-library/exception-class.md)\
[C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
