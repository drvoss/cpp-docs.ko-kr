---
title: '레코드 필드 교환: RFX 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: dc0cdcee758f4842b0738068a8a11c4e2e404155
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367138"
---
# <a name="record-field-exchange-using-rfx"></a>레코드 필드 교환: RFX 사용

이 항목에서는 프레임워크가 수행하는 항목과 관련하여 RFX를 사용하는 작업을 설명합니다.

> [!NOTE]
> 이 항목은 대량 행 가져오기가 구현되지 않은 [CRecordset에서](../../mfc/reference/crecordset-class.md) 파생된 클래스에 적용됩니다. 대량 행 페치를 사용하는 경우 대량 레코드 필드 교환(대량 RFX)이 구현됩니다. 대량 RFX는 RFX와 비슷합니다. 차이점을 이해하려면 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

다음 항목에는 관련 정보가 포함되어 있습니다.

- [레코드 필드 교환: 마법사 코드로 작업하는 경우](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) RFX의 주요 구성 요소를 소개하고 MFC 응용 프로그램 마법사 및 **클래스 추가(MFC** [ODBC 소비자 추가에](../../mfc/reference/adding-an-mfc-odbc-consumer.md)설명된 대로)가 RFX를 지원하기 위해 작성하는 코드와 마법사 코드를 수정하는 방법을 설명합니다.

- [레코드 필드 교환: RFX 함수를 사용하여](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) `DoFieldExchange` 재정의에서 RFX 함수에 대한 호출 작성에 대해 설명합니다.

다음 표에서는 프레임워크가 수행하는 역할과 관련하여 사용자의 역할을 보여 줍니다.

### <a name="using-rfx-you-and-the-framework"></a>RFX 사용: 귀하와 프레임워크

|이러한 항목을|프레임워크|
|---------|-------------------|
|마법사를 사용 하 고 레코드 집합 클래스를 선언 합니다. 필드 데이터 멤버의 이름 및 데이터 형식을 지정합니다.|마법사는 클래스를 `CRecordset` 파생하고 각 필드 데이터 멤버에 대한 RFX 함수 호출을 포함하여 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 재정의를 작성합니다.|
|(선택 사항) 필요한 매개 변수 데이터 멤버를 클래스에 수동으로 추가합니다. 각 매개 변수 데이터 멤버에 대한 RFX 함수 호출을 `DoFieldExchange` 수동으로 추가하고, 매개 변수 그룹에 대한 [CFieldExchange::SetFieldType에](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 대한 호출을 추가하고, [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)의 총 매개 변수 수를 지정합니다. [레코드 집합: 레코드 집합(ODBC) 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 참조하십시오.||
|(선택 사항) 필드 데이터 멤버에 추가 열을 수동으로 바인딩합니다. 수동으로 [m_nFields.](../../mfc/reference/crecordset-class.md#m_nfields) [레코드 집합: 동적으로 바인딩된 데이터 열(ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)을 참조하십시오.||
|레코드 집합 클래스의 개체를 생성합니다. 개체를 사용하기 전에 매개 변수 데이터 멤버(있는 경우)의 값을 설정합니다.|효율성을 위해 프레임워크는 ODBC를 사용하여 매개 변수를 미리 바인딩합니다. 매개 변수 값을 전달하면 프레임워크는 이를 데이터 원본으로 전달합니다. 정렬 및/또는 필터 문자열이 변경되지 않는 한 재쿼리를 위해 매개 변수 값만 전송됩니다.|
|[C레코드 집합::열기](../../mfc/reference/crecordset-class.md#open)를 사용하여 레코드 집합 개체를 엽니다.|레코드 집합의 쿼리를 실행하고, 레코드 집합의 필드 데이터 멤버에 열을 `DoFieldExchange` 바인딩하고, 첫 번째로 선택한 레코드와 레코드 집합의 필드 데이터 멤버 간에 데이터를 교환하도록 호출합니다.|
|[CRecordset::Move](../../mfc/reference/crecordset-class.md#move) 또는 메뉴 또는 도구 모음 명령을 사용하여 레코드 집합을 스크롤합니다.|새 `DoFieldExchange` 현재 레코드에서 필드 데이터 멤버로 데이터를 전송하는 호출입니다.|
|레코드를 추가, 업데이트 및 삭제합니다.|데이터 `DoFieldExchange` 원본으로 데이터를 전송하기 위한 호출입니다.|

## <a name="see-also"></a>참고 항목

[레코드 필드 교환(RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[레코드 집합: 합계 및 다른 집계 결과 구하기(ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)<br/>
[C필드익스체인지 클래스](../../mfc/reference/cfieldexchange-class.md)<br/>
[매크로, 전역 함수 및 전역 변수](../../mfc/reference/mfc-macros-and-globals.md)
