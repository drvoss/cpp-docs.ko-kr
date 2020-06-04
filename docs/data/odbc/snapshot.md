---
title: 스냅샷
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC cursor library [ODBC], snapshots
- cursors [ODBC], static
- recordsets, snapshots
- snapshots, support in ODBC
- static cursors
- ODBC recordsets, snapshots
- cursor library [ODBC], snapshots
- snapshots
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
ms.openlocfilehash: e487b5abcc5eee4e3f4b1941100980eac4a040c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366916"
---
# <a name="snapshot"></a>스냅샷

스냅숏은 스냅숏을 만들 때 존재했던 데이터의 정적 보기를 반영하는 레코드 집합입니다. 스냅숏을 열고 모든 레코드로 이동하면 에 포함된 레코드 집합과 해당 값이 호출하여 `Requery`스냅숏을 다시 빌드할 때까지 변경되지 않습니다.

> [!NOTE]
> 이 토픽은 MFC ODBC 클래스에 적용됩니다. MFC ODBC 클래스 대신 MFC DAO 클래스를 사용하는 경우 스냅숏 형식 레코드 집합에 대한 설명은 [CDaoRecordset::Open을](../../mfc/reference/cdaorecordset-class.md#open) 참조하십시오.

데이터베이스 클래스를 사용하여 업데이트 가능하거나 읽기 전용 스냅숏을 만들 수 있습니다. 다이너셋과 달리 업데이트 가능한 스냅숏은 다른 사용자가 만든 레코드 값의 변경 내용을 반영하지 않지만 프로그램에서 만든 업데이트 및 삭제를 반영합니다. 을 호출할 `Requery`때까지 스냅숏에 추가된 레코드가 스냅숏에 표시되지 않습니다.

> [!TIP]
> 스냅샷은 ODBC 정적 커서입니다. 정적 커서는 해당 레코드로 스크롤할 때까지 실제로 데이터 행을 얻지 못합니다. 모든 레코드를 즉시 검색하려면 레코드 집합의 끝으로 스크롤한 다음 표시할 첫 번째 레코드로 스크롤할 수 있습니다. 그러나 끝까지 스크롤하면 추가 오버헤드가 수반되고 성능이 저하될 수 있습니다.

스냅숏은 보고서를 생성하거나 계산을 수행할 때와 같이 작업 중에 데이터를 고정상태로 유지해야 할 때 가장 유용합니다. 그럼에도 불구하고 데이터 원본은 스냅숏과 상당히 다를 수 있으므로 수시로 다시 빌드할 수 있습니다.

스냅숏 지원은 모든 수준 1 드라이버에 대해 정적 커서 및 위치 업데이트(업데이트 가능성에 필요)를 제공하는 ODBC 커서 라이브러리를 기반으로 합니다. 이 지원을 위해 커서 라이브러리 DLL을 메모리에 로드해야 합니다. 개체를 `CDatabase` 생성하고 해당 `OpenEx` 멤버 함수를 `CDatabase::useCursorLib` 호출할 때 *dwOptions* 매개 변수옵션을 지정해야 합니다. 멤버 함수를 `Open` 호출하면 커서 라이브러리가 기본적으로 로드됩니다. 스냅숏 대신 다이너셋을 사용하는 경우 커서 라이브러리를 로드하지 않으려고 합니다.

스냅샷은 `CDatabase` 개체가 생성될 때 ODBC 커서 라이브러리가 로드되었거나 사용 중인 ODBC 드라이버가 정적 커서를 지원하는 경우에만 사용할 수 있습니다.

> [!NOTE]
> 일부 ODBC 드라이버의 경우 스냅숏(정적 커서)을 업데이트할 수 없습니다. 지원되는 커서 유형과 지원되는 동시성 유형에 대한 드라이버 설명서를 확인합니다. 업데이트 가능한 스냅숏을 보장하려면 `CDatabase` 개체를 만들 때 커서 라이브러리를 메모리에 로드해야 합니다. 자세한 내용은 [ODBC: ODBC 커서 라이브러리를](../../data/odbc/odbc-the-odbc-cursor-library.md)참조하십시오.

> [!NOTE]
> 스냅숏과 다이너셋을 모두 사용하려면 두 개의 서로 `CDatabase` 다른 개체(두 개의 서로 다른 연결)를 기반으로 해야 합니다.

모든 레코드 집합과 공유하는 속성 스냅숏에 대한 자세한 내용은 [레코드 집합(ODBC)을](../../data/odbc/recordset-odbc.md)참조하십시오. ODBC 커서 라이브러리를 포함한 ODBC 및 스냅샷에 대한 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[개방형 데이터베이스 연결(ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
