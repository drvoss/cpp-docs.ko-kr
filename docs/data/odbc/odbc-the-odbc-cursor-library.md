---
title: 'ODBC: ODBC 커서 라이브러리'
ms.date: 11/04/2016
helpviewer_keywords:
- cursor library [ODBC]
- snapshots, support in ODBC
- timestamps, ODBC timestamp columns
- ODBC cursor library [ODBC]
- static cursors
- ODBC drivers, Level 1
- ODBC drivers, cursor support
- positioned updates
- cursors, ODBC cursor library
- Level 1 ODBC drivers
- cursor library [ODBC], snapshots
- ODBC, timestamp
- positioning cursors
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
ms.openlocfilehash: 13640dd2a8593057bef708a45dfc8471ba212563
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367188"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC 커서 라이브러리

이 항목에서는 ODBC 커서 라이브러리를 설명하고 사용 방법에 대해 설명합니다. 자세한 내용은 다음을 참조하세요.

- [커서 라이브러리 및 레벨 1 ODBC 드라이버](#_core_the_cursor_library_and_level_1_odbc_drivers)

- [위치 업데이트 및 타임스탬프 열](#_core_positioned_updates_and_timestamp_columns)

- [커서 라이브러리 사용](#_core_using_the_cursor_library)

ODBC 커서 라이브러리는 ODBC 드라이버 관리자와 드라이버 사이에 있는 동적 링크 라이브러리(DLL)입니다. ODBC 용어에서 드라이버는 레코드 집합에서 해당 위치를 추적하기 위해 커서를 유지 관리합니다. 커서는 이미 스크롤한 레코드 집합(현재 레코드)의 위치를 표시합니다.

## <a name="cursor-library-and-level-1-odbc-drivers"></a><a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a>커서 라이브러리 및 레벨 1 ODBC 드라이버

ODBC 커서 라이브러리는 레벨 1 드라이버에게 다음과 같은 새로운 기능을 제공합니다.

- 앞으로 스크롤합니다. 수준 2 드라이버는 이미 스크롤할 수 있으므로 커서 라이브러리가 필요하지 않습니다.

- 스냅샷 에 대한 지원. 커서 라이브러리는 스냅숏 레코드를 포함하는 버퍼를 관리합니다. 이 버퍼는 레코드에 대한 프로그램의 삭제 및 편집을 반영하지만 다른 사용자의 추가, 삭제 또는 편집은 반영하지 않습니다. 따라서 스냅숏은 커서 라이브러리의 버퍼만큼이나 최신입니다. 또한 버퍼는 호출할 `Requery`때까지 사용자 고유의 추가 를 반영하지 않습니다. 커서 라이브러리를 사용하지 않는 다이나셋입니다.

커서 라이브러리는 드라이버에서 일반적으로 지원되지 않는 경우에도 스냅샷(정적 커서)을 제공합니다. 드라이버가 이미 정적 커서를 지원하는 경우 스냅숏 지원을 받기 위해 커서 라이브러리를 로드할 필요가 없습니다. 커서 라이브러리를 사용하는 경우 스냅숏 및 정방향 전용 레코드 집합만 사용할 수 있습니다. 드라이버가 다이너셋(KEYSET_DRIVEN 커서)을 지원하고 이를 사용하려는 경우 커서 라이브러리를 사용해서는 안 됩니다. 스냅숏과 다이너셋을 모두 사용하려면 드라이버가 둘 `CDatabase` 다 지원하지 않는 한 두 개의 서로 다른 개체(두 개의 서로 다른 연결)를 기반으로 해야 합니다.

## <a name="positioned-updates-and-timestamp-columns"></a><a name="_core_positioned_updates_and_timestamp_columns"></a>위치 업데이트 및 타임스탬프 열

> [!NOTE]
> ODBC 데이터 원본은 이 항목에 설명된 대로 MFC ODBC 클래스 또는 MFC 데이터 액세스 개체(DAO) 클래스를 통해 액세스할 수 있습니다.

> [!NOTE]
> ODBC `SQLSetPos`드라이버가 지원되는 경우 MFC가 사용 가능한 경우 이 항목은 적용되지 않습니다.

대부분의 레벨 1 드라이버는 위치 업데이트를 지원하지 않습니다. 이러한 드라이버는 이와 관련하여 수준 2 드라이버의 기능을 에뮬레이트하기 위해 커서 라이브러리에 의존합니다. 커서 라이브러리는 변경되지 않는 필드에서 검색된 업데이트를 수행하여 위치 된 업데이트 지원을 에뮬레이트합니다.

경우에 따라 레코드 집합에 타임스탬프 열이 변경되지 않는 필드 중 하나로 포함될 수 있습니다. 타임스탬프 열이 포함된 테이블이 있는 MFC 레코드 집합을 사용할 때 두 가지 문제가 발생합니다.

첫 번째 문제는 타임스탬프 열이 있는 테이블에서 업데이트 가능한 스냅숏과 관련이 있습니다. 스냅숏이 바인딩된 테이블에 타임스탬프 열이 포함되어 있으면 `Requery` 호출 `Edit` 한 `Update`후 호출해야 합니다. 그렇지 않으면 동일한 레코드를 다시 편집하지 못할 수 있습니다. 호출한 `Edit` 다음 `Update`레코드가 데이터 원본에 기록되고 타임스탬프 열이 업데이트됩니다. 호출하지 `Requery`않으면 스냅숏의 레코드에 대한 타임스탬프 값이 더 이상 데이터 원본의 해당 타임스탬프와 일치하지 않습니다. 레코드를 다시 업데이트하려고 하면 데이터 원본이 불일치로 인해 업데이트를 허용하지 않을 수 있습니다.

두 번째 문제는 테이블과 날짜 정보를 전송하는 `RFX_Date` 함수와 함께 사용할 때 클래스 [CTime의](../../atl-mfc-shared/reference/ctime-class.md) 제한에 관한 것입니다. 개체를 `CTime` 처리하면 데이터 전송 중에 추가 중간 처리 형식으로 일부 오버헤드가 발생합니다. 개체의 `CTime` 날짜 범위가 일부 응용 프로그램에 대해 너무 제한적일 수도 있습니다. 함수의 `RFX_Date` 새 버전은 개체 대신 ODBC *TIMESTAMP_STRUCT* 매개 변수를 `CTime` 사용합니다. 자세한 내용은 매크로 `RFX_Date` [및 전역을](../../mfc/reference/mfc-macros-and-globals.md) *참조하여 MFC 참조를*참조하십시오.

## <a name="using-the-cursor-library"></a><a name="_core_using_the_cursor_library"></a>커서 라이브러리 사용

[CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) 또는 [CDatabase::Open을](../../mfc/reference/cdatabase-class.md#open) 호출하여 데이터 원본에 연결할 때 데이터 원본에 커서 라이브러리를 사용할지 여부를 지정할 수 있습니다. 해당 데이터 원본에서 스냅숏을 만들 경우 `CDatabase::useCursorLib` `dwOptions` 매개 변수에 `OpenEx` 옵션을 지정하거나 *bUseCursorLib* `Open` 매개 변수에 대해 TRUE를 지정합니다(기본값은 TRUE). ODBC 드라이버가 다이너셋을 지원하고 데이터 원본에서 다이너셋을 열려면 커서 라이브러리를 사용하지 마십시오(다이너셋에 필요한 일부 드라이버 기능이 마스킹). `CDatabase::useCursorLib` 이 경우 `OpenEx` `Open`에서 *bUseCursorLib* 매개 변수에 대해 FALSE를 지정하거나 지정하지 마십시오.

## <a name="see-also"></a>참고 항목

[ODBC 기본 사항](../../data/odbc/odbc-basics.md)
