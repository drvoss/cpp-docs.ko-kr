---
title: __unhook
ms.date: 11/04/2016
f1_keywords:
- __unhook
- __unhook_cpp
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
ms.openlocfilehash: 221ffc30a9b8a40c44f8009dfa511b72aa160e01
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337560"
---
# <a name="__unhook"></a>__unhook

처리기 메서드를 이벤트에서 분리합니다.

## <a name="syntax"></a>구문

```cpp
long  __unhook(
   &SourceClass::EventMethod,
   source,
   &ReceiverClass::HandlerMethod
   [, receiver = this]
);
long  __unhook(
   interface,
   source
);
long  __unhook(
   source
);
```

#### <a name="parameters"></a>매개 변수

**&***SourceClass* `::` *EventMethod* 이벤트 처리기 메서드를 해제 하는 이벤트 메서드에 대 한 포인터:

- 네이티브 C++ 이벤트: *SourceClass는* 이벤트 소스 클래스이며 *EventMethod는* 이벤트입니다.

- COM 이벤트: *SourceClass는* 이벤트 소스 인터페이스이며 *EventMethod는* 해당 메서드 중 하나입니다.

- 관리되는 이벤트: *SourceClass는* 이벤트 소스 클래스이고 *EventMethod는* 이벤트입니다.

*interface(인터페이스)*<br/>
[event_receiver](../windows/attributes/event-receiver.md) 특성의 *layout_dependent* 매개 변수가 **true인**COM 이벤트 수신기에 대해서만 *수신기에서*연결 해제되는 인터페이스 이름입니다.

*소스*<br/>
이벤트 소스의 인스턴스에 대한 포인터입니다. `event_receiver` *소스에* 지정된 `type` 코드에 따라 다음 중 하나가 될 수 있습니다.

- 네이티브 이벤트 소스 개체 포인터입니다.

- `IUnknown`-기반 포인터(COM 소스)입니다.

- 관리되는 이벤트의 관리되는 개체 포인터입니다.

**&***ReceiverClass* `::` `HandlerMethod` 이벤트에서 후크 해제할 이벤트 처리기 메서드에 대한 포인터입니다. 처리기는 클래스의 메서드 또는 동일한 참조로 지정됩니다. 클래스 이름을 지정하지 않으면 **__unhook** 클래스가 호출되는 것으로 가정합니다.

- 네이티브 C++ 이벤트: *ReceiverClass는* 이벤트 `HandlerMethod` 수신기 클래스이며 처리기입니다.

- COM 이벤트: *ReceiverClass는* 이벤트 `HandlerMethod` 수신기 인터페이스이며 처리기 중 하나입니다.

- 관리되는 이벤트: *ReceiverClass는* 이벤트 `HandlerMethod` 수신기 클래스이며 처리기입니다.

*수신기(선택*사항) 이벤트 수신기 클래스의 인스턴스에 대한 포인터입니다. 수신기를 지정하지 않으면 기본값은 **__unhook** 호출되는 수신기 클래스 또는 구조입니다.

## <a name="usage"></a>사용

이벤트 수신기 클래스 외부의 main을 포함하여 모든 함수 범위에서 사용할 수 있습니다.

## <a name="remarks"></a>설명

이벤트 수신기에서 **__unhook** 내장 함수를 사용하여 이벤트 메서드에서 처리기 메서드를 분리하거나 "해제"합니다.

**__unhook**세 가지 형태가 있습니다. 대부분 첫 번째(인수 4개) 형식을 사용할 수 있습니다. COM 이벤트 수신기에 대해서만 두 번째(2인수) 형식의 **__unhook** 사용할 수 있습니다. 이렇게 하면 전체 이벤트 인터페이스가 연결 해제됩니다. 세 번째(인수 1개) 형식을 사용하여 지정된 소스에서 모든 대리자를 언후크할 수 있습니다.

0이 아닌 반환 값은 예외가 발생했음을 나타냅니다(관리되는 이벤트가 예외를 throw함).

아직 연결되지 않은 이벤트 및 이벤트 처리기에서 **__unhook** 호출하면 아무런 효과가 없습니다.

컴파일할 때 컴파일러는 이벤트가 있는지 확인하고 지정된 처리기를 사용하여 매개 변수 형식을 검사합니다.

COM 이벤트를 제외하고 이벤트 수신기 외부에서 **__hook** 및 **__unhook** 호출할 수 있습니다.

**__unhook** 사용하는 대안은 -= 연산을 사용하는 것입니다.

새 구문에서 관리되는 이벤트를 코딩하는 방법에 대한 자세한 내용은 [이벤트를](../extensions/event-cpp-component-extensions.md)참조하십시오.

> [!NOTE]
> 템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.

## <a name="example"></a>예제

샘플은 [네이티브 C++의 이벤트 처리](../cpp/event-handling-in-native-cpp.md) 및 [COM의 이벤트 처리를](../cpp/event-handling-in-com.md) 참조하십시오.

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__raise](../cpp/raise.md)
