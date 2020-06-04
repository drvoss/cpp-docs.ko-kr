---
title: 컴파일러 오류 C3278
ms.date: 11/04/2016
f1_keywords:
- C3278
helpviewer_keywords:
- C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
ms.openlocfilehash: ec51064853afa37f75022042c8c6121b6c5248a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201437"
---
# <a name="compiler-error-c3278"></a>컴파일러 오류 C3278

> 인터페이스 또는 순수 메서드 '*method*'의 직접 호출이 런타임에 실패 합니다.

## <a name="remarks"></a>주의

인터페이스 메서드 또는 순수 메서드를 호출했지만 허용되지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3278을 생성합니다.

```cpp
// C3278_2.cpp
// compile with: /clr
using namespace System;
interface class I
{
   void vmf();
};

public ref class C: public I
{
public:
   void vmf()
   {
      Console::WriteLine( "In C::vmf()" );
      I::vmf(); // C3278
   }

};

int main()
{
   C^ pC = gcnew C;
   pC->vmf();
}
```
