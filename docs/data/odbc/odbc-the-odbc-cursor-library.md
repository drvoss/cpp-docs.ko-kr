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
ms.openlocfilehash: 51524604cad34ace18ffda2b5f48cc3c5fd89ad7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213098"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC 커서 라이브러리

이 항목에서는 ODBC 커서 라이브러리에 대해 설명 하 고이를 사용 하는 방법을 설명 합니다. 자세한 내용은 다음을 참조하세요.

- [커서 라이브러리 및 수준 1 ODBC 드라이버](#_core_the_cursor_library_and_level_1_odbc_drivers)

- [위치 지정 업데이트 및 타임 스탬프 열](#_core_positioned_updates_and_timestamp_columns)

- [커서 라이브러리 사용](#_core_using_the_cursor_library)

ODBC 커서 라이브러리는 ODBC 드라이버 관리자와 드라이버 사이에 있는 DLL (동적 연결 라이브러리)입니다. ODBC 용어로 드라이버는 커서를 유지 하 여 레코드 집합에서의 위치를 추적 합니다. 커서는 이미 스크롤 된 레코드 집합의 위치 (현재 레코드)를 표시 합니다.

##  <a name="cursor-library-and-level-1-odbc-drivers"></a><a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a>커서 라이브러리 및 수준 1 ODBC 드라이버

ODBC 커서 라이브러리는 수준 1 드라이버에 다음과 같은 새 기능을 제공 합니다.

- 앞으로 및 뒤로 스크롤 수준 2 드라이버는 이미 스크롤할 수 있으므로 커서 라이브러리가 필요 하지 않습니다.

- 스냅숏에 대 한 지원. 커서 라이브러리는 스냅숏의 레코드를 포함 하는 버퍼를 관리 합니다. 이 버퍼는 프로그램의 삭제 및 편집을 반영 하지만 다른 사용자의 추가, 삭제 또는 편집은 반영 하지 않습니다. 따라서 스냅숏은 커서 라이브러리의 버퍼로만 최신입니다. 또한 `Requery`를 호출할 때까지 버퍼에는 자체의 추가 항목이 반영 되지 않습니다. 다이너셋은 커서 라이브러리를 사용 하지 않습니다.

커서 라이브러리는 드라이버에서 일반적으로 지원 되지 않는 경우에도 스냅숏 (정적 커서)을 제공 합니다. 드라이버가 이미 정적 커서를 지 원하는 경우 스냅숏 지원을 얻기 위해 커서 라이브러리를 로드할 필요가 없습니다. 커서 라이브러리를 사용 하는 경우에는 스냅숏과 전달 전용 레코드 집합만 사용할 수 있습니다. 드라이버가 다이너셋 (KEYSET_DRIVEN 커서)을 지 원하는 경우이를 사용 하려면 커서 라이브러리를 사용 하면 안 됩니다. 스냅숏과 다이너셋을 모두 사용 하려면 드라이버가 둘 다를 지 원하는 경우를 제외 하 고 두 개의 서로 다른 `CDatabase` 개체 (두 개의 연결)를 기반으로 해야 합니다.

##  <a name="positioned-updates-and-timestamp-columns"></a><a name="_core_positioned_updates_and_timestamp_columns"></a>위치 지정 업데이트 및 타임 스탬프 열

> [!NOTE]
>  ODBC 데이터 소스는 이 항목에서 설명하는 MFC ODBC 클래스뿐 아니라 MFC Data Access Object(DAO) 클래스를 통해서도 액세스할 수 있습니다.

> [!NOTE]
>  ODBC 드라이버가 사용 가능한 경우 MFC에서 사용 하는 `SQLSetPos`를 지 원하는 경우에는이 항목이 적용 되지 않습니다.

대부분의 수준 1 드라이버는 위치 지정 업데이트를 지원 하지 않습니다. 이러한 드라이버는 커서 라이브러리를 사용 하 여 이러한 측면에서 수준 2 드라이버의 기능을 에뮬레이트합니다. 커서 라이브러리는 변경 되지 않은 필드에서 검색 된 업데이트를 수행 하 여 위치 지정 업데이트 지원을 에뮬레이트합니다.

일부 경우에는 레코드 집합에 이러한 변경 되지 않은 필드 중 하나로 타임 스탬프 열이 포함 될 수 있습니다. 타임 스탬프 열이 포함 된 테이블과 MFC 레코드 집합을 사용 하는 경우 두 가지 문제가 발생 합니다.

첫 번째 문제는 타임 스탬프 열이 있는 테이블의 업데이트할 수 있는 스냅숏과 관련이 있습니다. 스냅숏이 바인딩된 테이블에 timestamp 열이 포함 된 경우 `Edit` 및 `Update`를 호출한 후 `Requery`를 호출 해야 합니다. 그렇지 않으면 같은 레코드를 다시 편집 하지 못할 수 있습니다. `Edit`를 호출 하 고 `Update`하면 레코드가 데이터 원본에 기록 되 고 타임 스탬프 열이 업데이트 됩니다. `Requery`를 호출 하지 않으면 스냅숏의 레코드에 대 한 타임 스탬프 값이 데이터 소스의 해당 타임 스탬프와 더 이상 일치 하지 않습니다. 레코드를 다시 업데이트 하려고 하면 일치 하지 않기 때문에 데이터 원본에서 업데이트를 허용 하지 않을 수 있습니다.

두 번째 문제는 `RFX_Date` 함수와 함께 사용 하 여 테이블 간에 시간 및 날짜 정보를 전송 하는 클래스 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 의 제한 사항을 다룹니다. `CTime` 개체를 처리 하면 데이터를 전송 하는 동안 추가 중간 처리 형태로 약간의 오버 헤드가 발생 합니다. `CTime` 개체의 날짜 범위는 일부 응용 프로그램에 대해 너무 제한 될 수도 있습니다. 새 버전의 `RFX_Date` 함수는 `CTime` 개체 대신 ODBC *TIMESTAMP_STRUCT* 매개 변수를 사용 합니다. 자세한 내용은 *MFC 참조*의 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) `RFX_Date`를 참조 하세요.

##  <a name="using-the-cursor-library"></a><a name="_core_using_the_cursor_library"></a>커서 라이브러리 사용

데이터 원본에 연결할 때 ( [cdatabase:: microsoft.office.interop.visio.documents.openex](../../mfc/reference/cdatabase-class.md#openex) 또는 [Cdatabase:: Open](../../mfc/reference/cdatabase-class.md#open) )를 호출 하 여 데이터 소스에 대 한 커서 라이브러리를 사용할지 여부를 지정할 수 있습니다. 해당 데이터 원본에 대 한 스냅숏을 만들 경우 `dwOptions` 매개 변수에 `CDatabase::useCursorLib` 옵션을 지정 하 여 `OpenEx` 하거나 *bUseCursorLib* 매개 변수에 true를 지정 하 여 `Open` 합니다 (기본값은 true 임). ODBC 드라이버가 다이너셋을 지원 하 고 데이터 원본에서 다이너셋을 열려면 커서 라이브러리를 사용 하지 마십시오 (다이너셋에 필요한 일부 드라이버 기능을 마스크 함). 이 경우 `OpenEx`에서 `CDatabase::useCursorLib` 지정 하지 않거나 `Open`에서 *bUseCursorLib* 매개 변수에 대해 FALSE를 지정 합니다.

## <a name="see-also"></a>참고 항목

[ODBC 기본 사항](../../data/odbc/odbc-basics.md)
