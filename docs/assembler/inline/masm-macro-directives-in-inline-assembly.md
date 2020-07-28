---
title: 인라인 어셈블리의 MASM 매크로 지시문
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 964f70aeef6e0e62ac4b941b2cc26d3e7c7ef466
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191796"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>인라인 어셈블리의 MASM 매크로 지시문

**Microsoft 전용**

인라인 어셈블러는 매크로 어셈블러가 아닙니다. MASM 매크로 지시문 (**매크로**, `REPT` , **IRC**, `IRP` 및 `ENDM` ) 또는 매크로 연산자 ( **<>** , **!**, **&** , `%` 및 `.TYPE` )를 사용할 수 없습니다. **`__asm`** 그러나 블록은 C 전처리기 지시문을 사용할 수 있습니다. 자세한 내용은 [__Asm 블록에서 C 또는 c + + 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) 을 참조 하세요.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[__Asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
