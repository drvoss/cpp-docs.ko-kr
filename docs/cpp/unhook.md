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
ms.openlocfilehash: 2a259b80b941e37e0c3040ad55894c114fe4bc82
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160530"
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

**&** *Sourceclass* `::` *eventmethod* 는 이벤트 처리기 메서드를 언 후크 할 이벤트 메서드에 대 한 포인터를&합니다.

- 네이티브 C++ 이벤트: *Sourceclass* 는 이벤트 소스 클래스이 고 *eventmethod* 는 이벤트입니다.

- COM 이벤트: *Sourceclass* 는 이벤트 소스 인터페이스 이며 *eventmethod* 는 해당 메서드 중 하나입니다.

- 관리 되는 이벤트: *Sourceclass* 는 이벤트 소스 클래스이 고 *eventmethod* 는 이벤트입니다.

*interface*<br/>
[Event_receiver](../windows/attributes/event-receiver.md) 특성의 *layout_dependent* 매개 변수가 **true**인 COM 이벤트 수신기에 대해서만 *수신기*에서 언 후크 되는 인터페이스 이름입니다.

*source*<br/>
이벤트 소스의 인스턴스에 대한 포인터입니다. `event_receiver`에 지정 된 코드 `type` 따라 *원본은* 다음 중 하나일 수 있습니다.

- 네이티브 이벤트 소스 개체 포인터입니다.

- `IUnknown`기반 포인터 (COM 원본)입니다.

- 관리되는 이벤트의 관리되는 개체 포인터입니다.

**&** *ReceiverClass* `::`&이벤트에서 언 후크 이벤트 처리기 메서드에 대 한 포인터를 `HandlerMethod` 합니다. 처리기는 클래스의 메서드 또는 동일한에 대 한 참조로 지정 됩니다. 클래스 이름을 지정 하지 않는 경우 **__unhook** 는 클래스가 호출 되는 것으로 가정 합니다.

- 네이티브 C++ 이벤트: *ReceiverClass* 는 이벤트 수신기 클래스이 고 `HandlerMethod`는 처리기입니다.

- COM 이벤트: *ReceiverClass* 는 이벤트 수신기 인터페이스 이며 `HandlerMethod`는 해당 처리기 중 하나입니다.

- 관리 되는 이벤트: *ReceiverClass* 는 이벤트 수신기 클래스이 고 `HandlerMethod`는 처리기입니다.

*수신기*(선택 사항) 이벤트 수신기 클래스의 인스턴스에 대 한 포인터입니다. 수신기를 지정 하지 않는 경우 기본값은 **__unhook** 가 호출 되는 받는 사람 클래스 또는 구조체입니다.

## <a name="usage"></a>사용법

이벤트 수신기 클래스 외부의 main을 포함하여 모든 함수 범위에서 사용할 수 있습니다.

## <a name="remarks"></a>설명

이벤트 수신기에서 **__unhook** 내장 함수를 사용 하 여 이벤트 메서드에서 처리기 메서드를 분리 하거나 "언 후크" 합니다.

**__Unhook**는 세 가지 형식이 있습니다. 대부분 첫 번째(인수 4개) 형식을 사용할 수 있습니다. 두 번째 (두 인수) 형식의 **__UNHOOK** COM 이벤트 수신기에만 사용할 수 있습니다. 이렇게 하면 전체 이벤트 인터페이스를 언 후크합니다. 세 번째(인수 1개) 형식을 사용하여 지정된 소스에서 모든 대리자를 언후크할 수 있습니다.

0이 아닌 반환 값은 예외가 발생했음을 나타냅니다(관리되는 이벤트가 예외를 throw함).

아직 후크 되지 않은 이벤트 및 이벤트 처리기에서 **__unhook** 를 호출 하는 경우에는 아무런 영향을 주지 않습니다.

컴파일할 때 컴파일러는 이벤트가 있는지 확인하고 지정된 처리기를 사용하여 매개 변수 형식을 검사합니다.

COM 이벤트를 제외 하 고, **__hook** 및 **__unhook** 를 이벤트 수신기 외부에서 호출할 수 있습니다.

**__Unhook** 를 사용 하는 대신-= 연산자를 사용 합니다.

새 구문에서 관리 되는 이벤트를 코딩 하는 방법에 대 한 자세한 내용은 [이벤트](../extensions/event-cpp-component-extensions.md)를 참조 하세요.

> [!NOTE]
>  템플릿 기반 클래스 또는 구조체는 event를 포함할 수 없습니다.

## <a name="example"></a>예제

샘플은 [COM의](../cpp/event-handling-in-com.md) 네이티브 [ C++ 및 이벤트 처리에서 이벤트 처리를](../cpp/event-handling-in-native-cpp.md) 참조 하세요.

## <a name="see-also"></a>참고 항목

[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__raise](../cpp/raise.md)
