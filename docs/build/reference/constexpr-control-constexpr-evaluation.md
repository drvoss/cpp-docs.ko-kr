---
title: /constexpr(컨트롤 constexpr 평가)
ms.date: 08/15/2017
f1_keywords:
- /constexpr
- -constexpr
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
ms.openlocfilehash: 4d3f33a64dcebfc40778f81354cb5067a5239ace
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825593"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr(컨트롤 constexpr 평가)

**/Oers** 컴파일러 옵션을 사용 하 여 컴파일 시간에 **constexpr** 평가에 대 한 매개 변수를 제어 합니다.

## <a name="syntax"></a>구문

> **/cerx: 깊이**<em>N</em>\
> **/constexpr: backtrace**<em>N</em>\
> **/constexpr:**<em>N</em> 단계

## <a name="arguments"></a>인수

**깊이**<em>n</em> 재귀 **constexpr** 함수 호출의 깊이를 *n* 수준으로 제한 합니다. 기본값은 512입니다.

**backtrace**<em>n</em> 진단에서 최대 *n* 개의 **constexpr** 평가를 표시 합니다. 기본값은 10입니다.

n **단계**는 *n* 단계 후 **constexpr** 평가<em>를 종료 합니다</em> . 기본값은 10만입니다.

## <a name="remarks"></a>설명

**/Sers** 컴파일러 옵션은 **constexpr** 식의 컴파일 타임 계산을 제어 합니다. 평가 단계, 재귀 수준 및 backtrace 깊이는 컴파일러에서 **constexpr** 평가에 너무 많은 시간을 소비 하지 않도록 제어 됩니다. **Constexpr** 언어 요소에 대 한 자세한 내용은 [Constexpr (c + +)](../../cpp/constexpr-cpp.md)을 참조 하세요.

**/Oere** 옵션은 Visual Studio 2015부터 사용할 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다.

2. **구성 속성**에서 **C/c + +** 폴더를 확장 하 고 **명령줄** 속성 페이지를 선택 합니다.

3. **추가 옵션** 상자에/cererers 옵션을 입력 합니다. **/constexpr** **확인** 또는 **적용** 을 선택 하 여 변경 내용을 저장 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
