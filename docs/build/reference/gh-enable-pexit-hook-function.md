---
title: /GH(_pexit 후크 함수 사용)
description: 로컬 _pexit 후크 함수를 설정 하는/GH 컴파일러 옵션에 대해 설명 합니다.
ms.date: 07/06/2020
f1_keywords:
- _pexit
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
ms.openlocfilehash: b8fc355503055af8b928874ced39cb8224901d3e
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058609"
---
# <a name="gh-enable-_pexit-hook-function"></a>/GH(_pexit 후크 함수 사용)

`_pexit`모든 메서드 또는 함수의 끝에서 함수를 호출 합니다.

## <a name="syntax"></a>구문

> **`/GH`**

## <a name="remarks"></a>설명

`_pexit`함수는 라이브러리의 일부가 아닙니다. 에 대 한 정의를 제공 해야 `_pexit` 합니다.

를 명시적으로 호출 하지 않을 경우 `_pexit` 프로토타입을 제공할 필요가 없습니다. 함수는 항목에 모든 레지스터의 콘텐츠를 푸시하고 종료 시 변경 되지 않은 콘텐츠를 팝 해야 합니다. 다음 프로토타입이 있는 것 처럼 표시 되어야 합니다.

```cpp
void __declspec(naked) __cdecl _pexit( void );
```

64 비트 프로젝트에는이 선언을 사용할 수 없습니다.

`_pexit`는와 유사 `_penter` 합니다. 함수를 작성 하는 방법에 대 한 예제는 [ `/Gh` (_penter 후크 함수 사용)](gh-enable-penter-hook-function.md) 을 참조 하세요 `_penter` .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**  >  **C/c + +**  >  **명령줄** 속성 페이지를 엽니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[`/Gh`(_Penter 후크 함수 사용)](gh-enable-penter-hook-function.md)
