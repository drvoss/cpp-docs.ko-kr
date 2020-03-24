---
title: 인라인 어셈블리의 데이터 지시문과 연산자
ms.date: 08/30/2018
helpviewer_keywords:
- data directives [C++]
- __asm keyword [C++], referencing limitations
- MASM (Microsoft Macro Assembler), directives
- directives [C++], MASM
- MASM (Microsoft Macro Assembler), structures
- operators [MASM]
- inline assembly, operators
- inline assembly, data directives
- MASM (Microsoft Macro Assembler), operators
- structures [C++], MASM
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
ms.openlocfilehash: 916dce0346bebfc5ff65ca558ae75317a187660a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169541"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>인라인 어셈블리의 데이터 지시문과 연산자

**Microsoft 전용**

`__asm` 블록은 C 또는 C++ 데이터 형식과 개체를 참조할 수 있지만 MASM 지시문이나 연산자를 사용하여 데이터 개체를 정의할 수 없습니다. 특히, 정의 지시문 **DB**, `DW`, **DD**, `DQ`, `DT`및 `DF`를 사용할 수 없으며, 또는 **이**`DUP` 연산자를 사용할 수 없습니다. MASM 구조체와 레코드도 사용할 수 없습니다. 인라인 어셈블러는 `STRUC`, `RECORD`, **WIDTH**또는 **MASK**지시문을 허용 하지 않습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
