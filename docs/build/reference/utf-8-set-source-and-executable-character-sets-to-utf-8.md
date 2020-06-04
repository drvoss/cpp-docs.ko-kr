---
title: /utf-8 (원본 및 실행 파일 문자 집합을 UTF-8로 설정)
ms.date: 04/26/2020
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
no-loc:
- UTF
- UTF-8
- UTF-16
ms.openlocfilehash: c98a30b0ec4b36b8bd87fb0956d9382751975cfd
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168867"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-opno-locutf-8"></a>`/utf-8`(원본 및 실행 문자 집합을로 UTF-8설정)

원본 문자 집합과로 UTF-8설정 된 실행 문자를 모두 지정 합니다.

## <a name="syntax"></a>구문

> **`/utf-8`**

## <a name="remarks"></a>설명

**`/utf-8`** 옵션을 사용 하 여를 사용 UTF-8하 여 인코딩된 원본 및 실행 문자 집합을 모두 지정할 수 있습니다. 명령줄에서를 지정 **`/source-charset:utf-8 /execution-charset:utf-8`** 하는 것과 같습니다. 이러한 옵션은 기본적으로 옵션을 **`/validate-charset`** 사용 하도록 설정 합니다. 지원 되는 코드 페이지 식별자 및 문자 집합 이름 목록은 [코드 페이지 식별자](/windows/win32/Intl/code-page-identifiers)를 참조 하세요.

기본적으로 Visual Studio는 바이트 순서 표시를 검색 하 여 원본 파일이 인코딩된 유니코드 형식 (예: UTF-16 또는 UTF-8) 인지 확인 합니다. 바이트 순서 표시가 없는 경우 또는 **`/utf-8`** **`/source-charset`** 옵션을 사용 하 여 코드 페이지를 지정 하지 않으면 현재 사용자 코드 페이지를 사용 하 여 소스 파일이 인코딩된 것으로 가정 합니다. Visual Studio에서는 여러 문자 인코딩 중 하나를 사용 하 여 c + + 소스 코드를 저장할 수 있습니다. 소스 및 실행 문자 집합에 대 한 자세한 내용은 언어 설명서에서 [문자 집합](../../cpp/character-sets.md) 을 참조 하세요.

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Visual Studio에서 옵션을 설정 하거나 프로그래밍 방식으로

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 정보는 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **구성 속성** > **C/c + +** > **명령줄** 속성 페이지를 선택 합니다.

1. **추가 옵션**에서 **`/utf-8`** 옵션을 추가 하 여 기본 설정 인코딩을 지정 합니다.

1. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/sv-ecin 문자 집합 (실행 문자 집합 설정)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (소스 문자 집합 설정)](source-charset-set-source-character-set.md)<br/>
[/validate-charset(호환 문자에 대한 유효성 검사)](validate-charset-validate-for-compatible-characters.md)
