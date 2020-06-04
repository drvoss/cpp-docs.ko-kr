---
title: 컴파일러 오류 C3808
ms.date: 11/04/2016
f1_keywords:
- C3808
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
ms.openlocfilehash: e854764dc3f8d3ede79965302b62055b91df0a4c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165628"
---
# <a name="compiler-error-c3808"></a>컴파일러 오류 C3808

> '*type*': ComImport 특성이 있는 클래스는 '*member*' 멤버를 정의할 수 없습니다. abstract 또는 dllimport 함수만 사용할 수 있습니다.

## <a name="remarks"></a>설명

<xref:System.Runtime.InteropServices.ComImportAttribute>에서 파생 된 형식은 *멤버*를 정의할 수 없습니다.

**/Clr: pure** 및 **/clr: safe** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3808를 생성 합니다.

```cpp
// C3808.cpp
// compile with: /c /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 {
   int f() {}   // C3808
   virtual int g() abstract;   // OK

   [DllImport("msvcrt.dll")]
   int printf(System::String ^, int i);   // OK
};
```
