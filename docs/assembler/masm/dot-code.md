---
title: .CODE
ms.date: 12/17/2019
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 7e53befcc46319d0ecf2287ab96a19a73a0b0b85
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076273"
---
# <a name="code"></a>.CODE

(32 비트 MASM에만 해당) 과 함께 사용 [됩니다. MODEL](dot-model.md)-코드 세그먼트의 시작을 나타냅니다.

## <a name="syntax"></a>구문

> **. CODE** ⟦*name*⟧ \
> ⟦ *segmentItem* ⟧ ...
> ⟦ *codesegmentnameId* **end**;; ⟧\

### <a name="parameters"></a>매개 변수

*이름*\
코드 세그먼트의 이름을 지정 하는 선택적 매개 변수입니다. 기본 이름은 소형, 소형, 소형 및 플랫 [모델](dot-model.md)에 **_TEXT** 됩니다. 다른 모델에 대 한 기본 이름은 *modulename*_TEXT입니다.

## <a name="see-also"></a>참고 항목

[지시문 참조](directives-reference.md)\
[. 데이터](dot-data.md)\
[MASM BNF 문법](masm-bnf-grammar.md)
