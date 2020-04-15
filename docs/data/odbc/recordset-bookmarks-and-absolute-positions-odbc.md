---
title: '레코드 집합: 책갈피와 절대 위치(ODBC)'
ms.date: 11/04/2016
f1_keywords:
- SetAbsolutePosition
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
ms.openlocfilehash: 77c8bbaf7c0bc21dab62c3785364e72656287815
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367063"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>레코드 집합: 책갈피와 절대 위치(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

레코드 집합을 탐색할 때 특정 레코드로 돌아가는 방법이 필요한 경우가 많습니다. 레코드의 책갈피와 절대 위치는 두 가지 방법을 제공합니다.

이 토픽에서는 다음 내용을 설명합니다.

- [책갈피 를 사용하는 방법](#_core_bookmarks_in_mfc_odbc).

- [절대 위치를 사용하여 현재 레코드를 설정하는 방법](#_core_absolute_positions_in_mfc_odbc).

## <a name="bookmarks-in-mfc-odbc"></a><a name="_core_bookmarks_in_mfc_odbc"></a>MFC ODBC의 책갈피

책갈피는 레코드를 고유하게 식별합니다. 레코드 집합을 탐색할 때 레코드 집합에서 레코드를 삭제할 수 있으므로 레코드의 절대 위치에 항상 의존할 수는 없습니다. 레코드의 위치를 추적하는 신뢰할 수 있는 방법은 책갈피를 사용하는 것입니다. 클래스는 `CRecordset` 다음을 위한 멤버 함수를 제공합니다.

- 현재 레코드의 책갈피를 얻으면[변수(GetBookmark)에](../../mfc/reference/crecordset-class.md#getbookmark)저장할 수 있습니다.

- 변수[(SetBookmark)에](../../mfc/reference/crecordset-class.md#setbookmark)이전에 저장 한 책갈피를 지정하여 지정된 레코드로 빠르게 이동합니다.

다음 예제에서는 이러한 멤버 함수를 사용하여 현재 레코드를 표시하고 나중에 다시 반환하는 방법을 보여 줍니다.

```cpp
// rs is a CRecordset or
// CRecordset-derived object

CDBVariant varRecordToReturnTo;
rs.GetBookmark( varRecordToReturnTo );

// More code in which you
// move to other records

rs.SetBookmark( varRecordToReturnTo );
```

[CDBVariant 클래스](../../mfc/reference/cdbvariant-class.md) 개체에서 기본 데이터 형식을 추출할 필요가 없습니다. 값을 `GetBookmark` 할당하고 `SetBookmark`을 사용하여 해당 책갈피로 돌아갑니다.

> [!NOTE]
> ODBC 드라이버 및 레코드 집합 유형에 따라 책갈피가 지원되지 않을 수 있습니다. [CRecordset::CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark)를 호출하여 책갈피가 지원되는지 여부를 쉽게 확인할 수 있습니다. 또한 책갈피가 지원되는 경우 [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) `CRecordset::useBookmarks` 멤버 함수에서 옵션을 지정하여 북마크를 구현하도록 명시적으로 선택해야 합니다. 또한 특정 레코드 집합 작업 후 책갈피의 지속성도 확인해야 합니다. 예를 들어 레코드 `Requery` 집합의 경우 책갈피가 더 이상 유효하지 않을 수 있습니다. [CDatabase::GetBookmark지속성으로](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) 안전하게 호출할 `SetBookmark`수 있는지 확인합니다.

## <a name="absolute-positions-in-mfc-odbc"></a><a name="_core_absolute_positions_in_mfc_odbc"></a>MFC ODBC의 절대 위치

책갈피 외에도 `CRecordset` 클래스를 사용하면 서수 위치를 지정하여 현재 레코드를 설정할 수 있습니다. 이를 절대 위치 지정이라고 합니다.

> [!NOTE]
> 정방향 전용 레코드 집합에는 절대 위치 지정을 사용할 수 없습니다. 정방향 전용 레코드 집합에 대한 자세한 내용은 [레코드 집합(ODBC)을](../../data/odbc/recordset-odbc.md)참조하십시오.

절대 위치를 사용하여 현재 레코드 포인터를 이동하려면 [CRecordset::SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition)를 호출합니다. `SetAbsolutePosition`에 값을 전달하면 해당 서수 위치에 해당하는 레코드가 현재 레코드가 됩니다.

> [!NOTE]
> 레코드의 절대 위치는 잠재적으로 신뢰할 수 없습니다. 사용자가 레코드 집합에서 레코드를 삭제하면 후속 레코드의 서수 위치가 변경됩니다. 책갈피는 현재 레코드를 이동하는 데 권장되는 방법입니다. 자세한 내용은 [MFC ODBC의 북마크](#_core_bookmarks_in_mfc_odbc)를 참조하십시오.

레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 스크롤(ODBC)을](../../data/odbc/recordset-scrolling-odbc.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)
