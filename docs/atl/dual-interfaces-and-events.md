---
title: 듀얼 인터페이스 및 이벤트
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: 4ce5048c25bd55feb0f1eb20fc04ec6bfeead746
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319613"
---
# <a name="dual-interfaces-and-events"></a>듀얼 인터페이스 및 이벤트

이벤트 인터페이스를 이중으로 디자인할 수 있지만 그렇게 하지 않는 데는 여러 가지 좋은 디자인 이유가 있습니다. 근본적인 이유는 이벤트의 소스가 vtable을 통해 또는 둘 다 `Invoke`를 통해 이벤트를 발생하기 때문입니다. 이벤트 소스가 이벤트를 직접 vtable 메서드 호출로 `IDispatch` 발생하면 메서드가 사용되지 않으며 인터페이스가 순수한 vtable 인터페이스여야 합니다. 이벤트 소스가 이벤트를 호출로 발생하면 `Invoke`vtable 메서드가 사용되지 않으며 인터페이스가 디스피인터페이스여야 한다는 것이 분명합니다. 이벤트 인터페이스를 이중으로 정의하는 경우 클라이언트가 사용되지 않는 인터페이스의 일부를 구현하도록 요구할 수 있습니다.

> [!NOTE]
> 이 인수는 일반적으로 이중 인터페이스에는 적용되지 않습니다. 구현 관점에서 Duals는 다양한 클라이언트가 액세스할 수 있는 인터페이스를 빠르고 편리하며 잘 지원하는 방법입니다.

이중 이벤트 인터페이스를 피해야 하는 추가 이유가 있습니다. 비주얼 베이직이나 인터넷 익스플로러가 지원하지 않습니다.

## <a name="see-also"></a>참고 항목

[듀얼 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)
