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
ms.openlocfilehash: 931051296dff495939fcbd894102a1b00e48ee90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366933"
---
# <a name="recordset-scrolling-odbc"></a>레코드 집합: 스크롤(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

레코드 집합을 연 후에는 레코드에 액세스하여 값을 표시하고 계산을 수행하며 보고서를 생성해야 합니다. 스크롤을 사용하면 레코드에서 레코드 집합으로 이동할 수 있습니다.

이 토픽에서는 다음 내용을 설명합니다.

- [레코드 집합에서 한 레코드에서 다른 레코드로 스크롤하는 방법.](#_core_scrolling_from_one_record_to_another)

- [어떤 상황에서 스크롤은 지원되지 않습니다.](#_core_when_scrolling_is_supported)

## <a name="scrolling-from-one-record-to-another"></a><a name="_core_scrolling_from_one_record_to_another"></a>한 레코드에서 다른 레코드로 스크롤

클래스는 `CRecordset` `Move` 레코드 집합 내에서 스크롤할 수 있는 멤버 함수를 제공합니다. 이러한 함수는 현재 레코드를 행 집합으로 이동합니다. 대량 행 가져오기를 구현한 `Move` 경우 작업은 레코드 집합을 행 집합크기로 재배치합니다. 대량 행 가져오기를 구현하지 않은 경우 `Move` 함수호출은 레코드 집합을 매번 하나의 레코드로 재배치합니다. 대량 행 가져오기에 대한 자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

> [!NOTE]
> 레코드 집합을 이동할 때 삭제된 레코드를 건너뛸 수 없습니다. 자세한 내용은 [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) 멤버 함수를 참조하십시오.

`Move` 함수 외에도 레코드 집합의 끝을 지나또는 앞서 스크롤했는지 여부를 확인하는 멤버 함수를 `CRecordset` 제공합니다.

레코드 집합에서 스크롤이 가능한지 확인하려면 `CanScroll` 멤버 함수를 호출합니다.

#### <a name="to-scroll"></a>스크롤하려면

1. 하나의 레코드 또는 하나의 행 집합을 전달: [MoveNext](../../mfc/reference/crecordset-class.md#movenext) 멤버 함수를 호출합니다.

1. 뒤로 하나의 레코드 또는 하나의 행 집합: [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) 멤버 함수를 호출합니다.

1. 레코드 집합의 첫 번째 레코드에 [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) 멤버 함수를 호출합니다.

1. 레코드 집합의 마지막 레코드 또는 마지막 행 집합에: [MoveLast](../../mfc/reference/crecordset-class.md#movelast) 멤버 함수를 호출합니다.

1. *현재* 위치를 기준으로 N 레코드: [Move](../../mfc/reference/crecordset-class.md#move) 멤버 함수를 호출합니다.

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>레코드 집합의 끝 또는 시작 부분을 테스트하려면

1. 마지막 레코드를 지나 스크롤했습니까? [IsEOF](../../mfc/reference/crecordset-class.md#iseof) 멤버 함수를 호출합니다.

1. 첫 번째 레코드보다 먼저 스크롤했습니까(뒤로 이동)? [IsBOF](../../mfc/reference/crecordset-class.md#isbof) 멤버 함수를 호출합니다.

다음 코드 예제에서는 `IsEOF` 어느 방향으로든 스크롤할 때 레코드 집합의 한계를 검색하고 사용합니다. `IsBOF`

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

`IsEOF`은 레코드 집합이 마지막 레코드를 지나 위치하는 경우 비영값을 반환합니다. `IsBOF`레코드 집합이 첫 번째 레코드보다 먼저 위치하는 경우 비영값을 반환합니다(모든 레코드 앞). 두 경우 모두 작동할 현재 레코드가 없습니다. TRUE가 `MovePrev` 이미 `IsBOF` 있는 경우 `MoveNext` 호출하거나 이미 TRUE인 경우 `IsEOF` `CDBException`호출하는 경우 프레임워크는 을 throw합니다. 빈 레코드 `IsBOF` `IsEOF` 집합을 사용하고 확인할 수도 있습니다.

레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 북마크 및 절대 위치(ODBC)를](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)참조하십시오.

## <a name="when-scrolling-is-supported"></a><a name="_core_when_scrolling_is_supported"></a>스크롤이 지원되는 경우

원래 설계된 대로 SQL은 앞으로 스크롤만 제공했지만 ODBC는 스크롤 기능을 확장합니다. 스크롤에 사용할 수 있는 지원 수준은 응용 프로그램에서 작동하는 ODBC 드라이버, 드라이버의 ODBC API 준수 수준 및 ODBC 커서 라이브러리가 메모리에 로드되는지 여부에 따라 달라집니다. 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 및 [ODBC: ODBC 커서 라이브러리를](../../data/odbc/odbc-the-odbc-cursor-library.md)참조하십시오.

> [!TIP]
> 커서 라이브러리가 사용되는지 여부를 제어할 수 있습니다. [cDatabase:::open](../../mfc/reference/cdatabase-class.md#open)에 대한 *bUseCursorLib* 및 *dwOptions* 매개 변수를 참조하십시오.

> [!NOTE]
> MFC DAO 클래스와 달리 MFC ODBC 클래스는 `Find` 지정된 기준을 충족하는 다음(또는 이전) 레코드를 찾기 위한 함수 집합을 제공하지 않습니다.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[C레코드 집합::수스크롤](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[C레코드 집합::검사행집합오류](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[레코드 집합: 레코드 필터링(ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
