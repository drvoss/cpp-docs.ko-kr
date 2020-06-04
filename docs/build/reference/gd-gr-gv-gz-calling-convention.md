---
title: /Gd, /Gr, /Gv, /Gz(호출 규칙)
ms.date: 09/05/2018
f1_keywords:
- /Gr
- /Gv
- /Gd
- VC.Project.VCCLCompilerTool.CallingConvention
helpviewer_keywords:
- -Gd compiler option [C++]
- -Gv compiler option [C++]
- /Gv compiler option [C++]
- -Gr compiler option [C++]
- Gd compiler option [C++]
- Gr compiler option [C++]
- /Gz compiler option [C++]
- -Gz compiler option [C++]
- /Gd compiler option [C++]
- Gz compiler option [C++]
- Gv compiler option [C++]
- /Gr compiler option [C++]
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
ms.openlocfilehash: 73fce079a98a3f4afaa35f8b8c6630fc8a9b4ca4
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825528"
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd, /Gr, /Gv, /Gz(호출 규칙)

이 옵션들은 스택 위로 푸시되는 순서, 호출자 함수 또는 호출된 함수가 호출이 끝나면 스택에서 인수를 제거하는지 여부, 그리고 컴파일러가 개별 함수를 식별하는 데 사용하는 식별 이름 데코레이션 규칙을 결정합니다.

## <a name="syntax"></a>구문

> **/Gd**\
> **/Gr**\
> **/Gv**\
> **/Gz**

## <a name="remarks"></a>설명

**/Gd**, 기본 설정으로 C++ 멤버 함수 및 [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md), 또는 [__vectorcall](../../cpp/vectorcall.md)로 표시된 함수를 제외한 모든 함수에 대하여 [__cdecl](../../cpp/cdecl.md) 호출 규칙을 지정합니다.

**/Gr** 는 c `__fastcall` + + 멤버 함수, 이라는 `main`함수 및, `__cdecl` `__stdcall`또는 `__vectorcall`로 표시 된 함수를 제외한 모든 함수에 대해 호출 규칙을 지정 합니다. 모든 `__fastcall` 함수에는 프로토타입이 있어야 합니다. 이 호출 규칙은 x86을 대상으로 하는 컴파일러에서만 사용할 수 있으며 다른 아키텍처를 대상으로 하는 컴파일러에서는 무시됩니다.

**/Gz** 는 c `__stdcall` + + 멤버 함수, 이라는 `main`함수 및, `__cdecl` `__fastcall`또는 `__vectorcall`로 표시 된 함수를 제외한 모든 함수에 대해 호출 규칙을 지정 합니다. 모든 `__stdcall` 함수에는 프로토타입이 있어야 합니다. 이 호출 규칙은 x86을 대상으로 하는 컴파일러에서만 사용할 수 있으며 다른 아키텍처를 대상으로 하는 컴파일러에서는 무시됩니다.

**/Gv** 는 c `__vectorcall` + + 멤버 함수, 명명 `main`된 함수, `vararg` 가변 인수 목록이 있는 함수 또는 충돌 `__cdecl`, `__stdcall`또는 `__fastcall` 특성으로 표시 된 함수를 제외한 모든 함수에 대해 호출 규칙을 지정 합니다. 이 호출 규칙은 /arch:SSE2 이상을 지원하는 x86 및 x64 아키텍처에서만 사용할 수 있으며 ARM 아키텍처를 대상으로 하는 컴파일러에서는 무시됩니다.

가변 개수의 인수를 사용하는 함수는 `__cdecl`로 표시되어야 합니다.

**/Gd**, **/Gr**, **/Gv**와 **/Gz**는 [/clr:safe](clr-common-language-runtime-compilation.md) 또는 **/clr:pure**와 호환되지 않습니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않으며 Visual Studio 2017 이상에서는 지원되지 않습니다.


> [!NOTE]
> 기본적으로 x86 프로세서에서 C++ 멤버 함수는 [__thiscall](../../cpp/thiscall.md)을 사용합니다.

모든 프로세서에서 명시적으로 `__cdecl`, `__fastcall`, `__vectorcall` 또는 `__stdcall`로 표시된 멤버 함수는 해당 아키텍처에서 무시되지 않는 경우 지정된 호출 규칙을 사용합니다. 가변 개수의 인수를 사용하는 멤버 함수는 항상 `__cdecl` 호출 규칙을 사용합니다.

이러한 컴파일러 옵션은 C++ 메서드 및 함수의 이름 데코레이션에는 영향을 주지 않습니다. `extern "C"`로 선언되지 않은 한 C++ 메서드와 함수는 다른 이름 데코레이션 구성표를 사용합니다. 자세한 내용은 [데코레이트된 이름](decorated-names.md)을 참조합니다.


호출 규칙에 대한 자세한 내용은  [호출 규칙](../../cpp/calling-conventions.md)을 참조합니다.

## <a name="__cdecl-specifics"></a>__cdecl 특성

x86 프로세서에서 모든 함수 인수는 오른쪽에서 왼쪽으로 스택에 전달됩니다. ARM 및 x64 아키텍처에서 일부 인수는 레지스터로 전달되고 나머지는 스택에서 오른쪽에서 왼쪽으로 전달됩니다. 호출 루틴은 스택에서 인수를 팝합니다.

C의 경우 `__cdecl` 명명 규칙은 앞에 밑줄 (`_`)이 있는 함수 이름을 사용합니다. 대/소문자 변환은 수행되지 않습니다. `extern "C"`로 선언되지 않은 한 C++ 함수는 다른 이름 데코레이션 구성표를 사용합니다. 자세한 내용은 [데코레이트된 이름](decorated-names.md)을 참조합니다.

## <a name="__fastcall-specifics"></a>__fastcall 특성


`__fastcall` 함수의 인수 중 일부는 레지스터(x86 프로세서, ECX 및 EDX의 경우)에 전달되고 나머지는 오른쪽에서 왼쪽으로 스택에 푸시됩니다. 호출된 루틴은 반환하기 전에 스택에서 이러한 인수를 팝합니다. 일반적으로 **/Gr**은 실행 시간을 줄입니다.


> [!NOTE]
> 인라인 어셈블리 언어로 작성된 함수에 대해 `__fastcall` 호출 규칙을 사용하는 것을 주의해야 합니다. 레지스터 사용이 컴파일러의 사용과 충돌할 수 있습니다.

C의 경우 명명 `__fastcall` 규칙은 앞에 at 기호 (**\@**) 뒤에 함수 인수의 크기 (바이트)가 오는 함수 이름을 사용 합니다. 대/소문자 변환은 수행되지 않습니다. 컴파일러는 이 템플릿을 명명 규칙에 사용합니다.


`@function_name@number`

`__fastcall` 이름 지정 규칙을 사용하는 경우 표준 include 파일을 사용하세요. 그렇지 않으면 해결되지 않은 외부 참조가 표시됩니다.

## <a name="__stdcall-specifics"></a>__stdcall 특성

`__stdcall` 함수의 인수는 오른쪽에서 왼쪽으로 스택에 푸시되고 호출된 함수는 반환하기 전에 스택에서 이러한 인수를 팝합니다.

C의 경우 명명 `__stdcall` 규칙은 앞에 밑줄 (**\_**)이 오고 그 뒤에 () 기호 ()와 함수의**\@** 인수 크기 (바이트)를 차례로 사용 합니다. 대/소문자 변환은 수행되지 않습니다. 컴파일러는 이 템플릿을 명명 규칙에 사용합니다.


`_functionname@number`

## <a name="__vectorcall-specifics"></a>__vectorcall 특성

`__vectorcall` 함수의 정수 인수는 값으로 전달 되 고, 최대 2 (x 86) 또는 4 (x64) 정수 레지스터를 사용 하 고, 부동 소수점 및 벡터 값의 경우 최대 6 개의 XMM 레지스터를 사용 하 고, 나머지는 오른쪽에서 왼쪽으로 스택에 전달 됩니다. 호출된 함수는 반환하기 전에 스택을 정리합니다. 벡터 및 부동 소수점 반환 값은 XMM0으로 반환됩니다.

C의 경우 명명 `__vectorcall` 규칙은 함수 이름 뒤에 두 개의 at 기호 ()**\@** 를 사용 하 고 함수 인수의 크기 (바이트)를 사용 합니다. 대/소문자 변환은 수행되지 않습니다. 컴파일러는 이 템플릿을 명명 규칙에 사용합니다.


`functionname@@number`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **C/c + +** > **고급** 속성 페이지를 선택 합니다.


1. **호출 규칙** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

- [MSVC 컴파일러 옵션](compiler-options.md)
- [MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
