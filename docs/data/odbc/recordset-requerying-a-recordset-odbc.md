---
title: '레코드 집합: 레코드 집합 다시 쿼리(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
ms.openlocfilehash: cdae28f81eebe8427bc829072e0d9a83c6ec1722
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366955"
---
# <a name="recordset-requerying-a-recordset-odbc"></a>레코드 집합: 레코드 집합 다시 쿼리(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

이 항목에서는 레코드 집합 개체를 사용하여 데이터베이스에서 자체적으로 다시 쿼리(즉, 새로 고침)하는 방법과 [Requery](../../mfc/reference/crecordset-class.md#requery) 멤버 함수를 사용하여 이를 수행할 수 있는 시기에 대해 설명합니다.

레코드 집합을 다시 쿼리하는 주요 이유는 다음과 같습니다.

- 사용자 또는 다른 사용자가 추가한 레코드 및 다른 사용자가 삭제한 레코드(삭제한 레코드가 이미 레코드 집합에 반영됨)와 관련하여 레코드 집합을 최신 상태로 유지합니다.

- 매개 변수 값 변경에 따라 레코드 집합을 새로 고칩니다.

## <a name="bringing-the-recordset-up-to-date"></a><a name="_core_bringing_the_recordset_up_to_date"></a>레코드 집합을 최신 상태로 설정

레코드 집합 개체를 최신 상태로 유지하려면 자주 쿼리해야 합니다. 다중 사용자 데이터베이스 환경에서 다른 사용자는 레코드 집합의 수명 동안 데이터를 변경할 수 있습니다. 레코드 집합이 다른 사용자의 변경 내용을 반영하는 시기와 다른 사용자의 레코드 집합이 변경 내용을 반영하는 시기에 대한 자세한 내용은 [레코드 집합: 레코드 집합 업데이트 레코드(ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 및 [Dynaset을](../../data/odbc/dynaset.md)참조하십시오.

## <a name="requerying-based-on-new-parameters"></a><a name="_core_requerying_based_on_new_parameters"></a>새 매개 변수에 따라 다시 쿼리

[Requery를](../../mfc/reference/crecordset-class.md#requery) 사용하는 또 다른 빈도와 마찬가지로 중요한 것은 매개 변수 값 변경에 따라 새 레코드 집합을 선택하는 것입니다.

> [!TIP]
> 매개 변수 값을 변경하는 경우 `Requery` 다시 호출하는 `Open` 경우보다 쿼리 속도가 훨씬 빠릅니다.

## <a name="requerying-dynasets-vs-snapshots"></a><a name="_core_requerying_dynasets_vs.._snapshots"></a>다이나셋 재쿼리 vs. 스냅샷

다이너셋은 동적 최신 데이터가 있는 레코드 집합을 표시하기 위한 것이기 때문에 다른 사용자의 추가 를 반영하려는 경우 다이너셋을 자주 쿼리하려고 합니다. 반면 스냅숏은 보고서를 준비하고 합계를 계산하는 동안 정적 내용을 안전하게 사용할 수 있으므로 유용합니다. 그래도 스냅샷도 다시 쿼리할 수 있습니다. 다중 사용자 환경에서는 다른 사용자가 데이터베이스를 변경할 때 스냅숏 데이터가 데이터 원본과의 동기화를 잃을 수 있습니다.

#### <a name="to-requery-a-recordset-object"></a>레코드 집합 개체를 다시 쿼리하려면

1. 개체의 [Requery](../../mfc/reference/crecordset-class.md#requery) 멤버 함수를 호출합니다.

또는 원래 레코드 집합을 닫고 다시 열 수 있습니다. 두 경우 모두 새 레코드 집합은 데이터 원본의 현재 상태를 나타냅니다.

예를 들어 [두 번째 레코드 집합에서 목록 상자 채우기 보기 레코드를](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)참조하십시오.

> [!TIP]
> 성능을 `Requery` 최적화하려면 레코드 집합의 [필터](../../data/odbc/recordset-filtering-records-odbc.md) 또는 [정렬을](../../data/odbc/recordset-sorting-records-odbc.md)변경하지 마십시오. 을 호출하기 전에 `Requery`매개 변수 값만 변경합니다.

호출에 `Requery` 실패하면 호출을 다시 시도할 수 있습니다. 그렇지 않으면 응용 프로그램이 정상적으로 종료되어야 합니다. 여러 가지 `Requery` `Open` 이유로 호출하거나 실패할 수 있습니다. 네트워크 오류가 발생할 수 있습니다. 또는 통화 중에 기존 데이터가 해제된 후 새 데이터를 얻기 전에 다른 사용자가 단독 액세스 권한을 얻을 수 있습니다. 또는 레코드 집합이 종속된 테이블을 삭제할 수 있습니다.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 데이터 열 동적 바인딩(ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[레코드 집합: 레코드 집합 만들기 및 닫기(ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)
