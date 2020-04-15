---
title: out_of_memory 클래스
ms.date: 11/04/2016
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
ms.openlocfilehash: e716d4952bdb9634cc0d195285d3a65c5c06b0a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336813"
---
# <a name="out_of_memory-class"></a>out_of_memory 클래스

시스템 또는 장치 메모리 부족으로 인해 메서드가 실패할 때 throw되는 예외입니다.

## <a name="syntax"></a>구문

```cpp
class out_of_memory : public runtime_exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[out_of_memory 생성자](#ctor)|`out_of_memory` 클래스의 새 인스턴스를 초기화합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>요구 사항

**헤더:** 앰프.h

**네임스페이스:** 동시성

## <a name="out_of_memory"></a><a name="ctor"></a>out_of_memory

클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
explicit out_of_memory(
    const char * _Message ) throw();

out_of_memory () throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류에 대한 설명입니다.

### <a name="return-value"></a>Return Value

`out_of_memory` 클래스의 새 인스턴스입니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
