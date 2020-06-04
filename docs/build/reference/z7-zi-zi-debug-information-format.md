---
title: /Z7, /Zi, /ZI(디버깅 정보 형식)
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /ZI
- /Zi
- /Z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
helpviewer_keywords:
- C7 compatible compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
ms.openlocfilehash: aeaf435874b6d6b9dbc8a3d12ec06d38bf33aaae
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078259"
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI(디버깅 정보 형식)

프로그램에 대해 생성 되는 디버깅 정보의 형식과이 정보를 개체 파일이 나 PDB (프로그램 데이터베이스) 파일에 유지할지 여부를 지정 합니다.

## <a name="syntax"></a>구문

> **/Z**{**7**|**i**|**i**}

## <a name="remarks"></a>주의

디버그 모드에서 코드를 컴파일하고 빌드할 때 컴파일러는 디버거에서 사용할 함수 및 변수, 형식 정보 및 줄 번호 위치에 대 한 기호 이름을 생성 합니다. 이 기호화 된 디버깅 정보는 컴파일러에 의해 생성 된 개체 파일 (.obj 파일) 또는 실행 파일에 대 한 별도의 PDB 파일 (.pdb 파일)에 포함 될 수 있습니다.  디버그 정보 형식 옵션은 다음 섹션에 설명 되어 있습니다.

### <a name="none"></a>없음

기본적으로 디버그 정보 형식 옵션이 지정 되지 않은 경우 컴파일러는 디버깅 정보를 생성 하지 않으므로 컴파일이 더 빠릅니다.

### <a name="z7"></a>/Z7

**/Z7** 옵션은 디버거와 함께 사용 하기 위한 전체 기호화 된 디버깅 정보를 포함 하는 개체 파일을 생성 합니다. 이러한 개체 파일과 빌드된 실행 파일은 디버깅 정보가 없는 파일 보다 크게 클 수 있습니다. 기호 디버깅 정보에는 변수의 이름과 형식, 함수 및 줄 번호가 들어 있습니다. PDB 파일이 생성 되지 않습니다.

타사 라이브러리의 디버그 버전 배포자의 경우 PDB 파일을 포함 하지 않는 이점이 있습니다. 그러나 라이브러리 링크 단계 및 디버깅을 수행 하는 동안 미리 컴파일된 헤더에 대 한 개체 파일이 필요 합니다. .Pch 개체 파일에 형식 정보 (코드 없음)만 있는 경우 라이브러리를 빌드할 때 기본적으로 사용 되는 [/Yl (디버그 라이브러리에 Pch 참조 삽입)](yl-inject-pch-reference-for-debug-library.md) 옵션도 사용 해야 합니다.

사용 되지 않는 [/gm (최소 다시 빌드 사용)](gm-enable-minimal-rebuild.md) 옵션은 **/z7** 이 지정 된 경우 사용할 수 없습니다.

### <a name="zi"></a>/ZI

**/Zi** 옵션은 디버거와 함께 사용 하기 위해 기호화 된 모든 디버깅 정보를 포함 하는 별도의 PDB 파일을 생성 합니다. 디버깅 정보는 개체 파일 또는 실행 파일에 포함 되지 않으므로 훨씬 더 작아집니다.

**/Zi** 를 사용 하면 최적화에 영향을 주지 않습니다. 그러나 **/zi** 는 **/debug**를 의미 합니다. 자세한 내용은 [/debug (디버그 정보 생성)](debug-generate-debug-info.md) 를 참조 하세요.

**/Zi** 와 **/clr**을 모두 지정 하면 <xref:System.Diagnostics.DebuggableAttribute> 특성이 어셈블리 메타 데이터에 배치 되지 않습니다. 원하는 경우 소스 코드에서 지정 해야 합니다. 이 특성은 애플리케이션의 런타임 성능에 영향을 줄 수 있습니다. **디버깅** 가능한 특성이 성능에 주는 영향 및 성능 영향을 수정 하는 방법에 대 한 자세한 내용은 [이미지를 더 쉽게 디버깅할 수 있도록 설정](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug)을 참조 하세요.

컴파일러는 PDB 파일의 이름을 *프로젝트*.pdb로 합니다. 프로젝트 외부에서 파일을 컴파일하는 경우 컴파일러는 VC*x*.PDB 라는 pdb 파일을 만듭니다. 여기서 *x* 는 사용 중인 컴파일러 버전의 주 및 부 버전 번호를 연결한 것입니다. 컴파일러는이 옵션을 사용 하 여 만든 각 개체 파일에 PDB의 이름과 타임 스탬프 서명을 식별 하며,이 옵션을 사용 하면 디버거가 기호화 된 정보와 줄 번호 정보 위치를 가리킵니다. PDB 파일의 이름과 서명은 디버거에 로드할 기호의 실행 파일과 일치 해야 합니다. WinDBG 디버거는 `.symopt+0x40` 명령을 사용 하 여 일치 하지 않는 기호를 로드할 수 있습니다. Visual Studio에는 일치 하지 않는 기호를 로드 하는 유사한 옵션이 없습니다.

**/Zi**를 사용 하 여 컴파일된 개체에서 라이브러리를 만드는 경우 라이브러리를 프로그램에 연결할 때 연결 된 .pdb 파일을 사용할 수 있어야 합니다. 따라서 라이브러리를 배포 하는 경우에는 PDB 파일도 배포 해야 합니다. PDB 파일을 사용 하지 않고 디버깅 정보를 포함 하는 라이브러리를 만들려면 **/Z7** 옵션을 선택 해야 합니다. 미리 컴파일된 헤더 옵션을 사용 하면 미리 컴파일된 헤더와 소스 코드의 나머지 부분에 대 한 디버깅 정보가 PDB 파일에 배치 됩니다.

### <a name="zi"></a>/ZI

**/Zi** 옵션은 **/Zi**와 비슷하지만 [편집 하며 계속 하기](/visualstudio/debugger/edit-and-continue-visual-cpp) 기능을 지 원하는 형식으로 PDB 파일을 생성 합니다. 편집 하며 계속 하기 디버깅 기능을 사용 하려면이 옵션을 사용 해야 합니다. 편집 하며 계속 하기 기능은 개발자 생산성에 유용 하지만 코드 크기, 성능 및 컴파일러 규칙에서 문제를 일으킬 수 있습니다. 대부분의 최적화는 편집 하며 계속 하기와 호환 되지 않으므로 **/zi** 를 사용 하면 코드에서 모든 `#pragma optimize` 문을 사용할 수 없습니다. **/Zi** 옵션은 [ &#95; &#95;미리&#95; &#95; 정의 된 줄 매크로](../../preprocessor/predefined-macros.md)를 사용 하는 경우에도 호환 되지 않습니다. **/zi** 를 사용 하 여 컴파일된 코드는 줄을 비 형식의 템플릿  **&#95; &#95;인수로&#95; 사용할 수** 없습니다. 단, **&#95; &#95;줄&#95;** 은 매크로 확장에서 사용할 수 있습니다.

**/Zi** 옵션을 사용 하면 컴파일에서 사용 될 [/Gy (함수 수준 링크 사용)](gy-enable-function-level-linking.md) 및 [/Fc (진단의 소스 코드 파일의 전체 경로)](fc-full-path-of-source-code-file-in-diagnostics.md) 옵션이 모두 강제로 적용 됩니다.

**/Zi** 는 [/Clr (공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md)과 호환 되지 않습니다.

> [!NOTE]
> **/Zi** 옵션은 x86 및 x64 프로세서를 대상으로 하는 컴파일러 에서만 사용할 수 있습니다. ARM 프로세서를 대상으로 하는 컴파일러에서는이 컴파일러 옵션을 사용할 수 없습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++**  > **일반** 속성 페이지를 엽니다.

1. **디버그 정보 형식** 속성을 수정 합니다. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
