---
title: /Gh(_penter 후크 함수 사용)
ms.date: 11/04/2016
f1_keywords:
- _penter
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
ms.openlocfilehash: 87815b5f0e0450b84acbe3c35b7ef4f31216ec72
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749300"
---
# <a name="gh-enable-_penter-hook-function"></a>/Gh(_penter 후크 함수 사용)

모든 메서드 또는 `_penter` 함수가 시작될 때 함수에 대한 호출을 발생시킵니다.

## <a name="syntax"></a>구문

```
/Gh
```

## <a name="remarks"></a>설명

이 `_penter` 함수는 라이브러리의 일부가 아니며 에 대한 `_penter`정의를 제공하는 것은 사용자몫입니다.

명시적으로 호출할 `_penter`계획이 없다면 프로토타입을 제공할 필요가 없습니다. 함수는 다음 프로토타입이 있는 것처럼 나타나야 하며 항목에 있는 모든 레지스터의 내용을 푸시하고 종료시 변경되지 않은 콘텐츠를 팝업해야 합니다.

```cpp
void __declspec(naked) __cdecl _penter( void );
```

64비트 프로젝트에는 이 선언을 사용할 수 없습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="example"></a>예제

다음 코드는 **/Gh로**컴파일할 때 `_penter` 두 번 호출되는 방법을 보여 주며, 함수를 `main` 입력할 때 한 `x`번, 함수를 입력할 때 한 번 .

```cpp
// Gh_compiler_option.cpp
// compile with: /Gh
// processor: x86
#include <stdio.h>
void x() {}

int main() {
   x();
}

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

```Output
In a function!
In a function!
```

## <a name="see-also"></a>참조

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
