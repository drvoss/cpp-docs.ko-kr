---
title: 표준 대화 상자 데이터 유효성 검사 루틴
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: 83e3e215ec8d66321bbac5a4a308b04ef69dc68c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372907"
---
# <a name="standard-dialog-data-validation-routines"></a>표준 대화 상자 데이터 유효성 검사 루틴

이 항목에서는 일반적인 MFC 대화 상자 컨트롤에 사용되는 표준 대화 상자 데이터 유효성 검사(DDV) 루틴을 나열합니다.

> [!NOTE]
> 표준 대화 상자 데이터 교환 루틴은 헤더 파일 afxdd_.h에 정의되어 있습니다. 그러나 응용 프로그램에는 afxwin.h가 포함되어야 합니다.

### <a name="ddv-functions"></a>DDV 기능

|||
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|지정된 컨트롤 값의 문자 수가 지정된 최대값을 초과하지 않는지 확인합니다.|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|지정된 제어 값이 지정된 **BYTE** 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|지정된 제어 값이 지정된 시간 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|지정된 제어 값이 지정된 **이중** 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|지정된 제어 값이 지정된 **DWORD** 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|지정된 제어 값이 지정된 **float** 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxInt](#ddv_minmaxint)|지정된 제어 값이 지정된 **int** 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxLong](#ddv_minmaxlong)|지정된 제어 값이 지정된 **긴** 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|지정된 제어 값이 지정된 **LONGLONG** 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|지정된 제어 값이 지정된 날짜 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxShort](#ddv_minmaxshort)|지정된 제어 값이 지정된 **짧은** 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|지정된 슬라이더 컨트롤 값이 지정된 범위 내에 속하는지 확인합니다.|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|지정된 제어 값이 지정된 **UINT** 범위를 초과하지 않는지 확인합니다.|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|지정된 컨트롤 값이 지정된 두 값 사이에 속하는지 확인합니다.|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|지정된 제어 값이 지정된 **ULONGLONG** 범위를 초과하지 않는지 확인합니다.|

## <a name="ddv_maxchars"></a><a name="ddv_maxchars"></a>DDV_MaxChars

`DDV_MaxChars` *호출을* 호출하여 값과 연결된 컨트롤의 문자 양이 *nChars를*초과하지 않는지 확인합니다.

```cpp
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*nChars*<br/>
허용되는 최대 문자 수입니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxbyte"></a><a name="ddv_minmaxbyte"></a>DDV_MinMaxByte

호출을 `DDV_MinMaxByte` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
허용되는 최소값(바이트 형식)입니다.

*맥스발 (주)*<br/>
최대값(바이트 형식)이 허용됩니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxdatetime"></a><a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime

`DDV_MinMaxDateTime` *refValue와* 연관된 날짜 및 시간 선택기 [제어(CDateTimeCtrl)의](../../mfc/reference/cdatetimectrl-class.md)시간/날짜 값이 *refMinRange와* *refMaxRange*사이에 속하는지 확인하려면 호출합니다.

```cpp
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다. 이 개체를 삭제할 필요가 없습니다.

*refValue*<br/>
대화 상자, 양식 뷰 또는 제어 뷰 개체의 멤버 변수와 연결된 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 또는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체에 대한 참조입니다. 이 개체에는 유효성을 검사할 데이터가 포함되어 있습니다.

*레프민레인지*<br/>
허용되는 최소 날짜/시간 값입니다.

*레프맥스 레인지*<br/>
허용되는 최대 날짜/시간 값입니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxdouble"></a><a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble

호출을 `DDV_MinMaxDouble` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
최소값(이중 **double**형식)은 허용됩니다.

*맥스발 (주)*<br/>
최대값(이중 **double**형식)은 허용됩니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxdword"></a><a name="ddv_minmaxdword"></a>DDV_MinMaxDWord

호출을 `DDV_MinMaxDWord` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
허용되는 최소값(DWORD 형식)입니다.

*맥스발 (주)*<br/>
최대값(DWORD 형식)이 허용됩니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxfloat"></a><a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat

호출을 `DDV_MinMaxFloat` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
최소값(float **float**형식)이 허용됩니다.

*맥스발 (주)*<br/>
최대값(float **float**형식)이 허용됩니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxint"></a><a name="ddv_minmaxint"></a>DDV_MinMaxInt

호출을 `DDV_MinMaxInt` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
최소값(int 형식)이 **허용됩니다.**

*맥스발 (주)*<br/>
최대값(int 형식)이 **허용됩니다.**

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxlong"></a><a name="ddv_minmaxlong"></a>DDV_MinMaxLong

호출을 `DDV_MinMaxLong` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
최소값(긴 **long**형식)이 허용됩니다.

*맥스발 (주)*<br/>
최대값(긴 **long**형식)이 허용됩니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxlonglong"></a><a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong

호출을 `DDV_MinMaxLongLong` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
허용되는 최소값(LONGLONG 형식)입니다.

*맥스발 (주)*<br/>
최대값(LONGLONG 형식)이 허용됩니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxmonth"></a><a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth

`DDV_MinMaxMonth` *refValue와* 연결된 월 달력 [컨트롤(CMonthCalCtrl)의](../../mfc/reference/cmonthcalctrl-class.md)시간/날짜 값이 *refMinRange와* *refMaxRange*사이에 속하는지 확인하려면 호출합니다.

```cpp
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*refValue*<br/>
대화 상자, 양식 `CTime` 뷰 `COleDateTime` 또는 제어 뷰 개체의 멤버 변수와 연결된 형식의 개체에 대한 참조입니다. 이 개체에는 유효성을 검사할 데이터가 포함되어 있습니다. MFC는 호출될 `DDV_MinMaxMonth` 때 이 참조를 전달합니다.

*레프민레인지*<br/>
허용되는 최소 날짜/시간 값입니다.

*레프맥스 레인지*<br/>
허용되는 최대 날짜/시간 값입니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxshort"></a><a name="ddv_minmaxshort"></a>DDV_MinMaxShort

호출을 `DDV_MinMaxShort` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
최소값(짧은 **short**형식)이 허용됩니다.

*맥스발 (주)*<br/>
최대값(짧은 **short**형식)이 허용됩니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxslider"></a><a name="ddv_minmaxslider"></a>DDV_MinMaxSlider

호출을 `DDV_MinMaxSlider` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
유효성을 검사할 값에 대한 참조입니다. 이 매개변수는 슬라이더 컨트롤의 현재 엄지 손가락 위치를 유지하거나 설정합니다.

*광부 (것)중 (것)*<br/>
허용되는 최소 값입니다.

*맥스발 (주)*<br/>
허용되는 최대값입니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오. 슬라이더 컨트롤에 대한 자세한 내용은 [CSliderCtrl 사용](../../mfc/using-csliderctrl.md)을 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxuint"></a><a name="ddv_minmaxuint"></a>DDV_MinMaxUInt

호출을 `DDV_MinMaxUInt` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
허용되는 최소값(UINT 형식)입니다.

*맥스발 (주)*<br/>
최대값(UINT 형식)이 허용됩니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxulonglong"></a><a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong

호출을 `DDV_MinMaxULongLong` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

```cpp
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
허용되는 최소값(ULONGLONG 형식)입니다.

*맥스발 (주)*<br/>
최대값(ULONGLONG 형식)이 허용됩니다.

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../../mfc/dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddv_minmaxunsigned"></a>DDV_MinMaxUnsigned

호출을 `DDV_MinMaxUnsigned` 호출하여 *값과* 연결된 컨트롤의 값이 *minVal과* *maxVal*간에 속하는지 확인합니다.

### <a name="syntax"></a>구문

```cpp
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*value*<br/>
데이터의 유효성이 검사되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

*광부 (것)중 (것)*<br/>
최소값(서명되지 않은 형식)이 **허용됩니다.**

*맥스발 (주)*<br/>
최대값(서명되지 않은 형식)이 **허용됩니다.**

### <a name="remarks"></a>설명

DDV에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사를](../dialog-data-exchange-and-validation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxdd_.h

## <a name="see-also"></a>참고 항목

[표준 대화 상자 데이터 교환 루틴](standard-dialog-data-exchange-routines.md)<br/>
[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[DDX_Slider](standard-dialog-data-exchange-routines.md#ddx_slider)<br/>
[DDX_FieldSlider](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md#ddx_fieldslider)
