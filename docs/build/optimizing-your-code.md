---
title: 코드 최적화
ms.date: 05/06/2019
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: 00356cf50ca8e50c80e8a1142adf654816490c9b
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078502"
---
# <a name="optimizing-your-code"></a>코드 최적화

실행 파일을 최적화 하 여 빠른 실행 속도와 작은 코드 크기 간의 균형을 맞출 수 있습니다. 이 항목에서는 Visual Studio에서 코드를 최적화 하는 데 도움이 되는 몇 가지 메커니즘을 설명 합니다.

## <a name="language-features"></a>언어 기능

다음 항목에서는 C/C++ 언어의 최적화 기능 중 일부에 대해 설명 합니다.

[최적화 pragma 및 키워드](optimization-pragmas-and-keywords.md) \
성능 향상을 위해 코드에서 사용할 수 있는 키워드 및 pragma의 목록입니다.

[컴파일러 옵션 범주별 목록](reference/compiler-options-listed-by-category.md) \
실행 속도 또는 코드 크기에 특히 영향을 주는 **/o** 컴파일러 옵션 목록입니다.

[Rvalue 참조 선언 자: & &](../cpp/rvalue-reference-declarator-amp-amp.md) \
Rvalue 참조는 *의미 체계 이동*의 구현을 지원 합니다. 템플릿 라이브러리를 구현 하는 데 이동 의미 체계를 사용 하는 경우 해당 템플릿을 사용 하는 응용 프로그램의 성능이 크게 향상 될 수 있습니다.

### <a name="the-optimize-pragma"></a>Optimize pragma

코드의 최적화 된 섹션에서 오류가 발생 하거나 속도가 느려지는 경우 [optimize](../preprocessor/optimize.md) pragma를 사용 하 여 해당 섹션에 대 한 최적화를 해제할 수 있습니다.

다음과 같이 코드를 두 pragma로 묶습니다.

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>프로그래밍 방법

최적화를 사용 하 여 코드를 컴파일할 때 추가 경고 메시지가 표시 될 수 있습니다. 일부 경고는 최적화 된 코드에만 관련 되기 때문에이 동작이 예상 됩니다. 이러한 경고에 주의 하면 많은 최적화 문제를 방지할 수 있습니다.

Paradoxically 프로그램을 속도에 맞게 최적화 하면 코드가 느리게 실행 될 수 있습니다. 이는 속도에 대 한 일부 최적화로 인해 코드 크기가 증가 하기 때문입니다. 예를 들어 인라인 함수는 함수 호출의 오버 헤드를 제거 합니다. 그러나 너무 많은 코드를 인라인 하면 프로그램에서 가상 메모리 페이지 폴트 수가 증가할 수 있습니다. 따라서 함수 호출을 제거 하 여 얻은 속도는 메모리 스와핑에서 손실 될 수 있습니다.

다음 항목에서는 바람직한 프로그래밍 방법에 대해 설명 합니다.

[시간이 중요 한 코드 \ 개선 하기 위한 팁](tips-for-improving-time-critical-code.md)
코딩 기술이 향상 되 면 더 나은 성능을 얻을 수 있습니다. 이 항목에서는 코드의 시간이 중요 한 부분이 만족 스럽게 작동 하는지 확인 하는 데 도움이 되는 코딩 기법을 제안 합니다.

[최적화 모범 사례](optimization-best-practices.md) \
응용 프로그램을 최적화 하는 최상의 방법에 대 한 일반적인 지침을 제공 합니다.

## <a name="debugging-optimized-code"></a>최적화 된 코드 디버깅

최적화는 컴파일러에서 만든 코드를 변경할 수 있으므로 응용 프로그램을 디버그 하 고 성능을 측정 한 다음 코드를 최적화 하는 것이 좋습니다.

다음 항목에서는 릴리스 빌드를 디버그 하는 방법에 대 한 정보를 제공 합니다.

- [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio)

- [방법: 최적화된 코드 디버그](/visualstudio/debugger/how-to-debug-optimized-code)

- [부동 소수점 숫자의 정밀도가 떨어지는 이유](why-floating-point-numbers-may-lose-precision.md)

다음 항목에서는 코드 빌드, 로드 및 실행을 최적화 하는 방법에 대 한 정보를 제공 합니다.

- [컴파일러 처리량 향상](improving-compiler-throughput.md)

- [함수 이름을 () 없이 사용하면 코드가 생성되지 않음](using-function-name-without-parens-produces-no-code.md)

- [인라인 어셈블리 최적화](../assembler/inline/optimizing-inline-assembly.md)

- [ATL 프로젝트에 대해 컴파일러 최적화 지정](../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [로드할 때 클라이언트 응용 프로그램의 성능을 개선 하기 위해 사용 해야 하는 최적화 기술](../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="in-this-section"></a>섹션 내용

[최적화 pragma 및 키워드](optimization-pragmas-and-keywords.md) \
[컴파일러 처리량 향상](improving-compiler-throughput.md) \
[부동 소수점 숫자의 정밀도가 떨어질 수 있는 이유](why-floating-point-numbers-may-lose-precision.md) \
[IEEE 부동 소수점 표현](ieee-floating-point-representation.md) \
[시간이 중요 한 코드 \ 개선 하기 위한 팁](tips-for-improving-time-critical-code.md)
[함수 이름을 () 없이 사용 하면 코드가 생성 되지 않습니다](using-function-name-without-parens-produces-no-code.md) \
[최적화 모범 사례](optimization-best-practices.md) \
[프로필 기반 최적화](profile-guided-optimizations.md) \
[프로필 기반 최적화에 대 한 환경 변수](environment-variables-for-profile-guided-optimizations.md) \
[PgoAutoSweep](pgoautosweep.md) \
[pgomgr](pgomgr.md) \
[pgosweep](pgosweep.md) \
[방법: 여러 개의 PGO 프로필을 단일 프로필로 병합](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)

## <a name="see-also"></a>참고 항목

[C/C++ 빌드 참조](reference/c-cpp-building-reference.md)
