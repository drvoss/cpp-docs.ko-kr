---
title: 기준 계수(ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
ms.openlocfilehash: 095f0ad2ecc1e1a870077899d61a3c594f8cc95f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321738"
---
# <a name="reference-counting"></a>참조 계수

COM 자체는 개체가 더 이상 사용되지 않는다고 생각할 때 메모리에서 개체를 자동으로 제거하려고 시도하지 않습니다. 대신 개체 프로그래머는 사용하지 않는 개체를 제거해야 합니다. 프로그래머는 참조 수에 따라 개체를 제거할 수 있는지 여부를 결정합니다.

COM은 `IUnknown` 메서드인 [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) 및 [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)를 사용하여 개체의 인터페이스 의 참조 수를 관리합니다. 이러한 메서드를 호출하는 일반적인 규칙은 다음과 같습니다.

- 클라이언트가 인터페이스 포인터를 `AddRef` 받을 때마다 인터페이스에서 호출해야 합니다.

- 클라이언트가 인터페이스 포인터를 사용하여 완료될 `Release`때마다 을 호출해야 합니다.

간단한 구현에서는 각 `AddRef` 호출이 증분되고 `Release` 각 호출은 개체 내부의 카운터 변수를 감소시입니다. 카운트가 0으로 돌아오면 인터페이스에 더 이상 사용자가 없으며 메모리에서 자신을 제거할 수 있습니다.

개별 인터페이스가 아닌 개체에 대한 각 참조가 계산되도록 참조 카운트를 구현할 수도 있습니다. 이 경우 각 `AddRef` `Release` 및 호출 대리자를 개체의 중앙 `Release` 구현에 호출 하 고 참조 수가 0에 도달 하면 전체 개체를 해제 합니다.

> [!NOTE]
> -derive된 개체가 `CComObject` **새** 연산자를 사용하여 생성되면 참조 수는 0입니다. 따라서 `CComObject`-derived `AddRef` 개체를 성공적으로 만든 후 호출해야 합니다.


## <a name="see-also"></a>참고 항목

[COM 소개](../atl/introduction-to-com.md)<br/>
[참조 계수를 통해 개체 수명 관리](/windows/win32/com/managing-object-lifetimes-through-reference-counting)
