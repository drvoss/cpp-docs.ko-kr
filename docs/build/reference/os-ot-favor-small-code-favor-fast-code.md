---
title: /Os, /OT(크기 우선 코드, 속도 우선 코드)
ms.date: 11/04/2016
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
ms.openlocfilehash: 0eda9461b3ef730e0e0a832aa94a688e03c7e1bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336182"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /OT(크기 우선 코드, 속도 우선 코드)

EXEs 및 DLL의 크기를 최소화하거나 최대화합니다.

## <a name="syntax"></a>구문

```
/Os
/Ot
```

## <a name="remarks"></a>설명

**/Os(작은** 코드 선호)는 컴파일러에 속도보다 크기를 선호하도록 지시하여 EXEs 및 DLL의 크기를 최소화합니다. 컴파일러는 많은 C 및 C++ 구문에서 기능적으로 유사한 컴퓨터 코드 시퀀스를 줄일 수 있습니다. 경우에 따라 이러한 차이는 크기와 속도의 장단점을 제공합니다. **/Os** 및 **/Ot** 옵션을 사용하면 다른 옵션에 대한 기본 설정을 지정할 수 있습니다.

**/Ot(빠른** 코드 선호)는 컴파일러에 크기보다 속도를 선호하도록 지시하여 EXEs 및 DLL의 속도를 최대화합니다. 기본값입니다. 컴파일러는 많은 C 및 C++ 구문에서 기능적으로 유사한 컴퓨터 코드 시퀀스를 줄일 수 있습니다. 경우에 따라 이러한 차이는 크기와 속도의 장단점을 제공합니다. **/Ot** 옵션은 최대[속도(/O2)](o1-o2-minimize-size-maximize-speed.md)옵션으로 암시됩니다. **/O2** 옵션은 매우 빠른 코드를 생성하기 위해 여러 옵션을 결합합니다.
**/Ot**(속도 우선 코드)는 컴파일러가 크기보다 속도를 우선하도록 하여 EXE 및 DLL의 속도를 최대화합니다. (이것이 기본값입니다.) 컴파일러는 많은 C 와 C++ 기능이 비슷한 기계어 코드 시퀀스로 줄일 수 있습니다. 경우에 따라 이러한 차이는 크기와 속도의 균형을 제공합니다. **/Ot** 옵션은 속도 최대화([/O2](o1-o2-minimize-size-maximize-speed.md)) 옵션에 의해 설정됩니다. **/O2** 옵션은 매우 빠른 코드를 생성하기 위해 몇 가지 옵션을 결합합니다.


**/Os** 또는 **/Ot를**사용하는 경우 코드를 최적화하려면 [/Og도](og-global-optimizations.md) 지정해야 합니다.

> [!NOTE]
> 프로파일링 테스트 실행에서 수집된 정보는 **/Ob ,** **/Os**또는 **/Ot를**지정하는 경우 적용되는 최적화를 재정의합니다. 자세한 내용은 [프로필 기반 최적화.](../profile-guided-optimizations.md)

**x86 전용**

다음 예제 코드는 호지 작은 코드 **(/Os)** 옵션과 선호 빠른 코드 **(/Ot)** 옵션 간의 차이점을 보여 줍니다.

> [!NOTE]
> 다음은 **/Os** 또는 /Ot . 를 사용할 때 예상되는 **동작에 대해**설명합니다. 그러나 릴리스에서 릴리스까지 컴파일러 동작으로 인해 아래 코드에 대한 다른 최적화가 발생할 수 있습니다.


```
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

아래 컴퓨터 코드 의 조각에 나와 있듯이, DIFFERENT.c가 크기 **(/Os)에**대해 컴파일될 때 컴파일러는 짧지만 느린 코드 시퀀스를 생성하기 위해 return 문에서 곱하기 식을 명시적으로 곱하기 를 구현합니다.


```
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

또는, DIFFERENT.c 속도 **(/Ot)에**대 한 컴파일 될 때 컴파일러는 일련의 시프트 및 `LEA` 명령으로 return 문에 곱기 식을 구현 하 고 신속 하지만 더 긴 코드 시퀀스를 생성 합니다.
.c가 속도 우선 코드( **/Ot**) 옵션으로 컴파일되면, 컴파일러는 return 문에서 곱하기를 시프트의 계열 및 `LEA` 명령어로 구현하여 빠르지만 긴 시퀀스를 생성합니다.


```
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

**END x86 특정**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **C/C++** 폴더를 클릭합니다.

1. 최적화 속성 페이지를 **클릭합니다.**

1. 호의 **크기 또는 속도** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
