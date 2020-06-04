---
title: /GH(_pexit 후크 함수 사용)
ms.date: 11/04/2016
f1_keywords:
- _pexit
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
ms.openlocfilehash: 5382ba90f490aaa12e9e55767fdf15170a69ced5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749233"
---
# <a name="gh-enable-_pexit-hook-function"></a>/GH(_pexit 후크 함수 사용)

모든 `_pexit` 메서드 또는 함수의 끝에 함수를 호출합니다.

## <a name="syntax"></a>구문

```
/GH
```

## <a name="remarks"></a>설명

이 `_pexit` 함수는 라이브러리의 일부가 아니며 에 대한 `_pexit`정의를 제공하는 것은 사용자몫입니다.

명시적으로 호출할 `_pexit`계획이 없다면 프로토타입을 제공할 필요가 없습니다. 함수는 다음 프로토타입이 있는 것처럼 나타나야 하며 항목에 있는 모든 레지스터의 내용을 푸시하고 종료시 변경되지 않은 콘텐츠를 팝업해야 합니다.

```cpp
void __declspec(naked) __cdecl _pexit( void );
```

`_pexit`와 `_penter`유사하다. `_pexit` 함수를 작성하는 방법에 대한 [예제는 /Gh(_penter 후크 함수 사용)를](gh-enable-penter-hook-function.md) 참조하십시오.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참조

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
