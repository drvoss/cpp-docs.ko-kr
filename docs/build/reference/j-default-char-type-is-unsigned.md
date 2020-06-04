---
title: /J(부호 없는 기본 문자 형식)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
ms.openlocfilehash: 7bcf0f2eb2bef08757250999d0a6696b256fb15c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322193"
---
# <a name="j-default-char-type-is-unsigned"></a>/J(부호 없는 기본 문자 형식)

기본 `char` 형식을 `signed char`에서 `unsigned char`로 변경하고, `char` 형식은 `int` 형식으로 확장될 때 제로 확장됩니다.

## <a name="syntax"></a>구문

```
/J
```

## <a name="remarks"></a>설명

`char` 값이 명시적으로 `signed`로 선언된 경우 /J 옵션은 해당 **옵션에** 영향을 주지 않으며 `int` 형식으로 확대될 때 값이 부호 확장됩니다.

**/J** 옵션은 LIMITS.h 파일에서 `#ifndef` 기본 `char` 형식의 범위를 정의하는 데 사용되는 `_CHAR_UNSIGNED`을 정의합니다.

ANSI C 및 C++는 형식의 `char` 특정 구현이 필요하지 않습니다. 이 옵션은 결국 영어 이외의 언어로 번역되는 문자 데이터로 작업할 때 유용합니다.

> [!NOTE]
> ATL/MFC에 이 컴파일러 옵션을 사용하면 오류가 생성될 수 있습니다. `_ATL_ALLOW_CHAR_UNSIGNED`를 정의해서 이 오류를 비활성화할 수도 있지만 이 해결 방법은 지원되지 않으며, 항상 작동하지 않을 수도 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. **솔루션 탐색기에서**프로젝트의 바로 가기 메뉴를 열고 **속성을**선택합니다.

1. 프로젝트 **속성 페이지** 대화 상자에서 **구성 속성**아래의 왼쪽 창에서 **C/C++를** 확장한 다음 **명령줄을**선택합니다.

1. 추가 **옵션** 창에서 **/J** 컴파일러 옵션을 지정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)

