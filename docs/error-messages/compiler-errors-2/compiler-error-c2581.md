---
title: 컴파일러 오류 C2581
ms.date: 11/04/2016
f1_keywords:
- C2581
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
ms.openlocfilehash: a632d6a47afb29b8bb46761c3188391905eda842
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206876"
---
# <a name="compiler-error-c2581"></a>컴파일러 오류 C2581

' type ': static ' operator = ' 함수가 잘못 되었습니다.

대입 ( `=` ) 연산자가로 잘못 선언 되었습니다 **`static`** . 할당 연산자는 일 수 없습니다 **`static`** . 자세한 내용은 [사용자 정의 연산자 (c + +/cli)](../../dotnet/user-defined-operators-cpp-cli.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2581를 생성 합니다.

```cpp
// C2581.cpp
// compile with: /clr /c
ref struct Y {
   static Y ^ operator = (Y^ me, int i);   // C2581
   Y^ operator =(int i);   // OK
};
```
