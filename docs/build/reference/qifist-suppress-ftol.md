---
title: /QIfist(_ftol 사용 안 함)
ms.date: 11/04/2016
f1_keywords:
- /qifist
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
ms.openlocfilehash: 5d6e12a1003ea125b0da4bfef580d8096e97553a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336096"
---
# <a name="qifist-suppress-_ftol"></a>/QIfist(_ftol 사용 안 함)

사용되지 않습니다. 부동 소수점 형식에서 정수 계열 형식으로 변환해야 할 때 도우미 함수 `_ftol` 이 호출되지 않도록 합니다.

## <a name="syntax"></a>구문

```
/QIfist
```

## <a name="remarks"></a>설명

> [!NOTE]
> **/QIfist는** x86을 대상으로 하는 컴파일러에서만 사용할 수 있습니다. 이 컴파일러 옵션은 x64 orARM을 대상으로 하는 컴파일러에서 사용할 수 없습니다.

부동 점 형식에서 정수 유형으로 변환하는 `_ftol` 것 외에도 이 함수는 컨트롤 단어의 비트 10 과 11을 설정하여 부동 점 단위(FPU)의 반올림 모드가 0(truncate)을 향하도록 합니다. 이렇게 하면 부동 소수점 형식에서 정수 유형으로 변환하는 것이 ANSI C 표준(숫자의 소수 부분이 삭제됨)에 설명된 대로 발생합니다. **/QIfist를**사용하는 경우 이 보증은 더 이상 적용되지 않습니다. 반올림 모드는 인텔 참조 매뉴얼에 설명된 대로 다음 네 가지 중 하나가 됩니다.

- 가장 가까운 쪽으로 둥글게(등거리인 경우 짝수)

- 음의 무한대로 반올림

- 포지티브 무한대로 반올림

- 0을 향해 반올림

[_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C 런타임 함수를 사용하여 FPU의 반올림 동작을 수정할 수 있습니다. FPU의 기본 반올림 모드는 "가장 가까운 쪽으로 반올림"입니다. **/QIfist를** 사용하면 응용 프로그램의 성능이 향상될 수 있지만 위험없이 는 아닙니다. 프로덕션 환경에서 **/QIfist로** 빌드된 코드에 의존하기 전에 반올림 모드에 중요한 코드 부분을 철저히 테스트해야 합니다.

[/arch (x86)](arch-x86.md) 및 **/QIfist는** 동일한 컴파일에서 사용할 수 없습니다.

> [!NOTE]
> **/QIfist는** 반올림 비트도 부동점 반올림(모든 계산 후에 발생)에 부동점 반올림에 영향을 미치기 때문에 기본적으로 적용되지 않으므로 C 스타일(0) 반올림에 대한 플래그를 설정할 때 부동점 계산이 다를 수 있습니다. **/QIfist는** 코드가 부동 소수점 번호의 소수 부분을 잘리는 예상 동작에 의존하는 경우 사용해서는 안 됩니다. 당신이 확실하지 않은 경우, **/QIfist를**사용하지 마십시오.

**/QIfist** 옵션은 Visual Studio 2005에서 시작하여 더 이상 사용되지 않습니다. 컴파일러는 플로트에서 int 변환 속도로 크게 개선되었습니다. 더 이상 사용되지 제거된 컴파일러 옵션 목록은 [범주별로 나열된 컴파일러 옵션에서](compiler-options-listed-by-category.md) **더 이상 사용되지 않으며 제거된 컴파일러 옵션을** 참조하십시오.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[/Q 옵션(하위 수준 작업)](q-options-low-level-operations.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
