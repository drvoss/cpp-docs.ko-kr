---
title: CPrintDialogEx 클래스
ms.date: 11/04/2016
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
ms.openlocfilehash: 52e992cf021a592198daeddf0a4321fcea487f72
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364035"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx 클래스

Windows Print 속성 시트에서 제공하는 서비스를 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C프린트디아로그::C프린트디아로그](#cprintdialogex)|`CPrintDialogEx` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C프린트디아로그::프린터 만들기](#createprinterdc)|인쇄 대화 상자를 표시하지 않고 프린터 장치 컨텍스트를 만듭니다.|
|[C프린트디아로그엑스::D오모달](#domodal)|대화 상자를 표시하고 사용자가 선택할 수 있습니다.|
|[C프린트디아로그::GetCopys](#getcopies)|요청된 복사본 수를 검색합니다.|
|[C프린트디아로그::Getdefaults](#getdefaults)|대화 상자를 표시하지 않고 장치 기본값을 검색합니다.|
|[C프린트디아로그::GetDeviceName](#getdevicename)|현재 선택한 프린터 장치의 이름을 검색합니다.|
|[C프린트디아로그::겟데브모드](#getdevmode)|구조를 검색합니다. `DEVMODE`|
|[CPrintDialogEx::GetDriverName](#getdrivername)|시스템 정의 프린터 장치 드라이버의 이름을 검색합니다.|
|[C프린트디아로그::겟포트네임](#getportname)|현재 선택한 프린터 포트의 이름을 검색합니다.|
|[C프린트디아로그::겟프린터DC](#getprinterdc)|프린터 장치 컨텍스트에 대한 핸들을 검색합니다.|
|[C프린트디아로그::P모두](#printall)|문서의 모든 페이지를 인쇄할지 여부를 결정합니다.|
|[C프린트디아로그::P린트콜라테](#printcollate)|대조된 복사본이 요청되는지 여부를 결정합니다.|
|[C프린트디아로그::P음저변페이지](#printcurrentpage)|문서의 현재 페이지를 인쇄할지 여부를 결정합니다.|
|[C프린트디아로그::P린트레인지](#printrange)|지정된 페이지 범위만 인쇄할지 여부를 결정합니다.|
|[C프린트디아로그::P헹구선택](#printselection)|현재 선택한 항목만 인쇄할지 여부를 결정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C프린트디아로그::m_pdex](#m_pdex)|개체를 사용자 지정하는 `CPrintDialogEx` 데 사용되는 구조입니다.|

## <a name="remarks"></a>설명

프레임워크를 사용하여 응용 프로그램에 대한 인쇄 프로세스의 여러 측면을 처리할 수 있습니다. 인쇄 작업을 처리하기 위해 프레임 워크를 사용하는 것에 대한 자세한 내용은 [인쇄](../../mfc/printing.md)문서를 참조하십시오.

응용 프로그램이 프레임워크의 개입 없이 인쇄를 처리하도록 하려면 `CPrintDialogEx` 제공된 생성자와 함께 "있는 것처럼" 클래스를 사용하거나 사용자 `CPrintDialogEx` 고유의 대화 상자 클래스를 파생시키고 필요에 맞게 생성기를 작성할 수 있습니다. 두 경우 모두 이러한 대화 상자는 클래스에서 `CCommonDialog`파생되므로 표준 MFC 대화 상자처럼 동작합니다.

개체를 `CPrintDialogEx` 사용하려면 먼저 생성기를 `CPrintDialogEx` 사용하여 개체를 만듭니다. 대화 상자가 생성되면 [m_pdex](#m_pdex) 구조의 값을 설정하거나 수정하여 대화 상자 컨트롤의 값을 초기화할 수 있습니다. 구조는 `m_pdex` [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw)유형입니다. 이 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

`hDevMode` 및 `hDevNames` `m_pdex` 멤버에 대한 고유한 핸들을 제공하지 않는 경우 대화 상자를 `GlobalFree` 완료할 때 이러한 핸들에 대해 Windows 함수를 호출해야 합니다.

대화 상자 컨트롤을 초기화한 `DoModal` 후 멤버 함수를 호출하여 대화 상자를 표시하고 사용자가 인쇄 옵션을 선택할 수 있도록 합니다. 반환 `DoModal` 할 때 사용자가 확인, 적용 또는 취소 버튼을 선택했는지 여부를 확인할 수 있습니다.

사용자가 확인을 누르면's `CPrintDialogEx`멤버 함수를 사용하여 사용자가 입력한 정보를 검색할 수 있습니다.

`CPrintDialogEx::GetDefaults` 멤버 기능은 대화 상자를 표시하지 않고 현재 프린터 기본값을 검색하는 데 유용합니다. 이 메서드는 사용자 상호 작용이 필요하지 않습니다.

Windows `CommDlgExtendedError` 함수를 사용하여 대화 상자를 초기화하는 동안 오류가 발생했는지 확인하고 오류에 대해 자세히 알아볼 수 있습니다. 이 기능에 대한 자세한 내용은 Windows SDK를 참조하십시오.

사용에 `CPrintDialogEx`대한 자세한 내용은 [일반적인 대화 상자 클래스를](../../mfc/common-dialog-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

## <a name="cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a>C프린트디아로그::C프린트디아로그

Windows 인쇄 속성 시트를 생성합니다.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
비트OR 연산자를 사용하여 결합된 대화 상자의 설정을 사용자 지정하는 데 사용할 수 있는 하나 이상의 플래그입니다. 예를 들어 PD_ALLPAGES 플래그는 기본 인쇄 범위를 문서의 모든 페이지로 설정합니다. 이러한 플래그에 대한 자세한 내용은 Windows SDK의 [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) 구조를 참조하십시오.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 개체만 생성합니다. 멤버 `DoModal` 함수를 사용하여 대화 상자를 표시합니다.

## <a name="cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a>C프린트디아로그::프린터 만들기

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 및 [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) 구조에서 프린터 장치 컨텍스트(DC)를 만듭니다.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Return Value

새로 생성된 프린터 장치 컨텍스트를 처리합니다.

### <a name="remarks"></a>설명

반환된 DC는 [m_pdex](#m_pdex) `hDC` 멤버에도 저장됩니다.

이 DC는 현재 프린터 DC로 가정하며 이전에 가져온 다른 프린터 DC는 삭제해야 합니다. 이 함수를 호출할 수 있으며 인쇄 대화 상자를 표시하지 않고도 결과 DC를 사용할 수 있습니다.

## <a name="cprintdialogexdomodal"></a><a name="domodal"></a>C프린트디아로그엑스::D오모달

이 함수를 호출하여 Windows Print 속성 시트를 표시하고 사용자가 복사본 수, 페이지 범위 및 복사본을 대조할지 여부와 같은 다양한 인쇄 옵션을 선택할 수 있도록 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

INT_PTR 반환 값은 실제로 HRESULT입니다. Windows SDK의 [PrintDlgEx에서](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) 반환 값 섹션을 참조하십시오.

### <a name="remarks"></a>설명

`m_pdex` 구조체의 멤버를 설정하여 다양한 인쇄 대화 상자를 초기화하려면 호출하기 `DoModal`전에 이 작업을 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

호출 `DoModal`한 후 다른 멤버 함수를 호출하여 사용자가 대화 상자에 입력 한 설정 또는 정보를 검색 할 수 있습니다.

호출 `DoModal`할 때 PD_RETURNDC 플래그를 사용하는 경우 프린터 `hDC` DC는 [m_pdex](#m_pdex). 이 DC는 `CPrintDialogEx`의 호출자에 의해 [DeleteDC에](/windows/win32/api/wingdi/nf-wingdi-deletedc) 대한 호출로 해제되어야 합니다.

## <a name="cprintdialogexgetcopies"></a><a name="getcopies"></a>C프린트디아로그::GetCopys

호출 `DoModal` 후 이 함수를 호출하여 요청된 복사본 수를 검색합니다.

```
int GetCopies() const;
```

### <a name="return-value"></a>Return Value

요청한 사본 수입니다.

## <a name="cprintdialogexgetdefaults"></a><a name="getdefaults"></a>C프린트디아로그::Getdefaults

대화 상자를 표시하지 않고 기본 프린터의 장치 기본값을 검색하려면 이 함수를 호출합니다.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Return Value

TRUE 성공, 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 및 [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) 구조에서 프린터 장치 컨텍스트(DC)를 만듭니다.

`GetDefaults`속성 인쇄 시트가 표시되지 않습니다. 대신 `hDevNames` [m_pdex](#m_pdex) 멤버를 `hDevMode` 시스템 기본 프린터에 대해 초기화된 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 및 [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) 구조로 처리하도록 설정합니다. 둘 `hDevNames` `hDevMode` 다 NULL이거나 `GetDefaults` 실패해야 합니다.

PD_RETURNDC 플래그가 설정된 경우 이 함수는 `hDevNames` `hDevMode` 호출자에게 `m_pdex.hDevNames` 반환및(에 `m_pdex.hDevMode`위치) 있을 뿐만 아니라 `m_pdex.hDC`에서 프린터 DC를 반환합니다. 개체를 완료하면 프린터 DC를 삭제하고 핸들의 Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) 함수를 호출하는 것은 `CPrintDialogEx` 호출자의 책임입니다.

## <a name="cprintdialogexgetdevicename"></a><a name="getdevicename"></a>C프린트디아로그::GetDeviceName

[DoModal을](#domodal) 호출하여 현재 선택한 프린터의 이름을 검색하거나 [GetDefaults를](#getdefaults) 호출한 후 기본 프린터의 이름을 검색한 후 이 함수를 호출합니다.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Return Value

현재 선택한 프린터의 이름입니다.

### <a name="remarks"></a>설명

[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)에 `GetDeviceName` 대한 호출의 `lpszDeviceName` 값으로 반환되는 `CString` 개체에 대한 포인터를 사용합니다.

## <a name="cprintdialogexgetdevmode"></a><a name="getdevmode"></a>C프린트디아로그::겟데브모드

[DoModal](#domodal) 또는 [GetDefaults를](#getdefaults) 호출한 후 이 함수를 호출하여 인쇄 장치에 대한 정보를 검색합니다.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Return Value

인쇄 드라이버의 장치 초기화 및 환경에 대한 정보가 포함된 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 데이터 구조입니다. Windows SDK에 설명된 Windows [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) 기능을 통해 이 구조에서 가져온 메모리의 잠금을 해제해야 합니다.

## <a name="cprintdialogexgetdrivername"></a><a name="getdrivername"></a>CPrintDialogEx::GetDriverName

[DoModal](#domodal) 또는 [GetDefaults를](#getdefaults) 호출한 후 이 함수를 호출하여 시스템 정의 프린터 장치 드라이버의 이름을 검색합니다.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Return Value

시스템 `CString` 정의 드라이버 이름을 지정하는 A입니다.

### <a name="remarks"></a>설명

[CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc)호출에서 `GetDriverName` *lpszDriverName* 값으로 반환되는 `CString` 개체에 대한 포인터를 사용합니다.

## <a name="cprintdialogexgetportname"></a><a name="getportname"></a>C프린트디아로그::겟포트네임

[DoModal](#domodal) 또는 [GetDefaults를](#getdefaults) 호출한 후 이 함수를 호출하여 현재 선택한 프린터 포트의 이름을 검색합니다.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Return Value

현재 선택된 프린터 포트의 이름입니다.

## <a name="cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a>C프린트디아로그::겟프린터DC

핸들을 프린터 장치 컨텍스트에 반환합니다.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Return Value

프린터 장치 컨텍스트에 대한 핸들입니다.

### <a name="remarks"></a>설명

Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) 함수를 호출하여 사용이 완료되면 장치 컨텍스트를 삭제해야 합니다.

## <a name="cprintdialogexm_pdex"></a><a name="m_pdex"></a>C프린트디아로그::m_pdex

멤버가 대화 개체의 특성을 저장하는 PRINTDLGEX 구조입니다.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>설명

개체를 생성한 `CPrintDialogEx` 후 `m_pdex` [DoModal](#domodal) 멤버 함수를 호출하기 전에 대화 상자의 다양한 측면을 설정하는 데 사용할 수 있습니다. `m_pdex` 구조에 대한 자세한 내용은 Windows SDK의 [PRINTDLGEX를](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) 참조하십시오.

데이터 멤버를 `m_pdex` 직접 수정하는 경우 기본 동작을 재정의합니다.

## <a name="cprintdialogexprintall"></a><a name="printall"></a>C프린트디아로그::P모두

호출 `DoModal` 후 이 함수를 호출하여 문서의 모든 페이지를 인쇄할지 여부를 결정합니다.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Return Value

TRUE 문서의 모든 페이지를 인쇄해야 하는 경우 그렇지 않으면 거짓.

## <a name="cprintdialogexprintcollate"></a><a name="printcollate"></a>C프린트디아로그::P린트콜라테

호출 `DoModal` 후 이 함수를 호출하여 프린터가 문서의 인쇄된 모든 복사본을 대조해야 하는지 여부를 결정합니다.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Return Value

TRUE 사용자가 대화 상자에서 collate 확인란을 선택하는 경우; 그렇지 않으면 거짓.

## <a name="cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a>C프린트디아로그::P음저변페이지

호출 `DoModal` 후 이 함수를 호출하여 문서의 현재 페이지를 인쇄할지 여부를 결정합니다.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Return Value

TRUE 인쇄 **현재 페이지가** 인쇄 대화 상자에서 선택된 경우 그렇지 않으면 거짓.

## <a name="cprintdialogexprintrange"></a><a name="printrange"></a>C프린트디아로그::P린트레인지

호출 `DoModal` 후 이 함수를 호출하여 문서의 페이지 범위만 인쇄할지 여부를 결정합니다.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Return Value

TRUE 문서의 페이지 범위만 인쇄해야 하는 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

지정된 페이지 범위는 [m_pdex(Windows](#m_pdex) `nPageRanges` `nMaxPageRanges`SDK의 `lpPageRanges` [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) 구조 참조)에서 확인할 수 있습니다.

## <a name="cprintdialogexprintselection"></a><a name="printselection"></a>C프린트디아로그::P헹구선택

호출 `DoModal` 후 이 함수를 호출하여 현재 선택한 항목만 인쇄할지 여부를 결정합니다.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Return Value

TRUE 선택한 항목만 인쇄할 경우 그렇지 않으면 거짓.

## <a name="see-also"></a>참고 항목

[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C프린트정보 구조](../../mfc/reference/cprintinfo-structure.md)
