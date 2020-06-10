---
title: 'Lvalue 참조 선언 자: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
ms.openlocfilehash: 595f2b683d2abb4cdc8a328dc6e86338ab90f214
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178069"
---
# <a name="lvalue-reference-declarator-amp"></a>Lvalue 참조 선언 자: &amp;

개체의 주소를 보유하지만 구문상 개체처럼 동작합니다.

## <a name="syntax"></a>구문

```
type-id & cast-expression
```

## <a name="remarks"></a>주의

lvalue 참조를 개체의 또 다른 이름으로 간주할 수 있습니다. lvalue 참조 선언은 참조 선언자가 뒤에 나오는 선택적 지정자 목록으로 구성됩니다. 참조는 초기화되어야 하고 변경될 수 없습니다.

주소가 지정된 포인터 형식으로 변환될 수 있는 개체는 유사한 참조 형식으로도 변환될 수 있습니다. 예를 들어 주소가 `char *` 형식으로 변환될 수 있는 개체는 `char &` 형식으로도 변환될 수 있습니다.

참조 선언을 [주소 연산자](../cpp/address-of-operator-amp.md)사용과 혼동 하지 마십시오. `&`*식별자* 앞에 **int** 또는 **char**와 같은 형식이 있는 경우 *식별자* 는 해당 형식에 대 한 참조로 선언 됩니다. `&`*식별자* 가 형식이 아닌 경우에는 주소 연산자의 사용법이 사용 됩니다.

## <a name="example"></a>예제

다음 예제에서는 `Person` 개체 및 해당 개체에 대한 참조를 선언하여 참조 선언자를 보여 줍니다. `rFriend`가 `myFriend`에 대한 참조이기 때문에 변수 중 하나를 업데이트하면 동일한 개체가 변경됩니다.

```cpp
// reference_declarator.cpp
// compile with: /EHsc
// Demonstrates the reference declarator.
#include <iostream>
using namespace std;

struct Person
{
    char* Name;
    short Age;
};

int main()
{
   // Declare a Person object.
   Person myFriend;

   // Declare a reference to the Person object.
   Person& rFriend = myFriend;

   // Set the fields of the Person object.
   // Updating either variable changes the same object.
   myFriend.Name = "Bill";
   rFriend.Age = 40;

   // Print the fields of the Person object to the console.
   cout << rFriend.Name << " is " << myFriend.Age << endl;
}
```

```Output
Bill is 40
```

## <a name="see-also"></a>참고 항목 

[참조](../cpp/references-cpp.md)<br/>
[참조 형식 함수 인수](../cpp/reference-type-function-arguments.md)<br/>
[참조 형식 함수 반환](../cpp/reference-type-function-returns.md)<br/>
[포인터에 대한 참조](../cpp/references-to-pointers.md)
