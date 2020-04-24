---
title: CDB변형 클래스
ms.date: 11/04/2016
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
helpviewer_keywords:
- CDBVariant [MFC], CDBVariant
- CDBVariant [MFC], Clear
- CDBVariant [MFC], m_dwType
- CDBVariant [MFC], m_boolVal
- CDBVariant [MFC], m_chVal
- CDBVariant [MFC], m_dblVal
- CDBVariant [MFC], m_fltVal
- CDBVariant [MFC], m_iVal
- CDBVariant [MFC], m_lVal
- CDBVariant [MFC], m_pbinary
- CDBVariant [MFC], m_pdate
- CDBVariant [MFC], m_pstring
- CDBVariant [MFC], m_pstringA
- CDBVariant [MFC], m_pstringW
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
ms.openlocfilehash: 9bb70acb43f2e73ade86b753ebbb7949759ce88d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754605"
---
# <a name="cdbvariant-class"></a>CDB변형 클래스

MFC ODBC 클래스의 variant 데이터 형식을 나타냅니다.

## <a name="syntax"></a>구문

```
class CDBVariant
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDB 변형 ::CDB변형](#cdbvariant)|`CDBVariant` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDB 변형::지우기](#clear)|개체를 `CDBVariant` 지웁습니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDB변형:m_dwType](#m_dwtype)|현재 저장된 값의 데이터 형식을 포함합니다. `DWORD`을 입력합니다.|

### <a name="public-union-members"></a>공적 조합원

|속성|Description|
|----------|-----------------|
|[CDB변형:m_boolVal](#m_boolval)|**BOOL**형식의 값을 포함합니다.|
|[CDB변형:m_chVal](#m_chval)|**부호되지 않은 char**형식의 값을 포함합니다.|
|[CDB변형:m_dblVal](#m_dblval)|**double**형식의 값을 포함합니다.|
|[CDB변형:m_fltVal](#m_fltval)|형식 **float**의 값을 포함합니다.|
|[CDB변형:m_iVal](#m_ival)|**짧은**형식의 값을 포함합니다.|
|[CDB변형:m_lVal](#m_lval)|**긴**형식의 값을 포함합니다.|
|[CDB변형:m_pbinary](#m_pbinary)|형식의 개체에 대한 `CLongBinary`포인터가 포함되어 있습니다.|
|[CDB변형:m_pdate](#m_pdate)|**TIMESTAMP_STRUCT**형식의 개체에 대한 포인터가 포함되어 있습니다.|
|[CDB변형:m_pstring](#m_pstring)|형식의 개체에 대한 `CString`포인터가 포함되어 있습니다.|
|[CDB 변형:m_pstringA](#m_pstringa)|ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 포인터를 저장합니다.|
|[CDB변형:m_pstringW](#m_pstringw)|넓은 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 포인터를 저장합니다.|

## <a name="remarks"></a>설명

`CDBVariant`기본 클래스가 없습니다.

`CDBVariant`[COleVariant과](../../mfc/reference/colevariant-class.md)유사합니다. 그러나 `CDBVariant` OLE를 사용하지 않습니다. `CDBVariant`을 사용하면 값의 데이터 형식에 대해 걱정할 필요가 없이 값을 저장할 수 있습니다. `CDBVariant`은 공용 구조체에 저장되는 현재 값의 데이터 형식을 추적합니다.

클래스 [CRecordset은](../../mfc/reference/crecordset-class.md) `CDBVariant` 세 가지 멤버 `GetFieldValue`함수에서 개체를 사용합니다. `GetBookmark` `SetBookmark` 예를 들어 `GetFieldValue` 열에서 데이터를 동적으로 가져올 수 있습니다. 열의 데이터 형식을 런타임에 알 수 `GetFieldValue` 없으므로 `CDBVariant` 개체를 사용하여 열의 데이터를 저장합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CDBVariant`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="cdbvariantcdbvariant"></a><a name="cdbvariant"></a>CDB 변형 ::CDB변형

NULL `CDBVariant` 개체를 만듭니다.

```
CDBVariant();
```

### <a name="remarks"></a>설명

[m_dwType](#m_dwtype) 데이터 멤버를 DBVT_NULL 설정합니다.

## <a name="cdbvariantclear"></a><a name="clear"></a>CDB 변형::지우기

이 멤버 함수를 `CDBVariant` 호출하여 개체를 지웁습니다.

```cpp
void Clear();
```

### <a name="remarks"></a>설명

[m_dwType](#m_dwtype) 데이터 멤버의 값이 DBVT_DATE, DBVT_STRING 또는 `Clear` DBVT_BINARY 경우 공용 구조자 포인터 멤버와 연결된 메모리가 해제됩니다. `Clear`DBVT_NULL `m_dwType` 설정합니다.

`CDBVariant` 소멸자는 을 호출합니다. `Clear`

## <a name="cdbvariantm_boolval"></a><a name="m_boolval"></a>CDB변형:m_boolVal

BOOL 형식의 값을 저장합니다.

### <a name="remarks"></a>설명

데이터 `m_boolVal` 멤버는 공용 구조에 속합니다. 액세스하기 `m_boolVal`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_BOOL `m_dwType` 설정된 경우 유효한 `m_boolVal` 값이 포함됩니다. 그렇지 않으면 `m_boolVal` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

## <a name="cdbvariantm_chval"></a><a name="m_chval"></a>CDB변형:m_chVal

**부호없는 char**형식의 값을 저장합니다.

### <a name="remarks"></a>설명

데이터 `m_chVal` 멤버는 공용 구조에 속합니다. 액세스하기 `m_chVal`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_UCHAR `m_dwType` 설정된 경우 유효한 `m_chVal` 값이 포함됩니다. 그렇지 않으면 `m_chVal` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

## <a name="cdbvariantm_dblval"></a><a name="m_dblval"></a>CDB변형:m_dblVal

double 형식의 값을 **저장합니다.**

### <a name="remarks"></a>설명

데이터 `m_dblVal` 멤버는 공용 구조에 속합니다. 액세스하기 `m_dblVal`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_DOUBLE `m_dwType` 설정된 경우 유효한 `m_dblVal` 값이 포함됩니다. 그렇지 않으면 `m_dblVal` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

## <a name="cdbvariantm_dwtype"></a><a name="m_dwtype"></a>CDB변형:m_dwType

이 데이터 멤버에는 현재 개체의 공용 구조체 `CDBVariant` 데이터 멤버에 저장된 값에 대한 데이터 형식이 포함되어 있습니다.

### <a name="remarks"></a>설명

이 공용 구조체에 액세스하기 전에 `m_dwType` 액세스할 공용 구조체 데이터 멤버를 결정하려면 해당 값의 값을 확인해야 합니다. 다음 표에는 가능한 `m_dwType` 값과 해당 공용 구조자 데이터 멤버가 나열되어 있습니다.

|m_dwType|연합 데이터 멤버|
|---------------|-----------------------|
|DBVT_NULL|액세스에 유효한 조합원이 없습니다.|
|DBVT_BOOL|[m_boolVal](#m_boolval)|
|DBVT_UCHAR|[m_chVal](#m_chval)|
|DBVT_SHORT|[m_iVal](#m_ival)|
|DBVT_LONG|[m_lVal](#m_lval)|
|DBVT_SINGLE|[m_fltVal](#m_fltval)|
|DBVT_DOUBLE|[m_dblVal](#m_dblval)|
|DBVT_DATE|[m_pdate](#m_pdate)|
|DBVT_STRING|[m_pstring](#m_pstring)|
|DBVT_BINARY|[m_pbinary](#m_pbinary)|
|DBVT_ASTRING|[m_pstringA](#m_pstringa)|
|DBVT_WSTRING|[m_pstringW](#m_pstringw)|

## <a name="cdbvariantm_fltval"></a><a name="m_fltval"></a>CDB변형:m_fltVal

형식 **float**값을 저장합니다.

### <a name="remarks"></a>설명

데이터 `m_fltVal` 멤버는 공용 구조에 속합니다. 액세스하기 `m_fltVal`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_SINGLE `m_dwType` 설정된 경우 유효한 `m_fltVal` 값이 포함됩니다. 그렇지 않으면 `m_fltVal` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

## <a name="cdbvariantm_ival"></a><a name="m_ival"></a>CDB변형:m_iVal

**짧은**형식의 값을 저장합니다.

### <a name="remarks"></a>설명

데이터 `m_iVal` 멤버는 공용 구조에 속합니다. 액세스하기 `m_iVal`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_SHORT `m_dwType` 설정된 경우 유효한 `m_iVal` 값이 포함됩니다. 그렇지 않으면 `m_iVal` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

## <a name="cdbvariantm_lval"></a><a name="m_lval"></a>CDB변형:m_lVal

**형식**긴 값을 저장합니다.

### <a name="remarks"></a>설명

데이터 `m_lVal` 멤버는 공용 구조에 속합니다. 액세스하기 `m_lVal`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_LONG `m_dwType` 설정된 경우 유효한 `m_lVal` 값이 포함됩니다. 그렇지 않으면 `m_lVal` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

## <a name="cdbvariantm_pbinary"></a><a name="m_pbinary"></a>CDB변형:m_pbinary

[CLongBinary](../../mfc/reference/clongbinary-class.md)형식의 개체에 대한 포인터를 저장합니다.

### <a name="remarks"></a>설명

데이터 `m_pbinary` 멤버는 공용 구조에 속합니다. 액세스하기 `m_pbinary`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_BINARY `m_dwType` 설정된 경우 유효한 `m_pbinary` 포인터가 포함되어 있습니다. 그렇지 않으면 `m_pbinary` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

## <a name="cdbvariantm_pdate"></a><a name="m_pdate"></a>CDB변형:m_pdate

TIMESTAMP_STRUCT 형식의 개체에 대한 포인터를 저장합니다.

### <a name="remarks"></a>설명

데이터 `m_pdate` 멤버는 공용 구조에 속합니다. 액세스하기 `m_pdate`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_DATE `m_dwType` 설정된 경우 유효한 `m_pdate` 포인터가 포함되어 있습니다. 그렇지 않으면 `m_pdate` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

TIMESTAMP_STRUCT 데이터 형식에 대한 자세한 내용은 Windows SDK의 *ODBC 프로그래머 참조* 부록 D의 C [데이터 형식](/sql/odbc/reference/appendixes/c-data-types) 항목을 참조하십시오.

## <a name="cdbvariantm_pstring"></a><a name="m_pstring"></a>CDB변형:m_pstring

[CString](../../atl-mfc-shared/reference/cstringt-class.md)형식의 개체에 대 한 포인터를 저장 합니다.

### <a name="remarks"></a>설명

데이터 `m_pstring` 멤버는 공용 구조에 속합니다. 액세스하기 `m_pstring`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_STRING `m_dwType` 설정된 경우 유효한 `m_pstring` 포인터가 포함되어 있습니다. 그렇지 않으면 `m_pstring` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

## <a name="cdbvariantm_pstringa"></a><a name="m_pstringa"></a>CDB 변형:m_pstringA

ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 포인터를 저장합니다.

### <a name="remarks"></a>설명

데이터 `m_pstringA` 멤버는 공용 구조에 속합니다. 액세스하기 `m_pstringA`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_ASTRING `m_dwType` 설정된 경우 유효한 `m_pstringA` 포인터가 포함되어 있습니다. 그렇지 않으면 `m_pstringA` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

## <a name="cdbvariantm_pstringw"></a><a name="m_pstringw"></a>CDB변형:m_pstringW

넓은 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 대한 포인터를 저장합니다.

### <a name="remarks"></a>설명

데이터 `m_pstringW` 멤버는 공용 구조에 속합니다. 액세스하기 `m_pstringW`전에 먼저 [CDBVariant:m_dwType](#m_dwtype)값을 확인합니다. DBVT_WSTRING `m_dwType` 설정된 경우 유효한 `m_pstringW` 포인터가 포함되어 있습니다. 그렇지 않으면 `m_pstringW` 액세스하면 신뢰할 수 없는 결과가 생성됩니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)
