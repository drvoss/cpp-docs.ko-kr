---
title: /FI(강제 포함 파일 이름 지정)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
ms.openlocfilehash: 6460f75e2cad81bc1dcc540e3c687de5d0dc0d32
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439792"
---
# <a name="fi-name-forced-include-file"></a>/FI(강제 포함 파일 이름 지정)

전처리기로 하여금 지정된 헤더파일을 처리하도록 합니다.

## <a name="syntax"></a>구문

```
/FI[ ]pathname
```

## <a name="remarks"></a>설명

이 옵션은 명령줄, CL 환경 변수 또는 명령 파일에 지정 된 모든 소스 파일의 첫 번째 줄에 있는 `#include` 지시문에 큰따옴표를 사용 하 여 파일을 지정 하는 것과 동일한 효과를 가집니다. 여러 **/fi** 옵션을 사용 하는 경우 파일은 CL에서 처리 하는 순서 대로 포함 됩니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **고급** 속성 페이지를 클릭 합니다.

1. **강제 포함 파일** 속성을 수정 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)
