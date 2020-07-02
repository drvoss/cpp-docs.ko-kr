---
title: /Od(디버그 비활성화)
ms.date: 11/04/2016
f1_keywords:
- /od
helpviewer_keywords:
- no optimizations
- fast compiling
- /Od compiler option [C++]
- disable optimizations
- Od compiler option [C++]
- -Od compiler option [C++]
- disable (debug) compiler option [C++]
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
ms.openlocfilehash: 83ece0865eb74a4e9e292b78733df9d24602fe1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320684"
---
# <a name="od-disable-debug"></a>/Od(디버그 비활성화)

프로그램에서 모든 최적화를 해제하여 컴파일 속도를 빠르게 합니다.

## <a name="syntax"></a>구문

```
/Od
```

## <a name="remarks"></a>설명

이 옵션은 기본값입니다. **/Od**는 코드 이동을 하지 않게 하여 디버깅을 간소화합니다. 디버깅과 관련된 컴파일러 옵션에 대한 자세한 내용은 [/Z7, /Zi, /ZI (디버그 정보 형식)](z7-zi-zi-debug-information-format.md)을 참조합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **최적화** 속성 페이지를 클릭합니다.

1. **최적화** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/Z7, /Zi, /ZI(디버깅 정보 형식)](z7-zi-zi-debug-information-format.md)

