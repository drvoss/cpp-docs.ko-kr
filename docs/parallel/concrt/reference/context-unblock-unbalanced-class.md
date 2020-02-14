---
title: context_unblock_unbalanced 클래스
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: 261ec96c1a83fbec423e6dbbfe403c4db53a2962
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143102"
---
# <a name="context_unblock_unbalanced-class"></a>context_unblock_unbalanced 클래스

이 클래스는 동일한 컨텍스트에서 `Block` 개체의 `Unblock` 및 `Context` 메서드 호출 쌍이 잘못된 경우 발생하는 예외를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|오버로드됨. `context_unblock_unbalanced` 개체를 생성합니다.|

## <a name="remarks"></a>설명

`Context` 개체의 `Block` 및 `Unblock` 메서드에 대 한 호출은 항상 적절 하 게 쌍을 이루어야 합니다. 동시성 런타임를 사용 하 여 작업을 순서에 따라 수행할 수 있습니다. 예를 들어 `Block` 호출 다음에 `Unblock` 호출이 오거나 그 반대가 될 수 있습니다. 이 예외는 예를 들어 `Unblock` 메서드를 두 번 호출 하는 경우 차단 되지 않은 `Context` 개체에 대해 수행 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>요구 사항

**헤더:** concrt .h

**네임스페이스:** 동시성

## <a name="ctor"></a>context_unblock_unbalanced

`context_unblock_unbalanced` 개체를 생성합니다.

```cpp
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
