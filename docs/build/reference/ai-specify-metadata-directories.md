---
title: /AI(메타데이터 디렉터리 지정)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
ms.openlocfilehash: 3633cfe34a4f9c627f84cf401cb559f02f8c8229
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273224"
---
# <a name="ai-specify-metadata-directories"></a>/AI(메타데이터 디렉터리 지정)

`#using` 지시문에 전달된 파일 참조를 확인하기 위해 컴파일러가 검색할 디렉터리를 지정합니다.

## <a name="syntax"></a>구문

> **/AI**_directory_

## <a name="arguments"></a>인수

*directory*<br/>
검색할 컴파일러의 디렉터리나 경로

## <a name="remarks"></a>설명

디렉터리를 하나만 전달할 수는 **/AI** 호출 합니다. 하나를 지정할 **/AI** 컴파일러로 검색 하려는 각 경로 대 한 옵션입니다. 예를 들어에 대 한 컴파일러 검색 경로에 C:\Project\Meta와 C:\Common\Meta를 모두 추가 하려면 `#using` 지시문을 추가 `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` 컴파일러 명령줄에 각 디렉터리를 추가 하거나 합니다 **추가 #using 디렉터리** Visual Studio의 속성입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **구성 속성** > **C/C++** > **일반** 속성 페이지.

1. 수정 된 **추가 #using 디렉터리** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[#using 지시문](../../preprocessor/hash-using-directive-cpp.md)
