---
title: 표준 대화 상자 데이터 교환 루틴
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
ms.openlocfilehash: 83d4a66cd3ec41008506b55f0b351fd9bcbc24b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372924"
---
# <a name="standard-dialog-data-exchange-routines"></a>표준 대화 상자 데이터 교환 루틴

이 항목에서는 일반적인 MFC 대화 상자 컨트롤에 사용되는 표준 대화 상자 데이터 교환(DDX) 루틴을 나열합니다.

> [!NOTE]
> 표준 대화 상자 데이터 교환 루틴은 헤더 파일 afxdd_.h에 정의되어 있습니다. 그러나 응용 프로그램에는 afxwin.h가 포함되어야 합니다.

### <a name="ddx-functions"></a>DDX 기능

|||
|-|-|
|[DDX_CBIndex](#ddx_cbindex)|콤보 상자 컨트롤의 현재 선택 인덱스를 초기화하거나 검색합니다.|
|[DDX_CBString](#ddx_cbstring)|콤보 상자 컨트롤의 편집 필드의 현재 내용을 초기화하거나 검색합니다.|
|[DDX_CBStringExact](#ddx_cbstringexact)|콤보 상자 컨트롤의 편집 필드의 현재 내용을 초기화하거나 검색합니다.|
|[DDX_Check](#ddx_check)|확인란 컨트롤의 현재 상태를 초기화하거나 검색합니다.|
|[DDX_Control](#ddx_control)|대화 상자 내에서 지정된 컨트롤을 하위 클래스로 지정합니다.|
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|날짜 및 시간 선택기 컨트롤의 날짜 및/또는 시간 데이터를 초기화하거나 검색합니다.|
|[DDX_IPAddress](#ddx_ipaddress)|IP 주소 컨트롤의 현재 값을 초기화하거나 검색합니다.|
|[DDX_LBIndex](#ddx_lbindex)|목록 상자 컨트롤의 현재 선택 인덱스를 초기화하거나 검색합니다.|
|[DDX_LBString](#ddx_lbstring)|목록 상자 컨트롤 내에서 현재 선택을 초기화하거나 검색합니다.|
|[DDX_LBStringExact](#ddx_lbstringexact)|목록 상자 컨트롤 내에서 현재 선택을 초기화하거나 검색합니다.|
|[DDX_ManagedControl](#ddx_managedcontrol)|컨트롤의 리소스 ID와 일치하는 .NET 컨트롤을 만듭니다.|
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|월 달력 컨트롤의 현재 값을 초기화하거나 검색합니다.|
|[DDX_Radio](#ddx_radio)|현재 무선 제어 그룹 내에서 확인된 라디오 컨트롤의 0기반 인덱스를 초기화하거나 검색합니다.|
|[DDX_Scroll](#ddx_scroll)|스크롤 컨트롤의 엄지 손가락의 현재 위치를 초기화하거나 검색합니다.|
|[DDX_Slider](#ddx_slider)|슬라이더 컨트롤의 엄지 손가락의 현재 위치를 초기화하거나 검색합니다.|
|[DDX_Text](#ddx_text)|편집 컨트롤의 현재 값을 초기화하거나 검색합니다.|

## <a name="ddx_cbindex"></a><a name="ddx_cbindex"></a>DDX_CBIndex

이 `DDX_CBIndex` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체와 대화 상자, 양식 뷰 또는 제어 뷰 **개체의** int 데이터 멤버에서 콤보 상자 컨트롤 간의 **int** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
제어 속성과 연관된 콤보 상자 컨트롤의 리소스 ID입니다.

*index*<br/>
데이터가 교환되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_CBIndex` *인덱스는* 현재 콤보 상자 선택의 인덱스로 설정됩니다. 항목을 선택하지 않으면 *인덱스가* 0으로 설정됩니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_cbstring"></a><a name="ddx_cbstring"></a>DDX_CBString

이 `DDX_CBString` 함수는 대화 `CString` 상자, 양식 뷰 또는 제어 뷰 개체와 대화 상자, 양식 뷰 또는 `CString` 제어 뷰 개체의 데이터 멤버에서 콤보 상자 컨트롤의 편집 컨트롤 간의 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_CBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
제어 속성과 연관된 콤보 상자 컨트롤의 리소스 ID입니다.

*value*<br/>
데이터가 교환되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_CBString` *값은* 현재 콤보 상자 선택으로 설정됩니다. 항목을 선택하지 않으면 *값이* 0 길이의 문자열로 설정됩니다.

> [!NOTE]
> 콤보 상자가 드롭다운 목록 상자인 경우 교환된 값은 255자로 제한됩니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_cbstringexact"></a><a name="ddx_cbstringexact"></a>DDX_CBStringExact

이 `DDX_CBStringExact` 함수는 대화 `CString` 상자, 양식 뷰 또는 제어 뷰 개체와 대화 상자, 양식 뷰 또는 `CString` 제어 뷰 개체의 데이터 멤버에서 콤보 상자 컨트롤의 편집 컨트롤 간의 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
제어 속성과 연관된 콤보 상자 컨트롤의 리소스 ID입니다.

*value*<br/>
데이터가 교환되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_CBStringExact` *값은* 현재 콤보 상자 선택으로 설정됩니다. 항목을 선택하지 않으면 *값이* 0 길이의 문자열로 설정됩니다.

> [!NOTE]
> 콤보 상자가 드롭다운 목록 상자인 경우 교환된 값은 255자로 제한됩니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_check"></a><a name="ddx_check"></a>DDX_Check

이 `DDX_Check` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체와 대화 상자, 양식 뷰 또는 제어 뷰 **개체의** int 데이터 멤버에서 확인란 컨트롤 간의 **int** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_Check(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
제어 속성과 연결된 확인란 컨트롤의 리소스 ID입니다.

*value*<br/>
데이터가 교환되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_Check` *값은* 확인란 컨트롤의 현재 상태로 설정됩니다. 가능한 상태 값 목록은 Windows SDK의 [BM_GETCHECK](/windows/win32/Controls/bm-getcheck) 참조하세요.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_control"></a><a name="ddx_control"></a>DDX_Control

함수는 `DDX_Control` 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 *nIDC에*의해 지정된 컨트롤을 하위 클래스로 지정합니다.

```cpp
void AFXAPI DDX_Control(
    CDataExchange* pDX,
    int nIDC,
    CWnd& rControl);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다.

*nIDC*<br/>
하위 클래스가 될 컨트롤의 리소스 ID입니다.

*rControl*<br/>
대화 상자, 양식 뷰 또는 지정된 컨트롤과 관련된 제어 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

*pDX* 개체는 함수가 호출될 `DoDataExchange` 때 프레임워크에서 제공됩니다. 따라서 `DDX_Control` `DoDataExchange`의 재정의 내에서만 호출해야 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_datetimectrl"></a><a name="ddx_datetimectrl"></a>DDX_DateTimeCtrl

이 `DDX_DateTimeCtrl` 함수는 대화 상자 또는 양식 보기 개체와 대화 상자 또는 양식 보기 개체의 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 또는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 데이터 멤버에서 날짜 및 시간 선택기 컨트롤(CDateTimeCtrl) 간의 날짜 및/또는 시간 데이터 전송을 관리합니다. [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)

```cpp
void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,
    int nIDC,
    CTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다. 이 개체를 삭제할 필요가 없습니다.

*nIDC*<br/>
멤버 변수와 연결된 날짜 및 시간 선택기 컨트롤의 리소스 ID입니다.

*value*<br/>
처음 두 버전에서는 `CTime` 또는 `COleDateTime` 멤버 변수, 대화 상자, 양식 보기 또는 데이터가 교환되는 뷰 개체에 대한 참조입니다. 세 번째 버전에서는 데이터 `CString` 멤버 제어 뷰 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_DateTimeCtrl` *값은* 날짜 및 시간 선택기 컨트롤의 현재 상태로 설정되거나 컨트롤은 교환 방향에 따라 *값으로*설정됩니다.

위의 세 번째 `DDX_DateTimeCtrl` 버전에서는 날짜 `CString` 시간 컨트롤과 컨트롤 뷰 개체의 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 데이터 멤버 간의 데이터 전송을 관리합니다. 문자열은 날짜와 시간 서식을 지정하기 위해 현재 로캘의 규칙을 사용하여 서식이 지정됩니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_managedcontrol"></a><a name="ddx_managedcontrol"></a>DDX_ManagedControl

컨트롤의 리소스 ID와 일치하는 .NET 컨트롤을 만듭니다.

### <a name="syntax"></a>구문

```cpp
template <typename T>
void DDX_ManagedControl(
   CDataExchange* pDX,
   int nIDC,
   CWinFormsControl<T>& control );
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange 클래스](cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
제어 속성과 연결된 컨트롤의 리소스 ID입니다.

*컨트롤*<br/>
[CWinFormsControl 클래스](cwinformscontrol-class.md) 개체에 대 한 참조입니다.

### <a name="remarks"></a>설명

`DDX_ManagedControl`[CWinFormsControl::CreateManagedControl을](cwinformscontrol-class.md#createmanagedcontrol) 호출하여 리소스 제어 ID와 일치하는 컨트롤을 만듭니다. `DDX_ManagedControl` [CDialog::OnInitDialog](cdialog-class.md#oninitdialog)의 리소스 아이디에서 컨트롤을 만드는 데 사용합니다. 데이터 교환의 경우 Windows Forms 컨트롤에서 DDX/DDV 함수를 사용할 필요가 없습니다.

자세한 내용은 [방법을 참조하십시오: Windows 양식으로 DDX/DDV 데이터 바인딩 수행.](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

### <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h

## <a name="ddx_ipaddress"></a><a name="ddx_ipaddress"></a>DDX_IPAddress

이 `DDX_IPAddress` 함수는 IP 주소 컨트롤과 제어 뷰 개체의 데이터 멤버 간의 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
제어 속성과 연결된 IP 주소 컨트롤의 리소스 ID입니다.

*value*<br/>
IP 주소 컨트롤의 4필드 값을 포함하는 DWORD에 대한 참조입니다. 필드는 다음과 같이 채워지거나 읽습니다.

|필드|필드 값을 포함하는 비트|
|-----------|-------------------------------------|
|3|0 ~ 7|
|2|8 ~ 15|
|1|16 ~23|
|0|24 ~31|

Win32 [IPM_GETADDRESS](/windows/win32/Controls/ipm-getaddress) 사용하여 값을 읽거나 [IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress) 사용하여 값을 채웁니다. 이러한 메시지는 Windows SDK에 설명되어 있습니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_IPAddress` *값은* IP 주소 컨트롤에서 읽거나 교환 방향에 따라 *컨트롤에 값이* 기록됩니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_lbindex"></a><a name="ddx_lbindex"></a>DDX_LBIndex

이 `DDX_LBIndex` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체와 대화 상자, 양식 뷰 또는 제어 뷰 **개체의** int 데이터 멤버에서 목록 상자 컨트롤 간에 **int** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤 속성과 연결된 목록 상자 컨트롤의 리소스 ID입니다.

*index*<br/>
데이터가 교환되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_LBIndex` *인덱스는* 현재 목록 상자 선택의 인덱스로 설정됩니다. 항목을 선택하지 않으면 *인덱스가* -1로 설정됩니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_lbstring"></a><a name="ddx_lbstring"></a>DDX_LBString

이 `DDX_LBString` 함수는 대화 `CString` 상자, 양식 보기 또는 제어 뷰 개체와 대화 상자, `CString` 양식 뷰 또는 제어 뷰 개체의 데이터 멤버에서 목록 상자 컨트롤 간의 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_LBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤 속성과 연결된 목록 상자 컨트롤의 리소스 ID입니다.

*value*<br/>
데이터가 교환되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

데이터를 `DDX_LBString` 목록 상자 컨트롤로 전송하도록 호출되면 컨트롤의 첫 번째 항목이 시작일치 *값으로* 선택됩니다. 접두사가 아닌 전체 항목을 일치하려면 [DDX_LBStringExact](#ddx_lbstringexact)사용합니다. 일치하는 항목이 없는 경우 항목이 선택되지 않습니다. 일치는 대/소문자를 구분하지 않습니다.

목록 `DDX_LBString` 상자 컨트롤에서 데이터를 전송하도록 호출되면 *값이* 현재 목록 상자 선택으로 설정됩니다. 항목을 선택하지 않으면 *값이* 0 길이의 문자열로 설정됩니다.

> [!NOTE]
> 목록 상자가 드롭다운 목록 상자인 경우 교환된 값은 255자로 제한됩니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_lbstringexact"></a><a name="ddx_lbstringexact"></a>DDX_LBStringExact

이 `DDX_CBStringExact` 함수는 대화 `CString` 상자, 양식 보기 또는 제어 뷰 개체와 대화 상자, 양식 뷰 `CString` 또는 제어 뷰 개체의 데이터 멤버에서 목록 상자 컨트롤의 편집 컨트롤 간의 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤 속성과 연결된 목록 상자 컨트롤의 리소스 ID입니다.

*value*<br/>
데이터가 교환되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

데이터를 `DDX_LBStringExact` 목록 상자 컨트롤로 전송하도록 호출되면 *값과* 일치하는 컨트롤의 첫 번째 항목이 선택됩니다. 전체 항목이 아닌 접두사만 일치하려면 [DDX_LBString](#ddx_lbstring)사용합니다. 일치하는 항목이 없는 경우 항목이 선택되지 않습니다. 일치는 대/소문자를 구분하지 않습니다.

목록 `DDX_CBStringExact` 상자 컨트롤에서 데이터를 전송하도록 호출되면 *값이* 현재 목록 상자 선택으로 설정됩니다. 항목을 선택하지 않으면 *값이* 0 길이의 문자열로 설정됩니다.

> [!NOTE]
> 목록 상자가 드롭다운 목록 상자인 경우 교환된 값은 255자로 제한됩니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_monthcalctrl"></a><a name="ddx_monthcalctrl"></a>DDX_MonthCalCtrl

이 `DDX_MonthCalCtrl` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체와 대화 상자, 양식 보기 또는 제어 뷰 개체의 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 또는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 데이터 멤버에서 월 캘린더 컨트롤(CMonthCalCtrl) 간의 날짜 데이터 전송을 관리합니다. [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)

```cpp
void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,
    int nIDC,
    CTime& value);

void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다. 이 개체를 삭제할 필요가 없습니다.

*nIDC*<br/>
멤버 변수와 연결된 월 달력 컨트롤의 리소스 ID입니다.

*value*<br/>
데이터가 교환되는 `CTime` `COleDateTime` 대화 상자, 양식 보기 또는 제어 뷰 개체의 또는 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤은 날짜 값만 관리합니다. 시간 개체의 시간 필드는 컨트롤 창의 생성 시간 또는 에 대한 `CMonthCalCtrl::SetCurSel`호출을 사용하여 컨트롤에 설정된 시간을 반영하도록 설정되어 있습니다.

호출될 때 `DDX_MonthCalCtrl` *값은* 월 달력 컨트롤의 현재 상태로 설정됩니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_radio"></a><a name="ddx_radio"></a>DDX_Radio

이 `DDX_Radio` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체와 대화 상자, 양식 뷰 또는 제어 뷰 **개체의** int 데이터 멤버에서 무선 제어 그룹 간의 **int** 데이터 전송을 관리합니다. **int** 데이터 멤버의 값은 그룹 내의 어떤 라디오 단추를 선택하여 선택되어 있는지에 따라 결정됩니다.

```cpp
void AFXAPI DDX_Radio(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
그룹의 첫 번째 무선 컨트롤의 리소스 ID입니다.

*value*<br/>
데이터가 교환되는 대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_Radio` *값은* 무선 제어 그룹의 현재 상태로 설정됩니다. 이 값은 현재 확인된 라디오 컨트롤의 0기반 인덱스로 설정되거나 무선 컨트롤을 선택하지 않으면 -1로 설정됩니다.

예를 들어 그룹의 첫 번째 라디오 단추(WS_GROUP 스타일이 있는 단추)가 확인된 경우 **int** 멤버의 값은 0 등입니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_scroll"></a><a name="ddx_scroll"></a>DDX_Scroll

이 `DDX_Scroll` 함수는 대화 상자, 양식 보기 또는 제어 뷰 개체와 대화 상자, 양식 뷰 또는 제어 뷰 **개체의** int 데이터 멤버에서 스크롤 막대 컨트롤 간의 **int** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤 속성과 연결된 스크롤 막대 컨트롤의 리소스 ID입니다.

*value*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_Scroll` *값은* 컨트롤의 엄지 손가락의 현재 위치로 설정됩니다. 컨트롤의 현재 위치와 관련된 값에 대한 자세한 내용은 Windows SDK의 [GetScrollPos를](/windows/win32/api/winuser/nf-winuser-getscrollpos) 참조하십시오.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_slider"></a><a name="ddx_slider"></a>DDX_Slider

이 `DDX_Slider` 함수는 대화 상자 또는 양식 **보기의** 슬라이더 컨트롤과 대화 상자 또는 양식 뷰 개체의 int 데이터 멤버 간에 **int** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_Slider(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
슬라이더 컨트롤의 리소스 ID입니다.

*value*<br/>
교환할 값에 대한 참조입니다. 이 매개변수는 슬라이더 컨트롤의 현재 위치를 유지하거나 설정합니다.

### <a name="remarks"></a>설명

호출될 때 `DDX_Slider` *값은* 컨트롤의 엄지 손가락의 현재 위치로 설정되거나 값은 교환 방향에 따라 위치를 수신합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 슬라이더 컨트롤에 대한 자세한 내용은 [CSliderCtrl 사용](../../mfc/using-csliderctrl.md)을 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddx_text"></a><a name="ddx_text"></a>DDX_Text

이 `DDX_Text` 함수는 대화 상자, 양식 보기 또는 컨트롤 `CString`뷰에서 편집 컨트롤과 대화 상자, 양식 뷰 또는 제어 뷰 개체의 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 데이터 멤버 간에 **int,** **UINT,** **long**, DWORD, **float**또는 **이중** 데이터 전송을 관리합니다.

```cpp
void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    short& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    int& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    UINT& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    long& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    CString& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    float& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    double& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    COleCurrency& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 양식 보기 또는 컨트롤 뷰 개체에서 편집 컨트롤의 ID입니다.

*value*<br/>
대화 상자, 양식 보기 또는 컨트롤 뷰 개체의 데이터 멤버에 대한 참조입니다. *값의* 데이터 형식은 사용하는 오버로드된 버전에 `DDX_Text` 따라 달라집니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="see-also"></a>참고 항목

[표준 대화 상자 데이터 유효성 검사 루틴](standard-dialog-data-validation-routines.md)<br/>
[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[CWinForms 제어::만들기관리제어](cwinformscontrol-class.md#createmanagedcontrol)<br/>
[CDialog::OnInitDialog](cdialog-class.md#oninitdialog)
