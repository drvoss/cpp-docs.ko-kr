---
title: 관리 코드에서 네이티브 함수 호출
ms.date: 11/04/2016
helpviewer_keywords:
- native functions called from managed code [C++]
- managed code [C++], interoperability
- platform invoke [C++], interoperability
- interoperabiliy [C++], calling native functions from managed code
- calling native functions from managed code
- interop [C++], calling native functions from managed code
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
ms.openlocfilehash: 0cdd5db4fae8d9167fa9ab1aeb6a4e8cbfe76ded
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372518"
---
# <a name="calling-native-functions-from-managed-code"></a>관리 코드에서 네이티브 함수 호출

공통 언어 런타임은 DDL(네이티브 동적 연결 라이브러리)에서 관리되는 코드가 C 스타일 함수를 호출할 수 있도록 하는 플랫폼 호출 서비스 또는 PInvoke를 제공합니다. 런타임과의 COM 상호 운용성 및 "It Just Works" 또는 IJW 메커니즘에 대해 동일한 데이터 마샬링이 사용됩니다.

자세한 내용은 다음을 참조하세요.

- [C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

- [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

이 섹션의 샘플은 사용 `PInvoke` 방법을 보여 줍니다. `PInvoke`절차 마샬링 코드를 작성하는 대신 특성에 선언적으로 마샬링 정보를 제공하기 때문에 사용자 지정된 데이터 마샬링을 단순화할 수 있습니다.

> [!NOTE]
> 마샬링 라이브러리는 최적화된 방식으로 네이티브 환경과 관리되는 환경 간의 데이터를 마샬링하는 다른 방법을 제공합니다. 마샬링 라이브러리에 대한 자세한 내용은 [C++에서](../dotnet/overview-of-marshaling-in-cpp.md) 마샬링 개요를 참조하십시오. 마샬링 라이브러리는 데이터에만 사용할 수 있으며 함수에는 사용할 수 없습니다.

## <a name="pinvoke-and-the-dllimport-attribute"></a>핀보크 및 DllImport 속성

다음 예제에서는 Visual `PInvoke` C++ 프로그램에서의 사용을 보여 주며 있습니다. 기본 함수가 넣는 것은 msvcrt.dll에 정의되어 있습니다. DllImport 특성은 풋옵션 선언에 사용됩니다.

```cpp
// platform_invocation_services.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("msvcrt", CharSet=CharSet::Ansi)]
extern "C" int puts(String ^);

int main() {
   String ^ pStr = "Hello World!";
   puts(pStr);
}
```

다음 샘플은 이전 샘플과 동일하지만 IJW를 사용합니다.

```cpp
// platform_invocation_services_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#include <stdio.h>

int main() {
   String ^ pStr = "Hello World!";
   char* pChars = (char*)Marshal::StringToHGlobalAnsi(pStr).ToPointer();
   puts(pChars);

   Marshal::FreeHGlobal((IntPtr)pChars);
}
```

### <a name="advantages-of-ijw"></a>IJW의 장점

- 프로그램에서 사용하는 관리되지 `DLLImport` 않는 API에 대한 특성 선언을 작성할 필요가 없습니다. 헤더 파일을 포함하고 가져오기 라이브러리에 대한 링크를 포함하기만 하면 됩니다.

- IJW 메커니즘은 약간 더 빠릅니다(예: IJW 스텁은 개발자가 명시적으로 수행하기 때문에 데이터 항목을 고정하거나 복사할 필요가 없습니다).

- 성능 문제를 명확하게 보여 줍니다. 이 경우 유니코드 문자열에서 ANSI 문자열로 변환하고 수행자 메모리 할당 및 할당 할당이 있다는 사실입니다. 이 경우 IJW를 사용하여 코드를 작성하는 개발자는 `_putws` 호출 `PtrToStringChars` 및 사용이 성능에 더 좋을 것이라는 점을 깨닫게 됩니다.

- 동일한 데이터를 사용하여 관리되지 않는 많은 API를 호출하는 경우 한 번 마샬링하고 마샬링된 복사본을 전달하는 것이 매번 다시 마샬링하는 것보다 훨씬 효율적입니다.

### <a name="disadvantages-of-ijw"></a>IJW의 단점

- 마샬링은 특성(적절한 기본값)이 아닌 코드에서 명시적으로 지정해야 합니다.

- 마샬링 코드는 인라인으로 응용 프로그램 논리의 흐름에서 더 침입적입니다.

- 명시적 마샬링 API는 `IntPtr` 32비트에서 64비트 이식성에 대해 형식을 반환하므로 추가 `ToPointer` 호출을 사용해야 합니다.

C++에서 노출되는 특정 메서드는 몇 가지 추가 복잡성을 희생하여 보다 효율적이고 명시적인 메서드입니다.

응용 프로그램이 주로 관리되지 않는 데이터 형식을 사용하거나 .NET Framework API보다 더 관리되지 않는 API를 호출하는 경우 IJW 기능을 사용하는 것이 좋습니다. 대부분 관리되는 응용 프로그램에서 가끔 관리되지 않는 API를 호출하려면 선택이 더 미묘합니다.

## <a name="pinvoke-with-windows-apis"></a>윈도우 API를 가진 핀보크

PInvoke는 Windows에서 함수를 호출하는 데 편리합니다.

이 예제에서는 Visual C++ 프로그램이 Win32 API의 일부인 MessageBox 함수와 상호 작용합니다.

```cpp
// platform_invocation_services_4.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;
typedef void* HWND;
[DllImport("user32", CharSet=CharSet::Ansi)]
extern "C" int MessageBox(HWND hWnd, String ^ pText, String ^ pCaption, unsigned int uType);

int main() {
   String ^ pText = "Hello World! ";
   String ^ pCaption = "PInvoke Test";
   MessageBox(0, pText, pCaption, 0);
}
```

출력은 제목 PInvoke 테스트가 있고 텍스트 Hello World!를 포함하는 메시지 상자입니다.

마샬링 정보는 PInvoke에서 DLL의 함수를 조회하는 데도 사용됩니다. user32.dll에는 실제로 메시지 박스 기능이 없지만 CharSet = CharSet::Ansi를 사용하면 PInvoke가 유니코드 버전인 MessageBoxW 대신 ANSI 버전인 MessageBoxA를 사용할 수 있습니다. 일반적으로 .NET Framework 문자열 개체의 기본 유니코드 형식에서 ANSI로의 번역 오버헤드를 제거하기 때문에 관리되지 않는 API의 유니코드 버전을 사용하는 것이 좋습니다.

## <a name="when-not-to-use-pinvoke"></a>핀보크를 사용하지 않을 때

PInvoke를 사용하는 것은 DLL의 모든 C 스타일 함수에 적합하지 않습니다. 예를 들어 mylib.dll에 MakeSpecial 함수가 있다고 가정하면 다음과 같습니다.

`char * MakeSpecial(char * pszString);`

Visual C++ 응용 프로그램에서 PInvoke를 사용하는 경우 다음과 유사한 내용을 작성할 수 있습니다.

```cpp
[DllImport("mylib")]
extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);
```

여기서 어려움은 MakeSpecial에서 반환된 관리되지 않는 문자열에 대한 메모리를 삭제할 수 없다는 것입니다. PInvoke를 통해 호출 된 다른 함수는 사용자가 할당 할 필요가없는 내부 버퍼에 포인터를 반환합니다. 이 경우 IJW 기능을 사용하는 것이 당연한 선택입니다.

## <a name="limitations-of-pinvoke"></a>핀보크의 한계

매개 변수로 사용 했던 네이티브 함수에서 동일한 정확한 포인터를 반환할 수 없습니다. 네이티브 함수가 PInvoke에 의해 마샬링된 포인터를 반환하면 메모리 손상 및 예외가 발생할 수 있습니다.

```cpp
__declspec(dllexport)
char* fstringA(char* param) {
   return param;
}
```

다음 샘플에서는 이 문제가 발생하며 프로그램이 올바른 출력을 제공하는 것처럼 보일지라도 출력은 해제된 메모리에서 출력됩니다.

```cpp
// platform_invocation_services_5.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;
#include <limits.h>

ref struct MyPInvokeWrap {
public:
   [ DllImport("user32.dll", EntryPoint = "CharLower", CharSet = CharSet::Ansi) ]
   static String^ CharLower([In, Out] String ^);
};

int main() {
   String ^ strout = "AabCc";
   Console::WriteLine(strout);
   strout = MyPInvokeWrap::CharLower(strout);
   Console::WriteLine(strout);
}
```

## <a name="marshaling-arguments"></a>인수 마샬링

을 `PInvoke`사용하면 동일한 폼을 가진 관리되는 형식과 C++ 네이티브 기본 형식 간에 마샬링이 필요하지 않습니다. 예를 들어 Int32와 int 간에 또는 이중과 이중 사이에 는 마샬링이 필요하지 않습니다.

그러나 동일한 양식이 없는 형식을 마샬링해야 합니다. 여기에는 char, 문자열 및 구조체 형식이 포함됩니다. 다음 표에서는 마샬러가 다양한 형식에 대해 사용하는 매핑을 보여 주며 있습니다.

|wtypes.h|Visual C++|/clr가 있는 시각적 C++|공용 언어 런타임|
|--------------|------------------|-----------------------------|-----------------------------|
|HANDLE|Void\*|Void\*|인트프트르, 위트Ptr|
|BYTE|unsigned char|unsigned char|Byte|
|SHORT|short|short|Int16|
|WORD|unsigned short|unsigned short|UInt16|
|INT|int|int|Int32|
|UINT|부호 없는 정수|부호 없는 정수|UInt32|
|LONG|long|long|Int32|
|BOOL|long|bool|부울|
|DWORD|unsigned long|unsigned long|UInt32|
|ULONG|unsigned long|unsigned long|UInt32|
|CHAR|char|char|Char|
|LPSTR|Char\*|문자열 ^ [인], 스트링 빌더 ^ [인, 아웃]|문자열 ^ [인], 스트링 빌더 ^ [인, 아웃]|
|LPCSTR|const char\*|문자열 ^|String|
|LPWSTR|Wchar_t\*|문자열 ^ [인], 스트링 빌더 ^ [인, 아웃]|문자열 ^ [인], 스트링 빌더 ^ [인, 아웃]|
|LPCWSTR|wchar_t\*|문자열 ^|String|
|FLOAT|float|float|Single|
|DOUBLE|double|double|Double|

마샬러는 주소가 관리되지 않는 함수에 전달되는 경우 런타임 힙에 할당된 메모리를 자동으로 고정합니다. 고정을 사용하면 압축 중에 가비지 수집기에서 할당된 메모리 블록을 이동하지 않습니다.

이 항목의 앞에 표시된 예제에서 DllImport의 CharSet 매개 변수는 관리되는 문자열을 마샬링하는 방법을 지정합니다. 이 경우 네이티브 측에 대한 ANSI 문자열로 마샬링되어야 합니다.

MarshalAs 특성을 사용하여 네이티브 함수의 개별 인수에 대한 마샬링 정보를 지정할 수 있습니다. 문자열 \* 인수를 마샬링하기 위한 몇 가지 선택 사항은 BStr, ANSIBStr, TBStr, LPStr, LPWStr 및 LPTStr입니다. 기본값은 LPStr입니다.

이 예제에서 문자열은 이중 바이트 유니코드 문자열 인 LPWStr로 마샬링됩니다. 출력은 헬로 월드의 첫 글자입니다! 마샬링된 문자열의 두 번째 바이트가 null이고 이를 문자열 끝 마커로 해석하기 때문입니다.

```cpp
// platform_invocation_services_3.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("msvcrt", EntryPoint="puts")]
extern "C" int puts([MarshalAs(UnmanagedType::LPWStr)] String ^);

int main() {
   String ^ pStr = "Hello World!";
   puts(pStr);
}
```

MarshalAs 특성은 시스템:::런타임::InteropServices 네임스페이스에 있습니다. 특성은 배열과 같은 다른 데이터 형식과 함께 사용할 수 있습니다.

이 항목의 앞에서 설명한 것처럼 마샬링 라이브러리는 네이티브 환경과 관리되는 환경 간에 데이터를 마샬링하는 새롭고 최적화된 방법을 제공합니다. 자세한 내용은 [C++에서 마샬링 개요를](../dotnet/overview-of-marshaling-in-cpp.md)참조하십시오.

## <a name="performance-considerations"></a>성능 고려 사항

PInvoke는 통화당 10~30x86의 오버헤드를 가지고 있습니다. 이 고정 된 비용 외에도 마샬링 추가 오버 헤드를 만듭니다. 관리되는 코드와 관리되지 않는 코드에서 동일한 표현을 가진 blittable 형식 간에는 마샬링 비용이 없습니다. 예를 들어 int와 Int32 간에 변환하는 데는 비용이 들지 않습니다.

성능을 향상하기 위해 호출당 더 적은 데이터를 마샬링하는 호출이 더 많지 않고 가능한 한 많은 데이터를 마샬링하는 PInvoke 호출이 줄어듭니다.

## <a name="see-also"></a>참고 항목

[네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)
