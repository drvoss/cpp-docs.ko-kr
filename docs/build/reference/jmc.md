---
title: /JMC(내 코드만 디버깅)
ms.date: 08/20/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.SupportJustMyCode
helpviewer_keywords:
- /JMC compiler option [C++]
- Just my code [C++]
- -JMC compiler option [C++]
- User code, debugging
- JMC compiler option [C++]
ms.openlocfilehash: 90fcad40b3322f8a8ae7ffc58875c2850f143138
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341004"
---
# <a name="jmc-just-my-code-debugging"></a>/JMC(내 코드만 디버깅)

Visual Studio 디버거에서 네이티브 *내 코드만 디버깅*을 위한 컴파일러 지원을 지정합니다. 이 옵션은 Visual Studio에서 시스템, 프레임워크, 라이브러리 및 기타 사용자가 호출하지 않은 부분을 건너뛰거나 및 호출 스택 창에서 해당 호출을 축소하도록 하는 사용자 설정을 지원합니다. **/JMC** 컴파일러 옵션은 Visual Studio 2017 버전 15.8부터 사용할 수 있습니다.

## <a name="syntax"></a>구문

> **/JMC**\[ **-** ]

## <a name="remarks"></a>설명

Visual Studio [내 코드만 디버깅](/visualstudio/debugger/just-my-code) 설정은 Visual Studio 디버거가 시스템, 프레임워크, 라이브러리 및 기타 사용자가 호출하지 않는 코드를 단계별로 수행할지 여부를 지정합니다. **/JMC** 컴파일러 옵션은 네이티브 C++ 코드에서 내 코드만 디버깅을 지원합니다. **/JMC**가 활성화되면 컴파일러는 함수 프롤로그에서 도우미 함수 `__CheckForDebuggerJustMyCode`에 대한 호출을 삽입합니다. 도우미 함수는 Visual Studio 디버거 내 코드만 디버깅 단계 작업을 지원하는 후크를 제공합니다. Visual Studio 디버거에서 내 코드만 디버깅을 사용하도록 설정하려면 **도구**  >  **옵션**을 선택한 다음 **디버깅**  >  **일반**  >  **내 코드만 디버깅 사용**에서 옵션을 설정합니다.

**/JMC** 옵션을 사용하려면 코드가 `__CheckForDebuggerJustMyCode` 도우미 기능을 제공하는 C 런타임 라이브러리(CRT)에 연결되어 있어야 합니다. CRT에 연결되어 있지 않은 경우 링커 오류 **LNK2019: 외부 기호 __CheckForDebuggerJustMyCode를 확인할 수 없습니다.** 가 표시될 수 있습니다. 이 오류를 해결하려면 CRT에 대한 연결하거나 **/JMC** 옵션을 사용하지 않도록 설정합니다.

기본적으로 **/JMC** 컴파일러 옵션은 해제되어 있습니다. 그러나 Visual Studio 2017 버전 15.8부터는 대부분의 Visual Studio 프로젝트 템플릿에서 이 옵션이 사용 설정되어 있습니다. 명시적으로 이 옵션을 사용하지 않으려면 명령줄에서 **/JMC-** 옵션을 사용합니다. Visual Studio에서 프로젝트 속성 페이지 대화 상자를 열고 **구성 속성**  >  **C/C++**  >  **일반** 속성 페이지에서 **내 코드만 디버깅 지원** 속성을 **아니요**로 변경합니다.

자세한 내용은 [내 코드만 디버깅을 사용하여 Visual Studio에서 사용자 코드만 디버그할지 여부 지정](/visualstudio/debugger/just-my-code)의 [C++ 내 코드만 디버깅](/visualstudio/debugger/just-my-code#BKMK_C___Just_My_Code) 및 C++ 팀 블로그 게시물 [C++ Visual Studio에서 내 코드만 디버깅 단계별 실행](https://blogs.msdn.microsoft.com/vcblog/2018/06/29/announcing-jmc-stepping-in-visual-studio/)을 참조합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**  >  **C/C++**  >  **일반** 속성 페이지를 선택하세요.

1. **내 코드만 디버깅 지원** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
