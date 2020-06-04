---
title: /homeparams(스택에 레지스터 매개 변수 복사)
ms.date: 12/17/2018
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: a1f9269c7deae6c9ae2e4f198006ad09dd37abc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291420"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams(스택에 레지스터 매개 변수 복사)

함수 전달 시 레지스터에 전달된 매개 변수를 스택의 해당 위치에 강제로 기록합니다.

## <a name="syntax"></a>구문

> **/homeparams**

## <a name="remarks"></a>설명

이 컴파일러 옵션은 x64를 대상으로 하는 네이티브 및 크로스 컴파일러에서만 사용할 수 있습니다.

x64 호출 규칙에 따라 레지스터에 전달된 매개 변수에 대해서도 모든 매개 변수에 스택 공간을 할당해야 합니다. 자세한 내용은 [매개 변수 전달](../../build/x64-calling-convention.md#parameter-passing)을 참조합니다. 기본적으로 레지스터 매개 변수는 릴리스 빌드에서 할당된 스택 공간에 복사되지 않습니다. 따라서 프로그램의 최적화된 릴리스 빌드를 디버그하기가 어려워집니다.

릴리스 빌드의 경우 **/homeparams** 옵션을 사용하여 컴파일러에서 레지스터 매개 변수를 스택에 복사하여 응용 프로그램을 디버깅할 수 있도록 할 수 있습니다. **/homeparams** 옵션은 스택에 레지스터 매개 변수를 로드하는 추가 작업이 필요하기 때문에 성능이 떨어질 수 있습니다.

디버그 빌드에서 스택은 항상 레지스터에서 전달된 매개 변수로 채워집니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C /C++** > **명령줄** 속성 페이지를 엽니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
