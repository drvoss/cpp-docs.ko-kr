---
title: '&lt;atomic&gt; enums'
ms.date: 11/04/2016
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
helpviewer_keywords:
- std::memory_order
ms.openlocfilehash: d8a4e9196e27933c75a32c256114e968b55678a6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834897"
---
# <a name="ltatomicgt-enums"></a>&lt;atomic&gt; enums

## <a name="memory_order-enum"></a><a name="memory_order_enum"></a> memory_order 열거형

메모리 위치에서 동기화 연산에 대한 기호 이름을 제공합니다. 이러한 연산은 하나의 스레드의 할당이 다른 스레드에 표시될 방법에 영향을 미칩니다.

```cpp
typedef enum memory_order {
    memory_order_relaxed,
    memory_order_consume,
    memory_order_acquire,
    memory_order_release,
    memory_order_acq_rel,
    memory_order_seq_cst,
} memory_order;
```

### <a name="enumeration-members"></a>열거형 멤버

|Name|설명|
|-|-|
|`memory_order_relaxed`|순서 지정할 필요가 없습니다.|
|`memory_order_consume`|load 연산이 메모리 위치에서 consume 연산처럼 작동합니다.|
|`memory_order_acquire`|load 연산이 메모리 위치에서 acquire 연산처럼 작동합니다.|
|`memory_order_release`|store 연산이 메모리 위치에서 release 연산처럼 작동합니다.|
|`memory_order_acq_rel`|`memory_order_acquire` 및 `memory_order_release`를 결합합니다.|
|`memory_order_seq_cst`|`memory_order_acquire` 및 `memory_order_release`를 결합합니다. `memory_order_seq_cst`로 표시된 메모리 액세스의 순서는 일관적이어야 합니다.|

## <a name="see-also"></a>참고 항목

[\<atomic>](../standard-library/atomic.md)
