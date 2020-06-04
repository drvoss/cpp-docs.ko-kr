---
title: /openmp(OpenMP 지원 사용)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: d3454650bfaaacd756e5cfc73df056441a39f5ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336202"
---
# <a name="openmp-enable-openmp-support"></a>/openmp(OpenMP 지원 사용)

컴파일러가 OpenMP를 지원하기 위해 지시문을 처리하도록 [`#pragma omp`](../../preprocessor/omp.md) 합니다.

## <a name="syntax"></a>구문

::: moniker range=">= vs-2019"

> **/openmp**\[**:**__실험__]

::: moniker-end

::: moniker range="<= vs-2017"

> **/openmp**

::: moniker-end

## <a name="remarks"></a>설명

`#pragma omp`[명령어](../../parallel/openmp/reference/openmp-directives.md) 및 [절을 지정하는 데 사용됩니다.](../../parallel/openmp/reference/openmp-clauses.md) **/openmp가** 컴파일에 지정되지 않은 경우 컴파일러는 OpenMP 절 및 지시문을 무시합니다. [OpenMP 함수](../../parallel/openmp/reference/openmp-functions.md) 호출은 **/openmp가** 지정되지 않은 경우에도 컴파일러에서 처리됩니다.

::: moniker range=">= vs-2019"

C++ 컴파일러는 현재 OpenMP 2.0 표준을 지원합니다. 그러나 Visual Studio 2019는 이제 SIMD 기능도 제공합니다. SIMD를 사용하려면 **/openmp:실험** 옵션을 사용하여 컴파일하십시오. 이 옵션을 사용하면 일반적인 OpenMP 기능과 **/openmp** 스위치를 사용할 때 사용할 수 없는 추가 OpenMP SIMD 기능을 모두 사용할 수 있습니다.

::: moniker-end

**/openmp** 및 **/clr를** 모두 사용하여 컴파일된 응용 프로그램은 단일 응용 프로그램 도메인 프로세스에서만 실행할 수 있습니다. 여러 응용 프로그램 도메인이 지원되지 않습니다. 즉, 모듈 생성자 ()가`.cctor`실행될 때 **/openmp를**사용하여 프로세스가 컴파일되는지, 앱이 기본이 아닌 런타임에 로드되었는지 를 감지합니다. 자세한 내용은 [appdomain,](../../cpp/appdomain.md) [/clr(공통 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md)및 [혼합 어셈블리의 초기화를](../../dotnet/initialization-of-mixed-assemblies.md)참조하십시오.

**/openmp** 및 **/clr를** 모두 사용하여 컴파일된 앱을 기본이 아닌 응용 <xref:System.TypeInitializationException> 프로그램 도메인에 로드하려고 하면 예외가 `OpenMPWithMultipleAppdomainsException` 디버거 외부에 throw되고 디버거에서 예외가 throw됩니다.

이러한 예외는 다음과 같은 상황에서도 발생될 수 있습니다.

- 응용 프로그램이 **/clr을** 사용하여 컴파일되지만 **/openmp가**아닌 경우 프로세스가 **/openmp**를 사용하여 컴파일된 앱을 포함하는 비기본 응용 프로그램 도메인에 로드됩니다.

- **/clr** 앱을 [regasm.exe와](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)같은 유틸리티에 전달하는 경우 대상 어셈블리를 기본이 아닌 응용 프로그램 도메인으로 로드합니다.

OpenMP 리전에서는 공통 언어 런타임의 코드 액세스 보안이 작동하지 않습니다. 병렬 영역 외부에 CLR 코드 액세스 보안 특성을 적용하는 경우 병렬 영역에서는 적용되지 않습니다.

Microsoft는 부분적으로 신뢰할 수 있는 호출자가 허용하는 **/openmp** 앱을 작성하는 것을 권장하지 않습니다. 을 사용하지 <xref:System.Security.AllowPartiallyTrustedCallersAttribute>마십시오 또는 CLR 코드 액세스 보안 특성.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. 구성 **속성** > **C/C++** > **언어** 속성 페이지를 확장합니다.

1. **OpenMP 지원** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 스레드 풀 시작과 스레드 풀이 시작된 후 스레드 풀을 사용하는 효과 중 일부를 보여 주며 있습니다. x64, 단일 코어, 듀얼 프로세서를 가정하면 스레드 풀을 시작하는 데 약 16ms가 걸립니다. 그 후 스레드 풀에 대 한 약간의 추가 비용이 있다.

**/openmp를**사용하여 컴파일할 때 test2에 대한 두 번째 호출은 스레드 풀 시작이 없기 때문에 **/openmp-를**사용하여 컴파일하는 경우보다 더 이상 실행되지 않습니다. 백만 번 반복에서 **/openmp** 버전은 test2에 대한 두 번째 호출의 **/openmp-버전보다** 빠릅니다. 25회 반복에서 **/openmp-** 및 **/openmp** 버전은 모두 클럭 세분성보다 적게 등록됩니다.

응용 프로그램에 루프가 하나만 있고 15ms 미만으로 실행되는 경우(컴퓨터의 대략적인 오버헤드에 맞게 조정됨) **/openmp가** 적절하지 않을 수 있습니다. 더 높은 경우 **/openmp**를 사용하는 것이 좋습니다.

```cpp
// cpp_compiler_options_openmp.cpp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>
#include <windows.h>

volatile DWORD dwStart;
volatile int global = 0;

double test2(int num_steps) {
   int i;
   global++;
   double x, pi, sum = 0.0, step;

   step = 1.0 / (double) num_steps;

   #pragma omp parallel for reduction(+:sum) private(x)
   for (i = 1; i <= num_steps; i++) {
      x = (i - 0.5) * step;
      sum = sum + 4.0 / (1.0 + x*x);
   }

   pi = step * sum;
   return pi;
}

int main(int argc, char* argv[]) {
   double   d;
   int n = 1000000;

   if (argc > 1)
      n = atoi(argv[1]);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);
}
```

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md) \
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md) \
[MSVC의 OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)
