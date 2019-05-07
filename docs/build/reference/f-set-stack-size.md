---
title: /F(스택 크기 설정)
ms.date: 11/04/2016
f1_keywords:
- /f
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
ms.openlocfilehash: 9db595daa7de7820b594a8515ece7481b4382c98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293097"
---
# <a name="f-set-stack-size"></a>/F(스택 크기 설정)

프로그램의 스택 크기를 바이트 단위로 설정합니다.

## <a name="syntax"></a>구문

> **/F** *number*

## <a name="arguments"></a>인수

*number*<br/>
스택 크기 (바이트)입니다.

## <a name="remarks"></a>설명

이 옵션이 없다면 스택 크기는 기본값인 1MB로 설정됩니다. *number* 인수는 10진수 또는 C 언어 표기법의 수가 될 수 있습니다. 인수의 범위는 1에서 부터 링커가 허용하는 최대 스택 크기까지 입니다. 링커는 가장 가까운 4 바이트에 지정된 값으로 반올림합니다. **/F**와 *number* 사이 공백은 선택 사항입니다.

프로그램이 스택 오버플로 메시지를 받는다면 스택 크기를 증가 해야 합니다.

다음과 같이 스택 크기를 설정할 수 있습니다.

- **/STACK** 링커 옵션을 사용합니다. 자세한 내용은 [/STACK](stack.md)을 참조합니다.

- .exe 파일에서 EDITBIN를 사용합니다. 자세한 내용은 [EDITBIN 참조](editbin-reference.md)을 참조합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
