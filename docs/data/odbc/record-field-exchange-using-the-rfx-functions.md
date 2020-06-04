---
title: '레코드 필드 교환: RFX 함수 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
ms.openlocfilehash: f1afded360cfeff564f1f3d8bb9b294aa33cb733
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367126"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>레코드 필드 교환: RFX 함수 사용

이 항목에서는 재정의 본문을 구성하는 RFX 함수 `DoFieldExchange` 호출을 사용하는 방법을 설명합니다.

> [!NOTE]
> 이 항목은 대량 행 가져오기가 구현되지 않은 [CRecordset에서](../../mfc/reference/crecordset-class.md) 파생된 클래스에 적용됩니다. 대량 행 페치를 사용하는 경우 대량 레코드 필드 교환(대량 RFX)이 구현됩니다. 대량 RFX는 RFX와 비슷합니다. 차이점을 이해하려면 [레코드 집합: 대량 레코드 가져오기(ODBC)를](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)참조하십시오.

RFX 전역 함수는 레코드 집합의 데이터 원본 및 필드 데이터 멤버의 열 간에 데이터를 교환합니다. 레코드 집합의 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 멤버 함수에 RFX 함수 호출을 작성합니다. 이 항목에서는 함수를 간략하게 설명하고 RFX 함수를 사용할 수 있는 데이터 형식을 보여 주며 이를 보여 주습니다. [기술 참고 43추가](../../mfc/tn043-rfx-routines.md) 데이터 형식에 대 한 고유한 RFX 함수를 작성 하는 방법을 설명 합니다.

## <a name="rfx-function-syntax"></a><a name="_core_rfx_function_syntax"></a>RFX 함수 구문

각 RFX 함수에는 세 개의 매개 변수가 필요하며 일부는 선택적 네 번째 또는 다섯 번째 매개 변수를 사용합니다.

- [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체에 대한 포인터입니다. 에 전달된 `pFX` 포인터를 `DoFieldExchange`따라 전달하기만 하면 됩니다.

- 데이터 원본에 표시되는 열의 이름입니다.

- 레코드 집합 클래스의 해당 필드 데이터 멤버 또는 매개 변수 데이터 멤버의 이름입니다.

- (선택 사항) 일부 함수에서 전송되는 문자열 또는 배열의 최대 길이입니다. 기본값은 255바이트이지만 변경할 수 있습니다. 최대 크기는 `CString` INT_MAX(2,147,483,647) 바이트와 같은 개체의 최대 크기를 기준으로 하지만 해당 크기 보다 앞에 드라이버 제한이 발생할 수 있습니다. **INT_MAX**

- (선택 사항) 함수에서 `RFX_Text` 다섯 번째 매개 변수를 사용하여 열의 데이터 형식을 지정하는 경우가 있습니다.

자세한 내용은 *클래스 라이브러리 참조의* [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) 아래의 RFX 함수를 참조하십시오. 매개 변수를 특수 사용할 수 있는 경우의 예는 [레코드 집합: SM 및 기타 집계 결과(ODBC) 를](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)참조하십시오.

## <a name="rfx-data-types"></a><a name="_core_rfx_data_types"></a>RFX 데이터 유형

클래스 라이브러리는 데이터 원본과 레코드 집합 간에 다양한 데이터 형식을 전송하기 위한 RFX 함수를 제공합니다. 다음 목록은 데이터 유형별로 RFX 함수를 요약합니다. 고유한 RFX 함수 호출을 작성해야 하는 경우 데이터 유형별로 이러한 함수중에서 선택합니다.

|함수|데이터 형식|
|--------------|---------------|
|`RFX_Bool`|**Bool**|
|`RFX_Byte`|**바이트**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**double**|
|`RFX_Single`|**플 로트**|
|`RFX_Int`|**Int**|
|`RFX_Long`|**긴**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|

자세한 내용은 *클래스 라이브러리 참조의* [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) 아래의 RFX 함수 설명서를 참조하십시오. C++ 데이터 형식이 SQL 데이터 유형에 매핑되는 방식에 대한 자세한 내용은 SQL의 C++ 데이터 유형에 매핑된 ANSI SQL 데이터 형식 [표: SQL 및 C++ 데이터 유형(ODBC)을](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[레코드 필드 교환(RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[레코드 집합: 레코드 집합 매개 변수화(ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[레코드 집합: 데이터 열 동적 바인딩(ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)<br/>
[C필드익스체인지 클래스](../../mfc/reference/cfieldexchange-class.md)
