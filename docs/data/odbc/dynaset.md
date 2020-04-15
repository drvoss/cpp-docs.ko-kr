---
title: 다이너셋
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, dynasets
- ODBC cursor library [ODBC], dynasets
- keyset-driven cursors in dynasets
- cursors [ODBC], keyset-driven cursors in dynasets
- cursor library [ODBC], dynaset availability
- recordsets [C++], dynasets
- dynasets
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
ms.openlocfilehash: 2eb2447d1f984b7734d5e9c45087023e5a6f003f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371835"
---
# <a name="dynaset"></a>다이너셋

이 항목에서는 다이너셋에 대해 설명하고 [가용성에](#_core_availability_of_dynasets)대해 설명합니다.

> [!NOTE]
> 이 항목은 [CRecordset을](../../mfc/reference/crecordset-class.md)포함한 MFC ODBC 클래스에 적용됩니다. DAO 클래스의 다이너셋에 대한 자세한 내용은 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)을 참조하십시오. DAO를 사용하면 다이너셋 유형 레코드 집합을 열 수 있습니다.

다이너셋은 동적 속성이 있는 레코드 집합입니다. 수명 동안 다이너셋 모드(일반적으로 다이너셋이라고 함)의 레코드 집합 개체는 다음과 같은 방식으로 데이터 원본과 동기화된 상태로 유지됩니다. 다중 사용자 환경에서 다른 사용자는 다이나식에 있는 레코드를 편집 하거나 삭제하거나 다이너셋이 나타내는 테이블에 레코드를 추가할 수 있습니다. 응용 프로그램이 레코드 집합에 추가하거나 삭제한 레코드는 다이너셋에 반영됩니다. 다른 사용자가 테이블에 추가하는 레코드는 멤버 함수를 호출하여 다이너셋을 다시 `Requery` 빌드할 때까지 다이너셋에 반영되지 않습니다. 다른 사용자가 레코드를 삭제하면 MFC 코드는 레코드 집합의 삭제를 건너뜁니다. 영향을 받는 레코드로 스크롤하는 즉시 다른 사용자의 기존 레코드 편집 변경 내용이 다이너셋에 반영됩니다.

마찬가지로 다이너셋의 레코드에 대한 편집 사항은 다른 사용자가 사용하는 다이너셋에 반영됩니다. 추가하는 레코드는 다이너셋을 다시 쿼리할 때까지 다른 사용자의 다이너셋에 반영되지 않습니다. 삭제한 레코드는 다른 사용자의 레코드 집합에서 "삭제됨"으로 표시됩니다. 동일한 데이터베이스(여러 `CDatabase` 개체)에 대한 연결이 여러 개인 경우 해당 연결과 연결된 레코드 집합은 다른 사용자의 레코드 집합과 동일한 상태를 갖습니다.

다이너셋은 항공사 예약 시스템에서와 같이 데이터가 동적이어야 할 때 가장 유용합니다.

> [!NOTE]
> 다이너셋을 사용하려면 다이너셋을 지원하는 데이터 원본에 대한 ODBC 드라이버가 있어야 하며 ODBC 커서 라이브러리를 로드할 수 없습니다. 자세한 내용은 [다이너셋 의 가용성을](#_core_availability_of_dynasets)참조하십시오.

레코드 집합이 다이너셋임을 지정하려면 `CRecordset::dynaset` 레코드 집합 개체의 `Open` 멤버 함수에 첫 번째 매개 변수로 전달합니다.

> [!NOTE]
> 업데이터 다이너셋의 경우 ODBC 드라이버는 위치가 있는 `::SQLSetPos` 업데이트 문 또는 ODBC API 함수를 지원해야 합니다. 둘 다 지원되는 경우 `::SQLSetPos` MFC는 효율성을 위해 사용합니다.

## <a name="availability-of-dynasets"></a><a name="_core_availability_of_dynasets"></a>다이나셋의 가용성

MFC 데이터베이스 클래스는 다음 요구 사항이 충족되는 경우 다이너셋을 지원합니다.

- ODBC 커서 라이브러리 DLL은 이 데이터 원본에 사용되어서는 안 됩니다.

   커서 라이브러리를 사용하는 경우 다이너셋 지원에 필요한 기본 ODBC 드라이버의 일부 기능을 마스킹합니다. 다이너셋을 사용하려는 경우(ODBC 드라이버에 이 섹션의 나머지 부분에서 설명한 대로 다이너셋에 필요한 기능이 있음) 개체를 만들 `CDatabase` 때 MFC가 커서 라이브러리를 로드하지 않도록 할 수 있습니다. 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 및 `CDatabase`클래스의 OpenEx 또는 [OpenEx](../../mfc/reference/cdatabase-class.md#openex) 또는 [Open](../../mfc/reference/cdatabase-class.md#open) 멤버 함수를 참조하십시오.

   ODBC 용어에서 다이너셋 및 스냅숏을 커서라고 합니다. 커서는 레코드 집합에서 해당 위치를 추적하는 데 사용되는 메커니즘입니다.

- 데이터 원본의 ODBC 드라이버는 키집합 기반 커서를 지원해야 합니다.

   키 집합 기반 커서는 키 집합을 받고 저장하여 테이블에서 데이터를 관리합니다. 키는 사용자가 특정 레코드로 스크롤할 때 테이블에서 현재 데이터를 가져오는 데 사용됩니다. 드라이버가 이 지원을 제공하는지 확인하려면 `::SQLGetInfo` *odBC* API 함수에 SQL_SCROLL_OPTIONS 매개 변수를 호출합니다.

   키 집합 지원 `CDBException` 없이 다이너셋을 열려면 반환 코드 값이 AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED.

- 데이터 원본의 ODBC 드라이버는 확장 페칭을 지원해야 합니다.

   확장 페칭은 SQL 쿼리의 결과 레코드를 뒤로 스크롤하고 앞으로 스크롤하는 기능입니다. 드라이버가 이 기능을 지원하는지 확인하려면 `::SQLGetFunctions` *SQL_API_SQLEXTENDEDFETCH* 매개 변수를 사용하여 ODBC API 함수를 호출합니다.

업데이트 가능한 다이너셋(또는 스냅샷)을 원하는 경우 ODBC 드라이버는 `::SQLSetPos` ODBC API 함수 또는 위치 업데이트도 지원해야 합니다. 이 `::SQLSetPos` 함수를 사용하면 MFC가 SQL 문을 보내지 않고 데이터 원본을 업데이트할 수 있습니다. 이 지원을 사용할 수 있는 경우 MFC는 SQL을 사용하여 업데이트를 하는 데 기본 설정에서 이 지원을 사용합니다. 드라이버가 지원하는지 `::SQLSetPos`여부를 `::SQLGetInfo` 확인하려면 *SQL_POS_OPERATIONS* 매개 변수를 사용하여 호출합니다.

위치 가있는 업데이트는 SQL 구문 \<(커서남의 **현재**> 양식)을 사용하여 데이터 원본의 테이블에서 특정 행을 식별합니다. 드라이버가 위치 업데이트를 지원하는지 여부를 `::SQLGetInfo` 확인하려면 *SQL_POSITIONED_STATEMENTS* 매개 변수를 사용하여 문의하십시오.

일반적으로 MFC 다이너셋(정방향 전용 레코드 집합은 아님)에는 수준 2 API 준수가 있는 ODBC 드라이버가 필요합니다. 데이터 원본의 드라이버가 수준 1 API 집합을 준수하는 경우에도 업데이트 가능한 스냅숏과 읽기 전용 스냅숏과 정방향 전용 레코드 집합을 모두 사용할 수 있지만 다이너셋은 사용할 수 없습니다. 그러나 수준 1 드라이버는 확장 페칭 및 키 집합 기반 커서를 지원하는 경우 다이너셋을 지원할 수 있습니다. ODBC 적합성 수준에 대한 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md)를 참조하십시오.

> [!NOTE]
> 스냅숏과 다이너셋을 모두 사용하려면 두 개의 서로 `CDatabase` 다른 개체(두 개의 서로 다른 연결)를 기반으로 해야 합니다.

ODBC 커서 라이브러리에서 유지 관리하는 중간 저장소를 사용하는 스냅숏과 달리 다이너셋은 스크롤하는 즉시 데이터 원본에서 직접 레코드를 가져옵니다. 이렇게 하면 다이너셋에서 원래 선택한 레코드가 데이터 원본과 동기화됩니다.

이 버전의 Visual C++에 포함된 ODBC 드라이버 목록과 추가 드라이버를 가져오는 방법에 대한 자세한 내용은 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[개방형 데이터베이스 연결(ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
