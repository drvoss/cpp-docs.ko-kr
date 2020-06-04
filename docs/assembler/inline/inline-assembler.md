---
title: 인라인 어셈블러
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
ms.openlocfilehash: 2050f59601755a93c73b743debacbf52ba9cec05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318069"
---
# <a name="inline-assembler"></a>인라인 어셈블러

**마이크로소프트 특정**

어셈블리 언어는 프로그램 속도 향상, 메모리 요구 사항 감소, 하드웨어 제어 등의 다양한 용도로 사용됩니다. 인라인 어셈블러를 사용하여 추가 어셈블리 및 링크 단계 없이 C 및 C++ 소스 프로그램에 어셈블리 언어 명령을 직접 포함하도록 할 수 있습니다. 인라인 어셈블러가 컴파일러에 내장되어 있어 MASM(Microsoft Macro Assembler)과 같은 별도의 어셈블러는 필요하지 않습니다.

> [!NOTE]
> 인라인 어셈블러 코드를 포함하는 프로그램은 다른 하드웨어 플랫폼에 완벽하게 이식할 수 없습니다. 이식성을 위해 디자인할 경우 인라인 어셈블러를 사용하지 마십시오.

인라인 어셈블리는 ARM 및 x64 프로세서에서 지원되지 않습니다.  다음 항목에서는 x86 프로세서에서 Visual C/C++ 인라인 어셈블러를 사용하는 방법을 설명합니다.

- [인라인 어셈블러 개요](../../assembler/inline/inline-assembler-overview.md)

- [인라인 어셈블리의 장점](../../assembler/inline/advantages-of-inline-assembly.md)

- [__asm](../../assembler/inline/asm.md)

- [__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)

- [__asm 블록에서 C 또는 C++ 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)

- [인라인 어셈블리에서 레지스터 사용 및 유지](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)

- [인라인 어셈블리에서 레이블로 점프](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)

- [인라인 어셈블리에서 C 함수 호출](../../assembler/inline/calling-c-functions-in-inline-assembly.md)

- [인라인 어셈블리에서 C++ 함수 호출](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)

- [__asm 블록을 C 매크로로 정의](../../assembler/inline/defining-asm-blocks-as-c-macros.md)

- [인라인 어셈블리 최적화](../../assembler/inline/optimizing-inline-assembly.md)

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[컴파일러 내장 및 어셈블리 언어](../../intrinsics/compiler-intrinsics-and-assembly-language.md)<br/>
[C++ 언어 참조](../../cpp/cpp-language-reference.md)<br/>
