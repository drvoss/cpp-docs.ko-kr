---
title: for 문 (C++)
description: Microsoft 비주얼 스튜디오 C++의 문에 대한 표준 C++를 참조하십시오.
f1_keywords:
- for_cpp
ms.date: 04/14/2020
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: 92f7ae4b1f2fbaaf710cd5a8739b78cb98a0accb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375391"
---
# <a name="for-statement-c"></a>for 문 (C++)

조건이 false가 될 때까지 문을 반복적으로 실행합니다. 문범위에 대한 범위 기반에 대한 자세한 내용은 [문(C++)에 대한 범위 기반](../cpp/range-based-for-statement-cpp.md)을 참조하십시오.

## <a name="syntax"></a>구문

> **`for (`***init 식* **`;`** *cond 식* **`;`** *루프 식***`)`**\
> &nbsp;&nbsp;&nbsp;&nbsp;_문을_**`;`**

## <a name="remarks"></a>설명

**for** 문을 사용하여 지정된 횟수를 실행해야 하는 루프를 생성합니다.

**for** 문은 다음 표와 같이 세 가지 선택적 부분으로 구성됩니다.

### <a name="for-loop-elements"></a>루프 요소에 대해

|구문 이름|실행 시기|Description|
|-----------------|-------------------|-----------------|
|`init-expression`|**for 문(for)의** 다른 `init-expression` 요소 이전에는 한 번만 실행됩니다. 그런 다음 `cond-expression`으로 제어가 전달됩니다.|루프 인덱스를 초기화하는 데 자주 사용됩니다. 식 또는 선언을 포함할 수 있습니다.|
|`cond-expression`|첫 번째 반복을 포함한 `statement`의 각 반복을 실행하기 전에 `statement`는 `cond-expression`이 true(0이 아님)로 평가될 때만 실행됩니다.|정수 형식으로 명확한 변환을 하는 정수 형식 또는 클래스 형식으로 평가되는 식입니다. 일반적으로 루프 종료 기준을 테스트하는 데 사용됩니다.|
|`loop-expression`|`statement`의 각 반복 끝에서 `loop-expression`이 실행된 후, `cond-expression`이 평가됩니다.|일반적으로 루프 인덱스 증가에 사용됩니다.|

다음 예제는 **for** 문을 사용하는 여러 가지 방법을 보여 준다.

```cpp
#include <iostream>
using namespace std;

int main() {
    // The counter variable can be declared in the init-expression.
    for (int i = 0; i < 2; i++ ){
       cout << i;
    }
    // Output: 01
    // The counter variable can be declared outside the for loop.
    int i;
    for (i = 0; i < 2; i++){
        cout << i;
    }
    // Output: 01
    // These for loops are the equivalent of a while loop.
    i = 0;
    while (i < 2){
        cout << i++;
    }
}
    // Output: 012
```

`init-expression` 및 `loop-expression`은 쉼표로 구분된 여러 개의 문을 포함할 수 있습니다. 다음은 그 예입니다.

```cpp
#include <iostream>
using namespace std;

int main(){
    int i, j;
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {
        cout << "i + j = " << (i + j) << '\n';
    }
}
    // Output:
    i + j = 15
    i + j = 17
    i + j = 19
```

`loop-expression`은 증가 또는 감소하거나 다른 방식으로 수정될 수 있습니다.

```cpp
#include <iostream>
using namespace std;

int main(){
for (int i = 10; i > 0; i--) {
        cout << i << ' ';
    }
    // Output: 10 9 8 7 6 5 4 3 2 1
    for (int i = 10; i < 20; i = i+2) {
        cout << i << ' ';
    }
    // Output: 10 12 14 16 18
```

**for** 루프는 내에서 `statement` [break,](../cpp/break-statement-cpp.md) [return](../cpp/return-statement-cpp.md)또는 [goto(for](../cpp/goto-statement-cpp.md) 루프 외부의 레이블이 있는 문)가 실행될 때 종료됩니다. **for** **for** 루프의 [continue](../cpp/continue-statement-cpp.md) 문은 현재 반복만 종료합니다.

생략된 경우 `cond-expression` 이 루프가 `true`고려되고 **for** 루프가 **중단,** **반환**또는 **goto** `statement`내에서 종료되지 않습니다.

**for** 문의 세 필드는 일반적으로 초기화, 종료 테스트 및 증분에 사용되지만 이러한 용도로 제한되지는 않습니다. 예를 들어, 다음 코드는 0부터 4까지의 숫자를 인쇄합니다. 이 경우 `statement`은 null 문입니다.

**for** 문의 세 필드는 일반적으로 초기화, 종료 테스트 및 증가에 사용되지만 이러한 용도로만 제한되지 않습니다. 예를 들어, 다음 코드는 0에서 4까지의 숫자를 출력합니다. 이 경우 `statement`는 null 문입니다.

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i;
    for( i = 0; i < 5; cout << i << '\n', i++){
        ;
    }
}
```

## <a name="for-loops-and-the-c-standard"></a>루프와 C++ 표준에 대해

C++ 표준은 **for** 루프에서 선언된 변수가 **for** 루프가 끝난 후 범위를 벗어나야 한다고 말합니다. 다음은 그 예입니다.

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

기본적으로 [/Ze](../build/reference/za-ze-disable-language-extensions.md)에서 **for** 루프에 선언된 변수는 **for** 루프의 둘러싸는 범위가 끝날 때까지 범위에 남아 있습니다.

[/Zc:forScope를](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 사용하면 을 지정할 `/Za`필요 없이 for 루프에 대해 선언된 변수의 표준 동작을 사용할 수 있습니다.
/ Zc : forScope는 `/Za`를 지정할 필요없이 for 루프에 선언된 변수의 표준 동작을 가능하게 합니다.

**for** 루프의 범위 차이를 사용하여 다음과 `/Ze` 같이 변수를 다시 선언할 수도 있습니다.

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

이 동작은 **for** 루프에서 선언된 변수의 표준 동작을 더 가깝게 모방하므로 **루프가** 완료된 후 for 루프에서 선언된 변수가 범위를 벗어나도록 합니다. **for** 루프에서 변수가 선언되면 컴파일러는 **for** 루프의 둘러싸는 범위의 로컬 변수로 내부적으로 변수를 승격합니다. 이름이 같은 로컬 변수가 이미 있는 경우에도 승격됩니다.

## <a name="see-also"></a>참고 항목

[반복 문](../cpp/iteration-statements-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[while 문(C++)](../cpp/while-statement-cpp.md)<br/>
[do-while 문(C++)](../cpp/do-while-statement-cpp.md)<br/>
[범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)
