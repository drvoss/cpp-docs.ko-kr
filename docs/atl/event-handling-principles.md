---
title: 이벤트 처리 원칙(ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
ms.openlocfilehash: 2e810853e7c81f279039e0b3dfda5199d38deee2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319572"
---
# <a name="event-handling-principles"></a>이벤트 처리 원칙

모든 이벤트 처리에는 세 가지 단계가 공통적입니다. 다음을 수행해야 합니다.

- 개체에 이벤트 인터페이스를 구현합니다.

- 개체가 이벤트를 수신하려고 하는 이벤트 소스에 알부를 수 있습니다.

- 개체가 더 이상 이벤트를 수신할 필요가 없는 경우 이벤트 소스에 대한 조언을 해제합니다.

이벤트 인터페이스를 구현하는 방법은 해당 형식에 따라 다릅니다. 이벤트 인터페이스는 vtable, 이중 또는 dispinterface일 수 있습니다. 인터페이스를 정의하는 것은 이벤트 소스의 디자이너에게 달려 있습니다. 해당 인터페이스를 구현하는 것은 회원님의 말입니다.

> [!NOTE]
> 이벤트 인터페이스가 이중이 될 수 없는 기술적인 이유는 없지만 이중 인터페이스 사용을 피해야 하는 여러 가지 좋은 디자인 이유가 있습니다. 그러나 이것은 이벤트 *소스의*디자이너/구현자가 결정한 것입니다. 이벤트의 `sink`관점에서 작업하기 때문에 이중 이벤트 인터페이스를 구현할 수 있는 선택의 여지가 없을 수도 있습니다. 이중 인터페이스에 대한 자세한 내용은 [듀얼 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)을 참조하십시오.

이벤트 소스를 조언하는 것은 다음 세 단계로 나눌 수 있습니다.

- [IConnectionPointContainer에](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)대한 소스 개체를 쿼리합니다.

- [IConnectionPointContainer 호출::FindConnectionPoint](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) 관심 있는 이벤트 인터페이스의 IID를 전달 합니다. 성공하면 연결 지점 개체에서 [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) 인터페이스가 반환됩니다.

- [IConnectionPoint::이벤트](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) 싱크를 `IUnknown` 통과하는 것이 좋습니다. 성공하면 연결을 나타내는 `DWORD` 쿠키가 반환됩니다.

이벤트 수신에 대한 관심을 성공적으로 등록하면 소스 개체에서 발생한 이벤트에 따라 개체의 이벤트 인터페이스의 메서드가 호출됩니다. 이벤트를 더 이상 수신할 필요가 없는 경우 [IConnectionPoint::unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise)를 통해 쿠키를 연결 지점으로 다시 전달할 수 있습니다. 이렇게 하면 소스와 싱크 사이의 연결이 끊어집니다.

이벤트를 처리할 때 참조 주기를 방지하지 않도록 주의하십시오.

## <a name="see-also"></a>참고 항목

[이벤트 처리](../atl/event-handling-and-atl.md)
