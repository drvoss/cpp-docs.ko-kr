---
title: '방법: 관리되지 않는 메모리에 개체 참조 유지'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
ms.openlocfilehash: 2f2471e36d7551cab9edb68d7babeb1419e8e20c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544954"
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>방법: 관리되지 않는 메모리에 개체 참조 유지

<xref:System.Runtime.InteropServices.GCHandle>를 래핑하여 관리 되지 않는 메모리에 CLR 개체 참조를 저장 하는 gcroot를 사용할 수 있습니다. 또는 `GCHandle`를 직접 사용할 수 있습니다.

## <a name="example"></a>예제

```cpp
// hold_object_reference.cpp
// compile with: /clr
#include "gcroot.h"
using namespace System;

#pragma managed
class StringWrapper {

private:
   gcroot<String ^ > x;

public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      x = str;
   }

   void PrintString() {
      String ^ targetStr = x;
      Console::WriteLine("StringWrapper::x == {0}", targetStr);
   }
};
#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::x == ManagedString
```

## <a name="example"></a>예제

`GCHandle` 관리 되지 않는 메모리에서 관리 되는 개체 참조를 유지 하는 방법을 제공 합니다.  <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> 메서드를 사용 하 여 관리 되는 개체에 대 한 불투명 핸들을 만들고 해당 개체를 해제할 <xref:System.Runtime.InteropServices.GCHandle.Free%2A>. 또한 <xref:System.Runtime.InteropServices.GCHandle.Target%2A> 메서드를 사용 하면 관리 코드의 핸들에서 개체 참조를 다시 가져올 수 있습니다.

```cpp
// hold_object_reference_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed
class StringWrapper {
   IntPtr m_handle;
public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));
   }
   ~StringWrapper() {
      static_cast<GCHandle>(m_handle).Free();
   }

   void PrintString() {
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);
   }
};

#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::m_handle == ManagedString
```

## <a name="see-also"></a>참고 항목

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
