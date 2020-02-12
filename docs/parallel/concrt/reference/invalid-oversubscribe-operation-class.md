---
title: invalid_oversubscribe_operation 클래스
ms.date: 11/04/2016
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
ms.openlocfilehash: 7a879fc2da2f963cd4b5ea5fcd7e9506f86ce051
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140843"
---
# <a name="invalid_oversubscribe_operation-class"></a>invalid_oversubscribe_operation 클래스

이 클래스는 `_BeginOversubscription` 매개 변수를 **true**로 설정 하 여 `Context::Oversubscribe` 메서드를 이전에 호출 하지 않고 `_BeginOversubscription` 매개 변수를 **false** 로 설정한 상태에서 `Context::Oversubscribe` 메서드가 호출 될 때 throw 되는 예외를 설명 합니다.

## <a name="syntax"></a>구문

```cpp
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|오버로드됨. `invalid_oversubscribe_operation` 개체를 생성합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>요구 사항

**헤더:** concrt .h

**네임스페이스:** 동시성

## <a name="ctor"></a>invalid_oversubscribe_operation

`invalid_oversubscribe_operation` 개체를 생성합니다.

```cpp
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
