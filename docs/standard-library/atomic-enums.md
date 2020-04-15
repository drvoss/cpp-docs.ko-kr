---
title: '&lt;atomic&gt; enums'
ms.date: 11/04/2016
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
helpviewer_keywords:
- std::memory_order
ms.openlocfilehash: f41c5b238f74e85bc18e9ff5c3aa6a0050fe27e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376916"
---
# <a name="ltatomicgt-enums"></a>&lt;atomic&gt; enums

## <a name="memory_order-enum"></a><a name="memory_order_enum"></a>memory_order 에넘

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

### <a name="enumeration-members"></a>열거 멤버

|||
|-|-|
|`memory_order_relaxed`|순서 지정할 필요가 없습니다.|
|`memory_order_consume`|load 연산이 메모리 위치에서 consume 연산처럼 작동합니다.|
|`memory_order_acquire`|load 연산이 메모리 위치에서 acquire 연산처럼 작동합니다.|
|`memory_order_release`|store 연산이 메모리 위치에서 release 연산처럼 작동합니다.|
|`memory_order_acq_rel`|`memory_order_acquire` 및 `memory_order_release`를 결합합니다.|
|`memory_order_seq_cst`|`memory_order_acquire` 및 `memory_order_release`를 결합합니다. `memory_order_seq_cst`로 표시된 메모리 액세스의 순서는 일관적이어야 합니다.|

## <a name="see-also"></a>참고 항목

[\<원자>](../standard-library/atomic.md)
