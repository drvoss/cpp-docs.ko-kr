---
title: 멤버 함수 개요
ms.date: 11/04/2016
helpviewer_keywords:
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
ms.openlocfilehash: 6dec4ee53cd840c47d76ac0579daca710b0eeb68
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358404"
---
# <a name="overview-of-member-functions"></a>멤버 함수 개요

멤버 함수는 정적이거나 비정적입니다. 정적 멤버 함수의 동작은 static 멤버 함수에 암시적 **이** 인수가 없기 때문에 다른 멤버 함수와 다릅니다. 비정적 멤버 함수에는 **이** 포인터가 있습니다. 정적이든 비정적이든 클래스 선언 안이나 밖에서 멤버 함수를 정의할 수 있습니다.

멤버 함수가 클래스 선언 안에 정의될 경우 인라인 함수로 처리되며 함수 이름을 클래스 이름으로 정규화할 필요가 없습니다. 클래스 선언 내부에 정의된 함수는 이미 인라인 함수로 처리되지만 **인라인** 키워드를 사용하여 코드를 문서화할 수 있습니다.

클래스 선언 안에 함수를 선언하는 예제는 다음과 같습니다.

```cpp
// overview_of_member_functions1.cpp
class Account
{
public:
    // Declare the member function Deposit within the declaration
    //  of class Account.
    double Deposit( double HowMuch )
    {
        balance += HowMuch;
        return balance;
    }
private:
    double balance;
};

int main()
{
}
```

멤버 함수의 정의가 클래스 선언 외부에 있는 경우 명시적으로 **인라인으로**선언된 경우에만 인라인 함수로 처리됩니다. 또한 범위 결정 연산자(`::`)를 사용하여 클래스 이름으로 정의 안의 함수 이름을 정규화해야 합니다.

다음 예제는 `Account` 함수가 클래스 선언 밖에 정의된 점을 제외하고 위의 `Deposit` 클래스 선언과 동일합니다.

```cpp
// overview_of_member_functions2.cpp
class Account
{
public:
    // Declare the member function Deposit but do not define it.
    double Deposit( double HowMuch );
private:
    double balance;
};

inline double Account::Deposit( double HowMuch )
{
    balance += HowMuch;
    return balance;
}

int main()
{
}
```

> [!NOTE]
> 클래스 선언 안에 또는 별도로 멤버 함수를 정의할 수 있지만 클래스가 정의된 후에는 클래스에 멤버 함수를 추가할 수 없습니다.

멤버 함수가 포함된 클래스는 많은 선언을 포함할 수 있지만 멤버 함수 자체는 프로그램에 정의를 하나만 포함해야 합니다. 정의가 여러 개 있으면 링크 타임에 오류 메시지가 표시됩니다. 클래스에 인라인 함수 정의가 포함된 경우 함수 정의가 동일해야 이 "단일 정의" 규칙을 지킬 수 있습니다.
