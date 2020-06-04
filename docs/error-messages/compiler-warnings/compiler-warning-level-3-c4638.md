---
title: 컴파일러 경고(수준 3) C4638
ms.date: 08/27/2018
f1_keywords:
- C4638
helpviewer_keywords:
- C4638
ms.assetid: 2c07923a-e103-4e40-bd11-fdfed428a5ec
ms.openlocfilehash: 3662116359f906ef6f0a004fada8efd6771d0a0a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174130"
---
# <a name="compiler-warning-level-3-c4638"></a>컴파일러 경고(수준 3) C4638

> XML 문서 주석 대상: 알 수 없는 '*symbol*' 기호에 대 한 참조입니다.

## <a name="remarks"></a>설명

컴파일러에서 기호(*symbol*)를 확인할 수 없습니다. 컴파일할 때 기호가 유효해야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4638을 생성합니다.

```cpp
// C4638.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary> Text </summary>
   /// <see cref="aSymbolThatAppearsNowhereInMyProject"/>
   // Try the following line instead:
   // /// <see cref="System::Console::WriteLine"/>
   void MyMethod() {}
};   // C4638
```
