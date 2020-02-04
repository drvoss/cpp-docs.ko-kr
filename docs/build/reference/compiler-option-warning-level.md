---
title: /w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX(경고 수준)
description: Microsoft C/C++ 컴파일러 옵션에 대 한 참조:/W,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/wd,/we,/Wo,/WV 및/WX.
ms.date: 01/31/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarningLevel
- VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarnAsError
- VC.Project.VCCLWCECompilerTool.WarnAsError
- /wx
- VC.Project.VCCLWCECompilerTool.WarningLevel
- /wall
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- /Wv
- /w0
- /w1
- /w2
- /w3
- /w4
- /wd
- /we
- /wo
helpviewer_keywords:
- /W1 compiler option [C++]
- w compiler option [C++]
- -wo compiler option [C++]
- Warning Level compiler option
- W1 compiler option [C++]
- -we compiler option [C++]
- /WX compiler option [C++]
- -wd compiler option [C++]
- WX compiler option [C++]
- wo compiler option [C++]
- Wall compiler option [C++]
- /w compiler option
- W2 compiler option [C++]
- -W2 compiler option [C++]
- wd compiler option [C++]
- /we compiler option [C++]
- we compiler option [C++]
- -W1 compiler option [C++]
- -W4 compiler option [C++]
- -Wall compiler option [C++]
- /Wall compiler option [C++]
- -W0 compiler option [C++]
- W0 compiler option [C++]
- -WX compiler option [C++]
- /wo compiler option [C++]
- W4 compiler option [C++]
- W3 compiler option [C++]
- /wd compiler option [C++]
- warnings, as errors compiler option
- /W3 compiler option [C++]
- /W0 compiler option [C++]
- /W4 compiler option [C++]
- -W3 compiler option [C++]
- -w compiler option [C++]
- /W2 compiler option [C++]
- /Wv compiler option [C++]
ms.openlocfilehash: 80b6d0c1fe684de9af62683a75f0fd1107a94089
ms.sourcegitcommit: ba4180a2d79d7e391f2f705797505d4aedbc2a5e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "76972169"
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX(경고 수준)

컴파일러가 지정된 컴파일에 대해 경고를 생성하는 방법을 지정합니다.

## <a name="syntax"></a>구문

> **/w**\
> **/W0**\
> **/W1**\
> **/W2**\
> **/W3**\
> **/W4**\
> **/Wall**\
> **/Wv**\[ **:** _version_] \
> **/Wx**\
> **/w1**_경고_\
> **/w2**_경고_\
> **/w3**_경고_\
> **/w4**_경고_\
> **/wd**_경고_\
> **/we**_경고_\
> **/wo**_warning_

## <a name="remarks"></a>주의

경고 옵션은 표시할 컴파일러 경고와 전체 컴파일의 경고 동작을 지정 합니다.

경고 옵션 및 관련 인수는 다음 표에 설명 되어 있습니다.

옵션 | 설명
------ | -----------
**/w** | 모든 컴파일러 경고를 표시 하지 않습니다.
**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4** | 컴파일러에서 생성 되는 경고 수준을 지정 합니다. 유효한 경고 수준 범위는 0에서 4 사이입니다.<br />**/W0** 모든 경고를 표시 하지 않습니다. **/W**와 동일 합니다.<br />**/W1** 는 수준 1 (심각도) 경고를 표시 합니다. **/W1** 는 명령줄 컴파일러의 기본 설정입니다.<br />**/W2** 는 수준 1 및 수준 2 (중요) 경고를 표시 합니다.<br />**/W3** 는 수준 1, 수준 2 및 수준 3 (생산 품질) 경고를 표시 합니다. **/W3** 는 IDE의 기본 설정입니다.<br />**/W4** 는 수준 1, 수준 2, 수준 3 경고 및 기본적으로 해제 되지 않는 모든 수준 4 (정보) 경고를 표시 합니다. 이 옵션을 사용 하 여 보풀이 아닌 경고를 제공 하는 것이 좋습니다. 새 프로젝트의 경우 모든 컴파일에서 **/W4** 를 사용 하는 것이 가장 좋을 수 있습니다. 이 옵션은 찾기 어려운 코드 오류를 최소화 하는 데 도움이 됩니다.
**/Wall** | **/W4** 에 의해 표시 되는 모든 경고와 **/W4** 에 포함 되지 않은 모든 경고 (예: 기본적으로 해제 된 경고)를 표시 합니다. 자세한 내용은 [기본적으로 해제 되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조 하세요.
**/Wv**\[ **:** _version_] | 버전 컴파일러 버전 및 이전 *버전* 에 도입 된 경고만 표시 합니다. 최신 버전의 컴파일러로 마이그레이션할 때이 옵션을 사용 하 여 코드에서 새 경고를 표시 하지 않을 수 있습니다. 이를 통해 기존 빌드 프로세스를 수정 하는 동안 유지 관리할 수 있습니다. 선택적 매개 변수 *버전* 은 *nn*\[형식을 사용 합니다. *mm*\[입니다. *aaaaa-bbbbb-ccccc-dddddd-eeeeee*]], 여기서 *nn* 은 주 버전 번호, *mm* 은 선택적 부 버전 번호, *aaaaa-bbbbb-ccccc-dddddd-eeeeee* 는 컴파일러의 선택적 빌드 번호입니다. 예를 들어 **/Wv: 17** 을 사용 하 여 Visual Studio 2012 (주 버전 17) 또는 이전 버전에 도입 된 경고만 표시 합니다. 즉, 17 개 이하의 주 버전 번호를 포함 하는 모든 버전의 컴파일러에서 경고를 표시 합니다. Visual Studio 2013 (주 버전 18) 이상에서 도입 된 경고를 표시 하지 않습니다. 기본적으로 **/Wv** 는 현재 컴파일러 버전 번호를 사용 하며 경고는 표시 되지 않습니다. 컴파일러 버전에서 발생 하는 경고에 대 한 자세한 내용은 컴파일러 [버전 별 컴파일러 경고](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md)를 참조 하세요.
**/WX** | 모든 컴파일러 경고를 오류로 처리합니다. 새 프로젝트의 경우 모든 컴파일에서 **/wx** 를 사용 하는 것이 가장 좋을 수 있습니다. 모든 경고를 해결 하면 찾기 어려운 코드 오류를 최소화 하는 것이 가능 합니다.<br /><br /> 링커에는 **/wx** 옵션도 있습니다. 자세한 내용은 [/WX(링커 경고를 오류로 처리)](wx-treat-linker-warnings-as-errors.md)를 참조하세요.

다음 옵션은 서로 함께 사용할 수 없습니다. 이 그룹에서 마지막으로 지정 된 옵션은 적용 되는 옵션입니다.

옵션 | 설명
------ | -----------
**/w1**_nnnn_<br /><br /> **/w2**_nnnn_<br /><br /> **/w3**_nnnn_<br /><br /> **/w4**_nnnn_ | _Nnnn_으로 지정 된 경고 번호에 대 한 경고 수준을 설정 합니다. 이러한 옵션을 사용 하면 특정 경고 수준이 설정 된 경우 해당 경고에 대 한 컴파일러 동작을 변경할 수 있습니다. 이러한 옵션을 다른 경고 옵션과 함께 사용 하 여 Visual Studio에서 제공 하는 기본이 아닌 경고에 대해 고유한 코딩 표준을 적용할 수 있습니다.<br /><br /> 예를 들어 **/w34326** 를 설정 하면 C4326이 수준 1이 아닌 수준 3 경고로 생성 됩니다. **/W34326** 옵션과 **/W2** 옵션을 모두 사용 하 여 컴파일하는 경우에는 경고 C4326이 생성 되지 않습니다.
**/wd**_nnnn_ | _Nnnn_으로 지정 된 컴파일러 경고를 표시 하지 않습니다.<br /><br /> 예를 들어 **/wd4326** 은 컴파일러 경고 C4326을 표시 하지 않습니다.
**/we**_nnnn_ | _Nnnn_ 으로 지정 된 컴파일러 경고를 오류로 처리 합니다.<br /><br /> 예를 들어 **/we4326** 은 컴파일러에서 경고 번호 C4326을 오류로 처리 하도록 합니다.
**/wo**_nnnn_ | _Nnnn_ 으로 지정 된 컴파일러 경고를 한 번만 보고 합니다.<br /><br /> 예를 들어, **/wo4326** 는 컴파일러에서 처음 발견 될 때 경고 C4326이 한 번만 보고 되도록 합니다.

미리 컴파일된 헤더를 만들 때 경고 옵션을 사용 하면 해당 설정을 유지 합니다. 미리 컴파일된 헤더를 사용 하면 동일한 경고 옵션이 다시 적용 됩니다. 미리 컴파일된 헤더 경고 옵션을 재정의 하려면 명령줄에서 다른 경고 옵션을 설정 합니다.

[#Pragma warning](../../preprocessor/warning.md) 지시문을 사용 하 여 컴파일 타임에 특정 소스 파일에 보고 되는 경고 수준을 제어할 수 있습니다.

소스 코드의 경고 pragma 지시문은 **/w** 옵션의 영향을 받지 않습니다.

[빌드 오류 설명서](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) 에서는 경고 및 경고 수준에 대해 설명 하 고 특정 문이 의도 한 대로 컴파일되지 않을 수 있는 이유를 나타냅니다.

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 컴파일러 옵션을 설정 하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **/W0**, **/W1**, **/W2**, **/W3**, **/W4**, **/Wall**, **/Wv**, **/wx**또는 **/WX-** 옵션을 설정 하려면 **구성 속성** > **C++ C/**  > **일반**을 선택 합니다.

   - **/W0**, **/W1**, **/W2**, **/W3**, **/W4**또는 **/Wall** 옵션을 설정 하려면 **경고 수준** 속성을 수정 합니다.

   - **/Wx** 또는 **/WX-** 옵션을 설정 하려면 **경고를 오류로 처리** 속성을 수정 합니다.

   - **/Wv** 옵션에 대 한 버전을 설정 하려면 **경고 버전** 속성에 컴파일러 버전 번호를 입력 합니다.

1. **/Wd** 또는 **/we** 옵션을 설정 하려면 **구성 속성** > **C/C++**  > **고급** 속성 페이지를 선택 합니다.

   - **/Wd** 옵션을 설정 하려면 **특정 경고 사용 안 함** 속성 드롭다운 컨트롤을 선택한 다음 **편집**을 선택 합니다. **특정 경고 사용 안 함** 대화 상자의 편집 상자에 경고 번호를 입력 합니다. 둘 이상의 경고를 입력 하려면 세미콜론 ( **;** )을 사용 하 여 값을 구분 합니다. 예를 들어 C4001 및 C4010를 모두 사용 하지 않도록 설정 하려면 **4001; 4010**를 입력 합니다. **확인** 을 선택 하 여 변경 내용을 저장 하 고 **속성 페이지** 대화 상자로 돌아갑니다.

   - **/We** 옵션을 설정 하려면 **특정 경고를 오류로 처리** 속성 드롭다운 컨트롤을 선택한 다음 **편집**을 선택 합니다. **특정 경고를 오류로 처리** 대화 상자에서 편집 상자에 경고 번호를 입력 합니다. 둘 이상의 경고를 입력 하려면 세미콜론 ( **;** )을 사용 하 여 값을 구분 합니다. 예를 들어 C4001 및 C4010를 모두 오류로 처리 하려면 **4001; 4010**를 입력 합니다. **확인** 을 선택 하 여 변경 내용을 저장 하 고 **속성 페이지** 대화 상자로 돌아갑니다.

1. **/Wo** 옵션을 설정 하려면 **구성 속성** > **C++ C/**  > **명령줄** 속성 페이지를 선택 합니다. **추가 옵션** 상자에서 컴파일러 옵션을 입력합니다.

1. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-the-compiler-option-programmatically"></a>프로그래밍 방식으로 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.

## <a name="see-also"></a>참조

[MSVC 컴파일러 옵션](compiler-options.md)\
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
