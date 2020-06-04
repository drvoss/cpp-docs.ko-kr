---
title: 인터페이스(ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: 56d5a010bc28257dce181ee33e0ddf74655ccd3c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319382"
---
# <a name="interfaces-atl"></a>인터페이스(ATL)

인터페이스는 개체가 외부 세계에 해당 기능을 노출하는 방법입니다. COM에서 인터페이스는 개체에 의해 구현된 함수에 대한 포인터 테이블(예: C++ vtable)입니다. 테이블은 인터페이스를 나타내며 인터페이스가 가리키는 함수는 해당 인터페이스의 메서드입니다. 개체는 원하는 만큼 인터페이스를 노출할 수 있습니다.

각 인터페이스는 기본 COM 인터페이스인 [IUnknown을](../atl/iunknown.md)기반으로 합니다. 개체에서 `IUnknown` 노출되는 다른 인터페이스에 대한 탐색을 허용하는 메서드입니다.

또한 각 인터페이스에는 고유한 인터페이스 ID(IID)가 부여됩니다. 이 고유성을 통해 인터페이스 버전 만들기를 쉽게 지원할 수 있습니다. 인터페이스의 새 버전은 단순히 새로운 IID와 함께 새로운 인터페이스입니다.

> [!NOTE]
> 표준 COM 및 OLE 인터페이스에 대한 IID는 미리 정의됩니다.

## <a name="see-also"></a>참고 항목

[COM 소개](../atl/introduction-to-com.md)<br/>
[COM 개체 및 인터페이스](/windows/win32/com/com-objects-and-interfaces)
