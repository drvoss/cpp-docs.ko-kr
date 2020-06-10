---
title: /Oy(프레임 포인터 생략)
ms.date: 11/19/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
ms.openlocfilehash: 7884f52cc22766c6b1a864fc01abcd73f92cfabb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319969"
---
# <a name="oy-frame-pointer-omission"></a>/Oy(프레임 포인터 생략)

호출 스택에서 프레임 포인터를 생성하지 않습니다.

## <a name="syntax"></a>구문

> /Oy [-]

## <a name="remarks"></a>설명

이 옵션을 설정하면 프레임 포인터를 설정하고 제거할 필요가 없기 때문에 함수 호출 속도가 빨라집니다. 또한 일반 용도를 위해 레지스터를 하나 더 해제합니다.

**/Oy**는 프레임 포인터를 생략할 수 있도록 설정하고 **/Oy-** 는 생략을 사용하지 않도록 설정합니다. x64 컴파일러에서는 **/Oy**와 **/Oy-** 를 사용할 수 없습니다.

코드에 프레임 기반 주소 지정이 필요한 경우 **/Ox** 옵션 뒤에 **/Oy-** 옵션을 지정하거나 프레임 기반 주소지정을 통해 최대 최적화를 얻으려면 "**y**"및 **off** 인수와 함께 [최적화](../../preprocessor/optimize.md)를 사용합니다. 컴파일러는 프레임 기반 주소 지정이 필요한 대부분의 경우를 감지합니다.(예를 들어 `_alloca`, `setjmp` 함수 및 구조적된 예외 처리를 사용합니다.)

[/Ox(최대 속도 최적화 사용)](ox-full-optimization.md)과 [/O1, /O2(크기 최소화, 속도 최대화)](o1-o2-minimize-size-maximize-speed.md) 옵션은 **/Oy**를 의미합니다. **/Ox**, **/O1** 또는 **/O2** 옵션 뒤에 **/Oy-** 를 지정하면 명시적이건 암시적이건 **/Oy**를 비활성화합니다.

컴파일러에서 프레임 포인터 정보를 표시하지 않으므로 **/Oy** 컴파일러 옵션을 사용하면 디버거를 사용하기가 더 어려워집니다. 디버그 컴파일러 옵션([/Z7, /Zi, /ZI](z7-zi-zi-debug-information-format.md))을 지정하는 경우 다른 최적화 컴파일러 옵션 다음에 **/Oy-** 옵션을 지정하는 것이 좋습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **최적화** 속성 페이지를 선택합니다.

1. **프레임 포인터 생략** 속성을 수정합니다. 이 속성은 **/Oy** 옵션만 추가하거나 제거합니다. **/Oy-** 옵션을 추가하려면 **명령줄** 속성 페이지를 선택하고 **추가 옵션**을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
