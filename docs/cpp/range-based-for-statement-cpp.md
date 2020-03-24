---
title: 범위 기반 for 문(C++)
ms.date: 11/04/2016
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
ms.openlocfilehash: 504f177cf68b978642f15ba4799cab8cb517f447
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188352"
---
# <a name="range-based-for-statement-c"></a>범위 기반 for 문(C++)

`statement`의 각 요소에 대해 `expression`를 반복적 및 순차적으로 실행합니다.

## <a name="syntax"></a>구문

```
for ( for-range-declaration : expression )
   statement
```

## <a name="remarks"></a>설명

범위 기반 **for** 문을 사용 하 여 "범위"를 통해 실행 되어야 하는 루프를 생성할 수 있습니다. "범위"는 `std::vector`또는 범위가 `begin()` 및 `end()`정의 된 다른 C++ 표준 라이브러리 시퀀스와 같이 반복 될 수 있는 것으로 정의 됩니다. `for-range-declaration` 부분에 선언 된 이름은 **for** 문에 로컬 이며 `expression` 또는 `statement`에서 다시 선언할 수 없습니다. 문의 `for-range-declaration` 부분에 [auto](../cpp/auto-cpp.md) 키워드가 기본 설정 되어 있는지 확인 합니다.

**Visual Studio 2017의 새로운 작업:**  범위 기반 for 루프에는 더 이상 동일한 형식의 begin () 및 end () 반환 개체가 필요 하지 않습니다. 이 기능을 사용하면 end()가 Ranges-V3 제안에 정의된 대로 범위에서 사용되는 sentinel 개체를 반환할 수 있습니다. 자세한 내용은 [Generalizing the Range-Based For Loop](https://wg21.link/p0184r0)(범위 기반 for 루프 일반화) 및 [range-v3 library on GitHub](https://github.com/ericniebler/range-v3)(GitHub의 range-v3 라이브러리)를 참조하세요.

이 코드는 범위 기반 **for** 루프를 사용 하 여 배열 및 벡터를 반복 하는 방법을 보여 줍니다.

```cpp
// range-based-for.cpp
// compile by using: cl /EHsc /nologo /W4
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    // Basic 10-element integer array.
    int x[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

    // Range-based for loop to iterate through the array.
    for( int y : x ) { // Access by value using a copy declared as a specific type.
                       // Not preferred.
        cout << y << " ";
    }
    cout << endl;

    // The auto keyword causes type inference to be used. Preferred.

    for( auto y : x ) { // Copy of 'x', almost always undesirable
        cout << y << " ";
    }
    cout << endl;

    for( auto &y : x ) { // Type inference by reference.
        // Observes and/or modifies in-place. Preferred when modify is needed.
        cout << y << " ";
    }
    cout << endl;

    for( const auto &y : x ) { // Type inference by const reference.
        // Observes in-place. Preferred when no modify is needed.
        cout << y << " ";
    }
    cout << endl;
    cout << "end of integer array test" << endl;
    cout << endl;

    // Create a vector object that contains 10 elements.
    vector<double> v;
    for (int i = 0; i < 10; ++i) {
        v.push_back(i + 0.14159);
    }

    // Range-based for loop to iterate through the vector, observing in-place.
    for( const auto &j : v ) {
        cout << j << " ";
    }
    cout << endl;
    cout << "end of vector test" << endl;
}
```

출력은 다음과 같습니다.

```Output
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
end of integer array test

0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159
end of vector test
```

범위 **기반 for 루프는** `statement` 중 하나가 실행 될 때 종료 됩니다. 즉, 범위 기반 **for** 루프 외부의 레이블 문으로 [중단](../cpp/break-statement-cpp.md), [반환](../cpp/return-statement-cpp.md)또는 [이동](../cpp/goto-statement-cpp.md) 합니다. 범위 기반 **for** 루프의 [continue](../cpp/continue-statement-cpp.md) 문은 현재 반복만 종료 합니다.

범위 기반에 대 한 다음 사항에 유의 **하세요.**

- 배열을 자동으로 인식합니다.

- `.begin()` 및 `.end()`가 포함된 컨테이너를 인식합니다.

- 기타 항목에 대해 `begin()` 및 `end()` 인수 종속성 조회를 사용합니다.

## <a name="see-also"></a>참고 항목

[auto](../cpp/auto-cpp.md)<br/>
[반복 문](../cpp/iteration-statements-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[while 문(C++)](../cpp/while-statement-cpp.md)<br/>
[do-while 문(C++)](../cpp/do-while-statement-cpp.md)<br/>
[for 문(C++)](../cpp/for-statement-cpp.md)
