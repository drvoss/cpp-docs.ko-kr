---
title: 컴파일러 경고(수준 1) C4395
ms.date: 11/04/2016
f1_keywords:
- C4395
helpviewer_keywords:
- C4395
ms.assetid: 8051469a-3a39-4677-80f7-1300fbffe8ea
ms.openlocfilehash: 82c7ef9c20b62c0e082a7851bac0ec1e44a8f4c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186857"
---
# <a name="compiler-warning-level-1-c4395"></a>컴파일러 경고(수준 1) C4395

' function ': 멤버 함수가 initonly 데이터 멤버 ' member '의 복사본에 대해 호출 됩니다.

멤버 함수가 [initonly (C++/cli)](../../dotnet/initonly-cpp-cli.md) 데이터 멤버에 대해 호출 되었습니다.  C4395는 함수에서 **initonly** 데이터 멤버를 수정할 수 없다는 경고를 표시 합니다.

다음 샘플에서는 C4395를 생성 합니다.

```cpp
// C4395.cpp
// compile with: /W1 /clr
public value class V {
public:
   V(int data) : m_data(data) {}

   void Mutate() {
      System::Console::WriteLine("Enter Mutate: m_data = {0}", m_data);
      m_data *= 2;
      System::Console::WriteLine("Leave Mutate: m_data = {0}", m_data);
   }

   int m_data;
};

public ref class R {
public:
   static void f() {
      System::Console::WriteLine("v.m_data = {0}", v.m_data);
      v.Mutate();   // C4395
      System::Console::WriteLine("v.m_data = {0}", v.m_data);
   }

private:
   initonly static V v = V(4);
};

int main() {
   R::f();
}
```
