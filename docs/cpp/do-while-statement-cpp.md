---
title: do-while 문(C++)
ms.date: 11/04/2016
f1_keywords:
- do_cpp
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
ms.openlocfilehash: d930c1884975288ff11f4d4e5cf2728e717e17d5
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326669"
---
# <a name="do-while-statement-c"></a>do-while 문(C++)

지정된 종료 조건 (*표현식(expression)*)의 값이 0이 될때까지 *명령문(statement)*을 반복 실행합니다.

## <a name="syntax"></a>구문

```
do
   statement
while ( expression ) ;
```

## <a name="remarks"></a>설명

종료 조건의 확인은 루프를 실행할 때마다 수행됩니다. 따라서 **do-while** 루프는 종료식의 결과에 따라 한번 이상 실행됩니다. **do-while**문은 [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md)나 [return](../cpp/return-statement-cpp.md)문으로 인해 반복 실행되는 도중에 루프가 종료 될 수 있습니다.

*표현식(expression)*은 산술 형식이나 포인터 형식이어야 합니다. 다음과 같이 실행됩니다.

1. 명령문들이 실행됩니다.

1. 다음으로, *표현식(expression)*이 평가됩니다. *표현식(expression)*이 false인 경우 **do-while** 문이 종료되고 프로그램 제어가 다음 문으로 넘어갑니다. *표현식(expression)*이 true(0이 아님)인 경우에는 1단계부터 과정이 반복됩니다.

## <a name="example"></a>예제

다음 샘플의 **do-while** 문을 참조하세요.

```cpp
// do_while_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        printf_s("\n%d",i++);
    } while (i < 3);
}
```

## <a name="see-also"></a>참고자료

[반복문](../cpp/iteration-statements-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[while 문(C++)](../cpp/while-statement-cpp.md)<br/>
[for 문(C++)](../cpp/for-statement-cpp.md)<br/>
[범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)
