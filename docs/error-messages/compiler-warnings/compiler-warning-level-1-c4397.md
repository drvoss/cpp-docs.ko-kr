---
title: 컴파일러 경고(수준 1) C4397
ms.date: 11/04/2016
f1_keywords:
- C4397
helpviewer_keywords:
- C4397
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
ms.openlocfilehash: e9fb7527124d1838c1f900144f1fea943616f384
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162675"
---
# <a name="compiler-warning-level-1-c4397"></a>컴파일러 경고(수준 1) C4397

System.runtime.interopservices.defaultcharsetattribute은 무시 됩니다.

<xref:System.Runtime.InteropServices.DefaultCharSetAttribute> Microsoft C++ 컴파일러에서 무시 됩니다. DLL에 대 한 문자 집합을 지정 하려면 DllImport의 CharSet 옵션을 사용 합니다. 자세한 내용은 [Interop 사용 C++ (암시적 PInvoke)](../../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4397를 생성 합니다.

```cpp
// C4397.cpp
// compile with: /W1 /c /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[module:DefaultCharSetAttribute(CharSet::Unicode)];   // C4397

[DllImport("kernel32", EntryPoint="CloseHandle", CharSet=CharSet::Unicode)]   // OK
extern "C" bool ImportDefault(IntPtr hObject);

public ref class MySettingVC {
public:
   void method() {
      ImportDefault(IntPtr::Zero);
   }
};

[StructLayout(LayoutKind::Explicit)]
public ref struct StructDefault1{};

public ref class ClassDefault1{};
```
