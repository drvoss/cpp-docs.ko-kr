---
title: NMAKE 심각한 오류 U1099
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: c963180059a48d9aa0b09103df1ed54f82b8a2f1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193396"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE 심각한 오류 U1099

스택 오버플로

처리 중인 메이크파일이 NMAKE의 현재 스택 할당에 대해 너무 복잡 합니다. NMAKE는 0x3000 (12K)를 할당 합니다.

NMAKE의 스택 할당을 늘리려면 더 큰 스택 옵션을 사용 하 여 [editbin/stack](../../build/reference/stack.md) 유틸리티를 실행 합니다.

**editbin/STACK: reserve NMAKE. CONVERT.EXE**

여기서 *reserve* 는 NMAKE의 현재 스택 할당 보다 큰 숫자입니다.
