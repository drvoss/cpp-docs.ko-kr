---
title: /O 옵션(코드 최적화)
description: MSVC/O 컴파일러 옵션은 사용할 컴파일러 최적화를 지정 합니다.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
ms.openlocfilehash: 36ef582787a3ec2d7aee1e589c70b48712d9d552
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180879"
---
# <a name="o-options-optimize-code"></a>`/O`옵션 (코드 최적화)

**`/O`** 옵션은 최대 속도 또는 최소 크기에 대 한 코드를 만드는 데 도움이 되는 다양 한 최적화를 제어 합니다.

- [`/O1`](o1-o2-minimize-size-maximize-speed.md)최소 크기 코드를 생성 하는 최적화의 조합을 설정 합니다.

- [`/O2`](o1-o2-minimize-size-maximize-speed.md)최대 속도에 맞게 코드를 최적화 하는 최적화의 조합을 설정 합니다.

- [`/Ob`](ob-inline-function-expansion.md)인라인 함수 확장을 제어 합니다.

- [`/Od`](od-disable-debug.md)컴파일을 가속화 하 고 디버깅을 간소화 하기 위해 최적화를 사용 하지 않습니다.

- [`/Og`](og-global-optimizations.md)(사용 되지 않음) 전역 최적화를 사용 합니다.

- [`/Oi`](oi-generate-intrinsic-functions.md)적절 한 함수 호출에 대 한 내장 함수를 생성 합니다.

- [`/Os`](os-ot-favor-small-code-favor-fast-code.md)속도 최적화를 통해 크기 최적화를 우선 하도록 컴파일러에 지시 합니다.

- [`/Ot`](os-ot-favor-small-code-favor-fast-code.md)(기본 설정)은 크기에 대 한 최적화 보다 속도에 최적화를 선호 하도록 컴파일러에 지시 합니다.

- [`/Ox`](ox-full-optimization.md)는 속도에 중점을 두어 몇 가지 최적화를 선택 하는 조합 옵션입니다. **`/Ox`** 는 최적화의 엄격한 하위 집합입니다 **`/O2`** .

- [`/Oy`](oy-frame-pointer-omission.md)더 빠른 함수 호출을 위해 호출 스택에서 프레임 포인터를 생성 하지 않습니다.

## <a name="remarks"></a>설명

여러 **`/O`** 옵션을 단일 option 문으로 결합할 수 있습니다. 예를 들어, **`/Odi`** 는와 같습니다 **`/Od /Oi`** . 특정 옵션은 함께 사용할 수 없으며 함께 사용할 경우 컴파일러 오류가 발생 합니다. 자세한 내용은 개별 옵션을 참조 **`/O`** 하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
