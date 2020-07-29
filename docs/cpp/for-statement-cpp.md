---
title: for 문 (C++)
description: Microsoft Visual Studio c + +의 표준 c + +에 대 한 참조입니다.
f1_keywords:
- for_cpp
ms.date: 04/14/2020
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: 16486fd58a9b3fec750ebef6ec6647f9d92bca3b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231184"
---
# <a name="for-statement-c"></a>for 문 (C++)

조건이 false가 될 때까지 문을 반복적으로 실행합니다. 범위 기반 for 문에 대 한 자세한 내용은 [범위 기반 For 문 (c + +)](../cpp/range-based-for-statement-cpp.md)을 참조 하세요.

## <a name="syntax"></a>구문

> **`for (`***init 식* **`;`** *조건-식* **`;`** *루프 식***`)`**\
> &nbsp;&nbsp;&nbsp;&nbsp;_선언문_**`;`**

## <a name="remarks"></a>설명

문을 사용 **`for`** 하 여 지정 된 횟수 만큼 실행 해야 하는 루프를 생성 합니다.

**`for`** 문은 다음 표와 같이 세 가지 선택적 부분으로 구성 됩니다.

### <a name="for-loop-elements"></a>루프 요소에 대해

|구문 이름|실행 시기|설명|
|-----------------|-------------------|-----------------|
|`init-expression`|문의 다른 요소 앞 **`for`** 에 `init-expression` 는 한 번만 실행 됩니다. 그런 다음 `cond-expression`으로 제어가 전달됩니다.|루프 인덱스를 초기화하는 데 자주 사용됩니다. 식 또는 선언을 포함할 수 있습니다.|
|`cond-expression`|첫 번째 반복을 포함한 `statement`의 각 반복을 실행하기 전에 `statement`는 `cond-expression`이 true(0이 아님)로 평가될 때만 실행됩니다.|정수 형식으로 명확한 변환을 하는 정수 형식 또는 클래스 형식으로 평가되는 식입니다. 일반적으로 루프 종료 기준을 테스트하는 데 사용됩니다.|
|`loop-expression`|`statement`의 각 반복 끝에서 `loop-expression`이 실행된 후, `cond-expression`이 평가됩니다.|일반적으로 루프 인덱스 증가에 사용됩니다.|

다음 예에서는 문을 사용 하는 다양 한 방법을 보여 줍니다 **`for`** .

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

`init-expression` 및 `loop-expression`은 쉼표로 구분된 여러 개의 문을 포함할 수 있습니다. 예를 들면 다음과 같습니다.

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

루프는 **`for`** 내의 [break](../cpp/break-statement-cpp.md), [return](../cpp/return-statement-cpp.md)또는 [goto](../cpp/goto-statement-cpp.md) (루프 외부에 있는 레이블이 지정 된 문 **`for`** )가 실행 될 때 종료 `statement` 됩니다. 루프의 [continue](../cpp/continue-statement-cpp.md) 문은 **`for`** 현재 반복만 종료 합니다.

을 `cond-expression` 생략 하면로 간주 되 **`true`** 고, **`for`** **`break`** 또는 내에서 루프가 종료 되지 않습니다 **`return`** **`goto`** `statement` .

문의 세 필드는 **`for`** 일반적으로 초기화에 사용 되 고 종료를 테스트 하는 데 사용 되지만 이러한 사용으로 제한 되지 않습니다. 예를 들어, 다음 코드는 0부터 4까지의 숫자를 인쇄합니다. 이 경우 `statement`은 null 문입니다.

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

C + + 표준에서는 루프에서 선언 된 변수가 **`for`** 루프가 끝난 후 범위를 벗어나는 것으로 **`for`** 나타납니다. 예를 들면 다음과 같습니다.

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

기본적으로 [/ze](../build/reference/za-ze-disable-language-extensions.md)에서 루프에 선언 된 변수는 **`for`** **`for`** 루프의 바깥쪽 범위가 종료 될 때까지 범위 내에 남아 있습니다.

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 는를 지정할 필요 없이 루프에 대해 선언 된 변수의 표준 동작을 사용 하도록 설정 `/Za` 합니다.

다음과 같이 루프의 범위 차이를 사용 하 여 **`for`** 변수를 다시 선언할 수도 있습니다 `/Ze` .

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

이 동작은 루프에서 선언 된 변수의 표준 동작을 더욱 비슷하게 모방 하므로 루프에서 선언 된 변수가 루프를 **`for`** **`for`** 완료 한 후 범위를 벗어날 수 있습니다. 변수가 루프에서 선언 되 면 **`for`** 컴파일러는 내부적으로 **`for`** 루프의 바깥쪽 범위에서 지역 변수로이를 승격 합니다. 이름이 같은 지역 변수가 이미 있는 경우에도 승격 됩니다.

## <a name="see-also"></a>참고 항목

[반복 문](../cpp/iteration-statements-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[while 문(C++)](../cpp/while-statement-cpp.md)<br/>
[do-while 문(C++)](../cpp/do-while-statement-cpp.md)<br/>
[범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)
