---
title: NMAKE 경고 U4011
ms.date: 11/04/2016
f1_keywords:
- U4011
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
ms.openlocfilehash: 6b1701ffc83f849d2482bd14b25d65c04c496899
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193149"
---
# <a name="nmake-warning-u4011"></a>NMAKE 경고 U4011

' target ': 모든 종속 항목을 사용할 수 없습니다. 대상이 빌드되지 않음

지정 된 대상에 종속 된이 없거나, 해당 대상에 종속 되어 있지 않거나, 종속 업데이트를 위한 명령이 0이 아닌 종료 코드를 반환 했습니다. /K 옵션은 nmake 세션이 완료 되 면 NMAKE는 빌드에서 관련 되지 않은 부분을 계속 처리 하 고 종료 코드 1을 실행 하도록 지시 합니다.

이 경고는 생성 하거나 업데이트 하지 못한 각 종속에 대 한 경고 [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) 앞에 나옵니다.
