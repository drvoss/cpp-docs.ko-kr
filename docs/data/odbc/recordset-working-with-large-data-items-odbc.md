---
title: '레코드 집합: 대형 데이터 항목 작업(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
ms.openlocfilehash: 872fa7229738314b86b6ae6c0d5dc5a5562b27f1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360608"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>레코드 집합: 대형 데이터 항목 작업(ODBC)

이 항목은 MFC ODBC 클래스와 MFC DAO 클래스 모두에 적용됩니다.

> [!NOTE]
> MFC DAO 클래스를 사용하는 경우 [클래스 CLongBinary가](../../mfc/reference/clongbinary-class.md)아닌 클래스 [CByteArray를](../../mfc/reference/cbytearray-class.md) 사용하여 큰 데이터 항목을 관리합니다. 대량 행 가져오기와 함께 MFC ODBC 클래스를 `CLongBinary` 사용하는 `CByteArray`경우 를 대신 사용합니다. 대량 행 가져오기에 대한 자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

데이터베이스에서 비트맵(직원 사진, 지도, 제품 사진, OLE 개체 등)과 같은 큰 데이터를 저장할 수 있다고 가정합니다. 이러한 종류의 데이터는 다음과 같은 이유로 이진 대형 개체(또는 BLOB)라고도 합니다.

- 각 필드 값은 큽습니다.

- 숫자 및 기타 간단한 데이터 형식과 달리 예측 가능한 크기는 없습니다.

- 데이터는 프로그램의 관점에서 형태가 없습니다.

이 항목에서는 데이터베이스 클래스가 이러한 개체작업에 제공하는 지원에 대해 설명합니다.

## <a name="managing-large-objects"></a><a name="_core_managing_large_objects"></a>대형 개체 관리

레코드 집합에는 이진 큰 개체를 관리하는 특별한 어려움을 해결하는 두 가지 방법이 있습니다. 클래스 [CByteArray를](../../mfc/reference/cbytearray-class.md) 사용하거나 클래스 [CLongBinary를](../../mfc/reference/clongbinary-class.md)사용할 수 있습니다. 일반적으로 `CByteArray` 큰 이진 데이터를 관리하는 것이 선호되는 방법입니다.

`CByteArray``CLongBinary` [CByteArray 클래스에](#_core_the_cbytearray_class)설명된 대로 보다 더 많은 오버헤드가 필요하지만 더 많은 수의 오버헤드가 필요합니다. `CLongBinary`[CLongBinary 클래스에](#_core_the_clongbinary_class)간략하게 설명되어 있습니다.

대용량 데이터 `CByteArray` 항목으로 작업하는 데 사용하는 데 사용하는 것에 대한 자세한 내용은 [기술 참고 45를](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)참조하십시오.

## <a name="cbytearray-class"></a><a name="_core_the_cbytearray_class"></a>CByteArray 클래스

`CByteArray`는 MFC 컬렉션 클래스 중 하나입니다. 개체는 `CByteArray` 바이트의 동적 배열을 저장합니다 - 필요한 경우 배열이 증가할 수 있습니다. 클래스는 기본 제공 C ++ 배열과 마찬가지로 인덱스로 빠른 액세스를 제공합니다. `CByteArray`개체를 진단 목적으로 직렬화하고 덤프할 수 있습니다. 클래스는 지정된 바이트를 받고 설정하고, 바이트를 삽입 및 추가하고, 1바이트 또는 모든 바이트를 제거하기 위한 멤버 함수를 제공합니다. 이러한 시설을 통해 이진 데이터를 쉽게 구문 분석할 수 있습니다. 예를 들어 이진 개체가 OLE 개체인 경우 실제 개체에 도달하기 위해 일부 헤더 바이트를 통해 작업해야 할 수 있습니다.

## <a name="using-cbytearray-in-recordsets"></a><a name="_core_using_cbytearray_in_recordsets"></a>레코드 집합에서 CByteArray 사용

레코드 집합의 필드 데이터 멤버에게 `CByteArray`형식을 부여하면 [RFX가](../../data/odbc/record-field-exchange-rfx.md) 레코드 집합과 데이터 원본 간에 이러한 개체의 전송을 관리하고 개체 내부의 데이터를 조작할 수 있는 고정 된 기반을 제공합니다. RFX는 검색된 데이터에 대해 특정 사이트가 필요하며 기본 데이터에 액세스하는 방법이 필요합니다.

대용량 데이터 `CByteArray` 항목으로 작업하는 데 사용하는 데 사용하는 것에 대한 자세한 내용은 [기술 참고 45를](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)참조하십시오.

## <a name="clongbinary-class"></a><a name="_core_the_clongbinary_class"></a>CLongBinary 클래스

[CLongBinary](../../mfc/reference/clongbinary-class.md) 개체는 힙에 할당된 저장소 블록에 대한 `HGLOBAL` 핸들 주위의 간단한 셸입니다. 이진 큰 개체를 포함하는 테이블 열을 바인딩할 때 RFX는 데이터를 레코드 집합으로 전송해야 할 때 `HGLOBAL` 핸들을 할당하고 레코드 집합 필드에 핸들을 `CLongBinary` 저장합니다.

그런 다음 `HGLOBAL` 핸들, `m_hData`을 사용하여 데이터 자체로 작업하고 모든 핸들 데이터에서와 마찬가지로 데이터로 작동합니다. [CByteArray](../../mfc/reference/cbytearray-class.md) 기능을 추가하는 곳입니다.

> [!CAUTION]
> CLongBinary 개체는 함수 호출의 매개 변수로 사용할 수 없습니다. 또한 `::SQLGetData`호출하는 구현에서는 스크롤 가능한 스냅숏에 대한 스크롤 성능이 느려집니다. 동적 스키마 열을 검색하기 `::SQLGetData` 위해 직접 호출을 사용하는 경우에도 마찬가지일 수 있습니다.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 합계 및 다른 집계 결과 구하기(ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[레코드 필드 교환(RFX)](../../data/odbc/record-field-exchange-rfx.md)
