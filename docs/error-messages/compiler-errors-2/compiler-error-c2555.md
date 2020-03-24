---
title: 컴파일러 오류 C2555
ms.date: 11/04/2016
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: ebf3e4a3aff48311edd5fb95b01a7b2d23990231
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202426"
---
# <a name="compiler-error-c2555"></a>컴파일러 오류 C2555

' class1:: function1 ': 재정의 가상 함수 반환 형식이 다르고 ' class2:: function2 '의 공변 (covariant)이 아닙니다.

가상 함수와 파생 된 재정의 함수는 동일한 매개 변수 목록을 갖지만 반환 형식은 다릅니다. 파생 클래스의 재정의 함수는 반환 형식에 의해서만 기본 클래스의 가상 함수와 다를 수 있습니다.

이 오류를 해결 하려면 가상 함수가 호출 된 후 반환 값을 캐스팅 해야 합니다.

/Clr을 사용 하 여 컴파일하는 경우에도이 오류가 표시 될 수 있습니다.   예를 들어 다음 C++ C# 선언과 동일한 시각적 개체입니다.

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

다음인 경우

```
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
