---
title: '방법: PInvoke를 사용하여 문자열 마샬링'
ms.custom: get-started-article
ms.date: 09/09/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
ms.openlocfilehash: e89177261aa32d34ea392030078d4088ea61e2a5
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545224"
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>방법: PInvoke를 사용하여 문자열 마샬링

이 항목에서는 .NET Framework Platform Invoke support를 사용 하 여 CLR 문자열 형식 System:: String을 사용 하 여 C 스타일 문자열을 허용 하는 네이티브 함수를 호출할 수 있는 방법에 대해 설명 합니다. P C++ /Invoke는 컴파일 타임 오류 C++ 보고를 거의 제공 하지 않고, 형식이 안전 하지 않으며, 구현 하기가 번거로울 수 있으므로 Visual 프로그래머는 Interop 기능을 대신 사용 하는 것이 좋습니다 (가능한 경우). 관리 되지 않는 API가 DLL로 패키지 되 고 소스 코드를 사용할 수 없는 경우 P/Invoke는 유일한 옵션 이지만 [Interop 사용 C++ (암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조 하세요.

관리 되는 문자열과 관리 되지 않는 문자열은 메모리에서 다르게 배치 되므로 관리 되는 함수에서 관리 되지 않는 함수로 문자열을 전달 하려면 문자열 데이터를 정확 하 고 안전 하 게 마샬링하는 데 필요한 변환 메커니즘을 삽입 하도록 컴파일러에 지시 하는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성이 필요 합니다.

내장 데이터 형식만 사용 하는 함수와 마찬가지로 <xref:System.Runtime.InteropServices.DllImportAttribute>은 네이티브 함수에 대 한 관리 되는 진입점을 선언 하는 데 사용 되지만--문자열을 전달 하는 데 사용 됩니다. 즉, C 스타일 문자열을 사용 하 여 이러한 진입점을 정의 하는 대신 <xref:System.String> 형식에 대 한 핸들을 대신 사용할 수 있습니다. 그러면 컴파일러가 필요한 변환을 수행 하는 코드를 삽입 하 라는 메시지를 표시 합니다. 문자열을 사용 하는 관리 되지 않는 함수의 각 함수 인수에 대해 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용 하 여 문자열 개체를 C 스타일 문자열로 마샬링해야 함을 나타내야 합니다.

마샬러는 관리 되는 문자열을 고정 및 관리 되지 않는 컨텍스트에서 로컬로 할당 된 문자열에 복사한 다음 관리 되지 않는 함수에 전달 하는 숨겨진 래퍼 루틴의 관리 되지 않는 함수에 대 한 호출을 래핑합니다. 관리 되지 않는 함수가를 반환 하는 경우 래퍼는 리소스를 삭제 하거나, 스택에 있는 경우 래퍼가 범위를 벗어나면 회수 됩니다. 관리 되지 않는 함수는이 메모리를 담당 하지 않습니다. 비관리 코드는 자체 CRT로 설정 된 힙에서 메모리를 만들고 삭제 하므로 다른 CRT 버전을 사용 하는 마샬러에는 문제가 발생 하지 않습니다.

관리 되지 않는 함수가 문자열을 반환 값 또는 out 매개 변수로 반환 하는 경우 마샬러에서 새 관리 되는 문자열에 복사한 다음 메모리를 해제 합니다. 자세한 내용은 [기본 마샬링 동작](/dotnet/framework/interop/default-marshaling-behavior) 및 [플랫폼 호출을 사용 하 여 데이터 마샬링](/dotnet/framework/interop/marshaling-data-with-platform-invoke)을 참조 하세요.

## <a name="example"></a>예제

다음 코드는 관리 되지 않는 모듈과 관리 모듈로 구성 됩니다. 관리 되지 않는 모듈은 char * 형식의 C 스타일 ANSI 문자열을 허용 하는 TakesAString 이라는 함수를 정의 하는 DLL입니다. 관리 되는 모듈은 TakesAString 함수를 가져오지만 문자\*대신 관리 되는 System.string으로 정의 하는 명령줄 응용 프로그램입니다. <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 TakesAString이 호출 될 때 관리 되는 문자열을 마샬링하는 방법을 나타내는 데 사용 됩니다.

```cpp
// TraditionalDll2.cpp
// compile with: /LD /EHsc
#include <windows.h>
#include <stdio.h>
#include <iostream>

using namespace std;

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAString(char*);
}

void TakesAString(char* p) {
   printf_s("[unmanaged] %s\n", p);
}
```

```cpp
// MarshalString.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL
{
   [DllImport("TraditionalDLL2.dll")]
      static public void
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);
};

int main() {
   String^ s = gcnew String("sample string");
    Console::WriteLine("[managed] passing managed string to unmanaged function...");
   TraditionalDLL::TakesAString(s);
   Console::WriteLine("[managed] {0}", s);
}
```

이렇게 하면 관리 되지 않는 힙에서 문자열의 복사본이 생성 되므로 네이티브 함수에의 한 변경 내용이 문자열의 관리 되는 복사본에 반영 되지 않습니다.

기존 #include 지시문을 통해 관리 코드에 노출 되는 DLL 부분은 없습니다. 실제로 DLL은 런타임에만 액세스 되므로 `DllImport`로 가져온 함수 관련 문제는 컴파일 타임에 검색 되지 않습니다.

## <a name="see-also"></a>참고 항목

[C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
