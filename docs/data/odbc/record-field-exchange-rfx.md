---
title: RFX
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
ms.openlocfilehash: 6f965b90e1e0bbcfd3ad04bb5b40644d61050b2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367158"
---
# <a name="record-field-exchange-rfx"></a>RFX

MFC ODBC 데이터베이스 클래스는 데이터 원본과 [레코드 집합](../../data/odbc/recordset-odbc.md) 개체 간에 데이터를 자동으로 이동합니다. [CRecordset에서](../../mfc/reference/crecordset-class.md) 클래스를 파생 하 고 대량 행 가져오기를 사용 하지 않는 경우 데이터 레코드 필드 교환 (RFX) 메커니즘에 의해 전송 됩니다.

> [!NOTE]
> 파생 클래스에서 `CRecordset` 벌크 행 페칭을 구현한 경우 프레임워크는 대량 레코드 필드 교환(Bulk RFX) 메커니즘을 사용하여 데이터를 전송합니다. 자세한 내용은 [레코드 집합: 대량(ODBC)으로 레코드 가져오기를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

RFX는 대화 상자 데이터 교환(DDX)과 유사합니다. 데이터 원본과 레코드 집합의 필드 데이터 멤버 간에 데이터를 이동하려면 레코드 집합의 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 함수를 여러 번 호출하고 프레임워크와 [ODBC](../../data/odbc/odbc-basics.md)간에 상당한 상호 작용을 해야 합니다. RFX 메커니즘은 형식이 안전하며 와 같은 `::SQLBindCol`ODBC 함수를 호출하는 작업을 절약합니다. DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

RFX는 대부분 투명합니다. MFC 응용 프로그램 마법사 또는 클래스 [추가(MFC ODBC 소비자 추가에](../../mfc/reference/adding-an-mfc-odbc-consumer.md)설명된 대로)를 사용 하 여 레코드 집합 클래스를 선언 하는 경우 RFX가 자동으로 기본 제공 됩니다. **Add Class** 레코드 집합 클래스는 프레임워크에서 제공하는 `CRecordset` 기본 클래스에서 파생되어야 합니다. MFC 응용 프로그램 마법사를 사용하면 초기 레코드 집합 클래스를 만들 수 있습니다. **클래스를 추가하면** 필요에 따라 다른 레코드 집합 클래스를 추가할 수 있습니다. 자세한 정보 및 예제는 [MFC ODBC 소비자 추가를](../../mfc/reference/adding-an-mfc-odbc-consumer.md)참조하십시오.

다음을 수행하려는 경우 세 가지 경우에 소량의 RFX 코드를 수동으로 추가해야 합니다.

- 매개 변수화된 쿼리를 사용합니다. 자세한 내용은 [레코드 집합: 레코드 집합(ODBC) 매개 변수화를](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)참조하십시오.

- 조인을 수행합니다(둘 이상의 테이블의 열에 대해 하나의 레코드 집합사용). 자세한 내용은 [레코드 집합: ODBC(조인 수행)를](../../data/odbc/recordset-performing-a-join-odbc.md)참조하십시오.

- 데이터 열을 동적으로 바인딩합니다. 이는 매개 변수화보다 덜 일반적입니다. 자세한 내용은 [레코드 집합: ODBC(동적으로 바인딩된 데이터 열)를](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)참조하십시오.

RFX에 대한 보다 고급이해가 필요한 경우 [레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오.

다음 항목에서는 레코드 집합 개체 사용의 세부 정보를 설명합니다.

- [레코드 필드 교환: RFX 사용](../../data/odbc/record-field-exchange-using-rfx.md)

- [레코드 필드 교환: RFX 함수 사용](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)

- [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)

## <a name="see-also"></a>참고 항목

[개방형 데이터베이스 연결(ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[MFC ODBC 사용](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[MFC 애플리케이션 마법사, 데이터베이스 지원](../../mfc/reference/database-support-mfc-application-wizard.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)
