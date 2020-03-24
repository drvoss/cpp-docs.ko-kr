---
title: 컴파일러 오류 C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: 98c4bf43883d15cd17877d7146edf16a73c7ce46
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201106"
---
# <a name="compiler-error-c3391"></a>컴파일러 오류 C3391

' type_arg ': 제네릭 ' generic_type '의 제네릭 매개 변수 ' param '에 대 한 형식 인수가 null을 허용 하지 않는 값 형식 이어야 합니다.

제네릭 형식이 잘못 인스턴스화되었습니다. 형식 정의를 확인하세요. 자세한 내용은 <xref:System.Nullable> 및 [제네릭](../../extensions/generics-cpp-component-extensions.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는를 C# 사용 하 여/cli에서 C++제네릭 형식을 작성할 때 지원 되지 않는 특정 제약 조건이 있는 제네릭 형식을 포함 하는 구성 요소를 만듭니다. 자세한 내용은 [형식 매개 변수에 대한 제약 조건](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)을 참조하세요.

```csharp
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

C3391 구성 요소를 사용할 수 있는 경우 다음 샘플에서는 C3391을 생성 합니다.

```cpp
// C3391_b.cpp
// Compile by using: cl /clr C3391_b.cpp
#using <C3391.dll>
using namespace System;
value class VClass {};

int main() {
   GR< Nullable<VClass> >^ a =
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK
}
```
