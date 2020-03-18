---
title: /Fp (이름 &period;pch 파일)
description: /Fp 컴파일러 옵션을 사용 하 여 미리 컴파일된 헤더 파일 이름을 지정 합니다.
ms.date: 05/31/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
ms.openlocfilehash: d62c5bd9fc7920c0a2a5530879680fad2a01d39a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439789"
---
# <a name="fp-name-periodpch-file"></a>/Fp (이름 &period;pch 파일)

기본 경로 이름을 사용하는 대신 미리 컴파일된 헤더의 경로 이름을 제공합니다.

## <a name="syntax"></a>구문

> **/Fp**<em>경로 이름</em>

## <a name="remarks"></a>설명

[/Yc 옵션 (미리 컴파일된 헤더 파일 만들기)](yc-create-precompiled-header-file.md) 또는 [/yu (미리 컴파일된 헤더 파일 사용)](yu-use-precompiled-header-file.md) 를 사용 하 여 미리 컴파일된 헤더 (PCH) 파일의 경로와 파일 이름을 **지정 합니다.** 기본적으로 **/yc** 옵션은 소스 파일의 기본 이름과 *pch* 확장명을 사용 하 여 pch 파일 이름을 만듭니다.

확장명을 *pathname*의 일부로 지정 하지 않으면 *pch* 확장이 가정 됩니다. *Pathname*끝에 슬래시 ( **/** )를 사용 하 여 디렉터리 이름을 지정 하는 경우 기본 파일 이름은 vc*버전*0 .Pch입니다. 여기서 *version* 은 Visual Studio 도구 집합의 주 버전입니다. 이 디렉터리는 존재 해야 합니다. 그렇지 않으면 오류 C1083 생성 됩니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++**  > **미리 컴파일된 헤더** 속성 페이지를 엽니다.

1. **미리 컴파일된 헤더 출력 파일** 속성을 수정 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="examples"></a>예

프로그램의 디버그 빌드에 대해 미리 컴파일된 헤더 파일의 별도의 명명 된 버전을 만들려면 다음과 같은 명령을 지정할 수 있습니다.

```CMD
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

다음 명령은 MYPCH.pch라는 미리 컴파일된 헤더 파일을 사용하도록 지정합니다. 컴파일러는 MYAPP의 끝을 통해 PROG의 소스 코드를 미리 컴파일하고 미리 컴파일된 코드를 MYPCH에 넣습니다. 그런 다음 MYPCH의 내용을 사용 하 고 나머지 프로그램을 컴파일하여 .obj 파일을 만듭니다. 이 예제의 출력은 PROG.exe라는 파일입니다.

```CMD
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>참고 항목

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)
