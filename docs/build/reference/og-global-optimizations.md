---
title: /Og(전역 최적화)
ms.date: 09/22/2017
f1_keywords:
- VC.Project.VCCLCompilerTool.GlobalOptimizations
- /og
helpviewer_keywords:
- -Og compiler option [C++]
- global optimizations compiler option [C++]
- automatic register allocation
- /Og compiler option [C++]
- loop structures, optimizing
- common subexpression elimination
- Og compiler option [C++]
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
ms.openlocfilehash: 5e45273b6b609f1bf78504a519c1fb98e2147f76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320294"
---
# <a name="og-global-optimizations"></a>/Og(전역 최적화)

더 이상 사용되지 않습니다. 로컬 및 전역 최적화, 자동 레지스터 할당 및 루프 최적화를 제공합니다. [/O1(크기 최소화)](o1-o2-minimize-size-maximize-speed.md)나 [/O2(속도 최대화)](o1-o2-minimize-size-maximize-speed.md) 중 하나를 사용하는 것이 좋습니다.

## <a name="syntax"></a>구문

> /Og

## <a name="remarks"></a>설명

**/Og**는 더 이상 사용되지 않습니다. 이제 이러한 최적화는 기본적으로 적용됩니다. 최적화에 대한 자세한 내용은 [/O1, /O2 (크기 최소화, 속도 최대화)](o1-o2-minimize-size-maximize-speed.md) 및 [/Ox(대부분의 속도 최적화 사용)](ox-full-optimization.md)를 참조합니다.

**/Og**에서는 다음 최적화를 사용할 수 있습니다.

- 로컬 및 전역 공통 하위 식 제거

   이 최적화에서는 공통 하위 식의 값이 한 번 계산됩니다. 다음 예의 경우 `b` 및 `c` 값이 세 식 사이에서 변경되지 않으면, 컴파일러가 `b + c`의 계산 값을 임시 변수에 할당하고 `b + c`를 그 값으로 대체할 수 있습니다.

    ```C
    a = b + c;
    d = b + c;
    e = b + c;
    ```

   로컬 공통 하위 표현식 최적화의 경우, 컴파일러는 공통 하위 표현식에 대한 코드의 짧은 섹션을 검사합니다. 전역 공통 하위 표현식 최적화를 위해 컴파일러는 전체 함수에서 공통 하위 표현식을 검색합니다.

- 자동 레지스터 할당

   이 최적화는 컴파일러가 자주 사용하는 변수와 하위 식을 레지스터에 저장할 수 있게 합니다. `register` 키워드는 무시됩니다.

- 루프 최적화

   이 최적화는 루프의 본문에서 변하지 않는 부분 식을 제거합니다. 최적 루프는 루프의 각 실행을 통해 값이 변경되는 식만 포함합니다. 다음 예제에서 식 `x + y`는 루프 본문에서 변경되지 않습니다.

    ```C
    i = -100;
    while( i < 0 ) {
        i += x + y;
    }
    ```

   최적화 후 `x + y`는 루프가 실행될 때마다 계산되는 대신 한 번만 계산됩니다.

    ```C
    i = -100;
    t = x + y;
    while( i < 0 ) {
        i += t;
    }
    ```

   루프 최적화는 컴파일러가 별칭이 없다고 가정할 수 있는 경우 훨씬 효과적이며, 이는 [__restrict](../../cpp/extension-restrict.md), [noalias](../../cpp/noalias.md) 또는 [restrict](../../cpp/restrict.md)를 이용해 설정할 수 있습니다.

   > [!NOTE]
   > `g` 옵션과 함께 `optimize` pragma를 사용하여 함수 별로 전역 최적화를 사용하거나 사용하지 않도록 설정할 수 있습니다.

관련 정보는 [/Oi(내장 함수 생성)](oi-generate-intrinsic-functions.md) 및 [/Ox(최고 속도 사용 최적화)](ox-full-optimization.md)를 참조합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에서 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
