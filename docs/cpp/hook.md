---
title: __hook
ms.date: 11/04/2016
f1_keywords:
- __hook_cpp
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
ms.openlocfilehash: 5a0eaf0a3bc0617dbcd1f43805af8a95291e7e47
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87188169"
---
# <a name="__hook"></a>__hook

처리기 메서드를 이벤트와 연결합니다.

## <a name="syntax"></a>구문

```
long __hook(
    &SourceClass::EventMethod,
    source,
    &ReceiverClass::HandlerMethod
    [, receiver = this]
);
long __hook(
    interface,
    source
);
```

### <a name="parameters"></a>매개 변수

*&SourceClass:: EventMethod*<br/>
이벤트 처리기 메서드를 후크할 이벤트 메서드에 대한 포인터입니다.

- 네이티브 c + + 이벤트: *Sourceclass* 는 이벤트 소스 클래스이 고 *eventmethod* 는 이벤트입니다.

- COM 이벤트: *Sourceclass* 는 이벤트 소스 인터페이스 이며 *eventmethod* 는 해당 메서드 중 하나입니다.

- 관리 되는 이벤트: *Sourceclass* 는 이벤트 소스 클래스이 고 *eventmethod* 는 이벤트입니다.

*interface*<br/>
*수신자*에 게 후크 되는 인터페이스 이름으로, [event_receiver](../windows/attributes/event-receiver.md) 특성의 *layout_dependent* 매개 변수가 인 COM 이벤트 수신기에만 해당 됩니다 **`true`** .

*source*<br/>
이벤트 소스의 인스턴스에 대한 포인터입니다. 에 지정 된 코드에 따라 `type` `event_receiver` *원본은* 다음 중 하나일 수 있습니다.

- 네이티브 이벤트 소스 개체 포인터입니다.

- `IUnknown`기반 포인터 (COM 원본)입니다.

- 관리되는 이벤트의 관리되는 개체 포인터입니다.

*&ReceiverClass:: HandlerMethod*<br/>
이벤트에 후크될 이벤트 처리기 메서드에 대한 포인터입니다. 처리기는 클래스의 메서드 또는 동일한에 대 한 참조로 지정 됩니다. 클래스 이름을 지정 하지 않으면는 클래스를 호출 하는 것 **`__hook`** 으로 가정 합니다.

- 네이티브 c + + 이벤트: *ReceiverClass* 는 이벤트 수신기 클래스이 고 `HandlerMethod` 는 처리기입니다.

- COM 이벤트: *ReceiverClass* 는 이벤트 수신기 인터페이스 이며 `HandlerMethod` 해당 처리기 중 하나입니다.

- 관리 되는 이벤트: *ReceiverClass* 는 이벤트 수신기 클래스이 고 `HandlerMethod` 는 처리기입니다.

*수신자*<br/>
필드 이벤트 수신기 클래스의 인스턴스에 대 한 포인터입니다. 수신기를 지정 하지 않는 경우 기본값은가 호출 되는 받는 사람 클래스 또는 구조체입니다 **`__hook`** .

## <a name="usage"></a>사용

이벤트 수신기 클래스 외부의 main을 포함하여 모든 함수 범위에서 사용할 수 있습니다.

## <a name="remarks"></a>설명

이벤트 수신기에서 내장 함수를 사용 **`__hook`** 하 여 처리기 메서드를 이벤트 메서드와 연결 하거나 후크 합니다. 이렇게 하면 소스에서 지정된 이벤트를 발생시킬 때 지정된 처리기가 호출됩니다. 여러 처리기를 단일 이벤트에 후크하거나 여러 이벤트를 단일 처리기에 후크할 수 있습니다.

에는 두 가지 형태가 있습니다 **`__hook`** . 대부분의 경우, 특히 [event_receiver](../windows/attributes/event-receiver.md) 특성의 *layout_dependent* 매개 변수가 인 COM 이벤트 수신기에 대해 첫 번째 (4 개 인수) 형식을 사용할 수 있습니다 **`false`** .

이러한 경우 메서드 중 하나에서 이벤트를 발생시키기 전에 인터페이스에서 모든 메서드를 후크할 필요는 없습니다. 이벤트를 처리하는 메서드만 후크해야 합니다. **`__hook`** *Layout_dependent* **= true**인 COM 이벤트 수신기에만의 두 번째 (인수 2 개) 형식을 사용할 수 있습니다.

**`__hook`** long 값을 반환 합니다. 0이 아닌 반환 값은 오류가 발생했음을 나타냅니다(관리되는 이벤트가 예외를 throw함).

컴파일러는 이벤트가 있는지 확인하고 이벤트 시그니처가 대리자 시그니처와 일치하는지 확인합니다.

COM 이벤트를 제외 하 고, **`__hook`** **`__unhook`** 이벤트 수신기 외부에서 호출 될 수 있습니다.

를 사용 하는 대신 **`__hook`** + = 연산자를 사용 합니다.

새 구문에서 관리 되는 이벤트를 코딩 하는 방법에 대 한 자세한 내용은 [이벤트](../extensions/event-cpp-component-extensions.md)를 참조 하세요.

> [!NOTE]
> 템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.

## <a name="example"></a>예제

[네이티브 c + +에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md) 및 샘플에 대 한 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md) 를 참조 하세요.

## <a name="see-also"></a>참고 항목

[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[이벤트 처리](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)<br/>
