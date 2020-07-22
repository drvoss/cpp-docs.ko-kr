---
title: /Os, /OT(크기 우선 코드, 속도 우선 코드)
description: MSVC 컴파일러 옵션/Os 및/Ot는 코드를 최적화할 때 크기 또는 속도를 설정할지 여부를 지정 합니다.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
ms.openlocfilehash: 384019ddf7b80b8dd4e00197d73d1e4ac536634c
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180827"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>`/Os`, `/Ot` (크기 우선 코드, 속도 우선 코드)

Exe 및 Dll의 크기를 최소화 하거나 최대화 합니다.

## <a name="syntax"></a>구문

> **`/Os`**\
> **`/Ot`**

## <a name="remarks"></a>설명

**`/Os`**(작은 코드 우선) 컴파일러에 속도 보다 크기를 우선 하도록 지시 하 여 Exe 및 Dll의 크기를 최소화 합니다. 컴파일러는 여러 C 및 c + + 구문을 기능적으로 비슷한 컴퓨터 코드 시퀀스로 줄일 수 있습니다. 때로는 이러한 차이가 크기와 속도의 장단점을 제공 합니다. **`/Os`** 및 **`/Ot`** 옵션을 사용 하면 다른 항목에 대 한 기본 설정을 지정할 수 있습니다.

**`/Ot`**(빠른 코드 우선)는 크기 보다 빠른 속도로 컴파일러에 지시 하 여 Exe 및 Dll의 속도를 최대화 합니다. **`/Ot`** 최적화를 사용 하는 경우의 기본값입니다. 컴파일러는 여러 C 및 c + + 구문을 기능적으로 비슷한 컴퓨터 코드 시퀀스로 줄일 수 있습니다. 경우에 따라 이러한 차이가 크기와 속도의 장단점을 제공 합니다. **`/Ot`** 옵션은 [`/O2`](o1-o2-minimize-size-maximize-speed.md) (속도 최대화) 옵션에 포함 되어 있습니다. **`/O2`** 옵션은 여러 옵션을 결합 하 여 더 빠른 코드를 생성 합니다.

> [!NOTE]
> 프로 파일링 테스트 실행에서 수집 되는 정보는, 또는를 지정 하는 경우 적용 되는 모든 최적화를 재정의 **`/Ob`** **`/Os`** **`/Ot`** 합니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)를 참조하세요.

### <a name="x86-specific-example"></a>x86 관련 예제

다음 예제 코드에서는 **`/Os`** (코드 크기 우선) 옵션과 **`/Ot`** (빠른 코드 우선) 옵션의 차이점을 보여 줍니다.

> [!NOTE]
> 이 예제에서는 또는를 사용할 때 예상 되는 동작을 설명 합니다 **`/Os`** **`/Ot`** . 그러나 릴리스에 대 한 컴파일러 동작으로 인해 아래 코드에 대해 다른 최적화를 사용할 수 있습니다.

```c
/* differ.c
  This program implements a multiplication operator
  Compile with /Os to implement multiply explicitly as multiply.
  Compile with /Ot to implement as a series of shift and LEA instructions.
*/
int differ(int x)
{
    return x * 71;
}
```

아래 기계어 코드 조각에 표시 된 것 처럼, *`differ.c`* 가 size ()에 대해 컴파일될 때 **`/Os`** 컴파일러는 return 문으로 명시적으로 곱하기 식을 구현 하 여 짧은 코드 시퀀스를 생성 합니다.

```asm
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

또는 *`differ.c`* 가 speed ()로 컴파일될 때 **`/Ot`** 컴파일러는 반환 문에 일련의 shift 및 명령으로 곱하기 식을 구현 `LEA` 하 여 보다 빠르고 긴 코드 시퀀스를 생성 합니다.

```asm
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**  >  **C/c + +**  >  **최적화** 속성 페이지를 선택 합니다.

1. **크기 또는 속도 우선** 속성을 수정 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
