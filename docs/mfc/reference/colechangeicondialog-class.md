---
title: COle체인지아이콘디아로그 클래스
ms.date: 11/04/2016
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
helpviewer_keywords:
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
ms.openlocfilehash: 6cdc0ed6bfa4765817de8b7628f339db5e7e5bf5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369632"
---
# <a name="colechangeicondialog-class"></a>COle체인지아이콘디아로그 클래스

OLE 아이콘 변경 대화 상자에 사용합니다.

## <a name="syntax"></a>구문

```
class COleChangeIconDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|`COleChangeIconDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleChangeIcon대화문::DoChangeIcon](#dochangeicon)|대화 상자에 지정된 변경 을 수행합니다.|
|[COleChangeIconDialog::DoModal](#domodal)|OLE 2 변경 아이콘 대화 상자가 표시됩니다.|
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|이 항목의 상징적인 형식과 연결된 메타파일에 대한 핸들을 가져옵니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[COleChangeIconDialog::m_ci](#m_ci)|대화 상자의 동작을 제어하는 구조입니다.|

## <a name="remarks"></a>설명

이 대화 상자를 `COleChangeIconDialog` 호출할 때 클래스의 개체를 만듭니다. `COleChangeIconDialog` 개체를 생성한 후에는 [m_ci](#m_ci) 구조를 사용하여 대화 상자에서 컨트롤의 값 또는 상태를 초기화할 수 있습니다. 구조는 `m_ci` OLEUICHANGEICON 형식입니다. 이 대화 상자 클래스 사용에 대 한 자세한 내용은 [DoModal](#domodal) 멤버 함수를 참조 하십시오.

자세한 내용은 Windows SDK의 [OLEUICHANGEICON](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) 구조를 참조하십시오.

OLE 관련 대화 상자에 대한 자세한 내용은 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeIconDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

## <a name="colechangeicondialogcolechangeicondialog"></a><a name="colechangeicondialog"></a>COle체인지아이콘디올로그::COle체인지아이콘디올로그

이 함수는 `COleChangeIconDialog` 개체만 생성합니다.

```
explicit COleChangeIconDialog(
    COleClientItem* pItem,
    DWORD dwFlags = CIF_SELECTCURRENT,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
변환할 항목을 가리킵니다.

*dwFlags*<br/>
비트별 또는 연산자를 사용하여 결합된 다음 값의 수를 포함하는 생성 플래그:

- CIF_SELECTCURRENT 대화 상자가 호출될 때 현재 라디오 단추가 처음에 선택되도록 지정합니다. 이것이 기본값입니다.

- CIF_SELECTDEFAULT 대화 상자가 호출될 때 기본 라디오 버튼이 처음에 선택되도록 지정합니다.

- CIF_SELECTFROMFILE 대화 상자가 호출될 때 파일 에서 라디오 단추를 처음에 선택되도록 지정합니다.

- CIF_SHOWHELP 대화 상자가 호출될 때 도움말 버튼이 표시되도록 지정합니다.

- CIF_USEICONEXE 아이콘이 형식에서 검색되는 대신 `szIconExe` [m_ci](#m_ci) 필드에 지정된 실행 에서 추출되어야 한다고 지정합니다. 이 기능은 OLE가 아닌 파일을 포함하거나 링크하는 데 유용합니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 부모 `CWnd`또는 소유자 창 개체(형식)를 가리킵니다. NULL이면 대화 상자의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

### <a name="remarks"></a>설명

대화 상자를 표시하려면 [DoModal](#domodal) 함수를 호출합니다.

자세한 내용은 Windows SDK의 [OLEUICHANGEICON](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) 구조를 참조하십시오.

## <a name="colechangeicondialogdochangeicon"></a><a name="dochangeicon"></a>COleChangeIcon대화문::DoChangeIcon

[DoModal이](#domodal) IDOK를 반환한 후 대화 상자에서 선택한 아이콘으로 항목을 나타내는 아이콘을 변경하려면 이 함수를 호출합니다.

```
BOOL DoChangeIcon(COleClientItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
아이콘이 변경되는 항목을 가리킵니다.

### <a name="return-value"></a>Return Value

변경이 성공하면 0이 아닙니다. 그렇지 않으면 0.

## <a name="colechangeicondialogdomodal"></a><a name="domodal"></a>COleChangeIconDialog::DoModal

이 함수를 호출하여 OLE 변경 아이콘 대화 상자를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

대화 상자의 완료 상태입니다. 해당 값은

- 대화 상자가 성공적으로 표시되는 경우 IDOK입니다.

- 사용자가 대화 상자를 취소한 경우 IDCANCEL입니다.

- IDABORT 에러가 발생한 경우. IDABORT가 반환되면 멤버 `COleDialog::GetLastError` 함수를 호출하여 발생한 오류 유형에 대한 자세한 정보를 가져옵니다. 가능한 오류 목록은 Windows SDK의 [OleUIChangeIcon](/windows/win32/api/oledlg/nf-oledlg-oleuichangeiconw) 기능을 참조하십시오.

### <a name="remarks"></a>설명

[m_ci](#m_ci) 구조의 멤버를 설정하여 다양한 대화 상자 컨트롤을 초기화하려면 호출하기 `DoModal`전에 이 작업을 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

IDOK를 반환하는 경우 `DoModal` 다른 멤버 함수를 호출하여 사용자가 대화 상자에 입력한 설정 이나 정보를 검색할 수 있습니다.

## <a name="colechangeicondialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COle체인지아이콘디아로그::겟이니마크메타파일

선택한 항목의 상징적인 측면을 포함하는 메타파일에 대한 핸들을 얻으려면 이 함수를 호출합니다.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Return Value

**확인을**선택하여 대화 상자를 해제한 경우 새 아이콘의 상징적인 측면을 포함하는 메타파일핸들; 그렇지 않으면 대화 상자가 표시되기 전의 아이콘입니다.

## <a name="colechangeicondialogm_ci"></a><a name="m_ci"></a>COle체인지아이콘디올로그::m_ci

변경 아이콘 대화 상자의 동작을 제어하는 데 사용되는 OLEUICHANGEICON 형식의 구조입니다.

```
OLEUICHANGEICON m_ci;
```

### <a name="remarks"></a>설명

이 구조의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.

자세한 내용은 Windows SDK의 [OLEUICHANGEICON](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) 구조를 참조하십시오.

## <a name="see-also"></a>참고 항목

[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
