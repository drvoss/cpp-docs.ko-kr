---
title: '명시적 형식 변환 연산자: ()'
ms.date: 11/04/2016
helpviewer_keywords:
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
ms.openlocfilehash: c168653a82b4d4c5023de1f76a1e6269625c74d8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354856"
---
# <a name="explicit-type-conversion-operator-"></a>명시적 형식 변환 연산자: ()

C++에서는 함수 호출 구문과 유사한 구문을 사용하여 명시적인 형식 변환을 수행할 수 있습니다.

## <a name="syntax"></a>구문

```
simple-type-name ( expression-list )
```

## <a name="remarks"></a>설명

*단순 형식 이름* 다음에 괄호로 둘러싸인 식 *목록이* 지정된 식을 사용하여 지정된 형식의 개체를 생성합니다. 다음 예제에서는 int 형식으로의 명시적 형식 변환을 보여 줍니다.

```cpp
int i = int( d );
```

다음 예제에서는 `Point` 클래스를 보여 주다.

## <a name="example"></a>예제

```cpp
// expre_Explicit_Type_Conversion_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class Point
{
public:
    // Define default constructor.
    Point() { _x = _y = 0; }
    // Define another constructor.
    Point( int X, int Y ) { _x = X; _y = Y; }

    // Define "accessor" functions as
    // reference types.
    unsigned& x() { return _x; }
    unsigned& y() { return _y; }
    void Show()   { cout << "x = " << _x << ", "
                         << "y = " << _y << "\n"; }
private:
    unsigned _x;
    unsigned _y;
};

int main()
{
    Point Point1, Point2;

    // Assign Point1 the explicit conversion
    //  of ( 10, 10 ).
    Point1 = Point( 10, 10 );

    // Use x() as an l-value by assigning an explicit
    //  conversion of 20 to type unsigned.
    Point1.x() = unsigned( 20 );
    Point1.Show();

    // Assign Point2 the default Point object.
    Point2 = Point();
    Point2.Show();
}
```

## <a name="output"></a>출력

```Output
x = 20, y = 10
x = 0, y = 0
```

위의 예제에서는 상수를 사용한 명시적 형식 변환을 보여 주지만 개체에서 이러한 변환을 수행할 때도 동일한 기술을 사용할 수 있습니다. 다음 코드 조각에서 이를 보여 줍니다.

```cpp
int i = 7;
float d;

d = float( i );
```

"캐스트" 구문을 사용하여 명시적 형식 변환을 지정할 수도 있습니다. 캐스트 구문을 사용하여 다시 작성한 이전 예제는 다음과 같습니다.

```cpp
d = (float)i;
```

캐스트 스타일 변환과 함수 스타일 변환 모두 단일 값에서 변환할 때 동일한 결과를 생성합니다. 그러나 함수 스타일 구문에서는 변환을 위해 인수를 둘 이상 지정할 수 있습니다. 이 차이점은 사용자 정의 형식의 경우 중요합니다. `Point` 클래스 및 해당 변환을 고려해 보십시오.

```cpp
struct Point
{
    Point( short x, short y ) { _x = x; _y = y; }
    ...
    short _x, _y;
};
...
Point pt = Point( 3, 10 );
```

함수 스타일 변환을 사용하는 앞의 예제에서는 두 값(x및 *x* *y에*대해 하나)을 사용자 `Point`정의 형식으로 변환하는 방법을 보여 주십니다.

> [!CAUTION]
> 명시적 형식 변환은 C++ 컴파일러의 기본 제공 형식 검사를 재정의하므로 신중하게 사용하십시오.

[캐스트](../cpp/cast-operator-parens.md) 표기는 단순 형식 이름(예: 포인터 *simple-type-name* 또는 참조 형식)이 없는 형식으로 변환하는 데 사용해야 합니다. *단순 유형 이름으로* 표현할 수 있는 형식으로 변환하면 어느 형태로든 작성할 수 있습니다.

캐스트 내의 형식 정의는 올바르지 않습니다.

## <a name="see-also"></a>참고 항목

[후위 식](../cpp/postfix-expressions.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
