---
title: '방법: 포인터 및 배열 고정'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
ms.openlocfilehash: 8dc42690f0f56b97b2af3ed54dfb17d49b081695
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172219"
---
# <a name="how-to-pin-pointers-and-arrays"></a>방법: 포인터 및 배열 고정

관리되는 개체에 정의된 하위 개체를 고정하면 전체 개체를 고정하는 효과가 있습니다.  예를 들어, 모든 배열 요소가 고정되어 있는 경우 전체 배열도 고정됩니다. 고정된 배열을 선언하기 위한 언어 확장은 없습니다. 배열을 고정하려면 해당 요소 형식에 대한 고정 포인터를 선언하고 이러한 요소 중 하나를 고정합니다.

## <a name="example"></a>예제

### <a name="code"></a>코드

```cpp
// pin_ptr_array.cpp
// compile with: /clr
#include <stdio.h>
using namespace System;

int main() {
   array<Byte>^ arr = gcnew array<Byte>(4);
   arr[0] = 'C';
   arr[1] = '+';
   arr[2] = '+';
   arr[3] = '\0';
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned
   unsigned char * cp = p;

   printf_s("%s\n", cp); // bytes pointed at by cp
                         // will not move during call
}
```

```Output
++
```

## <a name="see-also"></a>참고 항목

[pin_ptr(C++/CLI)](pin-ptr-cpp-cli.md)
