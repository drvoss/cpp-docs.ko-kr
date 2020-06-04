---
title: break 문 (C++)
ms.date: 11/04/2016
f1_keywords:
- break_cpp
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
ms.openlocfilehash: 23d31e1456106d5f82c4a13079c72c231b8477bd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190484"
---
# <a name="break-statement-c"></a>break 문 (C++)

**Break** 문은 해당 문이 표시 되는 가장 가까운 바깥쪽 루프 또는 조건문의 실행을 종료 합니다. 제어는 종료된 문 뒤의 문이 있는 경우 전달됩니다.

## <a name="syntax"></a>구문

```
break;
```

## <a name="remarks"></a>주의

**Break** 문은 조건문과 함께 [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md)및 [while](../cpp/while-statement-cpp.md) [loop 문을 사용](../cpp/switch-statement-cpp.md) 하 여 사용 됩니다.

**Switch** 문에서 **break** 문은 프로그램이 **switch** 문 외부에서 다음 문을 실행 하도록 합니다. **Break** 문이 없으면 **default** 절을 포함 하 여 **switch** 문 끝에 대 한 일치 하는 **case** 레이블의 모든 문이 실행 됩니다.

루프에서 **break** 문은 가장 가까운 바깥쪽 **do**, **for**또는 **while** 문의 실행을 종료 합니다. 종료된 문 뒤에 문이 있는 경우 제어가 해당 문으로 전달됩니다.

중첩 문 내에서 **break** 문은 바로이를 포함 하는 **do**, **for**, **switch**또는 **while** 문만 종료 합니다. **Return** 또는 **goto** 문을 사용 하 여 보다 깊게 중첩 된 구조에서 컨트롤을 전송할 수 있습니다.

## <a name="example"></a>예제

다음 코드에서는 **for** 루프에서 **break** 문을 사용 하는 방법을 보여 줍니다.

```cpp
#include <iostream>
using namespace std;

int main()
{
    // An example of a standard for loop
    for (int i = 1; i < 10; i++)
    {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }

    // An example of a range-based for loop
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    for (int i : nums) {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }
}
```

```Output
In each case:
1
2
3
```

다음 코드에서는 **while** 루프와 **do** 루프에서 **break** 를 사용 하는 방법을 보여 줍니다.

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;

    while (i < 10) {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
        i++;
    }

    i = 0;
    do {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
        i++;
    } while (i < 10);
}
```

```Output
In each case:
0123
```

다음 코드에서는 switch 문에서 **break** 를 사용 하는 방법을 보여 줍니다. 각 사례를 별도로 처리 하려면 모든 경우에 **중단** 을 사용 해야 합니다. **break**를 사용 하지 않는 경우 코드 실행은 다음 사례로 진행 됩니다.

```cpp
#include <iostream>
using namespace std;

enum Suit{ Diamonds, Hearts, Clubs, Spades };

int main() {

    Suit hand;
    . . .
    // Assume that some enum value is set for hand
    // In this example, each case is handled separately
    switch (hand)
    {
    case Diamonds:
        cout << "got Diamonds \n";
        break;
    case Hearts:
        cout << "got Hearts \n";
        break;
    case Clubs:
        cout << "got Clubs \n";
        break;
    case Spades:
        cout << "got Spades \n";
        break;
    default:
          cout << "didn't get card \n";
    }
    // In this example, Diamonds and Hearts are handled one way, and
    // Clubs, Spades, and the default value are handled another way
    switch (hand)
    {
    case Diamonds:
    case Hearts:
        cout << "got a red card \n";
        break;
    case Clubs:
    case Spades:
    default:
        cout << "didn't get a red card \n";
    }
}
```

## <a name="see-also"></a>참고 항목

[점프 문](../cpp/jump-statements-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[continue 문](../cpp/continue-statement-cpp.md)
