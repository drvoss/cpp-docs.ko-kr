---
title: 토큰 계산
ms.date: 11/04/2016
helpviewer_keywords:
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
ms.openlocfilehash: 15775ca9a7ada46aaf4e53ae952cd67e95bbf8d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234025"
---
# <a name="evaluation-of-tokens"></a>토큰 계산

컴파일러는 토큰을 해석할 때 다음 토큰으로 이동하기 전에 단일 토큰에 최대한 많은 문자를 포함합니다. 이러한 동작 때문에 토큰을 공백으로 적절하게 구분하지 않으면 컴파일러가 토큰을 올바르게 해석하지 못할 수 있습니다. 다음 식을 살펴보십시오.

```
i+++j
```

이 예제에서는 컴파일러가 더하기 기호 3개에서 먼저 가능한 가장 긴 연산자(`++`)를 만든 다음 나머지 더하기 기호를 더하기 연산자(`+`)로 처리합니다. 따라서 식은 `(i++) + (j)`가 아닌 `(i) + (++j)`로 해석됩니다. 이 경우 및 이와 유사한 경우에서는 모호성을 피하고 식이 올바르게 계산되도록 하려면 공백과 괄호를 사용합니다.

**Microsoft 전용**

C 컴파일러는 Ctrl+Z 문자를 파일 끝 표시기로 처리합니다. Ctrl+Z 다음의 모든 텍스트는 무시됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[C 토큰](../c-language/c-tokens.md)
