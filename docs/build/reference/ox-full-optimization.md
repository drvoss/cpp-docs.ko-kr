---
title: /Ox (대부분의 속도 최적화 사용)
ms.date: 10/18/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /Ox
- /Oxs
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
ms.openlocfilehash: e39905608087425fe5a445f4ef88434d73bb2ded
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320099"
---
# <a name="ox-enable-most-speed-optimizations"></a>/Ox (대부분의 속도 최적화 사용)

**/Ox** 컴파일러 옵션은 속도를 우선 시하는 최적화 조합입니다. 일부 버전의 Visual Studio IDE 및 컴파일러 도움말 메시지에서는 이를 *전체 최적화*라고 부르지만 **/Ox** 컴파일러 옵션은 **/O2**를 사용한 속도 최적화 옵션의 하위 집합만 가능합니다.

## <a name="syntax"></a>구문

> **/Ox**

## <a name="remarks"></a>설명

**/Ox** 컴파일러 옵션을 사용하면 속도를 높이는 **/O** 컴파일러 옵션을 사용할 수 있습니다. **/Ox** 컴파일러 옵션에는 [/O1 또는/O2(크기 최소화, 속도 최대화)](o1-o2-minimize-size-maximize-speed.md)로 사용할 수 있는 [/GF(중복 문자열 제거)](gf-eliminate-duplicate-strings.md)와 [/Gy(함수 수준 링크 사용)](gy-enable-function-level-linking.md) 옵션이 포함되어 있지 않습니다. **/O1**과 **/O2**에 의해 추가 옵션을 적용하면 문자열이나 함수에 대한 포인터가 대상 주소를 공유하게 되어 디버깅 및 엄격한 언어 규칙에 영향을 줄 수 있습니다. **/Ox** 옵션은 **/GF**와 **/Gy**를 포함하지 않고 대부분의 최적화를 쉽게 수행할 수 있는 방법입니다. 자세한 설명은 [/GF](gf-eliminate-duplicate-strings.md)와 [/Gy](gy-enable-function-level-linking.md) 옵션을 참조합니다.

**/Ox** 컴파일러 옵션은 다음 옵션을 조합하여 사용하는 것과 같습니다.

- [/Ob(인라인 함수 확장)](ob-inline-function-expansion.md)option 매개 변수 자리에는 2를 넣습니다. (**/Ob2**)

- [/Og(전역 최적화)](og-global-optimizations.md)

- [/Oi(내장 함수 만들기)](oi-generate-intrinsic-functions.md)

- [/Ot (속도 우선 코드)](os-ot-favor-small-code-favor-fast-code.md)

- [/Oy (프레임 포인터 생략)](oy-frame-pointer-omission.md)

**/Ox** 다음과 상호 배타적입니다.

- [/O1(크기 최소화)](o1-o2-minimize-size-maximize-speed.md)

- [/O2(속도 최대화)](o1-o2-minimize-size-maximize-speed.md)

- [/Od(디버그 사용 안 함)](od-disable-debug.md)

**/Ox** 컴파일러 옵션을 [/Os(작은 코드 선호)](os-ot-favor-small-code-favor-fast-code.md)와 결합한 **/Oxs**를 지정하면 **/Ox** 컴파일러 옵션의 속도에 대한 치우침을 없앨 수 있습니다. 결합된 옵션은 더 작은 코드 크기를 선호합니다. **/Oxs** 옵션은 **/Ox** **/Os**가 순서대로 나타날 때와 완전히 동일합니다.

릴리스 빌드에 대한 모든 사용 가능한 파일 수준 최적화를 적용하려면 **/Ox**대신 [/O2(속도 최대화)](o1-o2-minimize-size-maximize-speed.md)를, **/Oxs** 대신 [/O1(크기 최소화)](o1-o2-minimize-size-maximize-speed.md)를 지정하는것이 좋습니다. 릴리스에서 더 많은 최적화를 적용하려면 [/GL(전체 프로그램 최적화)](gl-whole-program-optimization.md) 컴파일러 옵션과 [/LTCG(링크 타임 코드 생성)](ltcg-link-time-code-generation.md) 링커 옵션을 고려합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**에서 **C/C++**를 연 다음 **최적화** 속성 페이지를 선택합니다.

1. **최적화** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
