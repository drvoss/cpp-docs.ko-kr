---
title: protected (C++)
ms.date: 11/04/2016
f1_keywords:
- protected_cpp
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
ms.openlocfilehash: 79ca081726c1f26a251763e2533ade730f075e2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317274"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>구문

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>설명

**보호된** 키워드는 다음 액세스 지정자(공개 또는 **개인)** 또는 클래스 정의의 끝까지 *멤버 목록의* 클래스 멤버에 대한 액세스를 지정합니다.**public** **보호된** 것으로 선언된 클래스 멤버는 다음에서만 사용할 수 있습니다.

- 원래 이 멤버를 선언한 클래스의 멤버 함수

- 원래 이 멤버를 선언한 클래스의 friend

- 원래 이 멤버를 선언한 클래스에서 공용 또는 보호된 액세스로 파생된 클래스

- 보호된 멤버에 대해 전용 액세스 권한이 있으며 전용으로 직접 파생된 클래스

기본 클래스의 이름 앞에 지정하는 경우 **보호된** 키워드는 기본 클래스의 공용 및 보호된 멤버가 파생된 클래스의 보호된 멤버임을 지정합니다.

보호된 멤버는 **선언된** 클래스의 멤버만 액세스할 수 있는 개인 멤버만큼 비공개가 아니지만 모든 함수에서 액세스할 수 있는 **공용** 멤버만큼 공용이 아닙니다.

**또한 정적으로** 선언된 보호된 멤버는 파생 클래스의 모든 친구 또는 멤버 함수에 액세스할 수 있습니다. **정적으로** 선언되지 않은 보호된 멤버는 파생 클래스의 포인터, 참조 또는 개체를 통해서만 파생 클래스의 친구 및 멤버 함수에 액세스할 수 있습니다.

관련 정보는 [클래스 멤버에](member-access-control-cpp.md)대한 액세스 제어의 [친구,](../cpp/friend-cpp.md) [공용,](../cpp/public-cpp.md) [개인](../cpp/private-cpp.md)및 구성원 액세스 테이블을 참조하십시오.

## <a name="clr-specific"></a>/clr 관련

CLR 형식에서 C++ 액세스 지정기**키워드(공개,** **비공개**및 **보호)는**어셈블리와 관련된 형식 및 메서드의 가시성에 영향을 줄 수 있습니다. 자세한 내용은 [멤버 액세스 제어](member-access-control-cpp.md)를 참조하십시오.

> [!NOTE]
> [/LN으로](../build/reference/ln-create-msil-module.md) 컴파일된 파일은 이 동작의 영향을 받지 않습니다. 이 경우 관리되는 클래스(공용 또는 전용)가 모두 표시됩니다.

## <a name="end-clr-specific"></a>END /clr 관련

## <a name="example"></a>예제

```cpp
// keyword_protected.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class X {
public:
   void setProtMemb( int i ) { m_protMemb = i; }
   void Display() { cout << m_protMemb << endl; }
protected:
   int  m_protMemb;
   void Protfunc() { cout << "\nAccess allowed\n"; }
} x;

class Y : public X {
public:
   void useProtfunc() { Protfunc(); }
} y;

int main() {
   // x.m_protMemb;         error, m_protMemb is protected
   x.setProtMemb( 0 );   // OK, uses public access function
   x.Display();
   y.setProtMemb( 5 );   // OK, uses public access function
   y.Display();
   // x.Protfunc();         error, Protfunc() is protected
   y.useProtfunc();      // OK, uses public access function
                        // in derived class
}
```

## <a name="see-also"></a>참고 항목

[클래스 멤버에 대한 액세스 제어](member-access-control-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)
