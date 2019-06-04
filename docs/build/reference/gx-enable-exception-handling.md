---
title: /GX(예외 처리 사용)
ms.date: 11/04/2016
f1_keywords:
- /gx
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
ms.openlocfilehash: 43be8f6d0f080f0d85568ce5b089751fc68f0e8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292005"
---
# <a name="gx-enable-exception-handling"></a>/GX(예외 처리 사용)

이 컴파일 옵션은 더 이상 사용되지 않습니다. `extern "C"`를 사용하여 선언된 함수가 절대 예외를 throw 하지 않는다는 가정하에 동기 예외 처리를 활성화 합니다.

## <a name="syntax"></a>구문

```
/GX
```

## <a name="remarks"></a>설명

**/GX**는 더이상 사용 되지 않습니다. 대신 [/EHsc](eh-exception-handling-model.md) 옵션을 사용 합니다. 사용되지 않는 컴파일러 옵션의 목록은 **컴파일러 옵션 및 사용 되지 않음** 섹션의 [컴파일러 옵션 범주별 목록](compiler-options-listed-by-category.md)을 참조합니다.

기본적으로 **/EHsc**는 **/GX**에 해당하는 것으로 Visual Studio 개발 환경을 사용하여 컴파일하는 경우 적용 됩니다. 명령줄 도구를 사용하는 경우 예외처리를 하지 않도록 지정 됩니다. 이것은 **/GX-**와 동일 합니다.

자세한 내용은 [ C++ 예외 처리](../../cpp/cpp-exception-handling.md)를 참조합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 탐색 창에서 **구성 속성**, **C /C++**, **명령줄**을 선택합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/EH(예외 처리 모델)](eh-exception-handling-model.md)
