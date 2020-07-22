---
title: NMAKE 심각한 오류 U1100
description: Microsoft NMAKE 심각한 오류 U1100의 원인에 대 한 설명입니다.
ms.date: 07/17/2020
f1_keywords:
- U1100
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
ms.openlocfilehash: f908514469a6c9fdb53df3b2bded1b30bddc5a41
ms.sourcegitcommit: 00af3df3331854b23693ee844e5e7c10c8b05a90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86491390"
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE 심각한 오류 U1100

> '*macro-name*' 매크로는 '*rule-name*' 일괄 처리 규칙의 컨텍스트에서 잘못 되었습니다.

NMAKE는 배치 모드 규칙의 명령 블록이 아닌 특수 파일 매크로를 직접 또는 간접적으로 참조 하는 경우이 오류를 생성 `$<` 합니다.

`$<`는 배치 모드 규칙에 대해 유일 하 게 허용 되는 매크로입니다.

일괄 처리 규칙의 NMAKE 매크로에 대 한 자세한 내용은 [특수 NMAKE 매크로](../../build/reference/special-nmake-macros.md)를 참조 하세요.
