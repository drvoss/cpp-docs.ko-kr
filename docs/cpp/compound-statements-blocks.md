---
title: 복합문(블록)
ms.date: 11/04/2016
f1_keywords:
- '}'
- '{'
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
ms.openlocfilehash: 60d7e88c5ccccac5a1d967a91c8a82dd954d9afc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337334"
---
# <a name="compound-statements-blocks"></a>복합문(블록)

복합 문은 중괄호({**}**)로 둘러싸인 0개 이상의 문으로 구성됩니다. 복합 문은 원하는 어느 곳에서든 사용할 수 있습니다. 복합 문은 일반적으로 "블록"이라고 합니다.

## <a name="syntax"></a>구문

```
{ [ statement-list ] }
```

## <a name="remarks"></a>설명

다음 예제에서는 복합 문을 **if** 문의 *문* 부분으로 사용합니다(구문에 대한 자세한 내용은 [if 문](../cpp/if-else-statement-cpp.md) 참조).

```cpp
if( Amount > 100 )
{
    cout << "Amount was too large to handle\n";
    Alert();
}
else
{
    Balance -= Amount;
}
```

> [!NOTE]
> 선언은 명령문이므로 선언은 *명령문 목록의*문 중 하나가 될 수 있습니다. 결과적으로 복합 문 내에 선언되었지만 정적으로 명시적 선언되지 않은 이름은 지역 범위와 개체의 수명을 갖습니다. 로컬 [범위로](../cpp/scope-visual-cpp.md) 이름 처리에 대한 자세한 내용은 범위를 참조하십시오.

## <a name="see-also"></a>참고 항목

[C++ 문 개요](../cpp/overview-of-cpp-statements.md)
