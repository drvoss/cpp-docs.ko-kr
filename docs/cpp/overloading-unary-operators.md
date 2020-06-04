---
title: 단항 연산자 오버로드
ms.date: 11/04/2016
helpviewer_keywords:
- unary operators [C++], plus
- increment operators [C++], overloaded
- unary operators [C++], minus
- operators [C++], unary
- redefinable unary operators [C++]
- unary operators [C++]
- pointer dereference operator overloading
- plus operator
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
ms.openlocfilehash: 971ef08c5e79f851c502ea872c541517065797c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372029"
---
# <a name="overloading-unary-operators"></a>단항 연산자 오버로드

오버로드할 수 있는 단항 연산자는 다음과 같습니다.

1. `!`(논리적[NOT)](../cpp/logical-negation-operator-exclpt.md)

1. `&`[(주소-의)](../cpp/address-of-operator-amp.md)

1. `~`(하나의[보완)](../cpp/one-s-complement-operator-tilde.md)

1. `*`(포인터[디레퍼런스)](../cpp/indirection-operator-star.md)

1. `+`[(unary plus)](../cpp/additive-operators-plus-and.md)

1. `-`[(부정)](../cpp/additive-operators-plus-and.md)

1. `++`[(증분)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

1. `--`[(감소)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

1. conversion operators

접미사 증분 및 감소 연산자`++` `--`(및) 는 [증분 및 감소로](../cpp/increment-and-decrement-operator-overloading-cpp.md)별도로 처리됩니다.

변환 연산자는 별도의 항목에서도 설명합니다. [사용자 정의 형식 변환을](../cpp/user-defined-type-conversions-cpp.md)참조하십시오.

다음 규칙은 다른 모든 단항 연산자에 적용됩니다. 단항 연산자 함수를 비정적 멤버로 선언하려면 해당 함수를 다음 형식으로 선언해야 합니다.

> *ret 형* **연산자** *op* **()**

*ret-type은* 반환 유형이며 *op은* 이전 표에 나열된 연산자 중 하나입니다.

단항 연산자 함수를 전역 함수로 선언하려면 해당 함수를 다음 형식으로 선언해야 합니다.

> *ret 형* **연산자** *op* *(아르그)* **)** **(**

*ret-type* 및 *op는* 멤버 연산자 함수에 대해 설명된 대로 이고 *arg는* 작동할 클래스 형식의 인수입니다.

> [!NOTE]
> 단항 연산자의 반환 형식에 대한 제한은 없습니다. 예를 들어 논리 NOT(`!`)에서 정수 계열 값을 반환하는 것이 적합하지만 이는 적용되지 않습니다.

## <a name="see-also"></a>참고 항목

[연산자 오버로드](../cpp/operator-overloading.md)
