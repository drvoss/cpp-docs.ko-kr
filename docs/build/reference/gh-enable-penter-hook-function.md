---
title: /Gh(_penter 후크 함수 사용)
description: 제공 된 _penter 함수를 호출 하는/Gh 컴파일러 옵션에 대해 설명 합니다.
ms.date: 07/06/2020
f1_keywords:
- _penter
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
ms.openlocfilehash: 96597d964e6a341aa25f4d52d34974949eb7b096
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058583"
---
# <a name="gh-enable-_penter-hook-function"></a>/Gh(_penter 후크 함수 사용)

`_penter`모든 메서드 또는 함수의 시작 부분에서 함수를 호출 합니다.

## <a name="syntax"></a>구문

> **`/Gh`**

## <a name="remarks"></a>설명

`_penter`함수는 라이브러리의 일부가 아닙니다. 에 대 한 정의를 제공 해야 `_penter` 합니다.

를 명시적으로 호출 하지 않을 경우 `_penter` 프로토타입을 제공할 필요가 없습니다. 함수는 항목에 모든 레지스터의 콘텐츠를 푸시하고 종료 시 변경 되지 않은 콘텐츠를 팝 해야 합니다. 다음 프로토타입이 있는 것 처럼 표시 되어야 합니다.

```cpp
void __declspec(naked) __cdecl _penter( void );
```

64 비트 프로젝트에는이 선언을 사용할 수 없습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**  >  **C/c + +**  >  **명령줄** 속성 페이지를 엽니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="example"></a>예제

다음 코드는 **/Gh**로 컴파일될 때를 두 번 호출 하는 방법을 보여 줍니다. 함수를 입력 하 `_penter` `main` 고 함수를 입력 하면 한 번이 호출 됩니다 `x` . 이 예제는 별도로 컴파일되는 두 개의 소스 파일로 구성 되어 있습니다.

```cpp
// local_penter.cpp
// compile with: cl /EHsc /c local_penter.cpp
// processor: x86
#include <stdio.h>

extern "C" void __declspec(naked) __cdecl _penter( void ) {
   _asm {
      push eax
      push ebx
      push ecx
      push edx
      push ebp
      push edi
      push esi
    }

   printf_s("\nIn a function!");

   _asm {
      pop esi
      pop edi
      pop ebp
      pop edx
      pop ecx
      pop ebx
      pop eax
      ret
    }
}
```

```cpp
// Gh_compiler_option.cpp
// compile with: cl /EHsc /Gh Gh_compiler_option.cpp local_penter.obj
// processor: x86
#include <stdio.h>

void x() {}

int main() {
   x();
}
```

를 실행 하면 `_penter` 및에 대 한 항목에서 로컬 함수가 호출 됩니다 `main` `x` .

```Output

In a function!
In a function!
```

## <a name="see-also"></a>참조

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[`/GH`(_Pexit 후크 함수 사용)](gh-enable-pexit-hook-function.md)
