---
title: /doc(문서 주석 처리)(C/C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
ms.openlocfilehash: 90f63a972245114424b64d4131420dcb4e1e925a
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342921"
---
# <a name="doc-process-documentation-comments-cc"></a>/doc(문서 주석 처리)(C/C++)

컴파일러에서 문서 주석을 처리 소스 코드 파일에 문서 주석이 포함된 각 소스 코드 파일에 대한 .xdc 파일을 만듭니다.

## <a name="syntax"></a>구문

> **/doc**[*name*]

## <a name="arguments"></a>인수

*name*<br/>
컴파일러를 통해 생성 되는.xdc 파일의 이름입니다. 하나의.cpp 파일은 컴파일에서 전달 될 때만 유효 합니다.

## <a name="remarks"></a>설명

.Xdc 파일 xdcmake.exe 사용 하 여.xml 파일로 처리 됩니다. 자세한 내용은 [XDCMake 참조](xdcmake-reference.md)합니다.

소스 코드 파일에 문서 주석을 추가할 수 있습니다. 자세한 내용은 [문서 주석에 대한 권장 태그](recommended-tags-for-documentation-comments-visual-cpp.md)를 참조하세요.

IntelliSense를 사용 하 여 생성 된.xml 파일을 사용 하려면 지원 및.xml 파일을 저장 하려는 어셈블리와 동일한 어셈블리와 동일한 디렉터리에.xml 파일의 파일 이름을 지정 합니다. Visual Studio 프로젝트에서 어셈블리를 참조할 때.xml 파일을 찾을 수도 됩니다. 자세한 내용은 [IntelliSense를 사용 하 여](/visualstudio/ide/using-intellisense) 하 고 [XML 코드 주석 제공](/visualstudio/ide/supplying-xml-code-comments)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **출력 파일** 속성 페이지를 선택합니다.

1. **XML 문서 파일 생성** 속성을 수정합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
