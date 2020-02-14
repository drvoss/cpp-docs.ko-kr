---
title: invalid_operation 클래스
ms.date: 11/04/2016
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
ms.openlocfilehash: e17d530569d16ba0084a58bf0be00d4a8423b7f6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140877"
---
# <a name="invalid_operation-class"></a>invalid_operation 클래스

이 클래스는 잘못된 작업이 수행될 때 throw되는 예외로, 동시성 런타임에서 throw된 다른 예외 형식으로 보다 정확하게 설명되지 않은 예외를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class invalid_operation : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[invalid_operation](#ctor)|오버로드됨. `invalid_operation` 개체를 생성합니다.|

## <a name="remarks"></a>설명

이 예외를 throw하는 다양한 메서드는 일반적으로 어떤 상황에서 이를 throw할지 문서화합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`exception`

`invalid_operation`

## <a name="requirements"></a>요구 사항

**헤더:** concrt .h

**네임스페이스:** 동시성

## <a name="ctor"></a>invalid_operation

`invalid_operation` 개체를 생성합니다.

```cpp
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
