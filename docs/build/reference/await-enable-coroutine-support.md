---
title: /await(코루틴 지원 사용)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: 53a6cf4b3d14ee97a324fa01f83c0d0fee61180b
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373699"
---
# <a name="await-enable-coroutine-support"></a>/await(코루틴 지원 사용)

**/Swait** 컴파일러 옵션을 사용 하 여 코 루틴에 대 한 컴파일러 지원을 사용 하도록 설정 합니다.

## <a name="syntax"></a>구문

> /await

## <a name="remarks"></a>설명

**/Swait** 컴파일러 옵션을 사용 하면 c + + 코 루틴 및 키워드 **co_await**, **co_yield**및 **co_return**에 대 한 컴파일러 지원을 사용할 수 있습니다. 이 옵션은 기본적으로 해제되어 있습니다. Visual Studio의 코 루틴 지원에 대 한 자세한 내용은 [Visual Studio 팀 블로그](https://devblogs.microsoft.com/cppblog/category/coroutine/)를 참조 하세요. 코 루틴 표준 제안에 대 한 자세한 내용은 [N4628 작업 초안, 코 루틴 용 c + + 확장 기술 사양](https://wg21.link/n4628)을 참조 하십시오.

**/Swait** 옵션은 Visual Studio 2015부터 사용할 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다.

1. **구성 속성**에서 **C/c + +** 폴더를 확장 하 고 **명령줄** 속성 페이지를 선택 합니다.

1. **추가 옵션** 상자에 **/wait** 컴파일러 옵션을 입력 합니다. **확인** 또는 **적용** 을 선택 하 여 변경 내용을 저장 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
