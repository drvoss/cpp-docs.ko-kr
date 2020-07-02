---
title: class(C++)
ms.date: 11/04/2016
f1_keywords:
- class_cpp
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
ms.openlocfilehash: c1b9d8f6510dfe15644f0e47cad7e0aecbac36c9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180978"
---
# <a name="class-c"></a>class(C++)

Class **키워드는** 클래스 형식을 선언 하거나 클래스 형식의 개체를 정의 합니다.

## <a name="syntax"></a>구문

```
[template-spec]
class [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[ class ] tag declarators;
```

#### <a name="parameters"></a>매개 변수

*템플릿-사양*<br/>
선택적 템플릿 지정입니다. 자세한 내용은 [템플릿](templates-cpp.md)을 참조 하세요.

*class*<br/>
**Class** 키워드입니다.

*ms decl-사양*<br/>
선택적 스토리지 클래스 지정입니다. 자세한 내용은 [__declspec](../cpp/declspec.md) 키워드를 참조 하세요.

*태그가*<br/>
클래스에 주어진 형식 이름입니다. 태그는 클래스의 범위 내에서 예약어가 됩니다. 태그는 선택 사항입니다. 생략 하면 익명 클래스가 정의됩니다. 자세한 내용은 [익명 클래스 형식](../cpp/anonymous-class-types.md)을 참조 하세요.

*base-list*<br/>
이 클래스가 구성원을 파생시킬 클래스 또는 구조의 선택적 목록입니다. 자세한 내용은 [기본 클래스](../cpp/base-classes.md) 를 참조 하세요. 각 기본 클래스 또는 구조체 이름 앞에는 액세스 지정자 ([public](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), [protected](../cpp/protected-cpp.md)) 및 [virtual](../cpp/virtual-cpp.md) 키워드가 올 수 있습니다. 자세한 내용은 [클래스 멤버에 대 한 액세스 제어](member-access-control-cpp.md) 의 멤버 액세스 테이블을 참조 하세요.

*멤버 목록*<br/>
클래스 멤버의 목록입니다. 자세한 내용은 [클래스 멤버 개요](../cpp/class-member-overview.md) 를 참조 하세요.

*declarators*<br/>
클래스 형식의 하나 이상의 인스턴스 이름을 지정하는 이니셜라이저 목록입니다. 선언 자는 클래스의 모든 데이터 멤버가 **public**인 경우 이니셜라이저 목록을 포함할 수 있습니다. 이는 클래스에서와 같이 데이터 멤버가 기본적으로 **public** 인 구조체에서 더 일반적입니다. 자세한 내용은 [선언 자 개요](../cpp/overview-of-declarators.md) 를 참조 하세요.

## <a name="remarks"></a>주의

일반적인 클래스에 대한 자세한 내용은 다음 항목 중 하나를 참조하세요.

- [struct](../cpp/struct-cpp.md)

- [union](../cpp/unions.md)

- [__multiple_inheritance](../cpp/inheritance-keywords.md)

- [__single_inheritance](../cpp/inheritance-keywords.md)

- [__virtual_inheritance](../cpp/inheritance-keywords.md)

/Cli 및 C++ C++/cx의 관리 되는 클래스 및 구조체에 대 한 자세한 내용은 [클래스 및 구조체](../extensions/classes-and-structs-cpp-component-extensions.md) 를 참조 하세요.

## <a name="example"></a>예제

```cpp
// class.cpp
// compile with: /EHsc
// Example of the class keyword
// Exhibits polymorphism/virtual functions.

#include <iostream>
#include <string>
#define TRUE = 1
using namespace std;

class dog
{
public:
   dog()
   {
      _legs = 4;
      _bark = true;
   }

   void setDogSize(string dogSize)
   {
      _dogSize = dogSize;
   }
   virtual void setEars(string type)      // virtual function
   {
      _earType = type;
   }

private:
   string _dogSize, _earType;
   int _legs;
   bool _bark;

};

class breed : public dog
{
public:
   breed( string color, string size)
   {
      _color = color;
      setDogSize(size);
   }

   string getColor()
   {
      return _color;
   }

   // virtual function redefined
   void setEars(string length, string type)
   {
      _earLength = length;
      _earType = type;
   }

protected:
   string _color, _earLength, _earType;
};

int main()
{
   dog mongrel;
   breed labrador("yellow", "large");
   mongrel.setEars("pointy");
   labrador.setEars("long", "floppy");
   cout << "Cody is a " << labrador.getColor() << " labrador" << endl;
}
```

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)<br/>
[클래스 및 구조체](../cpp/classes-and-structs-cpp.md)
