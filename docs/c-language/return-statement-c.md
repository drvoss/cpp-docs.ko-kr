---
title: return 문 (C)
ms.date: 11/04/2016
helpviewer_keywords:
- ( ) parentheses in return statements
ms.assetid: 18cd82cf-f899-4b28-83ad-4eff353ddcb4
ms.openlocfilehash: c3975076ee65d267f3d278e20a7770e6750c06d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158387"
---
# <a name="return-statement-c"></a>return 문 (C)

`return` 문은 함수 실행을 종료하고 호출 함수로 컨트롤을 반환합니다. 호출 바로 다음 지점의 호출 함수에서 실행을 다시 시작합니다. `return` 문은 호출 함수로 값을 반환할 수도 있습니다. 자세한 내용은 [반환 형식](../c-language/return-type.md)을 참조하세요.

## <a name="syntax"></a>구문

*점프 문*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**return** *expression*<sub>opt</sub> **;**

*expression*의 값(있는 경우)이 호출 함수로 반환됩니다. *expression*을 생략하면 함수의 반환 값이 정의되지 않습니다. 식이 있는 경우 평가된 다음 함수에서 반환한 형식으로 변환됩니다. 함수가 반환 형식 `void`로 선언되는 경우 식이 포함된 `return` 문은 경고를 발생시키고 식은 계산되지 않습니다.

함수 정의에 `return` 문이 표시되지 않으면 호출된 함수의 마지막 문이 실행된 후 호출 함수에 컨트롤이 자동으로 반환됩니다. 이 경우 호출된 함수의 반환 값은 정의되지 않습니다. 반환 값이 필요하지 않은 경우 `void` 반환 형식을 포함하도록 함수를 선언합니다. 그렇지 않은 경우의 기본 반환 형식은 `int`입니다.

대부분의 프로그래머는 `return` 문의 *expression* 인수를 괄호로 묶습니다. 그러나 C에서는 괄호가 필요하지 않습니다.

이 예제에서는 `return` 문을 보여 줍니다.

```C
#include <limits.h>
#include <stdio.h>

void draw( int i, long long ll );
long long sq( int s );

int main()
{
    long long y;
    int x = INT_MAX;

    y = sq( x );
    draw( x, y );
    return x;
}

long long sq( int s )
{
    // Note that parentheses around the return expression
    // are allowed but not required here.
    return( s * (long long)s );
}

void draw( int i, long long ll )
{
    printf( "i = %d, ll = %lld\n", i, ll );
    return;
}
```

이 예제에서 `main` 함수는 `sq` 및 `draw`의 두 함수를 호출합니다. `sq` 함수는 `x * x`의 값을 `main`에 반환합니다. 여기서 반환 값은 `y`에 할당됩니다. `sq`의 반환 표현식을 둘러싼 괄호는 식의 일부분으로 평가되고 반환 명령문에 필요하지 않습니다. 반환 표현식은 반환 형식으로 변환되기 전에 평가되기 때문에 `sq`는 캐스팅을 사용하여 표현식 형식이 반환 형식이 되도록 강제 지정함으로써 예기치 않은 결과를 발생시킬 수 있는 정수 오버플로를 방지합니다. `draw` 함수는 `void` 함수로 선언됩니다. 이 매개 변수의 값을 출력한 다음에는 빈 반환 명령문이 함수를 종료하고 값을 반환하지 않습니다. 반환 값 `draw`를 할당하려고 하면 진단 메시지가 표시됩니다. 그러면 `main` 함수가 `x`의 값을 운영 체제로 반환합니다.

예를 들어 다음과 같이 출력됩니다.

```Output
i = 2147483647, ll = 4611686014132420609
```

## <a name="see-also"></a>참조

[문](../c-language/statements-c.md)
