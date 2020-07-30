---
title: 컴파일러 오류 C2555
description: Visual Studio c + + 컴파일러 오류 C2555에 대 한 참조입니다.
ms.date: 03/30/2020
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: ecac92bc663a6344e9ddafe13c194a92ab944c51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207799"
---
# <a name="compiler-error-c2555"></a>컴파일러 오류 C2555

> '*class1*::*function1*': 재정의 가상 함수 반환 형식이 다르고 '*class2*::*function2*'의 공변 (covariant)이 아닙니다.

가상 함수와 파생 된 재정의 함수는 동일한 매개 변수 목록을 갖지만 반환 형식은 다릅니다.

## <a name="remarks"></a>설명

C + +에서 파생 클래스의 재정의 함수는 기본 클래스의 가상 함수에서 반환 형식만 다를 수 있습니다.

특정 반환 형식에 대해서는이 규칙에 대 한 예외가 있습니다. 파생 클래스가 공용 기본 클래스를 재정의 하는 경우 기본 클래스 포인터나 참조 대신 파생 클래스에 대 한 포인터 또는 참조를 반환할 수 있습니다. 이러한 반환 형식은 형식과 함께 다르므로 *공변 (covariant*) 이라고 합니다. 이 규칙 예외는 공변 (covariant) 포인터 또는 포인터 포인터 형식을 사용할 수 없습니다.

오류를 해결 하는 한 가지 방법은 기본 클래스와 동일한 형식을 반환 하는 것입니다. 그런 다음 가상 함수를 호출한 후 반환 값을 캐스팅 합니다. 또 다른 방법은 매개 변수 목록을 변경 하 여 파생 클래스 멤버가 재정의 대신 오버 로드를 수행 하도록 하는 것입니다.

## <a name="examples"></a>예제

로 컴파일하는 경우이 오류가 표시 될 수 있습니다 **`/clr`** . 예를 들어 c + +는 다음 c # 선언과 동일 합니다.

```csharp
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

is

```cpp
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

다음 샘플에서는 C2555를 생성 합니다.

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

이 문제를 해결 하려면의 반환 형식을로 변경 합니다 `Y::func` **`void`** .
