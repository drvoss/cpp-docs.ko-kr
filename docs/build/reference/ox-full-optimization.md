---
title: /Ox (대부분의 속도 최적화 사용)
description: MSVC/Ox 옵션은 속도에 대 한 일부 컴파일러 최적화 옵션을 단일 옵션으로 결합 합니다.
ms.date: 07/08/2020
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
ms.openlocfilehash: 10893fe1cf032f2ab56f27aa4af95b050c2ec37e
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180840"
---
# <a name="ox-enable-most-speed-optimizations"></a>`/Ox`(대부분의 속도 최적화 사용)

**`/Ox`** 컴파일러 옵션을 사용 하면 속도를 높이는 최적화의 조합을 사용할 수 있습니다. 일부 버전의 Visual Studio IDE 및 컴파일러 도움말 메시지는 *전체 최적화*라고 하지만 **`/Ox`** 컴파일러 옵션을 사용 하면에서 사용 하도록 설정 된 속도 최적화 옵션 중 일부만 사용할 수 있습니다 **`/O2`** .

## <a name="syntax"></a>구문

> **`/Ox`**

## <a name="remarks"></a>설명

**`/Ox`** 컴파일러 옵션을 사용 하면 **`/O`** 속도를 선호 하는 컴파일러 옵션을 사용할 수 있습니다. **`/Ox`** 컴파일러 옵션에는 [ `/O1` 또는 `/O2` (크기 최소화, 속도 최대화)](o1-o2-minimize-size-maximize-speed.md)에서 사용 하도록 설정 된 추가 [ `/GF` (중복 문자열 제거)](gf-eliminate-duplicate-strings.md) 및 [ `/Gy` (함수 수준 링크 사용](gy-enable-function-level-linking.md) ) 옵션이 포함 되지 않습니다. 및에서 적용 되는 추가 옵션은 **`/O1`** **`/O2`** 문자열이 나 함수에 대 한 포인터를 발생 시켜 대상 주소를 공유 하 여 디버깅 및 엄격한 언어 규칙에 영향을 줄 수 있습니다. **`/Ox`** 옵션은 및를 포함 하지 않고 대부분의 최적화를 사용 하도록 설정 하는 쉬운 방법입니다 **`/GF`** **`/Gy`** . 자세한 내용은 및 옵션에 대 한 설명을 참조 [`/GF`](gf-eliminate-duplicate-strings.md) 하십시오 [`/Gy`](gy-enable-function-level-linking.md) .

**`/Ox`** 컴파일러 옵션은 다음 옵션을 조합 하 여 사용 하는 것과 같습니다.

- [ `/Ob` (인라인 함수 확장)](ob-inline-function-expansion.md), 여기서 option 매개 변수는 2 ( **`/Ob2`** )입니다.

- [`/Oi`(내장 함수 생성)](oi-generate-intrinsic-functions.md)

- [`/Ot`(속도 우선 코드)](os-ot-favor-small-code-favor-fast-code.md)

- [`/Oy`(프레임 포인터 생략)](oy-frame-pointer-omission.md)

**`/Ox`** 는와 함께 사용할 수 없습니다.

- [`/O1`(크기 최소화)](o1-o2-minimize-size-maximize-speed.md)

- [`/O2`(속도 최대화)](o1-o2-minimize-size-maximize-speed.md)

- [`/Od`(디버그) 사용 안 함](od-disable-debug.md)

을 지정 하는 경우 컴파일러 옵션의 속도에 대 한 바이어스를 취소할 수 있습니다 **`/Ox`** .이 옵션 **`/Oxs`** 은 **`/Ox`** 컴파일러 옵션을 [ `/Os` (작은 코드 우선)](os-ot-favor-small-code-favor-fast-code.md)로 결합 합니다. 결합 된 옵션은 더 작은 코드 크기를 선호 합니다.  옵션은 **`/Oxs`** **`/Ox`** **`/Os`** 해당 순서로 옵션이 표시 되는 경우를 지정 하는 것과 동일 합니다.

릴리스 빌드에 대해 사용 가능한 모든 파일 수준 최적화를 적용 하려면 대신 [ `/O2` (속도 최대화)](o1-o2-minimize-size-maximize-speed.md) 를 지정 하 **`/Ox`** 고 [ `/O1` (크기 최소화) 대신 (크기 최소화)](o1-o2-minimize-size-maximize-speed.md) 를 지정 하는 것이 좋습니다 **`/Oxs`** . 릴리스 빌드에서 훨씬 더 최적화 하려면 [ `/GL` (전체 프로그램 최적화)](gl-whole-program-optimization.md) 컴파일러 옵션 및 [ `/LTCG` (링크 타임 코드 생성)](ltcg-link-time-code-generation.md) 링커 옵션도 고려해 야 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**  >  **C/c + +**  >  **최적화** 속성 페이지를 선택 합니다.

1. **최적화** 속성을 수정 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[`/O`옵션 (코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
