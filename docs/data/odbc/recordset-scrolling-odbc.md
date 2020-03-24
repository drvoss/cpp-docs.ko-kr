---
title: '레코드 집합: 스크롤(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets [C++], end of
- recordsets [C++], beginning of
- navigation [C++], recordsets
- recordsets [C++], moving to records
- ODBC recordsets, scrolling
- recordsets [C++], navigating
- scrolling [C++], recordsets
- Move method (recordsets)
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
ms.openlocfilehash: 8a8305d2acacc79f5d7fe395087a0bd13dcbd196
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212773"
---
# <a name="recordset-scrolling-odbc"></a>레코드 집합: 스크롤(ODBC)

이 항목은 MFC ODBC 클래스에 적용됩니다.

레코드 집합을 연 후에는 레코드에 액세스 하 여 값을 표시 하 고, 계산을 수행 하 고, 보고서를 생성 하는 등의 작업을 수행 해야 합니다. 스크롤을 사용 하면 레코드 집합 내에서 레코드 간에 이동할 수 있습니다.

이 항목에서는 다음 내용을 설명합니다.

- 레코드 [집합에서 한 레코드에서 다른 레코드로 스크롤 하는 방법](#_core_scrolling_from_one_record_to_another)입니다.

- [어떤 상황에서는 스크롤이 지원 되며 지원 되지 않습니다](#_core_when_scrolling_is_supported).

##  <a name="scrolling-from-one-record-to-another"></a><a name="_core_scrolling_from_one_record_to_another"></a>한 레코드에서 다른 레코드로 스크롤

`CRecordset` 클래스는 레코드 집합 내에서 스크롤 하기 위한 `Move` 멤버 함수를 제공 합니다. 이러한 함수는 현재 레코드를 행 집합으로 이동 합니다. 대량 행 페치를 구현한 경우 `Move` 작업은 행 집합의 크기에 따라 레코드 집합의 위치를 조정 합니다. 대량 행 페치를 구현 하지 않은 경우에는 `Move` 함수를 호출 하 여 레코드 집합의 위치를 매번 하나씩로 합니다. 대량 행 페치에 대 한 자세한 내용은 [레코드 집합: 대량 레코드 페치 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조 하세요.

> [!NOTE]
>  레코드 집합을 이동 하는 경우 삭제 된 레코드를 건너뛸 수 없습니다. 자세한 내용은 [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) 멤버 함수를 참조 하세요.

`Move` 함수 외에도 `CRecordset`는 레코드 집합의 끝 부분을 지나서 스크롤 했는지 여부를 확인 하기 위한 멤버 함수를 제공 합니다.

레코드 집합에서 스크롤이 가능한 지 여부를 확인 하려면 `CanScroll` 멤버 함수를 호출 합니다.

#### <a name="to-scroll"></a>스크롤합니다.

1. 하나의 레코드 또는 하나의 행 집합을 전달: [MoveNext](../../mfc/reference/crecordset-class.md#movenext) 멤버 함수를 호출 합니다.

1. 이전 한 레코드 또는 한 개의 행 집합: [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) 멤버 함수를 호출 합니다.

1. 레코드 집합의 첫 번째 레코드: [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) 멤버 함수를 호출 합니다.

1. 레코드 집합의 마지막 레코드나 마지막 행 집합으로 연결 하려면 [MoveLast](../../mfc/reference/crecordset-class.md#movelast) 멤버 함수를 호출 합니다.

1. 현재 위치에 상대적인 *N* 레코드: [Move](../../mfc/reference/crecordset-class.md#move) 멤버 함수를 호출 합니다.

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>레코드 집합의 끝 또는 시작 부분을 테스트 하려면

1. 마지막 레코드를 지나서 스크롤 했습니까? [IsEOF](../../mfc/reference/crecordset-class.md#iseof) 멤버 함수를 호출 합니다.

1. 첫 번째 레코드 (뒤로 이동) 앞으로 스크롤 했습니까? [IsBOF](../../mfc/reference/crecordset-class.md#isbof) 멤버 함수를 호출 합니다.

다음 코드 예제에서는 `IsBOF` 및 `IsEOF`를 사용 하 여 어느 방향으로든 스크롤할 때 레코드 집합의 한도를 검색 합니다.

```
// Open a recordset; first record is current
CCustSet rsCustSet( NULL );
rsCustSet.Open( );

if( rsCustSet.IsBOF( ) )
    return;
    // The recordset is empty

// Scroll to the end of the recordset, past
// the last record, so no record is current
while ( !rsCustSet.IsEOF( ) )
    rsCustSet.MoveNext( );

// Move to the last record
rsCustSet.MoveLast( );

// Scroll to beginning of the recordset, before
// the first record, so no record is current
while( !rsCustSet.IsBOF( ) )
    rsCustSet.MovePrev( );

// First record is current again
rsCustSet.MoveFirst( );
```

레코드 집합이 마지막 레코드를 지나서 배치 된 경우 `IsEOF`은 0이 아닌 값을 반환 합니다. 레코드 집합을 첫 번째 레코드 앞에 배치 하는 경우 (모든 레코드 앞) `IsBOF`에서 0이 아닌 값을 반환 합니다. 어떤 경우 든 작업할 현재 레코드가 없습니다. `IsBOF` 이미 TRUE 이거나 `IsEOF` 이미 TRUE 인 경우 `MoveNext`를 호출 `MovePrev` 하는 경우 프레임 워크는 `CDBException`을 throw 합니다. `IsBOF` 및 `IsEOF`를 사용 하 여 빈 레코드 집합을 확인할 수도 있습니다.

레코드 집합 탐색에 대 한 자세한 내용은 [레코드 집합: 책갈피 및 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)를 참조 하세요.

##  <a name="when-scrolling-is-supported"></a><a name="_core_when_scrolling_is_supported"></a>스크롤이 지원 되는 경우

원래 설계 했 듯이 SQL은 앞 으로만 스크롤 기능을 제공 하지만 ODBC는 스크롤 기능을 확장 합니다. 스크롤에 대 한 사용 가능한 지원 수준은 응용 프로그램이 작동 하는 ODBC 드라이버, 드라이버의 ODBC API 규칙 수준 및 ODBC 커서 라이브러리가 메모리에 로드 되는지 여부에 따라 달라 집니다. 자세한 내용은 odbc 및 odbc [: Odbc 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)를 [참조 하십시오.](../../data/odbc/odbc-basics.md)

> [!TIP]
>  커서 라이브러리가 사용 되는지 여부를 제어할 수 있습니다. *BUseCursorLib* 및 *DwOptions* parameters To [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open)을 참조 하세요.

> [!NOTE]
>  Mfc DAO 클래스와 달리 MFC ODBC 클래스는 지정 된 조건을 충족 하는 다음 (또는 이전) 레코드를 찾기 위한 `Find` 함수 집합을 제공 하지 않습니다.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset:: CanScroll](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[CRecordset:: CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[레코드 집합: 레코드 필터링(ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
