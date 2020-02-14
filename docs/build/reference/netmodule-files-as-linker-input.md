---
title: .netmodule 링커 입력 파일로 파일
description: Mixed를 사용 하는 방법을 설명 합니다.obj 하거나.netmodule .NET 어셈블리를 만들 때 링커 입력 파일로 사용할 파일입니다.
ms.date: 01/30/2020
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodule files
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
no-loc:
- obj
- netmodule
- clr
- pure
- safe
ms.openlocfilehash: 83eab25624bdb81ba9191e4efe6a774551502ee0
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912822"
---
# <a name="opno-locnetmodule-files-as-linker-input"></a>.netmodule 링커 입력 파일로 파일

link .exe는 MSIL *`.obj`* 및 *`.netmodule`* 파일을 입력으로 받아들입니다. 링커에 의해 생성 된 출력 파일은 링커에 입력 된 *`.obj`* 또는 *`.netmodule`* 파일에 대해 런타임 종속성이 없는 어셈블리 또는 *`.netmodule`* 파일입니다.

## <a name="remarks"></a>주의

*`.netmodule`* 파일은 [/LN (msil 모듈 만들기)](ln-create-msil-module.md) 를 사용 하 여 MSVC 컴파일러에 의해 만들어지거나/noassembly를 사용 하는 링커 [(msil 모듈 만들기)](noassembly-create-a-msil-module.md)를 사용 하 여 만듭니다. *`.obj`* 파일은 항상 C++ 컴파일에서 생성 됩니다. 다른 Visual Studio 컴파일러의 경우 **/target: module** 컴파일러 옵션을 사용합니다.

링커에서는 *`.netmodule`* 를 만든 C++ 컴파일에서 *`.obj`* 파일을 전달 해야 합니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017 이상에서 지원 되지 않으므로 *`.netmodule`* 전달은 더 이상 지원 되지 않습니다.

명령줄에서 링커를 호출 하는 방법에 대 한 자세한 내용은 [링커 명령줄 구문](linking.md), [명령줄에서 MSVC 도구 집합 사용](../building-on-the-command-line.md)및 명령줄 [빌드에 대 한 경로 및 환경 변수 설정](../setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조 하세요.

**/clr** 를 사용 하 여 MSVC 컴파일러에 의해 컴파일된 링커에 *`.netmodule`* 또는 *`.dll`* 파일을 전달 하면 링커 오류가 발생할 수 있습니다. 자세한 내용은 [netmodule 입력 파일 형식 선택](choosing-the-format-of-netmodule-input-files.md)을 참조 하세요.

링커는 **/clr** 컴파일된 네이티브 *`.obj`* 파일 및 MSIL *`.obj`* 파일을 모두 허용 합니다. 동일한 빌드에서 혼합 *`.obj`* 파일을 전달할 수 있습니다. 결과 출력 파일의 기본 안정성은 가장 낮은 입력 모듈의 안정성과 동일 합니다.

둘 이상의 어셈블리로 구성 된 응용 프로그램을 하나의 어셈블리에 포함 하도록 변경할 수 있습니다. 어셈블리의 소스를 다시 컴파일한 다음 *`.obj`* 파일 또는 *`.netmodule`* 파일을 연결 하 여 단일 어셈블리를 생성 합니다.

실행 가능 이미지를 만들 때 [/entry (진입점 기호)](entry-entry-point-symbol.md) 를 사용 하 여 진입점을 지정 합니다.

MSIL *`.obj`* 또는 *`.netmodule`* 파일을 사용 하 여 연결 하는 경우 [/ltcg (링크 타임 코드 생성)](ltcg-link-time-code-generation.md)를 사용 합니다. 그렇지 않으면 링커가 MSIL *`.obj`* 또는 *`.netmodule`* 를 발견할 경우 **/ltcg**를 사용 하 여 링크를 다시 시작 합니다. 링크를 다시 시작 하는 정보 메시지가 표시 됩니다. 이 메시지는 무시 해도 되지만 링커 성능을 향상 시키려면 **/ltcg**를 명시적으로 지정 합니다.

MSIL *`.obj`* 또는 *`.netmodule`* 파일이 cl.exe에 전달 될 수도 있습니다.

입력 MSIL *`.obj`* 또는 *`.netmodule`* 파일은 포함 된 리소스를 가질 수 없습니다. [/ASSEMBLYRESOURCE (관리 되는 리소스 포함)](assemblyresource-embed-a-managed-resource.md) 링커 옵션을 사용 하 여 출력 모듈 또는 어셈블리 파일에 리소스를 포함 합니다. 또는 다른 Visual Studio 컴파일러에서 **/resource** 컴파일러 옵션을 사용 합니다.

## <a name="examples"></a>예

코드 C++ 에서 해당 **`try`** 의 **`catch`** 블록은`System` 되지 않은 예외에 대해 호출 됩니다. 그러나 기본적으로 CLR은 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>를 사용 하 여`System` 되지 않은 예외를 래핑합니다. 및 C++ C++ 모듈이 아닌에서 어셈블리를 만들 때 **`try`** 블록이`System` 아닌 예외를 throw 할 때 코드 C++ 의 **`catch`** 블록을 해당 **`try`** 절에서 호출 하려는 경우에는 비C++ 모듈의 소스 코드에 `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` 특성을 추가 해야 합니다.

```cpp
// MSIL_linking.cpp
// compile with: /c /clr
value struct V {};

ref struct MCPP {
   static void Test() {
      try {
         throw (gcnew V);
      }
      catch (V ^) {
         System::Console::WriteLine("caught non System exception in C++ source code file");
      }
   }
};

/*
int main() {
   MCPP::Test();
}
*/
```

`WrapNonExceptionThrows` 특성의 `Boolean` 값을 변경 하 여 코드에서 C++`System`이 아닌 예외를 catch 하는 기능을 수정 합니다.

```csharp
// MSIL_linking_2.cs
// compile with: /target:module /addmodule:MSIL_linking.obj
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console
using System.Runtime.CompilerServices;

// enable non System exceptions
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]

class MLinkTest {
   public static void Main() {
      try {
         MCPP.Test();
      }
      catch (RuntimeWrappedException) {
         System.Console.WriteLine("caught a wrapped exception in C#");
      }
   }
}
```

```Output
caught non System exception in C++ source code file
```

## <a name="see-also"></a>참조

- [LINK 입력 파일](link-input-files.md)
- [MSVC 링커 옵션](linker-options.md)
