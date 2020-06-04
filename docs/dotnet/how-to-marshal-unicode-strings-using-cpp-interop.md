---
title: '방법: C++ Interop를 사용하여 유니코드 문자열 마샬링'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- Unicode, marshaling strings
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
ms.openlocfilehash: f666e52b604e4713f02cb14744ac12a0407366a3
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544888"
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>방법: C++ Interop를 사용하여 유니코드 문자열 마샬링

이 항목에서는 시각적 C++ 상호 운용성의 한 가지 측면을 보여 줍니다. 자세한 내용은 [Interop 사용 C++ (암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조 하세요.

다음 코드 예제에서는 관리 되는 관리 [되지 않는](../preprocessor/managed-unmanaged.md) #pragma 지시문을 사용 하 여 동일한 파일에서 관리 되는 함수 및 관리 되지 않는 함수를 구현 하지만 이러한 함수는 별도의 파일에 정의 된 경우와 동일한 방식으로 상호 운용 됩니다 관리 되지 않는 함수만 포함 하는 파일은 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)을 사용 하 여 컴파일할 필요가 없습니다.

이 항목에서는 관리 되는 함수에서 관리 되지 않는 함수로 유니코드 문자열을 전달 하는 방법 및 그 반대로를 전달 하는 방법을 보여 줍니다. 다른 문자열 형식과의 상호 운용을 위해 다음 항목을 참조 하십시오.

- [방법: C++ Interop를 사용하여 ANSI 문자열 마샬링](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [방법: C++ Interop를 사용하여 COM 문자열 마샬링](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

## <a name="example"></a>예제

관리 되는 함수에서 관리 되지 않는 함수로 유니코드 문자열을 전달 하기 위해 PtrToStringChars 함수 (Vcclr에 선언 됨)를 사용 하 여 관리 되는 문자열이 저장 된 메모리에서에 액세스할 수 있습니다. 이 주소는 네이티브 함수에 전달 되기 때문에 관리 되지 않는 함수가 실행 되는 동안 가비지 수집 사이클이 발생 해야 하는 경우에는 메모리를 [pin_ptr (C++/cli)](../extensions/pin-ptr-cpp-cli.md) 로 고정 하 여 문자열 데이터의 위치가 다시 지정 되지 않도록 해야 합니다.

```cpp
// MarshalUnicode1.cpp
// compile with: /clr
#include <iostream>
#include <stdio.h>
#include <vcclr.h>

using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(const wchar_t* p) {
   printf_s("(native) received '%S'\n", p);
}

#pragma managed

int main() {
   String^ s = gcnew String("test string");
   pin_ptr<const wchar_t> str = PtrToStringChars(s);

   Console::WriteLine("(managed) passing string to native func...");
   NativeTakesAString( str );
}
```

## <a name="example"></a>예제

다음 예제에서는 관리 되지 않는 함수에서 호출 하는 관리 되는 함수의 유니코드 문자열에 액세스 하는 데 필요한 데이터 마샬링을 보여 줍니다. 네이티브 유니코드 문자열을 수신 하는 관리 되는 함수는 <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> 메서드를 사용 하 여 관리 되는 문자열로 변환 합니다.

```cpp
// MarshalUnicode2.cpp
// compile with: /clr
#include <iostream>

using namespace std;
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedStringFunc(wchar_t* s) {
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);
   Console::WriteLine("(managed) received '{0}'", ms);
}

#pragma unmanaged

void NativeProvidesAString() {
   cout << "(unmanaged) calling managed func...\n";
   ManagedStringFunc(L"test string");
}

#pragma managed

int main() {
   NativeProvidesAString();
}
```

## <a name="see-also"></a>참고 항목

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
