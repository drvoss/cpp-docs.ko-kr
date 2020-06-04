---
title: OLE 컨트롤에 대한 대화 상자 데이터 교환 함수
ms.date: 11/04/2016
f1_keywords:
- AFXDISP/DDX_OCBool
- AFXDISP/DDX_OCBoolRO
- AFXDISP/DDX_OCColor
- AFXDISP/DDX_OCColorRO
- AFXDISP/DDX_OCFloat
- AFXDISP/DDX_OCFloatRO
- AFXDISP/DDX_OCInt
- AFXDISP/DDX_OCIntRO
- AFXDISP/DDX_OCShort
- AFXDISP/DDX_OCShortRO
- AFXDISP/DDX_OCText
- AFXDISP/DDX_OCTextRO
helpviewer_keywords:
- OLE controls [MFC], DDX functions
- DDX (dialog data exchange), OLE support
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
ms.openlocfilehash: 61a5983eec13902ed4b0e397e3befca4860977d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365762"
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE 컨트롤에 대한 대화 상자 데이터 교환 함수

이 항목에서는 대화 상자, 양식 보기 또는 제어 뷰 개체에서 OLE 컨트롤의 속성 간에 데이터를 교환하는 데 사용되는 DDX_OC 함수와 대화 상자, 양식 보기 또는 제어 뷰 개체의 데이터 멤버를 나열합니다.

### <a name="ddx_oc-functions"></a>DDX_OC 기능

|||
|-|-|
|[DDX_OCBool](#ddx_ocbool)|OLE 컨트롤의 속성과 **BOOL** 데이터 멤버 간의 **BOOL** 데이터 전송을 관리합니다.|
|[DDX_OCBoolRO](#ddx_ocboolro)|OLE 컨트롤의 읽기 전용 속성과 **BOOL** 데이터 멤버 간에 **BOOL** 데이터 전송을 관리합니다.|
|[DDX_OCColor](#ddx_occolor)|OLE 컨트롤의 속성과 **OLE_COLOR** 데이터 멤버 간에 **OLE_COLOR** 데이터 전송을 관리합니다.|
|[DDX_OCColorRO](#ddx_occolorro)|OLE 컨트롤의 읽기 전용 속성과 **OLE_COLOR** 데이터 멤버 간에 **OLE_COLOR** 데이터 전송을 관리합니다.|
|[DDX_OCFloat](#ddx_ocfloat)|OLE 컨트롤의 속성과 **float(또는** 이중) 데이터 멤버 간의 **float(또는** **이중)** 데이터 전송을 관리합니다. **double**|
|[DDX_OCFloatRO](#ddx_ocfloatro)|OLE 컨트롤의 읽기 전용 속성과 **float(또는** **이중)** 데이터 멤버 간에 **float(또는** **이중)** 데이터 전송을 관리합니다.|
|[DDX_OCInt](#ddx_ocint)|OLE 컨트롤의 속성과 **int(또는** 긴) 데이터 멤버 간의 **int(또는** **긴)** 데이터 전송을 관리합니다. **long**|
|[DDX_OCIntRO](#ddx_ocintro)|OLE 컨트롤의 읽기 전용 속성과 int(또는 **긴)** 데이터 멤버 간에 **int(또는** **int** **긴)** 데이터 전송을 관리합니다.|
|[DDX_OCShort](#ddx_ocshort)|OLE 컨트롤의 속성과 **짧은** 데이터 멤버 간의 **짧은** 데이터 전송을 관리합니다.|
|[DDX_OCShortRO](#ddx_ocshortro)|OLE 컨트롤의 읽기 전용 속성과 **짧은** 데이터 멤버 간에 **짧은** 데이터 전송을 관리합니다.|
|[DDX_OCText](#ddx_octext)|OLE 컨트롤의 속성과 **CString** 데이터 멤버 간의 **CString** 데이터 전송을 관리합니다.|
|[DDX_OCTextRO](#ddx_octextro)|OLE 컨트롤의 읽기 전용 속성과 **CString** 데이터 멤버 간의 **CString** 데이터 전송을 관리합니다.|

## <a name="ddx_ocbool"></a><a name="ddx_ocbool"></a>DDX_OCBool

이 `DDX_OCBool` 함수는 대화 상자, 양식 뷰 또는 제어 뷰 개체에서 OLE 컨트롤의 속성과 대화 상자, 양식 뷰 또는 제어 뷰 개체의 **BOOL** 데이터 멤버 간에 **BOOL** 데이터의 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더:** afxdisp.h

## <a name="ddx_ocboolro"></a><a name="ddx_ocboolro"></a>DDX_OCBoolRO

이 `DDX_OCBoolRO` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체에서 OLE 컨트롤의 읽기 전용 속성과 대화 상자, 양식 뷰 또는 제어 뷰 개체의 **BOOL** 데이터 멤버 간에 **BOOL** 데이터의 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="ddx_occolor"></a><a name="ddx_occolor"></a>DDX_OCColor

이 `DDX_OCColor` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체에서 OLE 컨트롤의 속성과 대화 상자, 양식 뷰 또는 제어 뷰 개체의 OLE_COLOR 데이터 멤버 간에 OLE_COLOR 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="ddx_occolorro"></a><a name="ddx_occolorro"></a>DDX_OCColorRO

이 `DDX_OCColorRO` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체에서 OLE 컨트롤의 읽기 전용 속성과 대화 상자, 양식 보기 또는 제어 뷰 개체의 OLE_COLOR 데이터 멤버 간에 OLE_COLOR 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="ddx_ocfloat"></a><a name="ddx_ocfloat"></a>DDX_OCFloat

이 `DDX_OCFloat` 함수는 대화 상자, 양식 뷰 또는 제어 뷰 개체와 대화 상자, 양식 뷰 또는 제어 뷰 개체의 **FLOAT(또는** **이중)** 데이터 멤버에서 OLE 컨트롤의 속성 간에 **float(또는** **이중)** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    float& value);

void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    double& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="ddx_ocfloatro"></a><a name="ddx_ocfloatro"></a>DDX_OCFloatRO

이 `DDX_OCFloatRO` 함수는 대화 상자, 양식 뷰 또는 제어 뷰 개체에서 OLE 컨트롤의 읽기 전용 속성과 대화 상자, 양식 뷰 또는 제어 뷰 개체의 **float(또는** **이중)** 데이터 멤버 간에 **float(또는** **이중)** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    float& value);

void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    double& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="ddx_ocint"></a><a name="ddx_ocint"></a>DDX_OCInt

이 `DDX_OCInt` 함수는 대화 상자, 양식 뷰 또는 제어 뷰 개체에서 OLE 컨트롤의 속성 과 대화 상자, 양식 뷰 또는 제어 뷰 개체의 int(또는 **긴)** 데이터 멤버 간의 **int(또는** **int** **긴)** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCInt(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    int& value);

void AFXAPI DDX_OCInt(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    long& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="ddx_ocintro"></a><a name="ddx_ocintro"></a>DDX_OCIntRO

이 `DDX_OCIntRO` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체에서 OLE 컨트롤의 읽기 전용 속성과 대화 상자, 양식 뷰 또는 제어 뷰 개체의 int(또는 **긴)** 데이터 멤버 간의 **int(또는** **int** **긴)** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    int& value);

void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    long& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="ddx_ocshort"></a><a name="ddx_ocshort"></a>DDX_OCShort

이 `DDX_OCShort` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체에서 OLE 컨트롤의 속성과 대화 상자, 양식 뷰 또는 제어 뷰 개체의 짧은 데이터 멤버 간에 짧은 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="ddx_ocshortro"></a><a name="ddx_ocshortro"></a>DDX_OCShortRO

이 `DDX_OCShortRO` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체에서 OLE 컨트롤의 읽기 전용 속성과 대화 상자, 양식 뷰 또는 제어 뷰 개체의 짧은 데이터 멤버 간에 짧은 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="ddx_octext"></a><a name="ddx_octext"></a>DDX_OCText

**DDX_OCText** 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체에서 OLE 컨트롤의 속성과 대화 상자, 양식 뷰 또는 제어 뷰 **개체의** CString 데이터 멤버 간에 **CString** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCText(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
**CDataExchange** 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="ddx_octextro"></a><a name="ddx_octextro"></a>DDX_OCTextRO

`DDX_OCTextRO` 함수는 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 내 OLE 컨트롤의 읽기 전용 속성과 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 `CString` 데이터 멤버 간 `CString` 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*디스피드 (것)들*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
