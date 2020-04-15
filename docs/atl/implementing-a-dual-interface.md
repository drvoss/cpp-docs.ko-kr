---
title: 이중 인터페이스(ATL) 구현
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: a85597adad045bee3edb5cc3ed63c72a22fa08fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319462"
---
# <a name="implementing-a-dual-interface"></a>이중 인터페이스 구현

이중 인터페이스에서 메서드의 기본 구현을 제공하는 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 클래스를 사용하여 이중 인터페이스를 `IDispatch` 구현할 수 있습니다. 자세한 내용은 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)을 참조하십시오.

이 클래스를 사용하려면 다음을 수행하십시오.

- 형식 라이브러리에서 이중 인터페이스를 정의합니다.

- 의 전문화에서 클래스를 `IDispatchImpl` 파생 (템플릿 인수로 인터페이스 및 형식 라이브러리에 대 한 정보를 전달).

- COM 맵에 항목(또는 항목)을 추가하여 을 `QueryInterface`통해 이중 인터페이스를 노출합니다.

- 클래스에서 인터페이스의 vtable 부분을 구현합니다.

- 인터페이스 정의가 포함된 형식 라이브러리를 런타임에 개체에서 사용할 수 있는지 확인합니다.

## <a name="atl-simple-object-wizard"></a>ATL 단순 개체 마법사

이를 구현하기 위해 새 인터페이스와 새 클래스를 만들려면 [ATL 클래스 추가 대화 상자](../ide/add-class-dialog-box.md)및 [ATL 단순 개체 마법사를](../atl/reference/atl-simple-object-wizard.md)사용할 수 있습니다.

## <a name="implement-interface-wizard"></a>인터페이스 구현 마법사

기존 인터페이스가 있는 경우 인터페이스 [구현 마법사를](../atl/reference/adding-a-new-interface-in-an-atl-project.md) 사용하여 기존 클래스에 필요한 기본 클래스, COM 맵 항목 및 스켈레톤 메서드 구현을 추가할 수 있습니다.

> [!NOTE]
> 형식 라이브러리의 주 및 부 버전 번호가 기본 클래스에 템플릿 인수로 전달되도록 생성된 `IDispatchImpl` 기본 클래스를 조정해야 할 수 있습니다. 인터페이스 구현 마법사는 형식 라이브러리 버전 번호를 확인하지 않습니다.

## <a name="implementing-idispatch"></a>IDispatch 구현

해당 이중 `IDispatchImpl` 인터페이스를 설명하는 형식 라이브러리가 있는 경우 COM 맵에 적절한 항목을 지정하거나(COM_INTERFACE_ENTRY2 또는 [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) 매크로사용)를 지정하여 기본 클래스를 사용하여 dispinterface의 구현을 제공할 수 있습니다. [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) 예를 들어 이러한 방식으로 `IDispatch` 인터페이스를 구현하는 것이 일반적입니다. ATL 단순 개체 마법사 와 인터페이스 구현 마법사는 `IDispatch` 모두 이러한 방식으로 구현하려는 것으로 가정하므로 맵에 적절한 항목을 추가합니다.

> [!NOTE]
> ATL은 호환되는 이중 인터페이스의 정의를 포함하는 형식 라이브러리를 필요로 하지 않고 디스프인터페이스를 구현하는 데 도움이 되는 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 및 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 클래스를 제공합니다.

## <a name="see-also"></a>참고 항목

[듀얼 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)
