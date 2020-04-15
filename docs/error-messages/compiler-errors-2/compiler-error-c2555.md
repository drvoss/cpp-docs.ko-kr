---
title: 컴파일러 오류 C2555
description: Visual Studio C++ 컴파일러 오류 C2555에 대한 참조입니다.
ms.date: 03/30/2020
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: fe0e6379e783387506e6098c9b14a047baa8e6c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374182"
---
# <a name="compiler-error-c2555"></a>컴파일러 오류 C2555

> '*class1*::*function1*': 가상 함수 반환 형식을 재정의 하는 것은 다르며 '*class2*::*function2'*

가상 함수와 파생된 재정의 함수는 매개 변수 목록이 동일하지만 반환 형식은 다릅니다.

## <a name="remarks"></a>설명

C++에서 파생 된 클래스의 재정의 함수는 기본 클래스의 가상 함수에서 반환 형식에 의해서만 다를 수 없습니다.

특정 반환 형식에 대 한이 규칙에 대 한 예외가 있다. derived 클래스가 공용 기본 클래스를 재정의하면 기본 클래스 포인터 또는 참조 대신 파생 클래스에 대한 포인터 또는 참조를 반환할 수 있습니다. 이러한 반환 형식은 형식과 함께 다르기 때문에 *고정이라고*합니다. 이 규칙 예외는 공동 변종 참조-포인터 또는 포인터-포인터-포인터-포인터 형식을 허용 하지 않습니다.

오류를 해결하는 한 가지 방법은 기본 클래스와 동일한 형식을 반환하는 것입니다. 그런 다음 가상 함수가 호출된 후 반환 값을 캐스팅합니다. 또 다른 방법은 매개 변수 목록을 변경하여 파생된 클래스 멤버 함수를 재정의 대신 오버로드로 만드는 것입니다.

## <a name="examples"></a>예

을 사용 하 **`/clr`** 고 컴파일하는 경우 이 오류가 표시될 수 있습니다. 예를 들어 다음 C# 선언과 동일한 C++

```csharp
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

is

```cpp
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

다음 샘플은 C2555를 생성합니다.

```cpp
// C2555.cpp
// compile with: /c
struct X {
   virtual void func();
};
struct Y : X {
   char func();  // C2555
   void func2();   // OK
};
```

이 문제를 해결하려면 의 `Y::func` 반환 `void`유형을 로 변경합니다.
