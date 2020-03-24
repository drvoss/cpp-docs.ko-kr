---
title: NMAKE 경고 U4010
ms.date: 11/04/2016
f1_keywords:
- U4010
helpviewer_keywords:
- U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
ms.openlocfilehash: f68da1893eec6325ccccfd0e2e2dd0e612f28eb9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193136"
---
# <a name="nmake-warning-u4010"></a>NMAKE 경고 U4010

' target ': 빌드하지 못했습니다. /K를 지정 했습니다. 계속 하는 동안 ...

지정 된 대상에 대 한 명령 블록의 명령이 0이 아닌 종료 코드를 반환 했습니다. /K 옵션은 nmake 세션이 완료 되 면 NMAKE는 빌드에서 관련 되지 않은 부분을 계속 처리 하 고 종료 코드 1을 실행 하도록 지시 합니다.

지정 된 대상이 다른 대상에 종속 된 경우 NMAKE는이 경고 후에 [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) 경고를 발생 시킵니다.
