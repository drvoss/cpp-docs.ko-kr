---
title: /Fo(개체 파일 이름)
description: Visual Studio의 Microsoft C++ /Fo(개체 파일 이름) 컴파일러 옵션에 대한 참조 가이드입니다.
ms.date: 04/20/2020
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
ms.openlocfilehash: cd22ba745128fe1df67853d98c1495491b9ca840
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748967"
---
# <a name="fo-object-file-name"></a>/Fo(개체 파일 이름)

기본값 대신 사용할*`.obj`* 개체 () 파일 이름 또는 디렉터리지정합니다.

## <a name="syntax"></a>구문

> **`/Fo`**_경로_

## <a name="remarks"></a>설명

**`/Fo`** 컴파일러 옵션을 사용하여 CL 컴파일러 명령에서 생성된 모든 개체 파일에 대한 출력 디렉터리를 설정할 수 있습니다. 또는 단일 개체 파일의 이름을 바꿀 때 사용할 수 있습니다.

기본적으로 컴파일러에서 생성된 개체 파일은 현재 디렉터리에 배치됩니다. 소스 파일의 기본 이름과 확장인이 *`.obj`* 부여됩니다.

이 **`/Fo`** 옵션을 사용하여 개체 파일의 이름을 바꾸려면 출력 파일 이름을 *경로 이름* 인수로 지정합니다. 개체 파일의 이름을 바꿀 때 원하는 이름과 확장명을 사용할 수 있지만 을 *`.obj`* 사용하는 것이 좋습니다. 컴파일러는 컴파일할 두 개 이상의 소스 파일을 지정한 경우 **`/Fo`** 파일 이름을 지정하는 경우 명령줄 오류 D8036을 생성합니다.

CL 명령에서 만든 모든 개체 파일에 대한 출력 디렉터리를 설정하는 **`/Fo`** 옵션을 사용하려면 디렉터리를 *pathname* 인수로 지정합니다. 디렉터리는 *경로 이름* 인수에서 후행 슬래시로 표시됩니다. 지정된 디렉터리가 있어야 합니다. 자동으로 만들어지지 않습니다.

## <a name="example"></a>예제

다음 명령줄은 드라이브 D의 기존 * \\디렉터리, 중간*에 *sample.obj라는* 개체 파일을 만듭니다.

```cmd
CL /Fo"D:\intermediate\" /EHsc /c sample.cpp
```

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>비주얼 스튜디오 또는 프로그래밍 방식으로 옵션 설정

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. 구성 **속성** > **C/C++** > **출력 파일** 속성 페이지를 선택합니다.

1. 개체 **파일 이름** 속성을 수정하여 출력 디렉터리를 설정합니다. IDE에서 개체 파일의 *`.obj`* 확장명이 있어야 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>을 참조하세요.

## <a name="see-also"></a>참조

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)
