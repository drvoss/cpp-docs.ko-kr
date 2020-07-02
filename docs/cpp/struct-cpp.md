---
title: struct (C++)
ms.date: 11/04/2016
f1_keywords:
- struct_cpp
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
ms.openlocfilehash: e9ffd30dd0017e912fd7c196e2d3f0e987fb0810
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330585"
---
# <a name="struct-c"></a>struct (C++)

**struct** 키워드는 구조체의 형식 및/또는 구조체 형식 변수를 정의합니다.

## <a name="syntax"></a>구문

```
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[struct] tag declarators;
```

#### <a name="parameters"></a>매개 변수

*template-spec*<br/>
선택적으로 사용할 수 있으며 템플릿을 지정입니다. 자세한 내용은 참조 [템플릿 지정](templates-cpp.md)합니다.

*struct*<br/>
구조체를 사용하기 위한 **struct** 키워드 입니다.

*ms-decl-spec*<br/>
선택적 스토리지 클래스 지정입니다. 자세한 내용은 [__declspec](../cpp/declspec.md) 키워드를 참조합니다.

*tag*<br/>
구조체에 주어진 형식 이름입니다. 태그는 구조체의 범위 내에서 예약어가 됩니다. 태그는 선택 사항입니다. 생략할 경우 익명 구조체가 정의됩니다. 자세한 내용은 [익명 클래스 형식](../cpp/anonymous-class-types.md)을 참조합니다.

*base-list*<br/>
이 구조체가 해당 멤버를 파생할 클래스 또는 구조체의 선택적 목록입니다. 자세한 내용은 [기본 클래스](../cpp/base-classes.md)를 참조하세요. 각 기본 클래스 또는 구조체 이름 앞에는 액세스 지정자 ([public](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), [protected](../cpp/protected-cpp.md)) 및 [virtual](../cpp/virtual-cpp.md) 키워드가 올 수 있습니다. 자세한 내용은 [클래스 멤버에 대한 액세스 제어](member-access-control-cpp.md)의 멤버 액세스 테이블을 참조하세요.

*member-list*<br/>
구조체 멤버 목록입니다. 더 자세한 정보는 [클래스 멤버 개요](../cpp/class-member-overview.md) 를 참조합니다. 여기에서 유일한 차이점 **구조체** 대신 사용 됩니다 **클래스**합니다.

*declarators*<br/>
구조체의 이름을 지정 하는 선언 자 목록입니다. 선언자 목록은 구조체 형식의 하나 이상의 인스턴스를 선언합니다. 구조체의 모든 데이터 멤버를 선언 자 이니셜라이저 목록을 포함할 수 있습니다 **공용**합니다. 데이터 멤버는 이니셜라이저 목록은 구조에서 흔히 **공용** 기본적으로 합니다.  자세한 내용은 [선언자 개요](../cpp/overview-of-declarators.md)를 참조하세요.

## <a name="remarks"></a>설명

구조체 형식은 사용자 정의 복합 형식입니다. 이 형식은 다른 형식을 가질 수 있는 필드 또는 멤버로 구성됩니다.

C++에서 구조체는 맴버가 기본적으로 **public**이라는 점을 제외하면 클래스와 같습니다.

관리 되는 클래스 및 구조체에 대 한 자세한 내용은 C++/CLI, 참조 [클래스 및 구조체](../extensions/classes-and-structs-cpp-component-extensions.md)합니다.

## <a name="using-a-structure"></a>구조체 사용

C에서는 명시적으로 **struct** 키워드를 사용하여 구조체를 선언합니다. C++에서는 형식이 정의된 후에 **struct** 키워드를 사용할 필요가 없습니다.

닫는 중괄호와 세미콜론 사이에 쉼표로 구분된 변수 이름을 하나 이상 넣어 구조체 형식이 정의될 때 변수를 선언하는 옵션이 있습니다.

구조체 변수를 초기화할 수 있습니다. 각 변수의 초기화는 중괄호로 묶어야 합니다.

관련 정보는 [class](../cpp/class-cpp.md), [union](../cpp/unions.md)과 [enum](../cpp/enumerations-cpp.md)을 참조합니다.

## <a name="example"></a>예제

```cpp
#include <iostream>
using namespace std;

struct PERSON {   // Declare PERSON struct type
    int age;   // Declare member types
    long ss;
    float weight;
    char name[25];
} family_member;   // Define object of type PERSON

struct CELL {   // Declare CELL bit field
    unsigned short character  : 8;  // 00000000 ????????
    unsigned short foreground : 3;  // 00000??? 00000000
    unsigned short intensity  : 1;  // 0000?000 00000000
    unsigned short background : 3;  // 0???0000 00000000
    unsigned short blink      : 1;  // ?0000000 00000000
} screen[25][80];       // Array of bit fields

int main() {
    struct PERSON sister;   // C style structure declaration
    PERSON brother;   // C++ style structure declaration
    sister.age = 13;   // assign values to members
    brother.age = 7;
    cout << "sister.age = " << sister.age << '\n';
    cout << "brother.age = " << brother.age << '\n';

    CELL my_cell;
    my_cell.character = 1;
    cout << "my_cell.character = " << my_cell.character;
}
// Output:
// sister.age = 13
// brother.age = 7
// my_cell.character = 1
```
