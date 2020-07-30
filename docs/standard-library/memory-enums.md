---
title: '&lt;memory&gt; 열거형'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 507628628fcf8bbf8993ce5beb1e02c28ff82147
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222253"
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; 열거형

## <a name="pointer_safety-enumeration"></a><a name="pointer_safety"></a>pointer_safety 열거형

`get_pointer_safety`에서 반환할 수 있는 값의 열거형입니다.

```cpp
class pointer_safety {
   relaxed,
   preferred,
   strict
};
```

### <a name="remarks"></a>설명

범위는 **`enum`** 에서 반환 될 수 있는 값을 정의 합니다 `get_pointer_safety()` .

`relaxed` - 안전하게 파생되지 않은 포인터(선언되거나 할당된 개체에 대한 포인터)를 안전하게 파생된 포인터와 동일하게 처리합니다.

`preferred` - 이전 설명과 같지만 안전하게 파생되지 않은 포인터를 역참조해서는 안 됩니다.

`strict` - 안전하게 파생되지 않은 포인터를 안전하게 파생된 포인터와 다르게 처리할 수 있습니다.
