---
title: 재귀 함수
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
ms.openlocfilehash: 82f0c820ab75fda4bae83db78fa402d7a07cb7fe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232135"
---
# <a name="recursive-functions"></a>재귀 함수

C 프로그램의 모든 함수를 재귀적으로 호출할 수 있습니다. 즉, 함수가 자신을 호출할 수 있습니다. 재귀적 호출 수는 스택의 크기로 제한됩니다. 스택 크기를 설정하는 링커 옵션에 대한 자세한 내용은 [/STACK(스택 할당)](../build/reference/stack-stack-allocations.md)(/STACK) 링크 옵션을 참조하세요. 함수가 호출될 때마다 완료되지 않은 이전 호출의 값이 덮어쓰이지 않도록 새로운 스토리지가 매개 변수와 **auto** 및 **register** 변수에 대해 할당됩니다. 매개 변수는 생성된 함수의 인스턴스에 의해서만 직접 액세스될 수 있습니다. 이전 매개 변수는 함수의 다음 인스턴스에 의해 직접 액세스될 수 없습니다.

**static** 스토리지로 선언된 변수에는 재귀적 호출 시마다 새로운 스토리지가 필요하지 않습니다. 해당 스토리지는 프로그램 수명 동안 존재합니다. 이러한 변수에 대한 각 참조는 동일한 스토리지 영역에 액세스합니다.

## <a name="example"></a>예제

다음 예제에서는 재귀적 호출을 보여 줍니다.

```C
int factorial( int num );      /* Function prototype */

int main()
{
    int result, number;
    .
    .
    .
    result = factorial( number );
}

int factorial( int num )      /* Function definition */
{
    .
    .
    .
    if ( ( num > 0 ) || ( num <= 10 ) )
        return( num * factorial( num - 1 ) );
}
```

## <a name="see-also"></a>참조

[함수 호출](../c-language/function-calls.md)
