---
title: COleBusyDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
ms.openlocfilehash: 5be42463c08cacd83de84900fb4d98771774e897
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364250"
---
# <a name="colebusydialog-class"></a>COleBusyDialog 클래스

OLE 서버가 응답하지 않음 또는 서버가 사용 중임 대화 상자에 사용합니다.

## <a name="syntax"></a>구문

```
class COleBusyDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|`COleBusyDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleBusyDialog::DoModal](#domodal)|OLE 서버 사용 중 대화 상자가 표시됩니다.|
|[COleBusyDialog::GetSelectionType](#getselectiontype)|대화 상자에서 선택한 선택을 결정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[COleBusyDialog::m_bz](#m_bz)|대화 상자의 동작을 제어하는 OLEUIBUSY 형식의 구조입니다.|

## <a name="remarks"></a>설명

이러한 대화 상자를 `COleBusyDialog` 호출할 때 클래스의 개체를 만듭니다. `COleBusyDialog` 개체를 생성한 후에는 [m_bz](#m_bz) 구조를 사용하여 대화 상자에서 컨트롤의 값 또는 상태를 초기화할 수 있습니다. 구조는 `m_bz` OLEUIBUSY 형식입니다. 이 대화 상자 클래스 사용에 대 한 자세한 내용은 [DoModal](#domodal) 멤버 함수를 참조 하십시오.

> [!NOTE]
> 응용 프로그램 마법사에서 생성한 컨테이너 코드는 이 클래스를 사용합니다.

자세한 내용은 Windows SDK의 [OLEUIBUSY](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) 구조를 참조하십시오.

OLE 관련 대화 상자에 대한 자세한 내용은 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleBusyDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

## <a name="colebusydialogcolebusydialog"></a><a name="colebusydialog"></a>COleBusyDialog::COleBusyDialog

이 함수는 `COleBusyDialog` 개체만 생성합니다.

```
explicit COleBusyDialog(
    HTASK htaskBusy,
    BOOL bNotResponding = FALSE,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*htaskBusy*<br/>
사용 중인 서버 작업을 처리합니다.

*bNotResponding*<br/>
TRUE이면 서버 사용 중 대화 상자 대신 응답하지 않음 대화 상자로 호출합니다. 응답하지 않음 대화 상자의 문구는 서버 사용 중 대화 상자의 문구와 약간 다르며 취소 단추는 비활성화됩니다.

*dwFlags*<br/>
생성 플래그입니다. 비트-OR 연산자와 결합된 다음 값 중 0 이상을 포함할 수 있습니다.

- BZ_DISABLECANCELBUTTON 대화 상자를 호출할 때 취소 단추를 사용하지 않도록 설정합니다.

- BZ_DISABLESWITCHTOBUTTON 대화 상자를 호출할 때 스위치 전환 단추를 사용하지 않도록 설정합니다.

- BZ_DISABLERETRYBUTTON 대화 상자를 호출할 때 다시 시도 단추를 사용하지 않도록 설정합니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 부모 `CWnd`또는 소유자 창 개체(형식)를 가리킵니다. NULL인 경우 대화 상자 개체의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

### <a name="remarks"></a>설명

대화 상자를 표시하려면 [DoModal](#domodal)을 호출합니다.

자세한 내용은 Windows SDK의 [OLEUIBUSY](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) 구조를 참조하십시오.

## <a name="colebusydialogdomodal"></a><a name="domodal"></a>COleBusyDialog::DoModal

이 함수를 호출하여 OLE 서버 사용 중이거나 응답하지 않는 서버 대화 상자를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

대화 상자의 완료 상태입니다. 해당 값은

- 대화 상자가 성공적으로 표시되는 경우 IDOK입니다.

- 사용자가 대화 상자를 취소한 경우 IDCANCEL입니다.

- IDABORT 에러가 발생한 경우. IDABORT가 반환되면 멤버 `COleDialog::GetLastError` 함수를 호출하여 발생한 오류 유형에 대한 자세한 정보를 가져옵니다. 가능한 오류 목록은 Windows SDK의 [OleUIBusy](/windows/win32/api/oledlg/nf-oledlg-oleuibusyw) 함수를 참조하십시오.

### <a name="remarks"></a>설명

[m_bz](#m_bz) 구조의 멤버를 설정하여 다양한 대화 상자 컨트롤을 초기화하려면 호출하기 `DoModal`전에 이 작업을 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

IDOK를 반환하는 경우 `DoModal` 다른 멤버 함수를 호출하여 사용자가 대화 상자에 입력한 설정 이나 정보를 검색할 수 있습니다.

## <a name="colebusydialoggetselectiontype"></a><a name="getselectiontype"></a>COleBusy Dialog::GetselectionType

이 함수를 호출하여 서버 사용 중 대화 상자에서 사용자가 선택한 선택 유형을 가져옵니다.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Return Value

선택 유형이 만들어집니다.

### <a name="remarks"></a>설명

반환 형식 값은 `Selection` `COleBusyDialog` 클래스에서 선언된 열거형 유형에 의해 지정됩니다.

```
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```

이러한 값에 대한 간략한 설명은 다음과 같습니다.

- `COleBusyDialog::switchTo`스위치 버튼을 눌렀습니다.

- `COleBusyDialog::retry`재시도 버튼을 눌렀습니다.

- `COleBusyDialog::callUnblocked`이제 서버 활성화를 위한 호출이 차단 해제되었습니다.

## <a name="colebusydialogm_bz"></a><a name="m_bz"></a>COleBusyDialog::m_bz

서버 사용 중 대화 상자의 동작을 제어하는 데 사용되는 OLEUIBUSY 형식의 구조입니다.

```
OLEUIBUSY m_bz;
```

### <a name="remarks"></a>설명

이 구조의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.

자세한 내용은 Windows SDK의 [OLEUIBUSY](/windows/win32/api/oledlg/ns-oledlg-oleuibusyw) 구조를 참조하십시오.

## <a name="see-also"></a>참고 항목

[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
