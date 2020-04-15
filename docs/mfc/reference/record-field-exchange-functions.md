---
title: 레코드 필드 교환 함수
ms.date: 09/17/2019
f1_keywords:
- AFXDB/RFX_Binary
- AFXDB/RFX_Bool
- AFXDB/RFX_Byte
- AFXDB/RFX_Date
- AFXDB/RFX_Double
- AFXDB/RFX_Int
- AFXDB/RFX_Long
- AFXDB/RFX_LongBinary
- AFXDB/RFX_Single
- AFXDB/RFX_Text
- AFXDB/RFX_Binary_Bulk
- AFXDB/RFX_Bool_Bulk
- AFXDB/RFX_Byte_Bulk
- AFXDB/RFX_Date_Bulk
- AFXDB/RFX_Double_Bulk
- AFXDB/RFX_Int_Bulk
- AFXDB/RFX_Long_Bulk
- AFXDB/RFX_Single_Bulk
- AFXDB/RFX_Text_Bulk
- AFXDB/DFX_Binary
- AFXDB/DFX_Bool
- AFXDB/DFX_Byte
- AFXDB/DFX_Currency
- AFXDB/DFX_DateTime
- AFXDB/DFX_Double
- AFXDB/DFX_Long
- AFXDB/DFX_LongBinary
- AFXDB/DFX_Short
- AFXDB/DFX_Single
- AFXDB/DFX_Text
helpviewer_keywords:
- DAO (Data Access Objects), record field exchange (DFX)
- ODBC, bulk RFX data exchange functions [MFC]
- RFX (record field exchange), ODBC classes
- DFX (DAO record field exchange), data exchange functions [MFC]
- DFX functions [MFC]
- bulk RFX functions [MFC]
- DFX (DAO record field exchange)
- RFX (record field exchange), DAO classes
- ODBC, RFX
- RFX (record field exchange), data exchange functions [MFC]
- RFX (record field exchange)
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
ms.openlocfilehash: bfd3ba64a33547b8a27e0f3bc896f39c94486464
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372986"
---
# <a name="record-field-exchange-functions"></a>레코드 필드 교환 함수

이 항목에서는 레코드 집합 개체와 해당 데이터 소스 간의 데이터 전송을 자동화하고 데이터에 대한 다른 작업을 수행하는 데 사용되는 레코드 필드 교환(RFX, 대량 RFX, 및 DFX) 함수를 나열합니다.

ODBC 기반 클래스를 사용하고 대량 행 페치를 구현한 경우 데이터 소스 열에 해당하는 각 데이터 멤버에 대해 대량 RFX 함수를 호출하여 `DoBulkFieldExchange` 의 `CRecordset` 멤버 함수를 수동으로 재정의해야 합니다.

ODBC 기반 클래스에서 벌크 행 페칭을 구현하지 않았거나 DAO 기반 클래스(사용되지 않음)를 사용하는 경우 ClassWizard는 `CRecordset` 레코드 `CDaoRecordset` 집합의 각 필드 데이터 멤버에 대해 RFX 함수(ODBC 클래스의 경우) 또는 DFX 함수(DAO 클래스의 경우)의 `DoFieldExchange` 멤버 함수를 무시합니다.

레코드 필드 교환 함수는 프레임워크에서 `DoFieldExchange` 또는 `DoBulkFieldExchange`를 호출할 때마다 데이터를 전송합니다. 각 함수는 특정 데이터 형식을 전송합니다.

이러한 함수의 사용 방법에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식(ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하세요. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.

동적으로 바인딩하는 데이터 열의 경우 [레코드 집합: 데이터 열 동적 바인딩 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)문서에 설명된 대로 RFX 또는 DFX 함수를 직접 호출할 수도 있습니다. 또한 Technical Note [43](../../mfc/tn043-rfx-routines.md) (ODBC) 및 Technical Note [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (DAO)에 설명된 대로 사용자 고유의 사용자 지정 RFX 또는 DFX 루틴을 작성할 수 있습니다.

`DoFieldExchange` RFX 및 대량 RFX 함수가 함수에 `DoBulkFieldExchange` 나타나는 경우 [RFX_Text](#rfx_text) 및 [RFX_Text_Bulk]#rfx_text_bulk)을 참조하십시오. DFX 함수는 RFX 함수와 매우 유사합니다.

### <a name="rfx-functions-odbc"></a>RFX 함수(ODBC)

|||
|-|-|
|[RFX_Binary](#rfx_binary)|[CByteArray](cbytearray-class.md)형식의 바이트 배열을 전송합니다.|
|[RFX_Bool](#rfx_bool)|부울 데이터를 전송합니다.|
|[RFX_Byte](#rfx_byte)|단일 바이트 데이터를 전송합니다.|
|[RFX_Date](#rfx_date)|[CTime](../../atl-mfc-shared/reference/ctime-class.md) 또는 TIMESTAMP_STRUCT 사용하여 시간 및 날짜 데이터를 전송합니다.|
|[RFX_Double](#rfx_double)|배정밀도 부동 소수점 수 데이터를 전송합니다.|
|[RFX_Int](#rfx_int)|정수 데이터를 전송합니다.|
|[RFX_Long](#rfx_long)|정수(Long) 데이터를 전송합니다.|
|[RFX_LongBinary](#rfx_longbinary)|[CLongBinary](clongbinary-class.md) 클래스의 개체와 함께 BLOB(Binary Large Object) 데이터를 전송합니다.|
|[RFX_Single](#rfx_single)|부동 소수점 수 데이터를 전송합니다.|
|[RFX_Text](#rfx_text)|문자열 데이터를 전송합니다.|

### <a name="bulk-rfx-functions-odbc"></a>대량 RFX 함수(ODBC)

|||
|-|-|
|[RFX_Binary_Bulk](#rfx_binary_bulk)|바이트 데이터 배열을 전송합니다.|
|[RFX_Bool_Bulk](#rfx_bool_bulk)|부울 데이터 배열을 전송합니다.|
|[RFX_Byte_Bulk](#rfx_byte_bulk)|단일 바이트 배열을 전송합니다.|
|[RFX_Date_Bulk](#rfx_date_bulk)|TIMESTAMP_STRUCT 형식의 데이터 배열을 전송합니다.|
|[RFX_Double_Bulk](#rfx_double_bulk)|배정밀도 부동 소수점 데이터 배열을 전송합니다.|
|[RFX_Int_Bulk](#rfx_int_bulk)|정수 데이터 배열을 전송합니다.|
|[RFX_Long_Bulk](#rfx_long_bulk)|정수(Long) 데이터 배열을 전송합니다.|
|[RFX_Single_Bulk](#rfx_single_bulk)|부동 소수점 데이터 배열을 전송합니다.|
|[RFX_Text_Bulk](#rfx_text_bulk)|LPSTR 형식의 데이터 배열을 전송합니다.|

### <a name="dfx-functions-dao"></a>DFX 함수(DAO)

|||
|-|-|
|[DFX_Binary](#dfx_binary)|[CByteArray](cbytearray-class.md)형식의 바이트 배열을 전송합니다.|
|[DFX_Bool](#dfx_bool)|부울 데이터를 전송합니다.|
|[DFX_Byte](#dfx_byte)|단일 바이트 데이터를 전송합니다.|
|[DFX_Currency](#dfx_currency)|[COleCurrency](colecurrency-class.md)형식의 통화 데이터를 전송합니다.|
|[DFX_DateTime](#dfx_datetime)|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)형식의 날짜 및 시간 데이터를 전송합니다.|
|[DFX_Double](#dfx_double)|배정밀도 부동 소수점 수 데이터를 전송합니다.|
|[DFX_Long](#dfx_long)|정수(Long) 데이터를 전송합니다.|
|[DFX_LongBinary](#dfx_longbinary)|`CLongBinary` 클래스의 개체와 함께 BLOB(Binary Large Object) 데이터를 전송합니다. DAO의 경우 대신 [DFX_Binary](#dfx_binary) 를 사용하는 것이 좋습니다.|
|[DFX_Short](#dfx_short)|정수(Short) 데이터를 전송합니다.|
|[DFX_Single](#dfx_single)|부동 소수점 수 데이터를 전송합니다.|
|[DFX_Text](#dfx_text)|문자열 데이터를 전송합니다.|

=============================================

## <a name="rfx_binary"></a><a name="rfx_binary"></a>RFX_Binary

`CRecordset` ODBC 형식 SQL_BINARY, SQL_VARBINARY 또는 SQL_LONGVARBINARY 데이터 원본에 있는 레코드의 열과 개체의 필드 데이터 멤버 간에 바이트 배열을 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Binary(
   CFieldExchange* pFX,
   const char* szName,
   CByteArray& value,
   int nMaxLength = 255);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[클래스 CFieldExchange의](cfieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 [CByteArray](cbytearray-class.md)형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*nMaxLength*<br/>
전송되는 문자열 또는 배열의 최대 허용 길이입니다. *nMaxLength의* 기본값은 255입니다. 법적 값은 1~INT_MAX. 프레임워크는 데이터에 대해 이 양의 공간을 할당합니다. 최상의 성능을 위해 예상한 가장 큰 데이터 항목을 수용할 수 있을 만큼 큰 값을 전달합니다.

### <a name="remarks"></a>설명

이러한 형식의 데이터 원본의 데이터는 레코드 집합의 유형과 `CByteArray` 매핑됩니다.

### <a name="example"></a>예제

[RFX_Text](#rfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_bool"></a><a name="rfx_bool"></a>RFX_Bool

`CRecordset` 개체의 필드 데이터 멤버와 ODBC 형식 SQL_BIT 데이터 원본에 있는 레코드의 열 간에 부울 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Bool(
   CFieldExchange* pFX,
   const char* szName,
   BOOL& value);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[클래스 CFieldExchange의](cfieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 BOOL 형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

### <a name="example"></a>예제

[RFX_Text](#rfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_byte"></a><a name="rfx_byte"></a>RFX_Byte

`CRecordset` 개체의 필드 데이터 멤버와 ODBC 형식 SQL_TINYINT 데이터 원본에 있는 레코드의 열 간에 단일 바이트를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Byte(
   CFieldExchange* pFX,
   const char* szName,
   BYTE& value);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[클래스 CFieldExchange의](cfieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 소스로 전송하기 위해 BYTE 형식의 값을 지정된 데이터 멤버에서 가져옵니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

### <a name="example"></a>예제

[RFX_Text](#rfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_date"></a><a name="rfx_date"></a>RFX_Date

ODBC 형식 SQL_DATE, SQL_TIME 또는 SQL_TIMESTAMP 데이터 원본에 있는 레코드의 열과 개체의 필드 데이터 멤버 간에 데이터를 전송하거나 `CTime` TIMESTAMP_STRUCT. `CRecordset`

### <a name="syntax"></a>구문

```cpp
void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   CTime& value);

void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   TIMESTAMP_STRUCT& value);

void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   COleDateTime& value);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[클래스 CFieldExchange의](cfieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값; 전송할 값입니다. 함수의 다양한 버전은 값에 대해 서로 다른 데이터 형식을 취합니다.

함수의 첫 번째 버전은 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체를 참조합니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 이 값은 지정된 데이터 멤버에서 가져온 값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

함수의 두 번째 버전은 구조를 `TIMESTAMP_STRUCT` 참조합니다. 호출 하기 전에 이 구조를 직접 설정 해야 합니다. 이 버전에는 DDX(대화 상자 데이터 교환) 지원이나 코드 마법사 지원을 사용할 수 없습니다. 함수의 세 번째 버전은 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체에 대한 참조를 사용한다는 점을 제외하면 첫 번째 버전과 유사하게 작동합니다.

### <a name="remarks"></a>설명

함수 `CTime` 버전은 일부 중간 처리의 오버헤드를 부과하고 다소 제한된 범위를 가집니다. 이러한 요소 중 하나가 너무 제한적이라면 함수의 두 번째 버전을 사용합니다. 그러나 코드 마법사 와 DDX 지원이 부족하고 구조를 직접 설정하는 요구 사항에 유의하십시오.

### <a name="example"></a>예제

[RFX_Text](#rfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_double"></a><a name="rfx_double"></a>RFX_Double

개체의 필드 데이터 멤버와 ODBC 형식 SQL_DOUBLE 데이터 원본에 있는 레코드의 열 간에 **이중 부동 데이터** 전송합니다. `CRecordset`

### <a name="syntax"></a>구문

```cpp
void RFX_Double(
   CFieldExchange* pFX,
   const char* szName,
   double& value);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[클래스 CFieldExchange의](cfieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 **double**형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

### <a name="example"></a>예제

[RFX_Text](#rfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_int"></a><a name="rfx_int"></a>RFX_Int

개체의 필드 데이터 멤버와 ODBC `CRecordset` 형식 SQL_SMALLINT 데이터 원본에 있는 레코드의 열 간에 정수 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[클래스 CFieldExchange의](cfieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 **int**형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

### <a name="example"></a>예제

[RFX_Text](#rfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_long"></a><a name="rfx_long"></a>RFX_Long

개체의 필드 데이터 멤버와 ODBC `CRecordset` 형식 SQL_INTEGER 데이터 원본에 있는 레코드의 열 간에 긴 정수 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Long(
   CFieldExchange* pFX,
   const char* szName,
   LONG&
value );
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[클래스 CFieldExchange의](cfieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 형식 **long의**값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

### <a name="example"></a>예제

[RFX_Text](#rfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_longbinary"></a><a name="rfx_longbinary"></a>RFX_LongBinary

ODBC 형식 SQL_LONGVARBINARY 또는 SQL_LONGVARCHAR 데이터 원본에 있는 레코드의 `CRecordset` 열과 개체의 필드 데이터 멤버 간에 [클래스 CLongBinary를](clongbinary-class.md) 사용하여 이진 큰 개체(BLOB) 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_LongBinary(
   CFieldExchange* pFX,
   const char* szName,
   CLongBinary& value);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[클래스 CFieldExchange의](cfieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 `CLongBinary`형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

### <a name="example"></a>예제

[RFX_Text](#rfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_single"></a><a name="rfx_single"></a>RFX_Single

`CRecordset` 개체의 필드 데이터 멤버와 ODBC 형식 SQL_REAL 데이터 원본에 있는 레코드의 열 간에 부동 지점 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Single(
   CFieldExchange* pFX,
   const char* szName,
   float& value);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[클래스 CFieldExchange의](cfieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 형식 **float의**값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

### <a name="example"></a>예제

[RFX_Text](#rfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_text"></a><a name="rfx_text"></a>RFX_Text

ODBC 형식 SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL 또는 SQL_NUMERIC 데이터 원본에 대한 `CString` `CRecordset` 레코드의 필드 데이터 멤버와 레코드 열 간에 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Text(
   CFieldExchange* pFX,
   const char* szName,
   CString& value,
   int nMaxLength = 255,
   int nColumnType = SQL_VARCHAR,
   short nScale = 0);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스의 `CFieldExchange`개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 `CString`형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*nMaxLength*<br/>
전송되는 문자열 또는 배열의 최대 허용 길이입니다. *nMaxLength의* 기본값은 255입니다. 법적 값은 1에서 INT_MAX)입니다. 프레임워크는 데이터에 대해 이 양의 공간을 할당합니다. 최상의 성능을 위해 예상한 가장 큰 데이터 항목을 수용할 수 있을 만큼 큰 값을 전달합니다.

*nColumnType*<br/>
매개 변수에 주로 사용됩니다. 매개 변수의 데이터 형식을 나타내는 정수입니다. 형식은 **SQL_XXX**양식의 ODBC 데이터 형식입니다.

*nScale*<br/>
ODBC 형식 SQL_DECIMAL 또는 SQL_NUMERIC 값에 대한 배율을 지정합니다. *nScale은* 매개 변수 값을 설정할 때만 유용합니다. 자세한 내용은 *ODBC SDK 프로그래머 참조*부록 D의 "정밀도, 배율, 길이 및 디스플레이 크기" 항목을 참조하십시오.

### <a name="remarks"></a>설명

이러한 모든 유형의 데이터 원본에 있는 데이터는 `CString` 레코드 집합에 매핑됩니다.

### <a name="example"></a>예제

이 예제에서는 에 `RFX_Text`대한 여러 호출을 보여 주며 있습니다. 또한 두 호출에 `CFieldExchange::SetFieldType`대해서도 확인합니다. 매개 변수의 경우 호출 `SetFieldType` 및 해당 RFX 호출을 작성해야 합니다. 출력 열 호출 및 관련 RFX 호출은 일반적으로 코드 마법사에 의해 작성됩니다.

```cpp
void CCustomer::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   // Macros such as RFX_Text() and RFX_Int() are dependent on the
   // type of the member variable, not the type of the field in the database.
   // ODBC will try to automatically convert the column value to the requested type
   RFX_Long(pFX, _T("[CustomerID]"), m_CustomerID);
   RFX_Text(pFX, _T("[ContactFirstName]"), m_ContactFirstName);
   RFX_Text(pFX, _T("[PostalCode]"), m_PostalCode);
   RFX_Text(pFX, _T("[L_Name]"), m_L_Name);
   RFX_Long(pFX, _T("[BillingID]"), m_BillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_binary_bulk"></a><a name="rfx_binary_bulk"></a>RFX_Binary_Bulk

ODBC 데이터 원본의 열에서 -derive된 개체의 해당 배열로 `CRecordset`여러 바이트 데이터 행을 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Binary_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) 개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 자세한 내용은 [문서 레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*prgByteVals*<br/>
BYTE 값의 배열에 대한 포인터입니다. 이 배열은 데이터 원본에서 레코드 집합으로 전송할 데이터를 저장합니다.

*prgLengths*<br/>
긴 정수 배열에 대한 포인터입니다. 이 배열은 *prgByteVals에*의해 가리키는 배열에 각 값의 바이트로 길이를 저장합니다. 해당 데이터 항목에 Null 값이 포함된 경우 SQL_NULL_DATA 값이 저장됩니다. 자세한 내용은 ODBC `SQLBindCol` *SDK 프로그래머의 참조에서 ODBC*API 함수를 참조하십시오.

*nMaxLength*<br/>
*prgByteVals에*의해 가리키는 배열에 저장된 값의 최대 허용 길이입니다. 데이터가 잘리지 않도록 하려면 예상한 가장 큰 데이터 항목을 수용할 수 있을 만큼 큰 값을 전달합니다.

### <a name="remarks"></a>설명

데이터 원본 열에는 ODBC 형식의 SQL_BINARY, SQL_VARBINARY 또는 SQL_LONGVARBINARY 있을 수 있습니다. 레코드 집합은 BYTE에 대한 형식 포인터의 필드 데이터 멤버를 정의해야 합니다.

*prgByteVals* 및 *prgLengths를* NULL로 초기화하면 해당 배열이 가리키는 배열이 행 집합 크기와 동일한 크기로 자동으로 할당됩니다.

> [!NOTE]
> 대량 레코드 필드 교환은 데이터 원본에서 레코드 집합 개체로만 데이터를 전송합니다. 레코드 집합을 업데이트하려면 ODBC API 함수를 `SQLSetPos`사용해야 합니다.

자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 및 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)문서를 참조하십시오.

### <a name="example"></a>예제

[RFX_Text_Bulk](#rfx_text_bulk)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_bool_bulk"></a><a name="rfx_bool_bulk"></a>RFX_Bool_Bulk

ODBC 데이터 원본의 열에서 -derive된 개체의 해당 배열로 `CRecordset`여러 부울 데이터 행을 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Bool_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BOOL** prgBoolVals,
   long** prgLengths);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) 개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 자세한 내용은 [문서 레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*prgBoolVals*<br/>
BOOL 값 배열에 대한 포인터입니다. 이 배열은 데이터 원본에서 레코드 집합으로 전송할 데이터를 저장합니다.

*prgLengths*<br/>
긴 정수 배열에 대한 포인터입니다. 이 배열은 *prgBoolVals에*의해 가리키는 배열에 각 값의 바이트로 길이를 저장합니다. 해당 데이터 항목에 Null 값이 포함된 경우 SQL_NULL_DATA 값이 저장됩니다. 자세한 내용은 ODBC `SQLBindCol` *SDK 프로그래머의 참조에서 ODBC*API 함수를 참조하십시오.

### <a name="remarks"></a>설명

데이터 원본 열에는 ODBC 유형의 SQL_BIT 있어야 합니다. 레코드 집합은 BOOL에 대한 형식 포인터의 필드 데이터 멤버를 정의해야 합니다.

*prgBoolVals* 및 *prgLengths를* NULL로 초기화하면 해당 배열이 자동으로 할당되고 크기는 행 집합 크기와 같습니다.

> [!NOTE]
> 대량 레코드 필드 교환은 데이터 원본에서 레코드 집합 개체로만 데이터를 전송합니다. 레코드 집합을 업데이트할 수 있도록 하려면 ODBC `SQLSetPos`API 함수를 사용해야 합니다.

자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 및 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)문서를 참조하십시오.

### <a name="example"></a>예제

[RFX_Text_Bulk](#rfx_text_bulk)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_byte_bulk"></a><a name="rfx_byte_bulk"></a>RFX_Byte_Bulk

ODBC 데이터 원본의 열에서 -derive된 개체의 해당 배열로 `CRecordset`여러 단일 바이트 행을 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Byte_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) 개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 자세한 내용은 [문서 레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*prgByteVals*<br/>
BYTE 값의 배열에 대한 포인터입니다. 이 배열은 데이터 원본에서 레코드 집합으로 전송할 데이터를 저장합니다.

*prgLengths*<br/>
긴 정수 배열에 대한 포인터입니다. 이 배열은 *prgByteVals에*의해 가리키는 배열에 각 값의 바이트로 길이를 저장합니다. 해당 데이터 항목에 Null 값이 포함된 경우 SQL_NULL_DATA 값이 저장됩니다. 자세한 내용은 ODBC `SQLBindCol` *SDK 프로그래머의 참조에서 ODBC*API 함수를 참조하십시오.

### <a name="remarks"></a>설명

데이터 원본 열에는 ODBC 형식의 SQL_TINYINT 있어야 합니다. 레코드 집합은 BYTE에 대한 형식 포인터의 필드 데이터 멤버를 정의해야 합니다.

*prgByteVals* 및 *prgLengths를* NULL로 초기화하면 해당 배열이 가리키는 배열이 행 집합 크기와 동일한 크기로 자동으로 할당됩니다.

> [!NOTE]
> 대량 레코드 필드 교환은 데이터 원본에서 레코드 집합 개체로만 데이터를 전송합니다. 레코드 집합을 업데이트할 수 있도록 하려면 ODBC `SQLSetPos`API 함수를 사용해야 합니다.

자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 및 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)문서를 참조하십시오.

### <a name="example"></a>예제

[RFX_Text_Bulk](#rfx_text_bulk)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_date_bulk"></a><a name="rfx_date_bulk"></a>RFX_Date_Bulk

ODBC 데이터 원본의 열에서 -derive개체의 해당 배열로 `CRecordset`여러 TIMESTAMP_STRUCT 데이터 행을 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Date_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   TIMESTAMP_STRUCT** prgTSVals,
   long** prgLengths);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) 개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 자세한 내용은 [문서 레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*prgTSVals*<br/>
TIMESTAMP_STRUCT 값의 배열에 대한 포인터입니다. 이 배열은 데이터 원본에서 레코드 집합으로 전송할 데이터를 저장합니다. TIMESTAMP_STRUCT 데이터 유형에 대한 자세한 내용은 *ODBC SDK 프로그래머*참조의 부록 D에서 "C 데이터 유형" 항목을 참조하십시오.

*prgLengths*<br/>
긴 정수 배열에 대한 포인터입니다. 이 배열은 *prgTSVals가*가리키는 배열의 각 값의 바이트로 길이를 저장합니다. 해당 데이터 항목에 Null 값이 포함된 경우 SQL_NULL_DATA 값이 저장됩니다. 자세한 내용은 ODBC `SQLBindCol` *SDK 프로그래머의 참조에서 ODBC*API 함수를 참조하십시오.

### <a name="remarks"></a>설명

데이터 원본 열에는 ODBC 유형의 SQL_DATE, SQL_TIME 또는 SQL_TIMESTAMP 있을 수 있습니다. 레코드 집합은 TIMESTAMP_STRUCT 위해 형식 포인터의 필드 데이터 멤버를 정의해야 합니다.

*prgTSVals* 및 *prgLengths를* NULL로 초기화하면 해당 배열이 가리키는 배열이 행 집합 크기와 동일한 크기로 자동으로 할당됩니다.

> [!NOTE]
> 대량 레코드 필드 교환은 데이터 원본에서 레코드 집합 개체로만 데이터를 전송합니다. 레코드 집합을 업데이트할 수 있도록 하려면 ODBC `SQLSetPos`API 함수를 사용해야 합니다.

자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 및 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)문서를 참조하십시오.

### <a name="example"></a>예제

[RFX_Text_Bulk](#rfx_text_bulk)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_double_bulk"></a><a name="rfx_double_bulk"></a>RFX_Double_Bulk

ODBC 데이터 원본의 열에서 `CRecordset`-derive개체의 해당 배열로 이중 정밀도 부동 지점 데이터의 여러 행을 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Double_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   double** prgDblVals,
   long** prgLengths);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) 개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 자세한 내용은 [문서 레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*prgDblVals*<br/>
**이중** 값 배열에 대한 포인터입니다. 이 배열은 데이터 원본에서 레코드 집합으로 전송할 데이터를 저장합니다.

*prgLengths*<br/>
긴 정수 배열에 대한 포인터입니다. 이 배열은 *prgDblVals에*의해 가리키는 배열에 각 값의 바이트로 길이를 저장합니다. 해당 데이터 항목에 Null 값이 포함된 경우 SQL_NULL_DATA 값이 저장됩니다. 자세한 내용은 ODBC `SQLBindCol` *SDK 프로그래머의 참조에서 ODBC*API 함수를 참조하십시오.

### <a name="remarks"></a>설명

데이터 원본 열에는 ODBC 유형의 SQL_DOUBLE 있어야 합니다. 레코드 집합은 형식 포인터의 필드 데이터 멤버를 **두 배로**정의해야 합니다.

*prgDblVals* 및 *prgLengths를* NULL로 초기화하면 해당 배열이 가리키는 배열이 행 집합 크기와 동일한 크기로 자동으로 할당됩니다.

> [!NOTE]
> 대량 레코드 필드 교환은 데이터 원본에서 레코드 집합 개체로만 데이터를 전송합니다. 레코드 집합을 업데이트할 수 있도록 하려면 ODBC `SQLSetPos`API 함수를 사용해야 합니다.

자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 및 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)문서를 참조하십시오.

### <a name="example"></a>예제

[RFX_Text_Bulk](#rfx_text_bulk)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_int_bulk"></a><a name="rfx_int_bulk"></a>RFX_Int_Bulk

개체의 필드 데이터 멤버와 ODBC `CRecordset` 형식 SQL_SMALLINT 데이터 원본에 있는 레코드의 열 간에 정수 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[클래스 CFieldExchange의](cfieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 개체가 지정할 수 `CFieldExchange` 있는 작업에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)문서를 참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 **int**형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

### <a name="example"></a>예제

[RFX_Text](#rfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_long_bulk"></a><a name="rfx_long_bulk"></a>RFX_Long_Bulk

ODBC 데이터 원본의 열에서 -derive된 개체의 해당 배열로 긴 `CRecordset`정수 데이터의 여러 행을 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Long_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   long** prgLongVals,
   long** prgLengths);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) 개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 자세한 내용은 [문서 레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*prgLongVals*<br/>
긴 정수 배열에 대한 포인터입니다. 이 배열은 데이터 원본에서 레코드 집합으로 전송할 데이터를 저장합니다.

*prgLengths*<br/>
긴 정수 배열에 대한 포인터입니다. 이 배열은 *prgLongVals에*의해 가리키는 배열에 각 값의 바이트로 길이를 저장합니다. 해당 데이터 항목에 Null 값이 포함된 경우 SQL_NULL_DATA 값이 저장됩니다. 자세한 내용은 ODBC `SQLBindCol` *SDK 프로그래머의 참조에서 ODBC*API 함수를 참조하십시오.

### <a name="remarks"></a>설명

데이터 원본 열에는 ODBC 유형의 SQL_INTEGER 있어야 합니다. 레코드 집합은 type 포인터의 필드 데이터 멤버를 **long으로**정의해야 합니다.

*prgLongVals* 및 *prgLengths를* NULL로 초기화하면 원하는 배열이 행 집합 크기와 동일한 크기로 자동으로 할당됩니다.

> [!NOTE]
> 대량 레코드 필드 교환은 데이터 원본에서 레코드 집합 개체로만 데이터를 전송합니다. 레코드 집합을 업데이트할 수 있도록 하려면 ODBC `SQLSetPos`API 함수를 사용해야 합니다.

자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 및 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)문서를 참조하십시오.

### <a name="example"></a>예제

[RFX_Text_Bulk](#rfx_text_bulk)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_single_bulk"></a><a name="rfx_single_bulk"></a>RFX_Single_Bulk

ODBC 데이터 원본의 열에서 -derive된 개체의 해당 배열로 부동 지점 데이터의 여러 행을 `CRecordset`전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Single_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   float** prgFltVals,
   long** prgLengths);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) 개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 자세한 내용은 [문서 레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*prgFltVals*<br/>
**float** 값 배열에 대한 포인터입니다. 이 배열은 데이터 원본에서 레코드 집합으로 전송할 데이터를 저장합니다.

*prgLengths*<br/>
긴 정수 배열에 대한 포인터입니다. 이 배열은 *prgFltVals에*의해 가리키는 배열에 각 값의 바이트로 길이를 저장합니다. 해당 데이터 항목에 Null 값이 포함된 경우 SQL_NULL_DATA 값이 저장됩니다. 자세한 내용은 ODBC `SQLBindCol` *SDK 프로그래머의 참조에서 ODBC*API 함수를 참조하십시오.

### <a name="remarks"></a>설명

데이터 원본 열에는 ODBC 형식의 SQL_REAL 있어야 합니다. 레코드 집합은 float 를 **참조할**형식 포인터의 필드 데이터 멤버를 정의해야 합니다.

*prgFltVals* 및 *prgLengths를* NULL로 초기화하면 해당 배열이 가리키는 배열이 행 집합 크기와 동일한 크기로 자동으로 할당됩니다.

> [!NOTE]
> 대량 레코드 필드 교환은 데이터 원본에서 레코드 집합 개체로만 데이터를 전송합니다. 레코드 집합을 업데이트할 수 있도록 하려면 ODBC `SQLSetPos`API 함수를 사용해야 합니다.

자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 및 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)문서를 참조하십시오.

### <a name="example"></a>예제

[RFX_Text_Bulk](#rfx_text_bulk)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="rfx_text_bulk"></a><a name="rfx_text_bulk"></a>RFX_Text_Bulk

ODBC 데이터 원본의 열에서 -derive개체의 해당 배열로 `CRecordset`여러 문자 데이터 행을 전송합니다.

### <a name="syntax"></a>구문

```cpp
void RFX_Text_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   LPSTR* prgStrVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) 개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다. 자세한 내용은 [문서 레코드 필드 교환: RFX 작동 방식을](../../data/odbc/record-field-exchange-how-rfx-works.md)참조하십시오.

*szName*<br/>
데이터 열의 이름입니다.

*prgStrVals*<br/>
LPSTR 값의 배열에 대한 포인터입니다. 이 배열은 데이터 원본에서 레코드 집합으로 전송할 데이터를 저장합니다. ODBC의 현재 버전에서는 이러한 값이 유니코드가 될 수 없습니다.

*prgLengths*<br/>
긴 정수 배열에 대한 포인터입니다. 이 배열은 *prgStrVals에*의해 가리키는 배열에 각 값의 바이트로 길이를 저장합니다. 이 길이는 null 종료 문자를 제외합니다. 해당 데이터 항목에 Null 값이 포함된 경우 SQL_NULL_DATA 값이 저장됩니다. 자세한 내용은 ODBC `SQLBindCol` *SDK 프로그래머의 참조에서 ODBC*API 함수를 참조하십시오.

*nMaxLength*<br/>
null 종료 문자를 포함하여 *prgStrVals가*가리키는 배열에 저장된 값의 최대 허용 길이입니다. 데이터가 잘리지 않도록 하려면 예상한 가장 큰 데이터 항목을 수용할 수 있을 만큼 큰 값을 전달합니다.

### <a name="remarks"></a>설명

데이터 원본 열에는 ODBC 유형의 SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL 또는 SQL_NUMERIC 있을 수 있습니다. 레코드 집합은 LPSTR 형식의 필드 데이터 멤버를 정의해야 합니다.

*prgStrVals* 및 *prgLengths를* NULL로 초기화하면 해당 배열이 가리키는 배열이 행 집합 크기와 동일한 크기로 자동으로 할당됩니다.

> [!NOTE]
> 대량 레코드 필드 교환은 데이터 원본에서 레코드 집합 개체로만 데이터를 전송합니다. 레코드 집합을 업데이트할 수 있도록 하려면 ODBC `SQLSetPos`API 함수를 사용해야 합니다.

자세한 내용은 [레코드 집합: 대량 레코드 가져오기(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) 및 [RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)문서를 참조하십시오.

### <a name="example"></a>예제

`DoBulkFieldExchange` 재정의에 수동으로 통화를 작성해야 합니다. 이 예제에서는 데이터 `RFX_Text_Bulk`전송에 대한 호출과 에 대한 호출을 `RFX_Long_Bulk`보여 주며 이러한 호출 앞에는 [CFieldExchange:SetFieldType](cfieldexchange-class.md#setfieldtype)에 대한 호출이 옵니다. 매개 변수의 경우 대량 RFX 함수 대신 RFX 함수를 호출해야 합니다.

```cpp
void CMultiCustomer::DoBulkFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Long_Bulk(pFX, _T("[CustomerID]"), &m_pCustomerID, &m_pcCustomerID);
   RFX_Text_Bulk(pFX, _T("[ContactFirstName]"), &m_pContactFirstName, &m_pcContactFirstName, 50);
   RFX_Text_Bulk(pFX, _T("[PostalCode]"), &m_pPostalCode, &m_pcPostalCode, 50);
   RFX_Text_Bulk(pFX, _T("[L_Name]"), &m_pL_Name, &m_pcL_Name, 50);
   RFX_Long_Bulk(pFX, _T("[BillingID]"), &m_pBillingID, &m_pcBillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="dfx_binary"></a><a name="dfx_binary"></a>DFX_Binary

[CDaoRecordset](cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 바이트 배열을 전송합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_Binary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CByteArray& value,
   int nPreAllocSize = AFX_DAO_BINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 [CByteArray](cbytearray-class.md)형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*nPreAllocSize*<br/>
프레임워크는 이 양의 메모리를 할당합니다. 데이터가 큰 경우 프레임워크는 필요에 따라 더 많은 공간을 할당합니다. 성능을 향상하려면 이 크기를 재할당을 방지할 수 있을 만큼 큰 값으로 설정합니다. 기본 크기는 AFXDAO에 정의되어 있습니다. H 파일은 AFX_DAO_BINARY_DEFAULT_SIZE.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DAO_DISABLE_FIELD_CACHE 이중 버퍼링을 사용하지 않으며 [SetFieldDirty](cdaorecordset-class.md#setfielddirty) 및 [SetFieldNull을](cdaorecordset-class.md#setfieldnull) 직접 호출해야 합니다. AFX_DAO_ENABLE_FIELD_CACHE 다른 가능한 값은 이중 버퍼링을 사용하며 필드를 더럽거나 Null로 표시하기 위해 추가 작업을 수행할 필요가 없습니다. 성능 및 메모리상의 이유로 이진 데이터가 상대적으로 작지 않으면 이 값을 사용하지 마십시오.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 모든 필드에 대해 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

데이터는 DAO의 형식 DAO_BYTES 레코드 집합의 [CByteArray](cbytearray-class.md) 유형 간에 매핑됩니다.

### <a name="example"></a>예제

[DFX_Text](#dfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="dfx_bool"></a><a name="dfx_bool"></a>DFX_Bool

[CDaoRecordset](cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 부울 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_Bool(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BOOL& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 BOOL 형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DAO_ENABLE_FIELD_CACHE 이중 버퍼링을 사용합니다. 다른 가능한 값은 AFX_DAO_DISABLE_FIELD_CACHE. 이 값을 지정하면, MFC가 이 필드를 검사하지 않습니다. `SetFieldDirty` 및 `SetFieldNull`을 직접 호출해야 합니다.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

데이터는 DAO의 형식 DAO_BOOL 레코드 집합의 BOOL 유형 간에 매핑됩니다.

### <a name="example"></a>예제

[DFX_Text](#dfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="dfx_byte"></a><a name="dfx_byte"></a>DFX_Byte

[CDaoRecordset](cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 단일 바이트를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_Byte(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BYTE& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 소스로 전송하기 위해 BYTE 형식의 값을 지정된 데이터 멤버에서 가져옵니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DAO_ENABLE_FIELD_CACHE 이중 버퍼링을 사용합니다. 다른 가능한 값은 AFX_DAO_DISABLE_FIELD_CACHE. 이 값을 지정하면, MFC가 이 필드를 검사하지 않습니다. `SetFieldDirty` 및 `SetFieldNull`을 직접 호출해야 합니다.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

데이터는 DAO의 DAO_BYTES 형식과 레코드 집합의 BYTE 형식 사이에 매핑됩니다.

### <a name="example"></a>예제

[DFX_Text](#dfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="dfx_currency"></a><a name="dfx_currency"></a>DFX_Currency

[CDaoRecordset](cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 통화 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_Currency(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleCurrency& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 이 값은 [COleCurrency](colecurrency-class.md)형식의 지정된 데이터 멤버에서 가져온 값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DAO_ENABLE_FIELD_CACHE 이중 버퍼링을 사용합니다. 다른 가능한 값은 AFX_DAO_DISABLE_FIELD_CACHE. 이 값을 지정하면, MFC가 이 필드를 검사하지 않습니다. `SetFieldDirty` 및 `SetFieldNull`을 직접 호출해야 합니다.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

데이터는 DAO의 형식 DAO_CURRENCY 레코드 집합의 [COleCurrency](colecurrency-class.md) 유형 간에 매핑됩니다.

### <a name="example"></a>예제

[DFX_Text](#dfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="dfx_datetime"></a><a name="dfx_datetime"></a>DFX_DateTime

[CDaoRecordset](cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 시간 및 날짜 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_DateTime(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleDateTime& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 함수는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체를 참조합니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 이 값은 지정된 데이터 멤버에서 가져온 값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DAO_ENABLE_FIELD_CACHE 이중 버퍼링을 사용합니다. 다른 가능한 값은 AFX_DAO_DISABLE_FIELD_CACHE. 이 값을 지정하면, MFC가 이 필드를 검사하지 않습니다. `SetFieldDirty` 및 `SetFieldNull`을 직접 호출해야 합니다.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

데이터는 DAO의 형식 DAO_DATE 레코드 집합의 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 유형 간에 매핑됩니다.

> [!NOTE]
> `COleDateTime`DAO 클래스에서 이러한 목적을 위해 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 및 TIMESTAMP_STRUCT 대체합니다. `CTime`TIMESTAMP_STRUCT 여전히 ODBC 기반 데이터 액세스 클래스에 사용됩니다.

### <a name="example"></a>예제

[DFX_Text](#dfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="dfx_double"></a><a name="dfx_double"></a>DFX_Double

[CDaoRecordset](cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 **이중 부동 데이터** 전송

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_Double(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   double& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 **double**형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DAO_ENABLE_FIELD_CACHE 이중 버퍼링을 사용합니다. 다른 가능한 값은 AFX_DAO_DISABLE_FIELD_CACHE. 이 값을 지정하면, MFC가 이 필드를 검사하지 않습니다. `SetFieldDirty` 및 `SetFieldNull`을 직접 호출해야 합니다.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

데이터는 DAO의 형식 DAO_R8 레코드 집합에 **double float** 유형 간에 매핑됩니다.

### <a name="example"></a>예제

[DFX_Text](#dfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="dfx_long"></a><a name="dfx_long"></a>DFX_Long

[CDaoRecordset](cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 긴 정수 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_Long(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   long& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 형식 **long의**값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DAO_ENABLE_FIELD_CACHE 이중 버퍼링을 사용합니다. 다른 가능한 값은 AFX_DAO_DISABLE_FIELD_CACHE. 이 값을 지정하면, MFC가 이 필드를 검사하지 않습니다. `SetFieldDirty` 및 `SetFieldNull`을 직접 호출해야 합니다.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

데이터는 DAO의 형식 DAO_I4 레코드 집합에 **긴** 형식 간에 매핑됩니다.

### <a name="example"></a>예제

[DFX_Text](#dfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="dfx_longbinary"></a><a name="dfx_longbinary"></a>DFX_LongBinary

**중요 사항** 이 함수 대신 [DFX_Binary](#dfx_binary) 사용하는 것이 좋습니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_LongBinary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CLongBinary& value,
   DWORD dwPreAllocSize = AFX_DAO_LONGBINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 [CLongBinary](clongbinary-class.md)형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*dwPreAllocSize*<br/>
프레임워크는 이 양의 메모리를 할당합니다. 데이터가 큰 경우 프레임워크는 필요에 따라 더 많은 공간을 할당합니다. 성능을 향상하려면 이 크기를 재할당을 방지할 수 있을 만큼 큰 값으로 설정합니다.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DISABLE_FIELD_CACHE 이중 버퍼링을 사용하지 않습니다. 다른 가능한 값은 AFX_DAO_ENABLE_FIELD_CACHE. 이중 버퍼링을 사용하며 필드를 더럽거나 Null로 표시하기 위해 추가 작업을 수행할 필요가 없습니다. 성능 및 메모리상의 이유로 이진 데이터가 상대적으로 작지 않으면 이 값을 사용하지 마십시오.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

`DFX_LongBinary`MFC ODBC 클래스와의 호환성을 위해 제공됩니다. 함수는 `DFX_LongBinary` [CDaoRecordset](cdaorecordset-class.md) 개체의 필드 `CLongBinary` 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 클래스를 사용하여 이진 대용량 개체(BLOB) 데이터를 전송합니다. 데이터는 DAO의 형식 DAO_BYTES 레코드 집합의 [CLongBinary](clongbinary-class.md) 유형 간에 매핑됩니다.

### <a name="example"></a>예제

[DFX_Text](#dfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="dfx_short"></a><a name="dfx_short"></a>DFX_Short

[CDaoRecordset](cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 짧은 정수 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_Short(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   short& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 **짧은**형식의 값은 지정된 데이터 멤버에서 가져온 값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DAO_ENABLE_FIELD_CACHE 이중 버퍼링을 사용합니다. 다른 가능한 값은 AFX_DAO_DISABLE_FIELD_CACHE. 이 값을 지정하면, MFC가 이 필드를 검사하지 않습니다. `SetFieldDirty` 및 `SetFieldNull`을 직접 호출해야 합니다.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

데이터는 DAO의 형식 DAO_I2 레코드 집합에서 **짧은** 형식 간에 매핑됩니다.

> [!NOTE]
> `DFX_Short`는 ODBC 기반 클래스의 [RFX_Int](#rfx_int) 동일합니다.

### <a name="example"></a>예제

[DFX_Text](#dfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="dfx_single"></a><a name="dfx_single"></a>DFX_Single

[CDaoRecordset](cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 부동 지점 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_Single(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   float& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 형식 **float의**값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DAO_ENABLE_FIELD_CACHE 이중 버퍼링을 사용합니다. 다른 가능한 값은 AFX_DAO_DISABLE_FIELD_CACHE. 이 값을 지정하면, MFC가 이 필드를 검사하지 않습니다. `SetFieldDirty` 및 `SetFieldNull`을 직접 호출해야 합니다.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

데이터는 DAO의 형식 DAO_R4 레코드 집합에 **float** 유형 간에 매핑됩니다.

### <a name="example"></a>예제

[DFX_Text](#dfx_text)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="dfx_text"></a><a name="dfx_text"></a>DFX_Text

[CDaoRecordset](cdaorecordset-class.md) 개체의 필드 데이터 멤버와 데이터 원본에 있는 레코드의 열 간에 `CString` 데이터를 전송합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DFX_Text(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CString& value,
   int nPreAllocSize = AFX_DAO_TEXT_DEFAULT_SIZE,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>매개 변수

*Pfx*<br/>
클래스 [CDaoFieldExchange의](cdaofieldexchange-class.md)개체에 대한 포인터입니다. 이 개체에는 각 함수 호출에 대한 컨텍스트를 정의하는 정보가 포함됩니다.

*szName*<br/>
데이터 열의 이름입니다.

*value*<br/>
표시된 데이터 멤버에 저장된 값(전송할 값)입니다. 레코드 집합에서 데이터 원본으로 전송하는 경우 [CString](../../atl-mfc-shared/reference/cstringt-class.md)형식의 값은 지정된 데이터 멤버에서 가져온값입니다. 데이터 소스에서 레코드 집합으로 전송하기 위해서는 값이 지정된 데이터 멤버에 저장됩니다.

*nPreAllocSize*<br/>
프레임워크는 이 양의 메모리를 할당합니다. 데이터가 큰 경우 프레임워크는 필요에 따라 더 많은 공간을 할당합니다. 성능을 향상하려면 이 크기를 재할당을 방지할 수 있을 만큼 큰 값으로 설정합니다.

*dwBindOptions*<br/>
변경된 레코드 집합 필드를 검색할 수 있도록 MFC의 이중 버퍼링 메커니즘을 활용할 수 있게 해주는 옵션입니다. 기본값인 AFX_DAO_ENABLE_FIELD_CACHE 이중 버퍼링을 사용합니다. 다른 가능한 값은 AFX_DAO_DISABLE_FIELD_CACHE. 이 값을 지정하면, MFC가 이 필드를 검사하지 않습니다. [SetFieldDirty](cdaorecordset-class.md#setfielddirty) 및 [SetFieldNull을](cdaorecordset-class.md#setfieldnull) 직접 호출해야 합니다.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)설정하여 기본적으로 데이터가 이중 버퍼링되는지 여부를 제어할 수 있습니다.

### <a name="remarks"></a>설명

데이터는 DAO의 DAO_CHAR 유형(또는 기호_UNICODE 정의된 경우 DAO_WCHAR) 및 레코드 집합의 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 유형 간에 매핑됩니다.  n

### <a name="example"></a>예제

이 예제에서는 에 `DFX_Text`대한 여러 호출을 보여 주며 있습니다. [또한 CDaoFieldExchange::SetFieldType에](cdaofieldexchange-class.md#setfieldtype)대한 두 호출도 확인합니다. 첫 번째 `SetFieldType` 호출과 **DFX** 호출을 작성해야 합니다. 두 번째 호출과 관련 **DFX** 호출은 일반적으로 클래스를 생성한 코드 마법사에 의해 작성됩니다.

```cpp
void CCustSet::DoFieldExchange(CDaoFieldExchange* pFX)
{
   pFX->SetFieldType(CDaoFieldExchange::param);
   DFX_Text(pFX, _T("Param"), m_strParam);
   pFX->SetFieldType(CDaoFieldExchange::outputColumn);
   DFX_Short(pFX, _T("EmployeeID"), m_EmployeeID);
   DFX_Text(pFX, _T("LastName"), m_LastName);
   DFX_Short(pFX, _T("Age"), m_Age);
   DFX_DateTime(pFX, _T("hire_date"), m_hire_date);
   DFX_DateTime(pFX, _T("termination_date"), m_termination_date);

   CDaoRecordset::DoFieldExchange(pFX);
}
```

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[CRecordset::DoFieldExchange](crecordset-class.md#dofieldexchange)<br/>
[CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)<br/>
[CDaoRecordset::DoFieldExchange](cdaorecordset-class.md#dofieldexchange)
