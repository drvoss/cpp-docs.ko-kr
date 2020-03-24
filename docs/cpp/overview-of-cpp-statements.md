---
title: C++문 개요
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
ms.openlocfilehash: 9aba5deddca6fbf480cd9d573606b16b7ab047db
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188430"
---
# <a name="overview-of-c-statements"></a>C++문 개요

C++ 문은 식 문, 선택 문, 반복 문 또는 점프 문이 해당 시퀀스를 특정하게 수정하는 경우를 제외하고 순차적으로 실행됩니다.

문은 다음과 같은 형식일 수 있습니다.

```
labeled-statement
expression-statement
compound-statement
selection-statement
iteration-statement
jump-statement
declaration-statement
try-throw-catch
```

대부분의 경우 C++ 문 구문은 ANSI C의 구문과 동일 합니다. 둘 간의 주요 차이점은 C에서 선언은 블록의 시작 부분에만 허용 된다는 것입니다. C++ 이 제한을 효과적으로 제거 하는 *선언문*을 추가 합니다. 이에 따라 미리 계산된 초기화 값이 계산될 수 있는 프로그램의 지점에 변수를 도입할 수 있습니다.

블록 내에 변수를 선언하면 해당 변수의 범위와 수명을 정확하게 제어할 수 있습니다.

문에 대한 항목에서는 다음과 같은 C++ 키워드에 대해 설명합니다.

|||||
|-|-|-|-|
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|
|[case](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[try](../cpp/try-throw-and-catch-statements-cpp.md)|
|[catch](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||
|[do](../cpp/do-while-statement-cpp.md)|[if](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||

## <a name="see-also"></a>참고 항목

[문](../cpp/statements-cpp.md)
