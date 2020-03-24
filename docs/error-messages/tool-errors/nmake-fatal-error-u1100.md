---
title: NMAKE 심각한 오류 U1100
ms.date: 11/04/2016
f1_keywords:
- U1100
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
ms.openlocfilehash: d5c62c1465bbb6463afbac2bc9ad5f4290473471
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193266"
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE 심각한 오류 U1100

' macroname ' 매크로는 ' rule ' 일괄 처리 규칙의 컨텍스트에서 잘못 되었습니다.

NMAKE는 배치 모드 규칙의 명령 블록이 $ < 아닌 특수 파일 매크로를 직간접적으로 참조 하는 경우이 오류를 생성 합니다.

일괄 처리 모드 규칙에 사용할 수 있는 유일한 매크로는 $ <입니다.
