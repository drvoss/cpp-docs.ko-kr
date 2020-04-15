---
title: CPrintDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CPrintDialog
- AFXDLGS/CPrintDialog
- AFXDLGS/CPrintDialog::CPrintDialog
- AFXDLGS/CPrintDialog::CreatePrinterDC
- AFXDLGS/CPrintDialog::DoModal
- AFXDLGS/CPrintDialog::GetCopies
- AFXDLGS/CPrintDialog::GetDefaults
- AFXDLGS/CPrintDialog::GetDeviceName
- AFXDLGS/CPrintDialog::GetDevMode
- AFXDLGS/CPrintDialog::GetDriverName
- AFXDLGS/CPrintDialog::GetFromPage
- AFXDLGS/CPrintDialog::GetPortName
- AFXDLGS/CPrintDialog::GetPrinterDC
- AFXDLGS/CPrintDialog::GetToPage
- AFXDLGS/CPrintDialog::PrintAll
- AFXDLGS/CPrintDialog::PrintCollate
- AFXDLGS/CPrintDialog::PrintRange
- AFXDLGS/CPrintDialog::PrintSelection
- AFXDLGS/CPrintDialog::m_pd
helpviewer_keywords:
- CPrintDialog [MFC], CPrintDialog
- CPrintDialog [MFC], CreatePrinterDC
- CPrintDialog [MFC], DoModal
- CPrintDialog [MFC], GetCopies
- CPrintDialog [MFC], GetDefaults
- CPrintDialog [MFC], GetDeviceName
- CPrintDialog [MFC], GetDevMode
- CPrintDialog [MFC], GetDriverName
- CPrintDialog [MFC], GetFromPage
- CPrintDialog [MFC], GetPortName
- CPrintDialog [MFC], GetPrinterDC
- CPrintDialog [MFC], GetToPage
- CPrintDialog [MFC], PrintAll
- CPrintDialog [MFC], PrintCollate
- CPrintDialog [MFC], PrintRange
- CPrintDialog [MFC], PrintSelection
- CPrintDialog [MFC], m_pd
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
ms.openlocfilehash: 6490e5488c5ab3b808a02e3608b75541e4063d8f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364058"
---
# <a name="cprintdialog-class"></a>CPrintDialog 클래스

Windows 공용 대화 상자에서 인쇄용으로 제공하는 서비스를 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CPrintDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C인쇄대화상자::C프린트디아로그](#cprintdialog)|`CPrintDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C프린트디아로그::프린터 만들기](#createprinterdc)|인쇄 대화 상자를 표시하지 않고 프린터 장치 컨텍스트를 만듭니다.|
|[C프린트디아로그::DoModal](#domodal)|대화 상자를 표시하고 사용자가 선택할 수 있습니다.|
|[C인쇄대화::GetCopys](#getcopies)|요청된 복사본 수를 검색합니다.|
|[C인쇄 대화상자::GetDefaults](#getdefaults)|대화 상자를 표시하지 않고 장치 기본값을 검색합니다.|
|[C프린트디아로그::GetDeviceName](#getdevicename)|현재 선택한 프린터 장치의 이름을 검색합니다.|
|[C프린트디아로그::겟데브모드](#getdevmode)|구조를 검색합니다. `DEVMODE`|
|[C인쇄디아로그::GetDriverName](#getdrivername)|현재 선택한 프린터 드라이버의 이름을 검색합니다.|
|[C인쇄대화상자::GetFromPage](#getfrompage)|인쇄 범위의 시작 페이지를 검색합니다.|
|[C프린트디아로그::겟포트네임](#getportname)|현재 선택한 프린터 포트의 이름을 검색합니다.|
|[C프린트디아로그::겟프린터DC](#getprinterdc)|프린터 장치 컨텍스트에 대한 핸들을 검색합니다.|
|[C인쇄대화상자::GetToPage](#gettopage)|인쇄 범위의 끝 페이지를 검색합니다.|
|[C프린트디아로그::P모든](#printall)|문서의 모든 페이지를 인쇄할지 여부를 결정합니다.|
|[C프린트디아로그::P린트콜라테](#printcollate)|대조된 복사본이 요청되는지 여부를 결정합니다.|
|[C프린트디아로그::P린트레인지](#printrange)|지정된 페이지 범위만 인쇄할지 여부를 결정합니다.|
|[C프린트디아로그::P린트선택](#printselection)|현재 선택한 항목만 인쇄할지 여부를 결정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C인쇄디아로그::m_pd](#m_pd)|개체를 사용자 지정하는 `CPrintDialog` 데 사용되는 구조입니다.|

## <a name="remarks"></a>설명

일반적인 인쇄 대화 상자는 Windows 표준과 일치하는 방식으로 설치 및 인쇄 대화 상자를 쉽게 구현할 수 있는 방법을 제공합니다.

> [!NOTE]
> 클래스는 `CPrintDialogEx` Windows Print 속성 시트에서 제공하는 서비스를 캡슐화합니다. 자세한 내용은 [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) 개요를 참조하십시오.

`CPrintDialog`'의 기능은 인쇄 설정 및 페이지 설정 모두에 대한 공통 대화 상자를 제공하도록 설계된 [CPageSetupDialog의](../../mfc/reference/cpagesetupdialog-class.md)기능으로 대체됩니다.

프레임워크를 사용하여 응용 프로그램에 대한 인쇄 프로세스의 여러 측면을 처리할 수 있습니다. 이 경우 프레임워크는 인쇄를 위한 Windows 공통 대화 상자를 자동으로 표시합니다. 응용 프로그램에 대한 프레임워크 핸들 인쇄를 할 수 있지만 고유한 인쇄 대화 상자를 통해 일반적인 인쇄 대화 상자를 재정의할 수도 있습니다. 인쇄 작업을 처리하기 위해 프레임 워크를 사용하는 것에 대한 자세한 내용은 [인쇄](../../mfc/printing.md)문서를 참조하십시오.

응용 프로그램이 프레임워크의 개입 없이 인쇄를 처리하도록 하려면 `CPrintDialog` 제공된 생성자와 함께 "있는 것처럼" 클래스를 사용하거나 사용자 `CPrintDialog` 고유의 대화 상자 클래스를 파생시키고 필요에 맞게 생성기를 작성할 수 있습니다. 두 경우 모두 이러한 대화 상자는 클래스에서 `CCommonDialog`파생되므로 표준 MFC 대화 상자처럼 동작합니다.

개체를 `CPrintDialog` 사용하려면 먼저 생성기를 `CPrintDialog` 사용하여 개체를 만듭니다. 대화 상자가 생성되면 [m_pd](#m_pd) 구조의 값을 설정하거나 수정하여 대화 상자 컨트롤의 값을 초기화할 수 있습니다. 구조는 `m_pd` [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga)유형입니다. 이 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

`hDevMode` 및 `hDevNames` `m_pd` 멤버에 대한 고유한 핸들을 제공하지 않는 경우 대화 상자를 `GlobalFree` 완료할 때 이러한 핸들에 대해 Windows 함수를 호출해야 합니다. `CWinApp::OnFilePrintSetup`에서 제공하는 프레임워크의 인쇄 설치 설정 구현을 사용하는 경우 이러한 핸들을 해제할 필요가 없습니다. 핸들은 에 의해 `CWinApp` 유지 되고 `CWinApp`'s 소멸자에서 해제 됩니다. 독립 실행형 을 사용할 `CPrintDialog` 때만 이러한 핸들을 해제해야 합니다.

대화 상자 컨트롤을 초기화한 `DoModal` 후 멤버 함수를 호출하여 대화 상자를 표시하고 사용자가 인쇄 옵션을 선택할 수 있도록 합니다. `DoModal`사용자가 확인(IDOK) 또는 취소(IDCANCEL) 단추를 선택했는지 여부를 반환합니다.

IDOK를 반환하는 `DoModal` 경우's `CPrintDialog`멤버 함수 중 하나를 사용하여 사용자가 입력한 정보를 검색할 수 있습니다.

`CPrintDialog::GetDefaults` 멤버 기능은 대화 상자를 표시하지 않고 현재 프린터 기본값을 검색하는 데 유용합니다. 이 멤버 함수에는 사용자 상호 작용이 필요하지 않습니다.

Windows `CommDlgExtendedError` 함수를 사용하여 대화 상자를 초기화하는 동안 오류가 발생했는지 확인하고 오류에 대해 자세히 알아볼 수 있습니다. 이 기능에 대한 자세한 내용은 Windows SDK를 참조하십시오.

`CPrintDialog`COMMDLG에 의존합니다. Windows 버전 3.1 이상과 함께 제공되는 DLL 파일입니다.

대화 상자를 사용자 지정하려면 에서 `CPrintDialog`클래스를 파생합니다. 처리되지 않은 모든 메시지는 기본 클래스에 전달되어야 합니다. 후크 기능을 사용자 지정할 필요는 없습니다.

대화 상자가 인쇄 또는 인쇄 설정인지 여부에 따라 동일한 메시지를 다르게 처리하려면 각 대화 상자에 대한 클래스를 파생해야 합니다. 또한 인쇄 설정 단추를 인쇄 대화 상자 내에서 선택할 때 새 대화 상자 만들기를 처리하는 Windows `AttachOnSetup` 함수를 재정의해야 합니다.

사용에 `CPrintDialog`대한 자세한 내용은 [일반적인 대화 상자 클래스를](../../mfc/common-dialog-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

## <a name="cprintdialogcprintdialog"></a><a name="cprintdialog"></a>C인쇄대화상자::C프린트디아로그

Windows 인쇄 또는 설치 설정 대화 상자 개체를 생성합니다.

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*b프린트셋만*<br/>
표준 Windows 인쇄 대화 상자 또는 인쇄 설정 대화 상자가 표시되는지 여부를 지정합니다. 표준 Windows 인쇄 설치 대화 상자를 표시하려면 이 매개 변수를 TRUE로 설정합니다. Windows 인쇄 대화 상자를 표시하려면 FALSE로 설정합니다. *bPrintSetupOnly가* FALSE인 경우 인쇄 설정 옵션 버튼이 인쇄 대화 상자에 계속 표시됩니다.

*dwFlags*<br/>
비트OR 연산자를 사용하여 결합된 대화 상자의 설정을 사용자 지정하는 데 사용할 수 있는 하나 이상의 플래그입니다. 예를 들어 PD_ALLPAGES 플래그는 기본 인쇄 범위를 문서의 모든 페이지로 설정합니다. 이러한 플래그에 대한 자세한 내용은 Windows SDK의 [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) 구조를 참조하십시오.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 개체만 생성합니다. 멤버 `DoModal` 함수를 사용하여 대화 상자를 표시합니다.

*bPrintSetupOnly* 가 FALSE로 설정된 생성자라고 하면 PD_RETURNDC 플래그가 자동으로 사용됩니다. 또는 `GetPrinterDC` `DoModal`또는 `GetDefaults`프린터 DC를 호출하면 에서 `m_pd.hDC`반환됩니다. 이 DC는 `CPrintDialog`의 호출자에 의해 [DeleteDC에](/windows/win32/api/wingdi/nf-wingdi-deletedc) 대한 호출로 해제되어야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

## <a name="cprintdialogcreateprinterdc"></a><a name="createprinterdc"></a>C프린트디아로그::프린터 만들기

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 및 [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) 구조에서 프린터 장치 컨텍스트(DC)를 만듭니다.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Return Value

새로 생성된 프린터 장치 컨텍스트를 처리합니다.

### <a name="remarks"></a>설명

이 DC는 현재 프린터 DC로 가정하며 이전에 가져온 다른 프린터 DC는 사용자가 삭제해야 합니다. 이 함수를 호출할 수 있으며 인쇄 대화 상자를 표시하지 않고도 결과 DC를 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

## <a name="cprintdialogdomodal"></a><a name="domodal"></a>C프린트디아로그::DoModal

Windows 일반 인쇄 대화 상자를 표시하고 사용자가 복사본 수, 페이지 범위 및 복사본을 대조할지 여부와 같은 다양한 인쇄 옵션을 선택할 수 있습니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

IDOK 또는 IDCANCEL. IDCANCEL가 반환되면 Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) 함수를 호출하여 오류가 발생했는지 확인합니다.

IDOK 및 IDCANCEL은 사용자가 확인 또는 취소 단추를 선택했는지 여부를 나타내는 상수입니다.

### <a name="remarks"></a>설명

`m_pd` 구조체의 멤버를 설정하여 다양한 인쇄 대화 상자를 초기화하려면 호출하기 `DoModal`전에 이 작업을 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

호출 `DoModal`한 후 다른 멤버 함수를 호출하여 사용자가 대화 상자에 입력 한 설정 또는 정보를 검색 할 수 있습니다.

*bPrintSetupOnly* 가 FALSE로 설정된 생성자라고 하면 PD_RETURNDC 플래그가 자동으로 사용됩니다. 또는 `GetPrinterDC` `DoModal`또는 `GetDefaults`프린터 DC를 호출하면 에서 `m_pd.hDC`반환됩니다. 이 DC는 `CPrintDialog`의 호출자에 의해 [DeleteDC에](/windows/win32/api/wingdi/nf-wingdi-deletedc) 대한 호출로 해제되어야 합니다.

### <a name="example"></a>예제

  [CPrintDialog::Create프린터DC의](#createprinterdc)예제를 참조하십시오.

## <a name="cprintdialoggetcopies"></a><a name="getcopies"></a>C인쇄대화::GetCopys

요청된 복사본 수를 검색합니다.

```
int GetCopies() const;
```

### <a name="return-value"></a>Return Value

요청한 사본 수입니다.

### <a name="remarks"></a>설명

호출 `DoModal` 후 이 함수를 호출하여 요청된 복사본 수를 검색합니다.

### <a name="example"></a>예제

  [CPrintDialog::PrintCollate에](#printcollate)대한 예제를 참조하십시오.

## <a name="cprintdialoggetdefaults"></a><a name="getdefaults"></a>C인쇄 대화상자::GetDefaults

대화 상자를 표시하지 않고 기본 프린터의 장치 기본값을 검색합니다.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

검색된 값은 구조에 `m_pd` 배치됩니다.

경우에 따라 이 함수에 대 한 호출은 `CPrintDialog` *bPrintSetupOnly* FALSE로 설정 된 [생성자](#cprintdialog) 호출 합니다. 이러한 경우 프린터 DC `hDevNames` `hDevMode` `m_pd` 및(데이터 멤버에 있는 두 개의 핸들)이 자동으로 할당됩니다.

에 대 한 `CPrintDialog` 생성자가 호출 된 경우 *bPrintSetupOnly* SET `hDevNames` FALSE, 이 함수뿐만 아니라 반환 하 `hDevMode` 고 에 `m_pd.hDC` `m_pd.hDevNames` 위치 하 `m_pd.hDevMode`고 ) 호출자에게, 하지만 또한 프린터 DC를 반환 합니다. 개체를 완료하면 프린터 DC를 삭제하고 핸들의 Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) 함수를 호출하는 것은 `CPrintDialog` 호출자의 책임입니다.

### <a name="example"></a>예제

이 코드 조각은 기본 프린터의 장치 컨텍스트를 얻고 인치당 점으로 프린터의 해상도를 사용자에게 보고합니다. 프린터 기능의 이 특성을 DPI라고도 합니다.

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

## <a name="cprintdialoggetdevicename"></a><a name="getdevicename"></a>C프린트디아로그::GetDeviceName

현재 선택한 프린터 장치의 이름을 검색합니다.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Return Value

현재 선택한 프린터의 이름입니다.

### <a name="remarks"></a>설명

[DoModal을](#domodal) 호출하여 현재 선택한 프린터의 이름을 검색하거나 [GetDefaults를](#getdefaults) 호출한 후 기본 프린터의 현재 장치 기본값을 검색한 후 이 함수를 호출합니다. [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)에 `GetDeviceName` 대한 호출의 `lpszDeviceName` 값으로 반환되는 `CString` 개체에 대한 포인터를 사용합니다.

### <a name="example"></a>예제

이 코드 조각에는 사용자의 기본 프린터 이름과 연결된 포트와 프린터가 사용하는 스풀러 이름이 표시됩니다. 예를 들어 이 코드에는 "기본 프린터는 winspool을 사용하여 \\\server\share의 HP LaserJet IIIP입니다."라는 메시지 상자가 표시될 수 있습니다.

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

## <a name="cprintdialoggetdevmode"></a><a name="getdevmode"></a>C프린트디아로그::겟데브모드

구조를 검색합니다. `DEVMODE`

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Return Value

인쇄 드라이버의 장치 초기화 및 환경에 대한 정보가 포함된 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 데이터 구조입니다. Windows SDK에 설명된 Windows [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) 기능을 통해 이 구조에서 가져온 메모리의 잠금을 해제해야 합니다.

### <a name="remarks"></a>설명

[DoModal](#domodal) 또는 [GetDefaults를](#getdefaults) 호출한 후 이 함수를 호출하여 인쇄 장치에 대한 정보를 검색합니다.

### <a name="example"></a>예제

  [CPrintDialog::PrintCollate에](#printcollate)대한 예제를 참조하십시오.

## <a name="cprintdialoggetdrivername"></a><a name="getdrivername"></a>C인쇄디아로그::GetDriverName

현재 선택한 프린터 드라이버의 이름을 검색합니다.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Return Value

시스템 `CString` 정의 드라이버 이름을 지정하는 A입니다.

### <a name="remarks"></a>설명

[DoModal](#domodal) 또는 [GetDefaults를](#getdefaults) 호출한 후 이 함수를 호출하여 시스템 정의 프린터 장치 드라이버의 이름을 검색합니다. [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)에 `GetDriverName` 대한 호출의 `lpszDriverName` 값으로 반환되는 `CString` 개체에 대한 포인터를 사용합니다.

### <a name="example"></a>예제

  [CPrintDialog::GetDeviceName에](#getdevicename)대한 예제를 참조하십시오.

## <a name="cprintdialoggetfrompage"></a><a name="getfrompage"></a>C인쇄대화상자::GetFromPage

인쇄 범위의 시작 페이지를 검색합니다.

```
int GetFromPage() const;
```

### <a name="return-value"></a>Return Value

인쇄할 페이지 범위의 시작 페이지 번호입니다.

### <a name="remarks"></a>설명

인쇄할 페이지 `DoModal` 범위의 시작 페이지 번호를 검색하려면 호출 후 이 함수를 호출합니다.

### <a name="example"></a>예제

  [CPrintDialog::m_pd](#m_pd)에 대한 예제를 참조하십시오.

## <a name="cprintdialoggetportname"></a><a name="getportname"></a>C프린트디아로그::겟포트네임

현재 선택한 프린터 포트의 이름을 검색합니다.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Return Value

현재 선택된 프린터 포트의 이름입니다.

### <a name="remarks"></a>설명

[DoModal](#domodal) 또는 [GetDefaults를](#getdefaults) 호출한 후 이 함수를 호출하여 현재 선택한 프린터 포트의 이름을 검색합니다.

### <a name="example"></a>예제

  [CPrintDialog::GetDeviceName에](#getdevicename)대한 예제를 참조하십시오.

## <a name="cprintdialoggetprinterdc"></a><a name="getprinterdc"></a>C프린트디아로그::겟프린터DC

프린터 장치 컨텍스트에 대한 핸들을 검색합니다.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Return Value

성공한 경우 프린터 장치 컨텍스트에 대한 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

생성자의 *bPrintSetupOnly* 매개 변수가 FALSE인 경우(인쇄 대화 상자가 표시되었음을 나타내는) 프린터 장치 컨텍스트에 핸들을 `GetPrinterDC` `CPrintDialog` Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) 함수를 호출하여 사용이 완료되면 장치 컨텍스트를 삭제해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

## <a name="cprintdialoggettopage"></a><a name="gettopage"></a>C인쇄대화상자::GetToPage

인쇄 범위의 끝 페이지를 검색합니다.

```
int GetToPage() const;
```

### <a name="return-value"></a>Return Value

인쇄할 페이지 범위의 끝 페이지 번호입니다.

### <a name="remarks"></a>설명

인쇄할 페이지 `DoModal` 범위의 끝 페이지 번호를 검색하려면 호출 후 이 함수를 호출합니다.

### <a name="example"></a>예제

  [CPrintDialog::m_pd](#m_pd)에 대한 예제를 참조하십시오.

## <a name="cprintdialogm_pd"></a><a name="m_pd"></a>C인쇄디아로그::m_pd

멤버가 대화 상자 개체의 특성을 저장하는 구조체입니다.

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>설명

개체를 생성한 `CPrintDialog` 후 `m_pd` [DoModal](#domodal) 멤버 함수를 호출하기 전에 대화 상자의 다양한 측면을 설정하는 데 사용할 수 있습니다. `m_pd` 구조에 대한 자세한 내용은 Windows SDK의 [PRINTDLG를](/windows/win32/api/commdlg/ns-commdlg-printdlga) 참조하십시오.

데이터 멤버를 `m_pd` 직접 수정하는 경우 기본 동작을 재정의합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

## <a name="cprintdialogprintall"></a><a name="printall"></a>C프린트디아로그::P모든

문서의 모든 페이지를 인쇄할지 여부를 결정합니다.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Return Value

문서의 모든 페이지를 인쇄할 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

호출 `DoModal` 후 이 함수를 호출하여 문서의 모든 페이지를 인쇄할지 여부를 결정합니다.

### <a name="example"></a>예제

  [CPrintDialog::m_pd](#m_pd)에 대한 예제를 참조하십시오.

## <a name="cprintdialogprintcollate"></a><a name="printcollate"></a>C프린트디아로그::P린트콜라테

대조된 복사본이 요청되는지 여부를 결정합니다.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Return Value

사용자가 대화 상자에서 대조 확인란을 선택하면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

호출 `DoModal` 후 이 함수를 호출하여 프린터가 문서의 인쇄된 모든 복사본을 대조해야 하는지 여부를 결정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

## <a name="cprintdialogprintrange"></a><a name="printrange"></a>C프린트디아로그::P린트레인지

지정된 페이지 범위만 인쇄할지 여부를 결정합니다.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Return Value

문서의 페이지 범위만 인쇄할 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

호출 `DoModal` 후 이 함수를 호출하여 문서의 페이지 범위만 인쇄할지 여부를 결정합니다.

### <a name="example"></a>예제

  [CPrintDialog::m_pd](#m_pd)에 대한 예제를 참조하십시오.

## <a name="cprintdialogprintselection"></a><a name="printselection"></a>C프린트디아로그::P린트선택

현재 선택한 항목만 인쇄할지 여부를 결정합니다.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Return Value

선택한 항목만 인쇄할 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

호출 `DoModal` 후 이 함수를 호출하여 현재 선택한 항목만 인쇄할지 여부를 결정합니다.

### <a name="example"></a>예제

  [CPrintDialog::m_pd](#m_pd)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[MFC 샘플 디브룩](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C프린트정보 구조](../../mfc/reference/cprintinfo-structure.md)
