---
title: invalid_link_target 클래스
ms.date: 11/04/2016
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
ms.openlocfilehash: bd3d82c06c174c69c60dec33592110f4de72ac99
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141045"
---
# <a name="invalid_link_target-class"></a>invalid_link_target 클래스

이 클래스는 메시징 블록의 `link_target` 메서드를 호출하고 메시징 블록이 대상에 연결할 수 없는 경우 발생하는 예외를 설명합니다. 메시징 블록에 허용되는 링크 수를 초과했거나 동일한 소스에 특정 대상을 두 번 연결하려고 시도한 결과일 수 있습니다.

## <a name="syntax"></a>구문

```cpp
class invalid_link_target : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[invalid_link_target](#ctor)|오버로드됨. `invalid_link_target` 개체를 생성합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`exception`

`invalid_link_target`

## <a name="requirements"></a>요구 사항

**헤더:** concrt .h

**네임스페이스:** 동시성

## <a name="ctor"></a>invalid_link_target

`invalid_link_target` 개체를 생성합니다.

```cpp
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)
