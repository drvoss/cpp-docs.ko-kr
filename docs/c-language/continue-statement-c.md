---
title: continue 문 (C)
ms.date: 11/04/2016
f1_keywords:
- continue
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
ms.openlocfilehash: 983775e6fe9887afa5784358ede1de9583b3afba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312565"
---
# <a name="continue-statement-c"></a>continue 문 (C)

`continue` 문은 자신이 배치되는 가장 가까운 바깥쪽 `do`, `for` 또는 `while` 문의 다음 반복으로 제어를 전달하고 `do`, `for` 또는 `while` 문 본문에서 나머지 문을 건너뜁니다.

## <a name="syntax"></a>구문

*점프 문*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**continue ;**

`do`, `for` 또는 `while` 문의 다음 반복은 다음과 같이 결정됩니다.

- `do` 또는 `while` 문 안에서 `do` 또는 `while` 문의 식을 다시 계산하여 다음 반복이 시작됩니다.

- `continue` 문 안의 `for` 문으로 인해 `for` 문의 루프 식이 계산됩니다. 그런 다음 컴파일러가 조건식을 다시 계산하고 결과에 따라 문 본문을 종결하거나 반복합니다. `for` 문과 비터미널에 대한 자세한 내용은 [for 문](../c-language/for-statement-c.md)을 참조하세요.

다음은 `continue` 문의 예제입니다.

```
while ( i-- > 0 )
{
    x = f( i );
    if ( x == 1 )
        continue;
    y += x * x;
}
```

이 예제에서 `i`가 0보다 크면 문 분문이 실행됩니다. 첫 번째 `f(i)`가 `x`에 할당되고 `x`가 1과 같으면 `continue` 문이 실행됩니다. 본문에서 나머지 문이 무시되고 루프의 테스트를 실행하여 루프 맨 위에서 실행이 다시 시작됩니다.

## <a name="see-also"></a>참조

[continue 문](../cpp/continue-statement-cpp.md)
