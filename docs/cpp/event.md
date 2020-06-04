---
title: __event
ms.date: 11/04/2016
f1_keywords:
- __event_cpp
- __event
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
ms.openlocfilehash: f8935408c6e9b43347d4ad6088505a461e254ae2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366298"
---
# <a name="__event"></a>__event

이벤트를 선언합니다.

## <a name="syntax"></a>구문

```
__event method-declarator;
__event __interface interface-specifier;
__event member-declarator;
```

## <a name="remarks"></a>설명

**__event** 키워드는 메서드 선언, 인터페이스 선언 또는 데이터 멤버 선언에 적용할 수 있습니다. 그러나 **__event** 키워드를 사용하여 중첩된 클래스의 구성원을 한정할 수는 없습니다.

이벤트 소스 및 수신기가 네이티브 C++ 또는 COM이거나 관리되는지(.NET Framework)에 따라 다음 구문을 이벤트로 사용할 수 있습니다.

|네이티브 C++|COM|관리됨(.NET Framework)|
|------------------|---------|--------------------------------|
|메서드|—|메서드|
|—|interface(인터페이스)|—|
|—|—|데이터 멤버(data member)|

이벤트 수신기에서 [__hook](../cpp/hook.md) 사용하여 처리기 메서드를 이벤트 메서드와 연결합니다. **__event** 키워드로 이벤트를 만든 후 이후에 해당 이벤트에 연결되는 모든 이벤트 처리기가 이벤트가 호출될 때 호출됩니다.

**__event** 메서드 선언에는 정의가 있을 수 없습니다. 정의는 암시적으로 생성되므로 이벤트 메서드를 일반 메서드인 것처럼 호출할 수 있습니다.

> [!NOTE]
> 템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.

## <a name="native-events"></a>네이티브 이벤트

네이티브 이벤트는 메서드입니다. 반환 형식은 일반적으로 HRESULT 또는 **void이지만** **열거형**을 포함한 모든 정수 형식일 수 있습니다. 이벤트가 정수 계열 반환 형식을 사용하는 경우 이벤트 처리기가 0이 아닌 값을 반환할 때 오류 조건이 정의됩니다. 이 경우 발생하는 이벤트는 다른 대리자를 호출합니다.

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

샘플 [코드는 네이티브 C++에서 이벤트 처리를](../cpp/event-handling-in-native-cpp.md) 참조하십시오.

## <a name="com-events"></a>COM 이벤트

COM 이벤트는 인터페이스입니다. 이벤트 소스 인터페이스에서 메서드의 매개 변수는 매개 *변수에* 있어야 합니다(그러나 이것은 *out* 엄격하게 적용되지 않음). *out* 매개 변수를 사용하는 경우 수준 1 경고가 발생합니다.

반환 형식은 일반적으로 HRESULT 또는 **void이지만** **열거형**을 포함한 모든 정수 형식일 수 있습니다. 이벤트가 정수 계열 반환 형식을 사용하고 이벤트 처리기가 0이 아닌 값을 반환하는 경우는 오류 조건이며 이 경우 발생하는 이벤트가 다른 대리자에 대한 호출을 중단합니다. 컴파일러는 생성된 IDL의 [소스로](../windows/attributes/source-cpp.md) 이벤트 소스 인터페이스를 자동으로 표시합니다.

[__interface](../cpp/interface.md) 키워드는 COM 이벤트 소스에 **__event** 후 항상 필요합니다.

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

샘플 코드는 [COM의 이벤트 처리를](../cpp/event-handling-in-com.md) 참조하십시오.

## <a name="managed-events"></a>관리되는 이벤트

새 구문의 코딩 이벤트에 대한 자세한 내용은 [이벤트를](../extensions/event-cpp-component-extensions.md)참조하십시오.

관리되는 이벤트는 데이터 멤버 또는 메서드입니다. 이벤트와 함께 사용할 경우 대리자의 반환 형식은 [공통 언어 사양을](/dotnet/standard/language-independence-and-language-independent-components)준수해야 합니다. 이벤트 처리기의 반환 형식은 대리자의 반환 형식과 일치해야 합니다. 대리자에 대한 자세한 내용은 [대리자 및 이벤트를](../dotnet/delegates-and-events.md)참조하십시오. 관리되는 이벤트가 데이터 멤버인 경우 그 형식은 대리자에 대한 포인터여야 합니다.

.NET Framework에서 데이터 멤버를 메서드(즉, 해당 대리자의 `Invoke` 메서드) 자체인 것처럼 취급할 수 있습니다. 관리되는 이벤트 데이터 멤버를 선언하기 위한 대리자 형식을 미리 정의해야 합니다. 반면에 관리되는 이벤트 메서드는 해당 관리되는 대리자(이미 정의되지 않은 경우)를 암시적으로 정의합니다. 예를 들어 `OnClick`과 같은 이벤트 값을 다음과 같이 이벤트로 선언할 수 있습니다.

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

관리되는 이벤트를 암시적으로 선언할 때 이벤트 처리기가 추가되거나 제거되는 경우 호출될 add 및 remove 접근자를 지정할 수 있습니다. 클래스 외부에서 이벤트를 호출하는(발생시키는) 메서드를 정의할 수도 있습니다.

## <a name="example-native-events"></a>예제: 네이티브 이벤트

```cpp
// EventHandling_Native_Event.cpp
// compile with: /c
[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};
```

## <a name="example-com-events"></a>예제: COM 이벤트

```cpp
// EventHandling_COM_Event.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT MyEvent();
};
[ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]
class CSource : public IEventSource {
public:
   __event __interface IEventSource;
   HRESULT FireEvent() {
      __raise MyEvent();
      return S_OK;
   }
};
```

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)<br/>
[이벤트 처리](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)
