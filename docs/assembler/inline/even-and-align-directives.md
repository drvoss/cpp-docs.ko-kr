---
title: EVEN 및 ALIGN 지시문
ms.date: 08/30/2018
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
ms.openlocfilehash: b191ce0942d7596090bfd7948a37a5c9e6aac15e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169437"
---
# <a name="even-and-align-directives"></a>EVEN 및 ALIGN 지시문

**Microsoft 전용**

인라인 어셈블러는 대부분의 MASM 지시문을 지원 하지 않지만 `EVEN` 및 **맞춤**을 지원 합니다. 이러한 지시문은 레이블을 특정 경계에 맞추기 위해 필요에 따라 어셈블리 코드에 **NOP** (작업 없음) 명령을 배치 합니다. 이를 통해 일부 프로세서에서 명령 페치 작업을 보다 효율적으로 수행할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
