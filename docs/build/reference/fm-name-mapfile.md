---
title: /Fm(맵 파일 이름 지정)
ms.date: 11/04/2016
f1_keywords:
- /fm
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
ms.openlocfilehash: eebb1bc0c553dba1934aea75e2e63edc0f222fff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292408"
---
# <a name="fm-name-mapfile"></a>/Fm(맵 파일 이름 지정)

링커가 해당 .exe 파일이나 DLL에 나타나는 순서대로 세그먼트 목록을 포함하는 mapfile을 생성하도록 지시합니다.

## <a name="syntax"></a>구문

```
/Fmpathname
```

## <a name="remarks"></a>설명

기본적으로 맵 파일에는 확장자가 .MAP인 C 또는 C++ 소스 파일의 기본 이름이 지정됩니다.

**/Fm**을 지정하면 [/MAP (맵 파일 생성)](map-generate-mapfile.md) 링커 옵션을 지정한 경우와 동일한 결과를 얻을 수 있습니다.

링크하지 않으려는 경우 [/c (링크 없이 컴파일)](c-compile-without-linking.md)을 지정하면 **/Fm**은 아무 효과가 없습니다.

컴파일러는 변수 이름에 선행 밑줄을 추가하기 때문에 일반적으로 맵 파일의 전역 기호는 하나 이상의 선행 밑줄이 있습니다. 맵 파일에 표시되는 많은 전역 기호는 컴파일러와 표준 라이브러리에서 내부적으로 사용됩니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)
