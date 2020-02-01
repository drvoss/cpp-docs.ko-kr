---
title: 컴파일러 오류 C3390
ms.date: 11/04/2016
f1_keywords:
- C3390
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
ms.openlocfilehash: c624d3b0379d057b0ed566deffc2a0efcc324f88
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912869"
---
# <a name="compiler-error-c3390"></a>컴파일러 오류 C3390

'type_arg': 제네릭 'generic_type'의 제네릭 매개 변수 'param'에 대한 형식 인수가 잘못되었습니다. 참조 형식이어야 합니다.

제네릭 형식이 잘못 인스턴스화되었습니다.  형식 정의를 확인하세요.  자세한 내용은 [제네릭](../../extensions/generics-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예

첫 번째 샘플에서는 C# 를 사용 하 여/clr에서 C++제네릭 형식을 제작할 때 지원 되지 않는 특정 제약 조건이 있는 제네릭 형식을 포함 하는 구성 요소를 만듭니다. 자세한 내용은 [형식 매개 변수에 대한 제약 조건](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)을 참조하세요.

```csharp
// C3390.cs
// Compile by using: csc /target:library C3390.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

C3390 구성 요소를 사용할 수 있는 경우 다음 샘플에서는 C3390을 생성 합니다.

```cpp
// C3390_b.cpp
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>
ref class R { R(int) {} };
value class V {};
ref struct N { N() {} };

int main () {
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type
   GR<R^, V, N^>^ gr2b; // OK
}
```