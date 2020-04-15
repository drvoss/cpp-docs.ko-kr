---
title: 이벤트 처리 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: f2f8269dcf0f59a5d0794d3f16d4c4f85d8841ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330142"
---
# <a name="event-handling-global-functions"></a>이벤트 처리 전역 함수

이 함수는 이벤트 처리기를 제공합니다.

> [!IMPORTANT]
> 다음 표에 나열된 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|개체가 신호를 받을 때까지 기다리는 한편 필요에 따라 창 메시지를 디스패치합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atlwaitwithmessageloop"></a><a name="atlwaitwithmessageloop"></a>아틀웨이트메시지루프

필요에 따라 창 메시지를 디스패치하는 중에 개체가 신호를 받는 동안 대기합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>매개 변수

*h이벤트*<br/>
【인】 기다릴 개체의 핸들입니다.

### <a name="return-value"></a>Return Value

개체가 신호를 받은 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 기능은 개체의 이벤트가 발생할 때까지 기다렸다가 발생 사실을 알리지만 기다리는 동안 창 메시지를 디스패치할 수 있도록 하려는 경우에 유용합니다.

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)
