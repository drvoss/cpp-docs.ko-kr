---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: ba1377359ba9bc960e5d7d2a55df15adfe0d5d33
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076213"
---
# <a name="invoke"></a>INVOKE

(32 비트 MASM에만 해당) *식*으로 지정 된 주소에서 프로시저를 호출 하 여 언어 형식의 표준 호출 규칙에 따라 스택에서 인수를 전달 하거나 레지스터에 프로시저를 전달 합니다.

## <a name="syntax"></a>구문

> **INVOKE** *식* ⟦ __,__ *인수* 를 호출 합니다. ⟧

## <a name="remarks"></a>주의

프로시저에 전달 되는 각 인수는 식, 레지스터 쌍 또는 주소 식 ( **주소 뒤에 오는 식) 일**수 있습니다.

## <a name="see-also"></a>참고 항목

[지시문 참조](directives-reference.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
