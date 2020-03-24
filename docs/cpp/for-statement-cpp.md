---
title: for 문 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: e3dfdb45bdf8a508eca9d29e90b3f7c05e7b147d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179915"
---
# <a name="for-statement-c"></a>for 문 (C++)

조건이 false가 될 때까지 문을 반복적으로 실행합니다. 범위 기반 for 문에 대 한 자세한 내용은 [범위 기반 For 문C++()](../cpp/range-based-for-statement-cpp.md)을 참조 하세요.

## <a name="syntax"></a>구문

```
for ( init-expression ; cond-expression ; loop-expression )
    statement;
```

## <a name="remarks"></a>설명

**For** 문을 사용 하 여 지정 된 횟수 만큼 실행 해야 하는 루프를 생성 합니다.

**For** 문은 다음 표에 표시 된 것 처럼 세 가지 선택적 부분으로 구성 됩니다.

### <a name="for-loop-elements"></a>루프 요소에 대해

|구문 이름|실행 시기|Description|
|-----------------|-------------------|-----------------|
|`init-expression`|For 문의 다른 요소 앞 **에** `init-expression`은 한 번만 실행 됩니다. 그런 다음 `cond-expression`으로 제어가 전달됩니다.|루프 인덱스를 초기화하는 데 자주 사용됩니다. 식 또는 선언을 포함할 수 있습니다.|
|`cond-expression`|첫 번째 반복을 포함한 `statement`의 각 반복을 실행하기 전에 `statement`는 `cond-expression`이 true(0이 아님)로 평가될 때만 실행됩니다.|정수 형식으로 명확한 변환을 하는 정수 형식 또는 클래스 형식으로 평가되는 식입니다. 일반적으로 루프 종료 기준을 테스트하는 데 사용됩니다.|
|`loop-expression`|`statement`의 각 반복 끝에서 `loop-expression`이 실행된 후, `cond-expression`이 평가됩니다.|일반적으로 루프 인덱스 증가에 사용됩니다.|

다음 예에서는 for 문을 사용 하는 다양 **한** 방법을 보여 줍니다.

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

**For** 루프는 `statement` 내에서 [break](../cpp/break-statement-cpp.md), [return](../cpp/return-statement-cpp.md)또는 [goto](../cpp/goto-statement-cpp.md) (for 루프 외부 **의** 레이블이 지정 된 문에 대 한)가 실행 될 때 종료 됩니다. **For** 루프의 [continue](../cpp/continue-statement-cpp.md) 문은 현재 반복만 종료 합니다.

`cond-expression` 생략 하면 true로 간주 되 고 **for** 루프는 `statement`내에서 **break**, **return**또는 **goto** 없이 종료 되지 않습니다.

**For** 문의 세 필드는 일반적으로 초기화에 사용 되 고 종료를 테스트 하 고 증가 하는 데 사용 되지만 이러한 사용으로 제한 되지 않습니다. 예를 들어, 다음 코드는 0부터 4까지의 숫자를 인쇄합니다. 이 경우 `statement`은 null 문입니다.

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

표준에 따르면 **for 루프에서** 선언 된 변수는 for 루프가 종료 된 후 범위를 벗어나는 것을 의미 합니다. **for** C++ 다음은 그 예입니다.

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

기본적으로 [/ze](../build/reference/za-ze-disable-language-extensions.md)에서 **for** 루프에 선언 된 변수는 **for** 루프의 바깥쪽 범위가 종료 될 때까지 범위 내에 남아 있습니다.

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 를 사용 하면 `/Za`를 지정할 필요 없이 루프에 대해 선언 된 변수의 표준 동작을 사용할 수 있습니다.

For 루프의 범위 차이를 사용 하 여 다음과 같이 `/Ze` **의** 변수를 다시 선언할 수도 있습니다.

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

이는 **for 루프에서** 선언 된 변수의 표준 동작을 더욱 비슷하게 모방 하므로 루프를 완료 한 후 **for** 루프에서 선언 된 변수가 범위를 벗어날 수 있습니다. 변수가 **for** 루프에서 선언 되 면 컴파일러는 동일한 이름을 가진 지역 변수가 이미 있더라도 **for** 루프의 바깥쪽 범위에서 지역 변수로 내부적으로 승격 합니다.

## <a name="see-also"></a>참고 항목

[반복 문](../cpp/iteration-statements-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[while 문(C++)](../cpp/while-statement-cpp.md)<br/>
[do-while 문(C++)](../cpp/do-while-statement-cpp.md)<br/>
[범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)
