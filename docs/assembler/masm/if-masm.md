---
title: IF (MASM)
ms.date: 12/17/2019
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 6e63f5c8075b3c94370ad8863d224c097cf0ecdf
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440755"
---
# <a name="if"></a>IF

*Expression1* 가 true (0이 아닌 경우) 또는 *elseifstatements* ( *expression1* 가 false)이 고 *식* 1이 true 인 경우 *ifstatements* 의 어셈블리를 부여 합니다.

## <a name="syntax"></a>구문

> **IF** *Expression1*\
> *if 문*\
> ⟦**ELSEIF** *식*\
> *elseif-문*⟧ \
> ⟦**ELSE**\
> *else 문*⟧ \
> **ENDIF**

## <a name="remarks"></a>설명

다음 지시문은 [ELSEIF](elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI**, **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**및 **ELSEIFNDEF**로 대체 될 수 있습니다. 필요에 따라 이전 식이 false 인 경우 *else 문을* 어셈블합니다. 식은 어셈블리 시간에 계산 됩니다.

## <a name="see-also"></a>참고 항목

[지시문 참조](directives-reference.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
