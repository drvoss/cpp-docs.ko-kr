---
title: 리소스 컴파일러 오류 RC2001
ms.date: 11/04/2016
f1_keywords:
- RC2001
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
ms.openlocfilehash: 35042687b798b53857becdedba57861bd4f41a05
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191727"
---
# <a name="resource-compiler-error-rc2001"></a>리소스 컴파일러 오류 RC2001

상수에서 줄 바꿈

백슬래시 ( **\\** ) 나 닫는 큰따옴표와 여는 큰따옴표 ( **"** )가 없는 두 번째 줄에서 문자열 상수가 계속 되었습니다.

소스 파일에서 두 줄에 있는 문자열 상수를 중단 하려면 다음 중 하나를 수행 합니다.

- 줄 연속 문자, 백슬래시를 사용 하 여 첫 번째 줄을 종료 합니다.

- 첫 번째 줄에서 큰따옴표를 사용 하 여 문자열을 닫고 다음 줄에서 다른 따옴표를 사용 하 여 문자열을 엽니다.

문자열 상수에 줄 바꿈 문자를 포함 하는 이스케이프 시퀀스인 \n을 사용 하 여 첫 번째 줄을 종료 하는 것은 충분 하지 않습니다.
