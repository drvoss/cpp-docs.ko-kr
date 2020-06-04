---
title: MACRO
ms.date: 12/16/2019
f1_keywords:
- MACRO
helpviewer_keywords:
- MACRO directive
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
ms.openlocfilehash: 8eb0afdf73270c3e741f43b2e1fba02fe965846c
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076142"
---
# <a name="macro"></a>MACRO

매크로 블록을 *이름* 이라고 표시 하 고 매크로가 호출 될 때 전달 되는 인수에 대 한 *매개 변수* 자리 표시자를 설정 합니다.

## <a name="syntax"></a>구문

> *name***매크로** ⟦*parameter* ⟦ **: 필수** | : =*default* | *args* **: VARARG**⟧ ... ⟧\
> *문*\
⟦**GOTO** :*macrolabelId*⟧ \
> ⟦**Exitm**⟧ \
> **Endm** ⟦*값*⟧

## <a name="remarks"></a>주의

매크로 함수는 호출 하는 문에 *값* 을 반환 합니다.

## <a name="see-also"></a>참고 항목

[지시문 참조](directives-reference.md)\
[GOTO (MASM)](goto-masm.md)\
[Endm](endm.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
