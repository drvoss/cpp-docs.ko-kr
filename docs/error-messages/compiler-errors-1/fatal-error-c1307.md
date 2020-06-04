---
title: 심각한 오류 C1307
ms.date: 11/04/2016
f1_keywords:
- C1307
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
ms.openlocfilehash: c7eb90c8e17408f6898ef7ff1a9d9e5efcafb4fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203348"
---
# <a name="fatal-error-c1307"></a>심각한 오류 C1307

프로필 데이터가 수집된 이후 프로그램이 편집되었습니다.

[/Ltcg: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)를 사용 하는 경우 링커에서/LTCG: pginstrument 후 다시 컴파일된 입력 모듈을 검색 하 고 모듈이 기존 프로필 데이터가 더 이상 관련이 없는 지점으로 변경 되었습니다. 예를 들어, 다시 컴파일된 모듈에서 호출 그래프가 변경 되 면 컴파일러는 C1307을 생성 합니다.

이 오류를 해결 하려면/LTCG: PGINSTRUMENT를 실행 하 고 모든 테스트 실행을 다시 실행 한 다음/LTCG: PGOPTIMIZE를 실행 합니다. /LTCG: PGINSTRUMENT 수 없으며 모든 테스트 실행을 다시 실행 하는 경우/ltcg: PGOPTIMIZE 대신/LTCG: PGINSTRUMENT를 사용 하 여 최적화 된 이미지를 만듭니다.
