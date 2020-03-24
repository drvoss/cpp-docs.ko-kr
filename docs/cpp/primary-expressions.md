---
title: 기본 식
ms.date: 11/04/2016
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
ms.openlocfilehash: 03f0d0d04ad8ef2b052b9303d15437c53369a003
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177627"
---
# <a name="primary-expressions"></a>기본 식

기본 식은 더 복잡한 식의 구성 요소이며 리터럴, 이름 및 범위 결정 연산자(`::`)로 정규화된 이름입니다.  기본 식의 형식은 다음 중 하나입니다.

```
literal
this
name
::name ( expression )
```

*리터럴은* 상수 기본 식입니다. 지정의 형태에 따라 형식이 결정됩니다. 리터럴을 지정 하는 방법에 대 한 자세한 내용은 [리터럴](../cpp/numeric-boolean-and-pointer-literals-cpp.md) 을 참조 하세요.

**This** 키워드는 클래스 개체에 대 한 포인터입니다. 비정적 멤버 함수 안에 사용할 수 있으며 함수가 호출된 인스턴스에 대한 클래스의 인스턴스를 가리킵니다. **이** 키워드는 클래스 멤버 함수 본문 외부에서 사용할 수 없습니다.

**This 포인터** 의 형식은 **this** 포인터를 특별히 수정 하지 않는 함수 내에서 const (`type`는 클래스 이름) **\*** `type` 됩니다. 다음 예제에서는 멤버 함수 선언과 **이**의 형식을 보여 줍니다.

```cpp
// expre_Primary_Expressions.cpp
// compile with: /LD
class Example
{
public:
    void Func();          //  * const this
    void Func() const;    //  const * const this
    void Func() volatile; //  volatile * const this
};
```

**This** 포인터의 형식을 수정 하는 방법에 대 한 자세한 내용은 [이 포인터](this-pointer.md) 를 참조 하십시오.

이름 앞의 범위 결정 연산자(`::`)는 기본 식을 구성합니다.  이러한 이름은 멤버 이름이 아니라 전역 범위의 이름이어야 합니다.  이름의 선언이 이 식의 형식을 결정합니다. 선언 이름이 l-value인 경우 l-value이므로 대입 연산자 식의 왼쪽에 나타날 수 있습니다. 범위 결정 연산자를 사용하면 전역 이름이 현재 범위에서 숨겨지더라도 해당 이름이 참조됩니다. 범위 결정 연산자를 사용 하는 방법에 대 한 예는 [범위](../cpp/scope-visual-cpp.md) 를 참조 하세요.

괄호로 묶은 식은 그 형식과 값이 괄호로 묶지 않은 식과 동일한 기본 식입니다. 괄호로 묶지 않은 식이 l-value일 경우 l-value입니다.

기본 식의 예제는 다음과 같습니다.

```cpp
100 // literal
'c' // literal
this // in a member function, a pointer to the class instance
::func // a global function
::operator + // a global operator function
::A::B // a global qualified name
( i + 1 ) // a parenthesized expression
```

아래 예제는 다음과 같은 다양 한 형식으로 모든 *이름*, 즉 기본 식으로 간주 됩니다.

```cpp
MyClass // a identifier
MyClass::f // a qualified name
operator = // an operator function name
operator char* // a conversion operator function name
~MyClass // a destructor name
A::B   // a qualified name
A<int> // a template id
```

## <a name="see-also"></a>참고 항목

[식의 형식](../cpp/types-of-expressions.md)
