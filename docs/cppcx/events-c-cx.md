---
title: 이벤트(C++/CX)
description: /Cx를 사용 C++하 여 Windows 런타임에서 이벤트 처리기를 만들고 사용 하는 방법입니다.
ms.date: 02/03/2020
ms.assetid: 31c8e08a-00ad-40f9-8f7e-124864aaad58
ms.openlocfilehash: b40f71b183561b52047c1f7316def3d895465d2a
ms.sourcegitcommit: 44eeb065c3148d0484de791080a3f963109744fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79509374"
---
# <a name="events-ccx"></a>이벤트(C++/CX)

Windows 런타임 형식은 이벤트를 선언 (즉, 게시) 할 수 있고, 동일한 구성 요소 또는 다른 구성 요소의 클라이언트 코드는 이벤트 *처리기* 라는 메서드를 이벤트와 연결 하 여 이러한 이벤트를 구독할 수 있습니다. 여러 이벤트 처리기를 단일 이벤트에 연결할 수 있습니다. 게시 개체에서 이벤트가 발생하면 호출되는 모든 이벤트 처리기가 발생됩니다. 이 방법으로 구독 클래스에서는 게시자가 이벤트를 발생시킬 때 적절한 사용자 지정 작업은 무엇이든 수행할 수 있습니다. 이벤트에는 모든 이벤트 처리기에서 이벤트를 구독하기 위해 필요한 서명을 지정하는 대리자 형식이 있습니다.

## <a name="consuming-events-in-windows-components"></a>Windows 구성 요소의 이벤트 사용

Windows 런타임의 많은 구성 요소가 이벤트를 노출 합니다. 예를 들어 LightSensor 개체는 센서가 새 luminescence 값을 보고하면 ReadingChanged 이벤트를 발생시킵니다. 프로그램에서 LightSensor 개체를 사용하는 경우 ReadingChanged 이벤트가 발생할 때 호출되는 메서드를 정의할 수 있습니다. 메서드는 원하는 모든 작업을 수행할 수 있습니다. 유일한 요구 사항은 해당 서명이 호출 된 대리자의 시그니처와 일치 해야 한다는 것입니다. 대리자 이벤트 처리기를 만들고 이벤트를 구독 하는 방법에 대 한 자세한 내용은 [대리자](../cppcx/delegates-c-cx.md)를 참조 하세요.

## <a name="creating-custom-events"></a>사용자 지정 이벤트 만들기

### <a name="declaration"></a>선언

ref 클래스 또는 인터페이스에서 이벤트를 선언할 수 있으며, 이 이벤트는 public, internal(public/private), public protected, protected, private protected 또는 private 액세스 가능성을 가질 수 있습니다. 이벤트를 선언하면 내부적으로 컴파일러가 두 개의 접근자 메서드(add 및 remove)를 노출하는 개체를 만듭니다. 구독 개체가 이벤트 처리기를 등록하면 이벤트 개체는 이 처리기를 컬렉션에 저장합니다. 이벤트가 발생하면 이벤트 개체는 목록의 모든 처리기를 차례로 호출합니다. 다음 예제의 이벤트와 같은 trivial 이벤트에는 암시적 백업 저장소와 암시적 `add` 및 `remove` 접근자 메서드가 있습니다. 또한 속성에 사용자 지정 `get` 및 `set` 접근자를 지정하는 방법과 동일한 방법으로 사용자 고유의 접근자를 지정할 수도 있습니다.  구현하는 클래스는 trivial 이벤트의 이벤트 구독자를 직접 순환할 수 없습니다.

다음 예제에서는 이벤트를 선언하고 발생시키는 방법을 보여 줍니다. 이벤트에는 대리자 형식이 있고 "^" 기호를 사용하여 선언되었습니다.

[!code-cpp[cx_events#01](../cppcx/codesnippet/CPP/cx_events/class1.h#01)]

### <a name="usage"></a>사용

다음 예제에서는 구독 클래스가 `+=` 연산자를 사용하여 이벤트를 구독하고 이벤트가 발생할 때 호출할 이벤트 처리기를 제공하는 방법을 보여 줍니다. 제공된 함수가 `EventTest` 네임스페이스에서 게시자 쪽에 정의된 대리자의 서명과 일치합니다.

[!code-cpp[cx_events#02](../cppcx/codesnippet/CPP/eventsupportinvs/eventclientclass.h#02)]

> [!WARNING]
> 일반적으로 순환 참조를 방지하기 위해 크게 주의하지 않는 한 이벤트 처리기에 람다 대신 명명된 함수를 사용하는 것이 좋습니다. 명명된 함수는 약한 참조로 "this" 포인터를 캡처하지만 람다는 강력한 참조로 캡처하고 순환 참조를 만듭니다. 자세한 내용은 [약한 참조 및 순환 끊기(C++/CX)](../cppcx/weak-references-and-breaking-cycles-c-cx.md)를 참조하세요.

### <a name="custom-add-and-remove-methods"></a>사용자 지정 add 및 remove 메서드

내부적으로 이벤트에는 add 메서드, remove 메서드 및 raise 메서드가 있습니다. 클라이언트 코드가 이벤트를 구독하면 add 메서드가 호출되고 전달된 대리자가 이벤트의 호출 목록에 추가됩니다. 게시 클래스는 이벤트를 호출하고 raise() 메서드가 호출되도록 하며 목록의 각 대리자가 차례로 호출됩니다. 구독자가 대리자 목록에서 자신을 제거할 수 있으며 이 경우 이벤트의 remove 메서드가 호출됩니다. 컴파일러는 코드에서 정의하지 않은 경우 이러한 메서드의 기본 버전을 제공합니다. 이를 trivial 이벤트라고 합니다. 많은 경우에 trivial 이벤트만 있으면 됩니다.

구독자 추가 또는 제거에 대한 응답으로 사용자 지정 논리를 수행해야 하는 경우 이벤트에 대한 사용자 지정 add, remove 및 raise 메서드를 지정할 수 있습니다. 예를 들어 이벤트 보고에만 사용되는 부담이 큰 개체가 있는 경우 클라이언트가 실제로 이벤트를 구독할 때 까지 개체 생성을 천천히 지연할 수 있습니다.

다음 예제에서는 이벤트에 사용자 지정 add, remove 및 raise 메서드를 추가하는 방법을 보여 줍니다.

[!code-cpp[cx_events#03](../cppcx/codesnippet/CPP/cx_events/class1.h#03)]

## <a name="removing-an-event-handler-from-the-subscriber-side"></a>구독자 측에서 이벤트 처리기 제거

드물지만, 경우에 따라서는 이전에 구독한 이벤트의 이벤트 처리기를 제거하는 것이 좋습니다. 예를 들어 다른 이벤트 처리기로 바꾸거나 보유하고 있는 일부 리소스를 제거하는 것이 좋습니다. 처리기를 제거하려면 `+=` 연산에서 반환된 EventRegistrationToken을 저장해야 합니다. 그런 다음 토큰에 `-=` 연산자를 사용하여 이벤트 처리기를 제거할 수 있습니다.  그러나 이벤트 처리기를 제거한 후에도 원래 처리기는 계속 호출될 수 있습니다. 예를 들어 이벤트 소스가 처리기 목록을 가져오고이를 호출 하기 시작 하면 경합 상태가 발생할 수 있습니다. 이 경우 이벤트 처리기가 제거 되 면 목록이 만료 됩니다. 따라서 이벤트 처리기를 제거 하려면 멤버 플래그를 만듭니다. 이벤트가 제거 되 면이를 설정 하 고, 이벤트 처리기에서 플래그를 확인 하 고, 설정 된 경우 즉시 반환 합니다. 다음 예제에서는 기본 패턴을 보여 줍니다.

[!code-cpp[cx_events#04](../cppcx/codesnippet/CPP/eventsupportinvs/eventclientclass.h#04)]

### <a name="remarks"></a>설명

여러 처리기를 동일한 이벤트와 연결할 수 있습니다. 이벤트 원본은 동일한 스레드의 모든 이벤트 처리기를 순차적으로 호출합니다. 이벤트 처리기 메서드 내에서 이벤트 수신기가 차단된 경우 이벤트 원본이 이 이벤트의 다른 이벤트 처리기를 호출하지 못하게 차단됩니다.

이벤트 원본이 이벤트 수신기에서 이벤트 처리기를 호출하는 순서는 정확하지 않으며 호출에 따라 달라질 수 있습니다.

## <a name="see-also"></a>참고 항목

[형식 시스템](../cppcx/type-system-c-cx.md)<br/>
[대리자](../cppcx/delegates-c-cx.md)<br/>
[C++/CX 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
