---
title: NMAKE 경고 U4004
ms.date: 11/04/2016
f1_keywords:
- U4004
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
ms.openlocfilehash: d59b5656d76025fa56bfc76bad800659f25acf53
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193201"
---
# <a name="nmake-warning-u4004"></a>NMAKE 경고 U4004

' targetname ' 대상에 대 한 규칙이 너무 많습니다.

단일 콜론 ( **:** )을 구분 기호로 사용 하 여 지정 된 대상에 대해 둘 이상의 설명 블록이 지정 되었습니다. NMAKE는 첫 번째 설명 블록의 명령을 실행 하 고 이후 블록을 무시 합니다.

여러 종속성에서 동일한 대상을 지정 하려면 각 종속성 줄에서 구분 기호로 이중 콜론 (`::`)을 사용 합니다.
