---
title: CRecordView 및 CDaoRecordView에 대한 대화 상자 데이터 교환 함수
ms.date: 09/17/2019
f1_keywords:
- AFXDAO/DDX_FieldCBIndex
- AFXDAO/DDX_FieldCBString
- AFXDAO/DDX_FieldCBStringExact
- AFXDAO/DDX_FieldCheck
- AFXDAO/DDX_FieldLBIndex
- AFXDAO/DDX_FieldLBString
- AFXDAO/DDX_FieldLBStringExact
- AFXDAO/DDX_FieldRadio
- AFXDAO/DDX_FieldScroll
- AFXDAO/DDX_FieldText
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
ms.openlocfilehash: 3128b1ba459cb017d1cdb2321bc55d865aa4f8b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365783"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView 및 CDaoRecordView에 대한 대화 상자 데이터 교환 함수

이 항목에서는 [CRecordset과](../../mfc/reference/crecordset-class.md) [CRecordView](../../mfc/reference/crecordview-class.md) 양식 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 양식 간에 데이터를 교환하는 데 사용되는 DDX_Field 함수를 나열합니다. DAO는 Access 데이터베이스와 함께 사용되며 Office 2013을 통해 지원됩니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다.

> [!NOTE]
> DDX_Field 함수는 형식을 제어하는 컨트롤과 데이터를 교환한다는 점에서 DDX 함수와 같습니다. 그러나 DDX와 달리 레코드 뷰 자체의 필드가 아니라 뷰의 관련 레코드 집합 개체 필드와 데이터를 교환합니다. 자세한 내용은 클래스 `CRecordView` 및 `CDaoRecordView`을 참조하십시오.

### <a name="ddx_field-functions"></a>DDX_Field 기능

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|[CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView의](../../mfc/reference/cdaorecordview-class.md)콤보 상자에서 레코드 집합 필드 데이터 멤버와 현재 선택 항목의 인덱스 간에 정수 데이터를 전송합니다.|
|[DDX_FieldCBString](#ddx_fieldcbstring)|레코드 `CString` 필드 데이터 멤버와 `CRecordView` 또는 `CDaoRecordView`에서 콤보 상자의 편집 컨트롤 간에 데이터를 전송합니다. 레코드 집합에서 컨트롤로 데이터를 이동할 때 이 함수는 지정된 문자열의 문자로 시작하는 콤보 상자의 항목을 선택합니다.|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|레코드 `CString` 필드 데이터 멤버와 `CRecordView` 또는 `CDaoRecordView`에서 콤보 상자의 편집 컨트롤 간에 데이터를 전송합니다. 레코드 집합에서 컨트롤로 데이터를 이동할 때 이 함수는 지정된 문자열과 정확히 일치하는 콤보 상자의 항목을 선택합니다.|
|[DDX_FieldCheck](#ddx_fieldcheck)|레코드 집합 필드 데이터 멤버와 `CRecordView` 또는 `CDaoRecordView`의 확인란 간에 부울 데이터를 전송합니다.|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|`CRecordView` 또는 `CDaoRecordView`의 목록 상자에서 레코드 집합 필드 데이터 멤버와 현재 선택 영역의 인덱스 간에 정수 데이터를 전송합니다.|
|[DDX_FieldLBString](#ddx_fieldlbstring)|목록 상자 컨트롤과 레코드 집합의 필드 데이터 멤버 간에 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 데이터 전송을 관리합니다. 레코드 집합에서 컨트롤로 데이터를 이동할 때 이 함수는 지정된 문자열의 문자로 시작하는 목록 상자의 항목을 선택합니다.|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|목록 상자 `CString` 컨트롤과 레코드 집합의 필드 데이터 멤버 간에 데이터 전송을 관리합니다. 레코드 집합에서 컨트롤로 데이터를 이동할 때 이 함수는 지정된 문자열과 정확히 일치하는 첫 번째 항목을 선택합니다.|
|[DDX_FieldRadio](#ddx_fieldradio)|또는 에서 레코드 집합 필드 데이터 멤버와 라디오 단추 그룹 `CRecordView` 간에 `CDaoRecordView`정수 데이터를 전송합니다.|
|[DDX_FieldScroll](#ddx_fieldscroll)|`CRecordView` 또는 에서 스크롤 막대 컨트롤의 스크롤 위치를 `CDaoRecordView`설정하거나 가져옵니다. [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) 함수에서 호출합니다.|
|[DDX_FieldSlider](#ddx_fieldslider)|레코드 뷰에서 슬라이더 컨트롤의 엄지 손가락 위치와 레코드 `int` 집합의 필드 데이터 멤버를 동기화합니다. |
|[DDX_FieldText](#ddx_fieldtext)|오버로드 된 버전은 전송에 `int`사용할 수 있습니다, `DWORD` **UINT,** **긴**, [, CString](../../atl-mfc-shared/reference/cstringt-class.md), **플로트**, **더블**, **짧은**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) `CDaoRecordView`, 및 [COleCurrency](../../mfc/reference/colecurrency-class.md) 데이터 사이 레코드 집합 필드 데이터 멤버와 `CRecordView` 또는 의 편집 상자.|

## <a name="ddx_fieldcbindex"></a><a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex

이 `DDX_FieldCBIndex` 함수는 레코드 뷰의 콤보 상자 컨트롤의 목록 상자 컨트롤에서 선택한 항목의 `int` 인덱스와 레코드 뷰와 연결된 레코드 집합의 필드 데이터 멤버를 동기화합니다.

```cpp
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체에서 컨트롤의 ID입니다.

*index*<br/>
연결된 `CRecordset` 개체 또는 `CDaoRecordset` 개체의 필드 데이터 멤버에 대한 참조입니다.

*pRecordset*<br/>
데이터가 교환되는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

레코드 집합에서 컨트롤로 데이터를 이동할 때 이 함수는 *인덱스에*지정된 값을 기반으로 컨트롤에서 선택을 설정합니다. 레코드 집합에서 컨트롤로 전송할 때 레코드 집합 필드가 Null인 경우 MFC는 인덱스 값을 0으로 설정합니다. 컨트롤에서 레코드 집합으로 전송할 때 컨트롤이 비어 있거나 항목이 선택되지 않은 경우 레코드 집합 필드가 0으로 설정됩니다.

ODBC 기반 클래스로 작업하는 경우 첫 번째 버전을 사용합니다. DAO 기반 클래스로 작업하는 경우 두 번째 버전을 사용합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드에 대한 DDX에 대한 예제 및 자세한 내용은 [레코드 보기](../../data/record-views-mfc-data-access.md)문서를 참조하십시오.

### <a name="example"></a>예제

일반적인 DDX_Field 예제는 [DDX_FieldText](#ddx_fieldtext) 참조하십시오. 예제는 에 대해 `DDX_FieldCBIndex`비슷합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="ddx_fieldcbstring"></a><a name="ddx_fieldcbstring"></a>DDX_FieldCBString

이 `DDX_FieldCBString` 함수는 레코드 뷰에서 콤보 상자 컨트롤의 편집 컨트롤과 레코드 뷰와 연결된 `CString` 레코드 집합의 필드 데이터 멤버 간에 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 데이터의 전송을 관리합니다.

```cpp
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체에서 컨트롤의 ID입니다.

*value*<br/>
연결된 `CRecordset` 개체 또는 `CDaoRecordset` 개체의 필드 데이터 멤버에 대한 참조입니다.

*pRecordset*<br/>
데이터가 교환되는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

레코드 집합에서 컨트롤로 데이터를 이동할 때 이 함수는 콤보 상자의 현재 선택을 *값으로*지정된 문자열의 문자로 시작하는 첫 번째 행으로 설정합니다. 레코드 집합에서 컨트롤로 전송할 때 레코드 집합 필드가 Null인 경우 콤보 상자에서 모든 선택이 제거되고 콤보 상자의 편집 컨트롤이 비어 있도록 설정됩니다. 컨트롤에서 레코드 집합으로 전송할 때 컨트롤이 비어 있으면 필드가 허용하는 경우 레코드 집합 필드가 Null로 설정됩니다.

ODBC 기반 클래스로 작업하는 경우 첫 번째 버전을 사용합니다. DAO 기반 클래스로 작업하는 경우 두 번째 버전을 사용합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드에 대한 DDX에 대한 예제 및 자세한 내용은 [레코드 보기](../../data/record-views-mfc-data-access.md)문서를 참조하십시오.

### <a name="example"></a>예제

일반적인 DDX_Field 예제는 [DDX_FieldText](#ddx_fieldtext) 참조하십시오. 이 예제에는 에 `DDX_FieldCBString`대한 호출이 포함됩니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="ddx_fieldcbstringexact"></a><a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact

이 `DDX_FieldCBStringExact` 함수는 레코드 뷰에서 콤보 상자 컨트롤의 편집 컨트롤과 레코드 뷰와 연결된 `CString` 레코드 집합의 필드 데이터 멤버 간에 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 데이터의 전송을 관리합니다.

```cpp
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체에서 컨트롤의 ID입니다.

*value*<br/>
연결된 `CRecordset` 개체 또는 `CDaoRecordset` 개체의 필드 데이터 멤버에 대한 참조입니다.

*pRecordset*<br/>
데이터가 교환되는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

레코드 집합에서 컨트롤로 데이터를 이동할 때 이 함수는 콤보 상자의 현재 선택을 *값에*지정된 문자열과 정확히 일치하는 첫 번째 행으로 설정합니다. 레코드 집합에서 컨트롤로 전송할 때 레코드 집합 필드가 NULL이면 콤보 상자에서 모든 선택이 제거되고 콤보 상자의 편집 상자가 비어 있도록 설정됩니다. 컨트롤에서 레코드 집합으로 전송할 때 컨트롤이 비어 있으면 레코드 집합 필드가 NULL로 설정됩니다.

ODBC 기반 클래스로 작업하는 경우 첫 번째 버전을 사용합니다. DAO 기반 클래스로 작업하는 경우 두 번째 버전을 사용합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드에 대한 DDX에 대한 예제 및 자세한 내용은 [레코드 보기](../../data/record-views-mfc-data-access.md)문서를 참조하십시오.

### <a name="example"></a>예제

일반적인 DDX_Field 예제는 [DDX_FieldText](#ddx_fieldtext) 참조하십시오. 호출은 `DDX_FieldCBStringExact` 비슷합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="ddx_fieldcheck"></a><a name="ddx_fieldcheck"></a>DDX_FieldCheck

이 `DDX_FieldCheck` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체와 대화 상자, 양식 뷰 또는 제어 뷰 **개체의** int 데이터 멤버에서 확인란 컨트롤 간의 **int** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
제어 속성과 연결된 확인란 컨트롤의 리소스 ID입니다.

*value*<br/>
데이터가 교환되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*pRecordset*<br/>
데이터가 교환되는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_FieldCheck` *값은* 확인란 컨트롤의 현재 상태로 설정되거나 컨트롤의 상태가 전송 방향에 따라 *값으로*설정됩니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="ddx_fieldlbindex"></a><a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex

이 `DDX_FieldLBIndex` 함수는 레코드 뷰의 목록 상자 컨트롤에서 선택한 항목의 인덱스와 레코드 뷰와 연결된 레코드 집합의 **int** 필드 데이터 멤버를 동기화합니다.

```cpp
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체에서 컨트롤의 ID입니다.

*index*<br/>
연결된 `CRecordset` 개체 또는 `CDaoRecordset` 개체의 필드 데이터 멤버에 대한 참조입니다.

*pRecordset*<br/>
데이터가 교환되는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

레코드 집합에서 컨트롤로 데이터를 이동할 때 이 함수는 *인덱스에*지정된 값을 기반으로 컨트롤에서 선택을 설정합니다. 레코드 집합에서 컨트롤로 전송할 때 레코드 집합 필드가 Null인 경우 MFC는 인덱스 값을 0으로 설정합니다. 컨트롤에서 레코드 집합으로 전송할 때 컨트롤이 비어 있으면 레코드 집합 필드가 0으로 설정됩니다.

ODBC 기반 클래스로 작업하는 경우 첫 번째 버전을 사용합니다. DAO 기반 클래스로 작업하는 경우 두 번째 버전을 사용합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드에 대한 DDX에 대한 예제 및 자세한 내용은 [레코드 보기](../../data/record-views-mfc-data-access.md)문서를 참조하십시오.

### <a name="example"></a>예제

일반적인 DDX_Field 예제는 [DDX_FieldText](#ddx_fieldtext) 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="ddx_fieldlbstring"></a><a name="ddx_fieldlbstring"></a>DDX_FieldLBString

레코드 `DDX_FieldLBString` 뷰에서 목록 상자 컨트롤의 현재 선택을 레코드 뷰와 연결된 레코드 집합의 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 필드 데이터 멤버에 복사합니다.

```cpp
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체에서 컨트롤의 ID입니다.

*value*<br/>
연결된 `CRecordset` 개체 또는 `CDaoRecordset` 개체의 필드 데이터 멤버에 대한 참조입니다.

*pRecordset*<br/>
데이터가 교환되는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

역방향에서 이 함수는 목록 상자의 현재 선택을 *값으로*지정된 문자열의 문자로 시작하는 첫 번째 행으로 설정합니다. 레코드 집합에서 컨트롤로 전송할 때 레코드 집합 필드가 Null인 경우 목록 상자에서 모든 선택이 제거됩니다. 컨트롤에서 레코드 집합으로 전송할 때 컨트롤이 비어 있으면 레코드 집합 필드가 Null로 설정됩니다.

ODBC 기반 클래스로 작업하는 경우 첫 번째 버전을 사용합니다. DAO 기반 클래스로 작업하는 경우 두 번째 버전을 사용합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드에 대한 DDX에 대한 예제 및 자세한 내용은 [레코드 보기](../../data/record-views-mfc-data-access.md)문서를 참조하십시오.

### <a name="example"></a>예제

일반적인 DDX_Field 예제는 [DDX_FieldText](#ddx_fieldtext) 참조하십시오. 호출은 `DDX_FieldLBString` 비슷합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="ddx_fieldlbstringexact"></a><a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact

이 `DDX_FieldLBStringExact` 함수는 레코드 뷰에서 목록 상자 컨트롤의 현재 선택을 레코드 뷰와 연결된 레코드 집합의 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 필드 데이터 멤버에 복사합니다.

```cpp
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체에서 컨트롤의 ID입니다.

*value*<br/>
연결된 `CRecordset` 개체 또는 `CDaoRecordset` 개체의 필드 데이터 멤버에 대한 참조입니다.

*pRecordset*<br/>
데이터가 교환되는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

역방향에서는 이 함수가 목록 상자의 현재 선택을 *값에*지정된 문자열과 정확히 일치하는 첫 번째 행으로 설정합니다. 레코드 집합에서 컨트롤로 전송할 때 레코드 집합 필드가 Null인 경우 목록 상자에서 모든 선택이 제거됩니다. 컨트롤에서 레코드 집합으로 전송할 때 컨트롤이 비어 있으면 레코드 집합 필드가 Null로 설정됩니다.

ODBC 기반 클래스로 작업하는 경우 첫 번째 버전을 사용합니다. DAO 기반 클래스로 작업하는 경우 두 번째 버전을 사용합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드에 대한 DDX에 대한 예제 및 자세한 내용은 [레코드 보기](../../data/record-views-mfc-data-access.md)문서를 참조하십시오.

### <a name="example"></a>예제

일반적인 DDX_Field 예제는 [DDX_FieldText](#ddx_fieldtext) 참조하십시오. 호출은 `DDX_FieldLBStringExact` 비슷합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="ddx_fieldradio"></a><a name="ddx_fieldradio"></a>DDX_FieldRadio

이 `DDX_FieldRadio` 함수는 레코드 뷰의 레코드 집합의 0기반 **int** 멤버 변수를 레코드 뷰의 라디오 단추 그룹에 현재 선택한 라디오 단추와 연결합니다.

```cpp
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체에서 인접한 라디오 단추 컨트롤의 그룹(스타일 WS_GROUP)의 첫 번째 ID입니다.

*value*<br/>
연결된 `CRecordset` 개체 또는 `CDaoRecordset` 개체의 필드 데이터 멤버에 대한 참조입니다.

*pRecordset*<br/>
데이터가 교환되는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

레코드 집합 필드에서 뷰로 전송할 때 이 함수는 *n번째* 라디오 단추(0기반)를 켜고 다른 단추를 끕니다. 역방향에서는 레코드 집합 필드를 현재 켜진 라디오 단추의 서수 번호(선택됨)로 설정합니다. 레코드 집합에서 컨트롤로 전송할 때 레코드 집합 필드가 Null인 경우 단추가 선택되지 않습니다. 컨트롤에서 레코드 집합으로 전송할 때 컨트롤을 선택하지 않으면 필드가 허용하는 경우 레코드 집합 필드가 Null로 설정됩니다.

ODBC 기반 클래스로 작업하는 경우 첫 번째 버전을 사용합니다. DAO 기반 클래스로 작업하는 경우 두 번째 버전을 사용합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드에 대한 DDX에 대한 예제 및 자세한 내용은 [레코드 보기](../../data/record-views-mfc-data-access.md)문서를 참조하십시오.

### <a name="example"></a>예제

일반적인 DDX_Field 예제는 [DDX_FieldText](#ddx_fieldtext) 참조하십시오. 호출은 `DDX_FieldRadio` 비슷합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="ddx_fieldscroll"></a><a name="ddx_fieldscroll"></a>DDX_FieldScroll

이 `DDX_FieldScroll` 함수는 레코드 뷰에서 스크롤 막대 컨트롤의 스크롤 위치와 레코드 뷰와 연결된 레코드 집합의 **int** 필드 데이터 멤버(또는 매핑하도록 선택한 정수 변수)를 동기화합니다.

```cpp
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체에서 인접한 라디오 단추 컨트롤의 그룹(스타일 WS_GROUP)의 첫 번째 ID입니다.

*value*<br/>
연결된 `CRecordset` 개체 또는 `CDaoRecordset` 개체의 필드 데이터 멤버에 대한 참조입니다.

*pRecordset*<br/>
데이터가 교환되는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

레코드 집합에서 컨트롤로 데이터를 이동할 때 이 함수는 스크롤 막대 컨트롤의 스크롤 위치를 *값에*지정된 값으로 설정합니다. 레코드 집합에서 컨트롤로 전송할 때 레코드 집합 필드가 Null이면 스크롤 막대 컨트롤이 0으로 설정됩니다. 컨트롤에서 레코드 집합으로 전송할 때 컨트롤이 비어 있으면 레코드 집합 필드의 값은 0입니다.

ODBC 기반 클래스로 작업하는 경우 첫 번째 버전을 사용합니다. DAO 기반 클래스로 작업하는 경우 두 번째 버전을 사용합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드에 대한 DDX에 대한 예제 및 자세한 내용은 [레코드 보기](../../data/record-views-mfc-data-access.md)문서를 참조하십시오.

### <a name="example"></a>예제

일반적인 DDX_Field 예제는 [DDX_FieldText](#ddx_fieldtext) 참조하십시오. 호출은 `DDX_FieldScroll` 비슷합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="ddx_fieldslider"></a><a name="ddx_fieldslider"></a>DDX_FieldSlider

이 `DDX_FieldSlider` 함수는 레코드 뷰에서 슬라이더 컨트롤의 엄지 손가락 위치와 레코드 뷰와 연결된 레코드 집합의 **int** 필드 데이터 멤버(또는 매핑하도록 선택한 정수 변수)를 동기화합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI DDX_FieldSlider(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset );

void AFXAPI DDX_FieldSlider(
   CDataExchange* pDX,
   int nIDC,
   int& value,
   CDaoRecordset* pRecordset );
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
슬라이더 컨트롤의 리소스 ID입니다.

*value*<br/>
교환할 값에 대한 참조입니다. 이 매개변수는 슬라이더 컨트롤의 현재 엄지 손가락 위치를 유지하거나 설정하는 데 사용됩니다.

*pRecordset*<br/>
데이터가 교환되는 `CRecordset` 관련 `CDaoRecordset` 또는 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

레코드 집합에서 슬라이더로 데이터를 이동할 때 이 함수는 슬라이더의 위치를 *값에*지정된 값으로 설정합니다. 레코드 집합에서 컨트롤로 전송할 때 레코드 집합 필드가 Null이면 슬라이더 컨트롤의 위치가 0으로 설정됩니다. 컨트롤에서 레코드 집합으로 전송할 때 컨트롤이 비어 있으면 레코드 집합 필드의 값은 0입니다.

`DDX_FieldSlider`단순히 위치가 아니라 범위를 설정할 수 있는 슬라이더 컨트롤로 범위 정보를 교환하지 않습니다.

ODBC 기반 클래스로 작업하는 경우 함수의 첫 번째 재정의를 사용합니다. DAO 기반 클래스에서 두 번째 재정의를 사용합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및 DDX 및 `CRecordView` `CDaoRecordView` 필드에 대한 자세한 내용은 보기 레코드 [를](../../data/record-views-mfc-data-access.md)참조하십시오. 슬라이더 컨트롤에 대한 자세한 내용은 [CSliderCtrl 사용](../using-csliderctrl.md)을 참조하십시오.

### <a name="example"></a>예제

일반적인 DDX_Field 예제는 [DDX_FieldText](#ddx_fieldtext) 참조하십시오. 호출은 `DDX_FieldSlider` 비슷합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="ddx_fieldtext"></a><a name="ddx_fieldtext"></a>DDX_FieldText

이 `DDX_FieldText` 함수는 편집 상자 컨트롤과 레코드 집합의 필드 데이터 멤버 간에 **int,** **짧은,** **긴, DWORD,** [CString,](../../atl-mfc-shared/reference/cstringt-class.md) **float**, **double**, **BOOL**또는 **BYTE** 데이터의 전송을 관리합니다.

```cpp
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    UINT& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    long& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    float& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    double& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    short& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BOOL& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    long& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    float& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    double& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    COleCurrency& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
[CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체에서 컨트롤의 ID입니다.

*value*<br/>
연결된 `CRecordset` 개체 또는 `CDaoRecordset` 개체의 필드 데이터 멤버에 대한 참조입니다. 값의 데이터 형식은 사용하는 오버로드된 버전에 `DDX_FieldText` 따라 달라집니다.

*pRecordset*<br/>
데이터가 교환되는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체에 대한 포인터입니다. 이 포인터를 사용하면 Null 값을 검색하고 설정할 수 `DDX_FieldText` 있습니다.

### <a name="remarks"></a>설명

[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체의 `DDX_FieldText` 경우 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)및 [COleCurrency](../../mfc/reference/colecurrency-class.md) 값 전송도 관리합니다. 빈 편집 상자 컨트롤은 Null 값을 나타냅니다. 레코드 집합에서 컨트롤로 전송할 때 레코드 집합 필드가 Null이면 편집 상자가 비어 있도록 설정됩니다. 컨트롤에서 레코드 집합으로 전송할 때 컨트롤이 비어 있으면 레코드 집합 필드가 Null로 설정됩니다.

ODBC 기반 클래스로 작업하는 경우 [CRecordset](../../mfc/reference/crecordset-class.md) 매개 변수가 있는 버전을 사용합니다. DAO 기반 클래스로 작업하는 경우 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 매개 변수가 있는 버전을 사용합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. [CRecordView](../../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 필드에 대한 DDX에 대한 예제 및 자세한 내용은 [레코드 보기](../../data/record-views-mfc-data-access.md)문서를 참조하십시오.

### <a name="example"></a>예제

[CRecordView](../../mfc/reference/crecordview-class.md)에 대한 다음 `DoDataExchange`함수는 세 개의 데이터 형식에 대한 `DDX_FieldText` 함수 호출을 포함합니다. `IDC_COURSELIST`는 콤보 상자이며 다른 두 컨트롤은 편집 상자입니다. DAO 프로그래밍의 경우 *m_pSet* 매개 변수는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset에](../../mfc/reference/cdaorecordset-class.md)대한 포인터입니다.

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](mfc-macros-and-globals.md)
