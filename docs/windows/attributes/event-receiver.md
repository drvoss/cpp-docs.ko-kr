---
title: event_receiver (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.event_receiver
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
ms.openlocfilehash: fb17eaa5d94636cedd650eb1bfb393d7c09e4fcc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217274"
---
# <a name="event_receiver"></a>event_receiver

이벤트 수신기(싱크)를 만듭니다.

## <a name="syntax"></a>구문

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>매개 변수

*type*<br/>
다음 값 중 하나의 열거형:

- `native`관리 되지 않는 C/c + + 코드의 경우 (네이티브 클래스의 경우 기본값)

- `com` - COM 코드용. 이 값을 사용하려면 다음 헤더 파일을 포함해야 합니다.

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
Com 인 경우에만 *layout_dependent* `type` = **com**을 지정 합니다. *layout_dependent* 은 부울입니다.

- **`true`** 는 이벤트 수신기에 있는 대리자의 서명이 이벤트 소스에서 후크 된 대리자와 정확히 일치 해야 함을 의미 합니다. 이벤트 수신기 처리기 이름은 관련 이벤트 원본 인터페이스에 지정 된 이름과 일치 해야 합니다. `coclass` *Layout_dependent* 가 인 경우를 사용 해야 합니다 **`true`** . 을 지정 하는 것이 약간 더 효율적입니다 **`true`** .

- **`false`**(기본값)은 호출 규칙 및 저장소 클래스 (가상, 정적 및 기타)가 이벤트 메서드 및 처리기와 일치할 필요가 없음을 의미 합니다. 처리기 이름도 이벤트 원본 인터페이스 메서드 이름과 일치 해야 합니다.

## <a name="remarks"></a>설명

**Event_receiver** c + + 특성은 Visual C++ 통합 이벤트 모델을 사용 하 여이 특성이 적용 되는 클래스 또는 구조가 이벤트 수신기가 되도록 지정 합니다.

**event_receiver** 는 [event_source](event-source.md) 특성 및 [__hook](../../cpp/hook.md) 및 [__unhook](../../cpp/unhook.md) 키워드와 함께 사용 됩니다. `event_source`를 사용 하 여 이벤트 원본을 만듭니다. 이벤트 **`__hook`** 수신기의 메서드 내에서를 사용 하 여 이벤트 수신기 메서드를 이벤트 소스의 이벤트에 연결 합니다 ("후크"). 를 사용 하 여 분리 **`__unhook`** 합니다.

*layout_dependent* com 이벤트 수신기 ( `type` = **com**)에 대해서만 지정 됩니다. *Layout_dependent* 의 기본값은 **`false`** 입니다.

> [!NOTE]
> 템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**`class`**, **`struct`**|
|**불가능**|예|
|**필수 특성**|`coclass`*layout_dependent* 경우=**`true`**|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[컴파일러 특성](compiler-attributes.md)<br/>
[event_source](event-source.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[클래스 특성](class-attributes.md)
