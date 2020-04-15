---
title: 다이너셋에 대한 ODBC 드라이버 요구 사항
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, dynasets
- drivers, for dynasets
- drivers, ODBC
- recordsets, dynasets
- dynasets
- ODBC drivers, dynasets
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
ms.openlocfilehash: c612e8ea91882a6e744a8f47afe0decbeba85358
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367209"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>다이너셋에 대한 ODBC 드라이버 요구 사항

MFC ODBC 데이터베이스 클래스에서 다이너셋은 동적 속성을 가진 레코드 집합입니다. 특정 방식으로 데이터 원본과 동기화된 상태로 유지됩니다. MFC 다이너셋(정방향 전용 레코드 집합은 아님)에는 수준 2 API 준수가 있는 ODBC 드라이버가 필요합니다. [데이터 원본의](../../data/odbc/data-source-odbc.md) 드라이버가 수준 1 API 집합을 준수하는 경우에도 업데이트 가능한 스냅숏과 읽기 전용 스냅숏과 정방향 전용 레코드 집합을 모두 사용할 수 있지만 다이너셋은 사용할 수 없습니다. 그러나 수준 1 드라이버는 확장 가져오기 및 키 집합 기반 커서를 지원하는 경우 다이너셋을 지원할 수 있습니다.

ODBC 용어에서 다이너셋 및 스냅숏을 커서라고 합니다. 커서는 레코드 집합에서 해당 위치를 추적하는 데 사용되는 메커니즘입니다. 다이나셋에 대한 드라이버 요구 사항에 대한 자세한 내용은 [Dynaset](../../data/odbc/dynaset.md)을 참조하십시오. 커서에 대한 자세한 내용은 MSDN 설명서의 [ODBC(개방형 데이터베이스 연결)](/sql/odbc/microsoft-open-database-connectivity-odbc) SDK를 참조하십시오.

> [!NOTE]
> 업데이트 가능한 레코드 집합의 경우 ODBC 드라이버는 위치가 `::SQLSetPos` 있는 업데이트 문 또는 ODBC API 함수를 지원해야 합니다. 둘 다 지원되는 경우 `::SQLSetPos` MFC는 효율성을 위해 사용합니다. 또는 스냅숏의 경우 업데이트 가능한 스냅숏(정적 커서 및 위치 지정 업데이트 문)에 필요한 지원을 제공하는 커서 라이브러리를 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[ODBC 기본 사항](../../data/odbc/odbc-basics.md)
