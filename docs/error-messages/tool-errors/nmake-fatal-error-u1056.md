---
title: NMAKE 심각한 오류 U1056
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: 10131e518fa608292fff58672ede36390bcd665b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182905"
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE 심각한 오류 U1056

명령 처리기를 찾을 수 없습니다.

명령 프로세서가 **COMSPEC** 또는 **path** 환경 변수에 지정 된 경로에 없습니다.

NMAKE는 COMMAND.COM 또는 CMD를 사용 합니다. 명령을 실행할 때 명령 프로세서로 서의 EXE **COMSPEC**에 설정 된 경로에서 먼저 명령 처리기를 찾습니다. **COMSPEC** 가 없는 경우 NMAKE는 **PATH**에 지정 된 디렉터리를 검색 합니다.
