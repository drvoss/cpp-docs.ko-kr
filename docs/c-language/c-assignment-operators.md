---
title: C 할당 연산자
ms.date: 06/14/2018
helpviewer_keywords:
- remainder assignment operator (%=)
- '&= operator'
- bitwise-AND assignment operator
- operators [C], assignment
- operators [C], shift
- ^= operator, assignment operators
- += operator
- '>>= operator'
- '|= operator'
- division assignment operator
- subtraction operator
- right shift operators
- subtraction operator, C assignment operators
- = operator, assignment operators
- '*= operator'
- '>> operator'
- '%= operator'
- assignment operators, C
- = operator
- assignment operators
- assignment conversions
- -= operator
- multiplication assignment operator (*=)
- shift operators, right
- /= operator
- operator >>=, C assignment operators
- <<= operator
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
ms.openlocfilehash: e8ada96daaec249a05882aceae9b7d9e86b92065
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168801"
---
# <a name="c-assignment-operators"></a>C 할당 연산자

할당 연산자는 오른쪽 피연산자의 값을 왼쪽 피연산자에서 이름을 지정한 스토리지 위치에 할당합니다. 따라서 할당 연산의 왼쪽 피연산자는 수정할 수 있는 l-value이어야 합니다. 할당 후 할당 식은 왼쪽 피연산자의 값을 갖지만 l-value는 아닙니다.

## <a name="syntax"></a>구문

*assignment-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*conditional-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unary-expression* *assignment-operator* *assignment-expression*

*assignment-operator*: 다음 중 하나<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **=** **\*=** **/=** **%=** **+=** **-=** **\<\<=** **>>=** **&=** **^=** **|=**

C의 할당 연산자는 단일 연산에서 값을 변형 및 할당할 수 있습니다. C에서는 다음과 같은 할당 연산자를 제공합니다.

|연산자|연산 수행|
|--------------|-------------------------|
|**=**|단순 할당|
|**&#42;=**|곱하기 할당|
|**/=**|나누기 할당|
|**%=**|나머지 할당|
|**+=**|더하기 할당|
|**-=**|빼기 할당|
|**<\<=**|왼쪽 시프트 할당|
|**>>=**|오른쪽 시프트 할당|
|**&=**|비트 AND 할당|
|**^=**|비트 제외 OR 할당|
|**&#124;=**|비트 포함 OR 할당|

할당에서 오른쪽 값의 형식은 왼쪽 값의 형식으로 변환되고 해당 값은 할당이 발생한 후 왼쪽 피연산자에 저장됩니다. 왼쪽 피연산자는 배열, 함수 또는 상수이어서는 안 됩니다. 두 형식에 의존하는 특정 변환 경로에 대한 자세한 내용은 [형식 변환](../c-language/type-conversions-c.md)을 참조하세요.

## <a name="see-also"></a>참조

- [할당 연산자](../cpp/assignment-operators.md)
