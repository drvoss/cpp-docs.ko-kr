---
title: 이벤트 처리
ms.date: 05/07/2019
helpviewer_keywords:
- event handling [C++]
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
ms.openlocfilehash: cf16ea0e6e14981f1105456a5f17d68c05a9c3fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189210"
---
# <a name="event-handling"></a>이벤트 처리

이벤트 처리는 기본적으로 COM 클래스 (C++ 일반적으로 ATL 클래스 또는 [coclass](../windows/coclass.md) 특성을 사용 하 여 com 개체를 구현 하는 클래스)에 대해 지원 됩니다. 자세한 내용은 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md)를 참조 하세요.

네이티브 C++ 클래스(COM 개체를 구현하지 않는 C++ 클래스)에 대해서도 이벤트 처리가 지원되지만 이 지원은 더 이상 사용되지 않으며 향후 릴리스에서 제거됩니다.  자세한 내용은 [Native C++에서 이벤트 처리 ](../cpp/event-handling-in-native-cpp.md)를 참조 하세요.

이벤트 처리는 단일 및 다중 스레드 사용을 지원하며 동시 다중 스레드 액세스로부터 데이터를 보호합니다. 이벤트 처리를 사용하면 이벤트 소스나 수신기 클래스에서 하위 클래스를 파생시키고 파생된 클래스에서 확장된 이벤트 소싱/수신을 지원할 수 있습니다.

Microsoft C++ 컴파일러에는 이벤트 및 이벤트 처리기를 선언 하는 특성 및 키워드가 포함 되어 있습니다. CLR 프로그램과 네이티브 C++ 프로그램에서 이벤트 특성과 키워드를 사용할 수 있습니다.

|항목|설명|
|-----------|-----------------|
|[event_source](../windows/attributes/event-source.md)|이벤트 소스를 만듭니다.|
|[event_receiver](../windows/attributes/event-receiver.md)|이벤트 수신기(싱크)를 만듭니다.|
|[__event](../cpp/event.md)|이벤트를 선언합니다.|
|[__raise](../cpp/raise.md)|이벤트의 호출 사이트를 강조합니다.|
|[__hook](../cpp/hook.md)|처리기 메서드를 이벤트와 연결합니다.|
|[__unhook](../cpp/unhook.md)|처리기 메서드를 이벤트에서 분리합니다.|

## <a name="see-also"></a>참고 항목

[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[키워드](../cpp/keywords-cpp.md)
