---
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: bf8293c6a6cf12154b02979de08035807991052c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376045"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>구문

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>설명

클래스 멤버 목록 앞에 있을 때 **공개** 키워드는 모든 함수에서 해당 멤버에 액세스할 수 있음을 지정합니다. 이 설정은 다음 액세스 지정자 또는 클래스 끝까지 선언된 모든 멤버에 적용됩니다.

기본 클래스의 이름 앞에 오는 경우 **공개** 키워드는 기본 클래스의 공용 및 보호된 멤버가 각각 파생 클래스의 공용 및 보호된 멤버임을 지정합니다.

클래스에서 멤버의 기본 액세스는 전용입니다. 구조체나 공용 구조체에서 멤버의 기본 액세스는 공용입니다.

기본 클래스의 기본 액세스는 클래스에 대해 전용이고 구조체에 대해 공용입니다. 공용 구조체에 기본 클래스를 사용할 수 없습니다.

자세한 내용은 [클래스 멤버에](member-access-control-cpp.md)대한 액세스 제어의 [개인](../cpp/private-cpp.md), [보호된,](../cpp/protected-cpp.md) [친구](../cpp/friend-cpp.md)및 구성원 액세스 테이블을 참조하십시오.

## <a name="clr-specific"></a>/clr 관련

CLR 형식에서 C++ 액세스 지정기**키워드(공개,** **비공개**및 **보호)는**어셈블리와 관련된 형식 및 메서드의 가시성에 영향을 줄 수 있습니다. 자세한 내용은 [멤버 액세스 제어](member-access-control-cpp.md)를 참조하십시오.

> [!NOTE]
> [/LN으로](../build/reference/ln-create-msil-module.md) 컴파일된 파일은 이 동작의 영향을 받지 않습니다. 이 경우 관리되는 클래스(공용 또는 전용)가 모두 표시됩니다.

## <a name="end-clr-specific"></a>END /clr 관련

## <a name="example"></a>예제

```cpp
// keyword_public.cpp
class BaseClass {
public:
   int pubFunc() { return 0; }
};

class DerivedClass : public BaseClass {};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   aBase.pubFunc();       // pubFunc() is accessible
                          //    from any function
   aDerived.pubFunc();    // pubFunc() is still public in
                          //    derived class
}
```

## <a name="see-also"></a>참고 항목

[클래스 멤버에 대한 액세스 제어](member-access-control-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)
