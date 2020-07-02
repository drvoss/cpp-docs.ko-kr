---
title: /analyze(코드 분석)
ms.date: 10/15/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
ms.openlocfilehash: c0cebe1cbd160bdec257a960f90039c1af3bfee2
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77416043"
---
# <a name="analyze-code-analysis"></a>/analyze(코드 분석)

코드 분석 및 제어 옵션을 사용합니다.

## <a name="syntax"></a>구문

> **/analyze**[-] [ **: WX**] [ **: 로그** *파일 이름*] [ **: quiet**] [ **: stacksize** *number*] [ **: max_paths** *number*] [ **: only**] [ **: 규칙** *집합 규칙 집합*] [ **:p lugin** *plugin*]

## <a name="arguments"></a>인수

**/analyze**\
기본 모드에서 분석을 설정합니다. 분석 출력은 다른 오류 메시지와 같이 **출력** 창으로 이동 합니다. **/Analyze-** 를 사용 하 여 분석을 명시적으로 해제 합니다.

**/analyze: WX-** \
**/Wx**를 사용 하 여 컴파일하는 경우 코드 분석 경고가 오류로 처리 되지 않습니다. 자세한 내용은 [/wx (경고 수준)](compiler-option-warning-level.md)를 참조 하세요.

**/analyze: 로그** *파일 이름*\
자세한 분석기 결과는 파일 *이름*으로 지정 된 파일에 XML로 기록 됩니다.

**/analyze: 자동**\
분석기 출력을 **출력** 창으로 끕니다.

**/analyze: stacksize** *number*\
이 옵션에 사용 되는 *숫자* 매개 변수는 경고 [C6262](/cpp/code-quality/c6262) 생성 되는 스택 프레임의 크기 (바이트)를 지정 합니다. *Number* 앞의 공백은 선택 사항입니다. 이 매개 변수를 지정 하지 않으면 기본적으로 스택 프레임 크기가 16KB 됩니다.

**/analyze: max_paths** *number*\
이 옵션에 사용 되는 *숫자* 매개 변수는 분석할 코드 경로의 최대 수를 지정 합니다. 이 매개 변수를 지정 하지 않으면 기본적으로 256이 표시 됩니다. 값이 클수록 더 철저 하 게 확인할 수 있지만 분석에 시간이 더 오래 걸릴 수 있습니다.

**/analyze:\만**
일반적으로 컴파일러는 코드를 생성하고 분석기를 실행한 후에 추가 구문 검사를 실시합니다. **/Analyze: only** 옵션은이 코드 생성 패스를 해제 합니다. 이를 통해 분석 속도를 높일 수 있지만 컴파일러의 코드 생성 통과에서 발견 될 수 있는 컴파일 오류 및 경고는 내보내지 않습니다. 프로그램에 코드 생성 오류가 없는 경우 분석 결과가 불안정 해질 수 있습니다. 코드가 이미 오류 없이 코드 생성 구문 검사를 통과 한 경우에만이 옵션을 사용 하는 것이 좋습니다.

**/analyze: 규칙 집합** *file_path*\
사용자가 직접 만들 수 있는 사용자 지정 규칙 집합을 포함 하 여 분석할 규칙 집합을 지정할 수 있습니다. 이 스위치가 설정 되 면 규칙 엔진이 실행 되기 전에 지정 된 규칙 집합의 멤버가 아닌 멤버를 제외 하기 때문에 더 효율적입니다. 그렇지 않으면 엔진이 모든 규칙을 검사 합니다.

Visual Studio와 함께 제공 되는 규칙 집합은 *%VSINSTALLDIR%\Team toolo정적 분석의 규칙 집합* 에서 찾을 수 있습니다.

다음 샘플 사용자 지정 규칙 집합은 C6001 및 C26494를 확인 하도록 규칙 엔진에 지시 합니다. 이 파일은 `.ruleset` 확장을 보유 하 고 있는 모든 위치에 저장할 수 있으며 인수의 전체 경로를 제공 합니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

**/analyze: 플러그** 인 *플러그 인-dll*\
코드 분석 실행의 일부로 지정 된 PREfast 플러그 인을 사용 하도록 설정 합니다.

::: moniker range="<=vs-2017"

LocalEspC는 C261XX 경고 범위에서 동시성 관련 코드 분석 검사를 구현 하는 플러그 인입니다. 예: [26100](/cpp/code-quality/c26100), [C26101](/cpp/code-quality/c26101), ..., [C26167](/cpp/code-quality/c26167).

LocalEspC를 실행 하려면이 컴파일러 옵션인 **/analyze: Plugin LocalEspC** 을 사용 합니다.

::: moniker-end
::: moniker range=">=vs-2019"

ConcurrencyCheck는 C261XX 경고 범위에서 동시성 관련 코드 분석 검사를 구현 합니다. 예: [26100](/cpp/code-quality/c26100), [C26101](/cpp/code-quality/c26101), ..., [C26167](/cpp/code-quality/c26167).

ConcurrencyCheck를 실행 하려면 먼저 개발자 명령 프롬프트에서 다음 명령을 실행 합니다.

```cmd
set Esp.Extensions=ConcurrencyCheck.dll
```

그런 다음이 컴파일러 옵션인 **/analyze: Plugin EspXEngine**을 사용 합니다.

::: moniker-end

CppCoreCheck를 실행 하려면 먼저 개발자 명령 프롬프트에서 다음 명령을 실행 합니다.

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

그런 다음이 컴파일러 옵션인 **/analyze: Plugin EspXEngine**을 사용 합니다.

## <a name="remarks"></a>주의

자세한 내용은 c/ [C++ 개요에 대 한 코드 분석](/cpp/code-quality/code-analysis-for-c-cpp-overview) 및 [c/C++ 경고에 대 한 코드 분석](/cpp/code-quality/code-analysis-for-c-cpp-warnings)을 참조 하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **코드 분석** > **일반** 속성 페이지를 선택 합니다.

1. 하나 이상의 **코드 분석** 속성을 수정 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)\
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
