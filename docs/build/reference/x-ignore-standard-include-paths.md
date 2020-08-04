---
title: /X(표준 포함 경로 무시)
ms.date: 07/31/2020
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLCompilerTool.IgnoreStandardIncludePath
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
ms.openlocfilehash: 652feeb200b7106aaca1ed7264f1e25c088a3dab
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520410"
---
# <a name="x-ignore-standard-include-paths"></a>`/X`(표준 포함 경로 무시)

컴파일러가 PATH 및 INCLUDE 환경 변수에 지정 된 디렉터리에서 포함 파일을 검색 하지 않도록 합니다.

## <a name="syntax"></a>구문

> **`/X`**

## <a name="remarks"></a>설명

[ `/I` (추가 포함 디렉터리)](i-additional-include-directories.md) 옵션과 함께이 옵션을 사용 하 여 표준 포함 파일에 대 한 대체 경로를 지정할 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**  >  **C/c + +**  >  **전처리기** 속성 페이지를 선택 합니다.

1. **표준 포함 경로 무시** 속성을 수정 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>을 참조하세요.

## <a name="example"></a>예제

다음 명령에서는 **`/X`** PATH 및 include 환경 변수에 의해 지정 된 위치를 무시 하도록 컴파일러에 지시 하 고 **`/I`** 포함 파일을 검색할 디렉터리를 지정 합니다.

```cmd
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>참조

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
