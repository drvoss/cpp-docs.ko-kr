---
title: add_const 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_const
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
ms.openlocfilehash: c82a3fac8ef95da9e226ca3e2e9122b3c8774cbf
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620838"
---
# <a name="add_const-class"></a>add_const 클래스

형식에서 const 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>매개 변수

*Ty*\
수정할 형식입니다.

## <a name="remarks"></a>설명

형식 한정자의 인스턴스는 *ty* 가 참조, 함수 또는 const 한정 형식인 경우 *ty* 인 수정 된 형식을 보유 합니다. 그렇지 않은 경우에는 `const Ty` 입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>요구 사항

**헤더:**\<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고 항목

[<type_traits>](type-traits.md)\
[remove_const 클래스](remove-const-class.md)
