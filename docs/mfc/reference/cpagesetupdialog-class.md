---
title: CPageSetupDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
ms.openlocfilehash: 3664149ef0d7476b460ef06cddaf2b8145ade701
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753693"
---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog 클래스

인쇄 여백 설정과 수정이 추가로 지원되는 Windows 공용 OLE 페이지 설정 대화 상자에서 제공하는, 서비스를 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CPageSetupDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CPageSetup Dialog::CPageSetupDialog](#cpagesetupdialog)|`CPageSetupDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPageSetup Dialog::프린터 만들기](#createprinterdc)|인쇄를 위한 장치 컨텍스트를 만듭니다.|
|[CPageSetupDialog::DoModal](#domodal)|대화 상자를 표시하고 사용자가 선택할 수 있습니다.|
|[CPageSetupDialog::GetDeviceName](#getdevicename)|프린터의 장치 이름을 반환합니다.|
|[CPageSetup디아로그::겟데브모드](#getdevmode)|프린터의 현재 DEVMODE를 반환합니다.|
|[CPageSetupDialog::GetDriverName](#getdrivername)|프린터에서 사용하는 드라이버를 반환합니다.|
|[CPageSetupDialog::GetMargins](#getmargins)|프린터의 현재 여백 설정을 반환합니다.|
|[CPageSetup디아로그::겟페이퍼사이즈](#getpapersize)|프린터의 용지 크기를 반환합니다.|
|[CPageSetupDialog::GetPortName](#getportname)|출력 포트 이름을 반환합니다.|
|[CPageSetupDialog::온드로우 페이지](#ondrawpage)|인쇄된 페이지의 화면 이미지를 렌더링하기 위해 프레임워크에서 호출됩니다.|
|[CPageSetupDialog::P다시 그리기 페이지](#predrawpage)|인쇄된 페이지의 화면 이미지를 렌더링하기 전에 프레임워크에서 호출합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CPageSetupDialog::m_psd](#m_psd)|개체를 사용자 지정하는 `CPageSetupDialog` 데 사용되는 구조입니다.|

## <a name="remarks"></a>설명

이 클래스는 설치 설정 인쇄 대화 상자를 대신하도록 설계되었습니다.

개체를 `CPageSetupDialog` 사용하려면 먼저 생성기를 `CPageSetupDialog` 사용하여 개체를 만듭니다. 대화 상자가 생성되면 데이터 멤버의 `m_psd` 값을 설정하거나 수정하여 대화 상자 컨트롤의 값을 초기화할 수 있습니다. [m_psd](#m_psd) 구조는 페이지셋업DLG 형식입니다.

대화 상자 컨트롤을 초기화한 `DoModal` 후 멤버 함수를 호출하여 대화 상자를 표시하고 사용자가 인쇄 옵션을 선택할 수 있도록 합니다. `DoModal`사용자가 확인(IDOK) 또는 취소(IDCANCEL) 단추를 선택했는지 여부를 반환합니다.

IDOK를 반환하는 경우 `DoModal` 여러 `CPageSetupDialog`멤버 함수를 사용하거나 `m_psd` 데이터 멤버에 액세스하여 사용자가 입력한 정보를 검색할 수 있습니다.

> [!NOTE]
> 일반적인 OLE 페이지 설치 대화 상자가 해제된 후에는 사용자가 변경한 내용이 프레임워크에 의해 저장되지 않습니다. 이 대화 상자의 값을 응용 프로그램 문서 또는 응용 프로그램 클래스의 구성원과 같은 영구적인 위치에 저장하는 것은 응용 프로그램 자체의 결정입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

## <a name="cpagesetupdialogcpagesetupdialog"></a><a name="cpagesetupdialog"></a>CPageSetup Dialog::CPageSetupDialog

이 함수를 호출하여 개체를 생성합니다. `CPageSetupDialog`

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
대화 상자의 설정을 사용자 지정하는 데 사용할 수 있는 하나 이상의 플래그입니다. 비트와이즈-OR 연산자를 사용하여 값을 결합할 수 있습니다. 이러한 값에는 다음과 같은 의미가 있습니다.

- PSD_DEFAULTMINMARGINS 페이지 여백의 허용 가능한 최소 너비를 프린터의 최소 너비와 동일하게 설정합니다. PSD_MARGINS PSD_MINMARGINS 플래그도 지정된 경우 이 플래그는 무시됩니다.

- PSD_INWININIINTLMEASURE 구현되지 않았습니다.

- PSD_MINMARGINS 시스템에서 `rtMinMargin` 멤버에 지정된 값을 왼쪽, 위쪽, 오른쪽 및 아래쪽 여백에 대해 허용되는 최소 너비로 사용하도록 합니다. 시스템은 사용자가 지정된 최소값보다 작은 너비를 입력하지 못하도록 합니다. PSD_MINMARGINS 지정하지 않으면 시스템은 프린터에서 허용하는 최소 허용 너비로 설정합니다.

- PSD_MARGINS 마진 제어 영역을 활성화합니다.

- PSD_INTHOUSANDTHSOFINCHES 대화 상자의 단위를 인치의 1/1000으로 측정합니다.

- PSD_INHUNDREDTHSOFMILLIMETERS 대화 상자의 단위를 밀리미터의 1/100으로 측정합니다.

- PSD_DISABLEMARGINS 여백 대화 상자 컨트롤을 사용하지 않도록 설정합니다.

- PSD_DISABLEPRINTER 프린터 단추를 사용하지 않도록 설정합니다.

- PSD_NOWARNING 기본 프린터가 없을 때 경고 메시지가 표시되지 않도록 합니다.

- PSD_DISABLEORIENTATION 페이지 방향 대화 상자 컨트롤을 사용하지 않도록 설정합니다.

- PSD_RETURNDEFAULT `CPageSetupDialog` 대화 상자를 표시하지 않고 시스템 기본 프린터에 대해 초기화된 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 및 [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) 구조를 반환하는 원인입니다. 둘 다 `hDevNames` NULL이라고 `hDevMode` 가정합니다. 그렇지 않으면 함수에서 오류를 반환합니다. 시스템 기본 프린터가 이전 프린터 드라이버에서 지원되는 경우(Windows 버전 `hDevNames` 3.0 이전) 만 반환됩니다. `hDevMode` 는 NULL입니다.

- PSD_DISABLEPAPER 용지 선택 컨트롤을 사용하지 않도록 설정합니다.

- PSD_SHOWHELP 대화 상자에 도움말 버튼이 표시됩니다. 이 `hwndOwner` 플래그를 지정하면 멤버가 NULL이 아니어야 합니다.

- PSD_ENABLEPAGESETUPHOOK 에 지정된 후크 `lpfnSetupHook`기능을 활성화합니다.

- PSD_ENABLEPAGESETUPTEMPLATE 으로 식별된 `hInstance` 대화 상자 및 `lpSetupTemplateName`을 사용하여 운영 체제가 대화 상자를 만들게 합니다.

- PSD_ENABLEPAGESETUPTEMPLATEHANDLE 미리 `hInstance` 로드된 대화 상자 템플릿이 포함된 데이터 블록을 식별합니다. 이 플래그가 `lpSetupTemplateName` 지정되면 시스템에서 무시합니다.

- PSD_ENABLEPAGEPAINTHOOK 에 지정된 후크 `lpfnPagePaintHook`기능을 활성화합니다.

- PSD_DISABLEPAGEPAINTING 대화 상자의 그리기 영역을 비활성화합니다.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자에 대한 포인터입니다.

### <a name="remarks"></a>설명

[DoModal](../../mfc/reference/cdialog-class.md#domodal) 함수를 사용하여 대화 상자를 표시합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

## <a name="cpagesetupdialogcreateprinterdc"></a><a name="createprinterdc"></a>CPageSetup Dialog::프린터 만들기

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 및 [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) 구조에서 프린터 장치 컨텍스트를 만듭니다.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Return Value

새로 생성된 프린터 장치 컨텍스트(DC)를 처리합니다.

## <a name="cpagesetupdialogdomodal"></a><a name="domodal"></a>CPageSetupDialog::DoModal

이 함수를 호출하여 Windows 공통 OLE 페이지 설정 대화 상자를 표시하고 사용자가 인쇄 여백, 용지 크기 및 방향, 대상 프린터와 같은 다양한 인쇄 설정 옵션을 선택할 수 있도록 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

IDOK 또는 IDCANCEL. IDCANCEL가 반환되면 Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) 함수를 호출하여 오류가 발생했는지 확인합니다.

IDOK 및 IDCANCEL은 사용자가 확인 또는 취소 단추를 선택했는지 여부를 나타내는 상수입니다.

### <a name="remarks"></a>설명

또한 사용자는 선택한 프린터와 관련된 네트워크 위치 및 속성과 같은 프린터 설정 옵션에 액세스할 수 있습니다.

`m_psd` 구조체의 멤버를 설정하여 다양한 페이지 설치 대화 상자를 초기화하려면 호출하기 `DoModal`전과 대화 상자 개체가 생성된 후에 수행해야 합니다. 호출 `DoModal`한 후 다른 멤버 함수를 호출하여 사용자가 대화 상자에 입력 한 설정 또는 정보를 검색합니다.

사용자가 입력한 현재 설정을 전파하려면 [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter)를 호출합니다. 이 함수는 `CPageSetupDialog` 개체의 정보를 가져와 적절한 특성을 가진 새 프린터 DC를 초기화하고 선택합니다.

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>예제

  [CPageSetupDialog::CPageSetupDialog에](#cpagesetupdialog)대 한 예제를 참조 하십시오.

## <a name="cpagesetupdialoggetdevicename"></a><a name="getdevicename"></a>CPageSetupDialog::GetDeviceName

현재 선택한 `DoModal` 프린터의 이름을 검색하려면 이 함수를 호출합니다.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Return Value

개체에서 사용하는 장치 `CPageSetupDialog` 이름입니다.

## <a name="cpagesetupdialoggetdevmode"></a><a name="getdevmode"></a>CPageSetup디아로그::겟데브모드

호출 `DoModal` 후 이 함수를 호출하여 개체의 `CPageSetupDialog` 프린터 장치 컨텍스트에 대한 정보를 검색합니다.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Return Value

인쇄 드라이버의 장치 초기화 및 환경에 대한 정보가 포함된 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 데이터 구조입니다. Windows SDK에 설명된 Windows [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) 기능을 통해 이 구조에서 가져온 메모리의 잠금을 해제해야 합니다.

## <a name="cpagesetupdialoggetdrivername"></a><a name="getdrivername"></a>CPageSetupDialog::GetDriverName

[DoModal을](../../mfc/reference/cprintdialog-class.md#domodal) 호출한 후 이 함수를 호출하여 시스템 정의 프린터 장치 드라이버의 이름을 검색합니다.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Return Value

시스템 `CString` 정의 드라이버 이름을 지정하는 A입니다.

### <a name="remarks"></a>설명

[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)에 `GetDriverName` 대한 호출의 `lpszDriverName` 값으로 반환되는 `CString` 개체에 대한 포인터를 사용합니다.

## <a name="cpagesetupdialoggetmargins"></a><a name="getmargins"></a>CPageSetupDialog::GetMargins

프린터 장치 드라이버의 `DoModal` 여백을 검색하려면 호출 후 이 함수를 호출합니다.

```cpp
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>매개 변수

*lpRectMargins*<br/>
현재 선택한 프린터의 인쇄 여백을 설명하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체에 대한 포인터입니다. 이 사각형에 관심이 없는 경우 이 매개 변수에 대해 NULL을 전달합니다.

*lpRectMinMargins*<br/>
현재 선택된 `RECT` `CRect` 프린터의 최소 인쇄 여백(1/1000인치 또는 1/100mm)을 설명하는 구조 또는 개체에 대한 포인터입니다. 이 사각형에 관심이 없는 경우 이 매개 변수에 대해 NULL을 전달합니다.

## <a name="cpagesetupdialoggetpapersize"></a><a name="getpapersize"></a>CPageSetup디아로그::겟페이퍼사이즈

이 함수를 호출하여 인쇄에 선택한 용지 크기를 검색합니다.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Return Value

인쇄를 위해 선택한 용지 크기(1/1000인치 또는 1/100mm)를 포함하는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.

## <a name="cpagesetupdialoggetportname"></a><a name="getportname"></a>CPageSetupDialog::GetPortName

호출 `DoModal` 후 이 함수를 호출하여 현재 선택한 프린터 포트의 이름을 검색합니다.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Return Value

현재 선택된 프린터 포트의 이름입니다.

## <a name="cpagesetupdialogm_psd"></a><a name="m_psd"></a>CPageSetupDialog::m_psd

대화 상자 개체의 특성을 저장하는 PAGESETUPDLG 형식의 구조입니다.

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>설명

개체를 생성한 `CPageSetupDialog` 후 `m_psd` `DoModal` 멤버 함수를 호출하기 전에 대화 상자의 다양한 측면을 설정하는 데 사용할 수 있습니다.

데이터 멤버를 `m_psd` 직접 수정하는 경우 기본 동작을 재정의합니다.

[PAGESETUPDLG](/windows/win32/api/commdlg/ns-commdlg-pagesetupdlgw) 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

[CPageSetupDialog::CPageSetupDialog에](#cpagesetupdialog)대 한 예제를 참조 하십시오.

## <a name="cpagesetupdialogondrawpage"></a><a name="ondrawpage"></a>CPageSetupDialog::온드로우 페이지

인쇄된 페이지의 화면 이미지를 그리는 프레임워크에서 호출됩니다.

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 장치 컨텍스트에 대한 포인터입니다.

*n 메시지*<br/>
현재 그려지고 있는 페이지의 영역을 나타내는 메시지를 지정합니다. 다음 중 하나일 수 있습니다.

- WM_PSD_FULLPAGERECT 전체 페이지 영역입니다.

- WM_PSD_MINMARGINRECT 현재 최소 여백입니다.

- WM_PSD_MARGINRECT 현재 여백을 참조하십시오.

- 페이지의 내용을 WM_PSD_GREEKTEXTRECT.

- WM_PSD_ENVSTAMPRECT 우표 표현을 위해 예약된 영역입니다.

- 반환 주소 표현을 위한 WM_PSD_YAFULLPAGERECT 영역입니다. 이 영역은 샘플 페이지 영역의 가장자리까지 확장됩니다.

*Lprect*<br/>
도면 영역의 좌표를 포함하는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 객체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

처리된 경우 비영값; 그렇지 않으면 0.

### <a name="remarks"></a>설명

그런 다음 이 이미지는 일반적인 OLE 페이지 설정 대화 상자의 일부로 표시됩니다. 기본 구현은 텍스트 페이지의 이미지를 그립니다.

이 함수를 재정의하여 이미지의 특정 영역 또는 전체 이미지의 드로잉을 사용자 지정합니다. *nMessage*의 값을 검사하는 **대/소문자가** 있는 **switch** 문을 사용하여 이 작업을 수행할 수 있습니다. 예를 들어 페이지 이미지의 내용 렌더링을 사용자 지정하려면 다음 예제 코드를 사용할 수 있습니다.

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

*nMessage*의 모든 대/소문자를 처리할 필요는 없습니다. 이미지의 한 구성 요소, 이미지의 여러 구성 요소 또는 전체 영역을 처리하도록 선택할 수 있습니다.

## <a name="cpagesetupdialogpredrawpage"></a><a name="predrawpage"></a>CPageSetupDialog::P다시 그리기 페이지

인쇄된 페이지의 화면 이미지를 그리기 전에 프레임워크에서 호출합니다.

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>매개 변수

*w페이퍼*<br/>
용지 크기를 나타내는 값을 지정합니다. 이 값은 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 구조설명에 나열된 **DMPAPER_** 값 중 하나일 수 있습니다.

*wFlags*<br/>
용지 또는 봉투의 방향과 프린터가 도트 매트릭스 또는 HPPCL(휴렛 패커드 프린터 제어 언어) 장치인지 여부를 나타냅니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.

- 0x001 가로 모드의 용지(도트 매트릭스)

- 0x003 가로 모드의 용지(HPPCL)

- 0x005 세로 모드의 용지(도트 매트릭스)

- 0x007 세로 모드(HPPCL)의 용지

- 가로 모드에서 0x00b 봉투 (HPPCL)

- 세로 모드의 0x00d 봉투(도트 매트릭스)

- 0x019 가로 모드의 봉투(도트 매트릭스)

- 세로 모드에서 0x01f 봉투(도트 매트릭스)

*pPSD*<br/>
`PAGESETUPDLG` 구조체에 대한 포인터입니다. [페이지셋업DLG에](/windows/win32/api/commdlg/ns-commdlg-pagesetupdlgw)대한 자세한 내용은 Windows SDK를 참조하십시오.

### <a name="return-value"></a>Return Value

처리된 경우 비영값; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수를 재정의하여 이미지 드로잉을 사용자 지정합니다. 이 함수를 재정의하고 TRUE를 반환하는 경우 전체 이미지를 그려야 합니다. 이 함수를 재정의하고 FALSE를 반환하면 전체 기본 이미지가 프레임워크에 의해 그려집니다.

## <a name="see-also"></a>참조

[MFC 샘플 워드패드](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
