---
title: COle체인지소스디월로그 클래스
ms.date: 11/04/2016
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
ms.openlocfilehash: 78da0a495de6ea951deab984550756a2d6f3e2bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321866"
---
# <a name="colechangesourcedialog-class"></a>COle체인지소스디월로그 클래스

OLE 소스 변경 대화 상자에 사용합니다.

## <a name="syntax"></a>구문

```
class COleChangeSourceDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COle체인지소스디올로그::COle체인지소스디월로그](#colechangesourcedialog)|`COleChangeSourceDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[코올체인지소스디아로그::D오모달](#domodal)|OLE 변경 소스 대화 상자를 표시합니다.|
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|전체 소스 표시 이름을 가져옵니다.|
|[COleChangeSourceDialog::GetFileName](#getfilename)|소스 이름에서 파일 이름을 가져옵니다.|
|[COle체인지소스디온로그::GetFromPrefix](#getfromprefix)|이전 소스의 접두사를 가져옵니다.|
|[COleChangeSourceDialog::GetItemName](#getitemname)|소스 이름에서 항목 이름을 가져옵니다.|
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|새 소스의 접두사를 가져옵니다.|
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|원본이 유효한지 나타냅니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[COle체인지소스디언로그::m_cs](#m_cs)|대화 상자의 동작을 제어하는 구조입니다.|

## <a name="remarks"></a>설명

이 대화 상자를 `COleChangeSourceDialog` 호출할 때 클래스의 개체를 만듭니다. `COleChangeSourceDialog` 개체를 생성한 후에는 [m_cs](#m_cs) 구조를 사용하여 대화 상자에서 컨트롤의 값 또는 상태를 초기화할 수 있습니다. 구조는 `m_cs` [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)형식입니다. 이 대화 상자 클래스 사용에 대 한 자세한 내용은 [DoModal](#domodal) 멤버 함수를 참조 하십시오.

자세한 내용은 Windows SDK의 [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 구조를 참조하십시오.

OLE 관련 대화 상자에 대한 자세한 내용은 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeSourceDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

## <a name="colechangesourcedialogcolechangesourcedialog"></a><a name="colechangesourcedialog"></a>COle체인지소스디올로그::COle체인지소스디월로그

이 함수는 `COleChangeSourceDialog` 개체를 생성합니다.

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
소스를 업데이트할 연결된 [COleClientItem에](../../mfc/reference/coleclientitem-class.md) 대한 포인터입니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 부모 `CWnd`또는 소유자 창 개체(형식)를 가리킵니다. NULL이면 대화 상자의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

### <a name="remarks"></a>설명

대화 상자를 표시하려면 [DoModal](#domodal) 함수를 호출합니다.

자세한 내용은 Windows SDK의 [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 구조 및 [올레UI체인지소스](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) 함수를 참조하십시오.

## <a name="colechangesourcedialogdomodal"></a><a name="domodal"></a>코올체인지소스디아로그::D오모달

이 함수를 호출하여 OLE 소스 변경 대화 상자를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

대화 상자의 완료 상태입니다. 해당 값은

- 대화 상자가 성공적으로 표시되는 경우 IDOK입니다.

- 사용자가 대화 상자를 취소한 경우 IDCANCEL입니다.

- IDABORT 에러가 발생한 경우. IDABORT가 반환되는 경우 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 멤버 함수를 호출하여 발생한 오류 유형에 대한 자세한 정보를 얻습니다. 가능한 오류 목록은 Windows SDK의 [OleUIChangeSource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) 함수를 참조하십시오.

### <a name="remarks"></a>설명

[m_cs](#m_cs) 구조의 멤버를 설정하여 다양한 대화 상자 컨트롤을 초기화하려면 호출하기 `DoModal`전에 이 작업을 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

IDOK를 반환하는 경우 `DoModal` 멤버 함수를 호출하여 대화 상자에서 사용자 입력 설정 또는 정보를 검색할 수 있습니다. 다음 목록은 일반적인 쿼리 함수의 이름을 지정합니다.

- [GetFileName](#getfilename)

- [GetDisplayName](#getdisplayname)

- [GetItemName](#getitemname)

## <a name="colechangesourcedialoggetdisplayname"></a><a name="getdisplayname"></a>COle체인지소스디월로그::GetDisplayName

이 함수를 호출하여 연결된 클라이언트 항목의 전체 표시 이름을 검색합니다.

```
CString GetDisplayName();
```

### <a name="return-value"></a>Return Value

생성자에서 지정된 [COleClientItem의](../../mfc/reference/coleclientitem-class.md) 전체 소스 표시 이름(모니커)입니다.

## <a name="colechangesourcedialoggetfilename"></a><a name="getfilename"></a>COleChange소스대화상자::GetFileName

이 함수를 호출하여 연결된 클라이언트 항목에 대한 표시 이름의 파일 모니커 부분을 검색합니다.

```
CString GetFileName();
```

### <a name="return-value"></a>Return Value

생성자에서 지정된 [COleClientItem에](../../mfc/reference/coleclientitem-class.md) 대한 소스 표시 이름의 파일 모니커 부분입니다.

### <a name="remarks"></a>설명

파일 모니커는 항목 모니커와 함께 전체 표시 이름을 지정합니다.

## <a name="colechangesourcedialoggetfromprefix"></a><a name="getfromprefix"></a>COle체인지소스디온로그::GetFromPrefix

이 함수를 호출하여 소스에 대한 이전 접두사 문자열을 가져옵니다.

```
CString GetFromPrefix();
```

### <a name="return-value"></a>Return Value

원본의 이전 접두사 문자열입니다.

### <a name="remarks"></a>설명

[DoModalIDOK를](#domodal) 반환한 후에만 이 함수를 호출합니다.

이 값은 `lpszFrom` [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 구조의 멤버에서 직접 발생합니다.

자세한 내용은 Windows SDK의 [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 구조를 참조하십시오.

## <a name="colechangesourcedialoggetitemname"></a><a name="getitemname"></a>COleChange소스대화상자::GetItemName

이 함수를 호출하여 연결된 클라이언트 항목에 대한 표시 이름의 항목 모니커 부분을 검색합니다.

```
CString GetItemName();
```

### <a name="return-value"></a>Return Value

생성자에서 지정된 [COleClientItem에](../../mfc/reference/coleclientitem-class.md) 대한 소스 표시 이름의 항목 모니커 부분입니다.

### <a name="remarks"></a>설명

파일 모니커는 항목 모니커와 함께 전체 표시 이름을 지정합니다.

## <a name="colechangesourcedialoggettoprefix"></a><a name="gettoprefix"></a>COle체인지소스디월로그::겟토프리픽스

이 함수를 호출하여 소스에 대한 새 접두사 문자열을 가져옵니다.

```
CString GetToPrefix();
```

### <a name="return-value"></a>Return Value

소스의 새 접두사 문자열입니다.

### <a name="remarks"></a>설명

[DoModalIDOK를](#domodal) 반환한 후에만 이 함수를 호출합니다.

이 값은 `lpszTo` [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 구조의 멤버에서 직접 발생합니다.

자세한 내용은 Windows SDK의 [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 구조를 참조하십시오.

## <a name="colechangesourcedialogm_cs"></a><a name="m_cs"></a>COle체인지소스디언로그::m_cs

이 데이터 멤버는 [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)형식의 구조입니다.

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>설명

`OLEUICHANGESOURCE`은 OLE 변경 소스 대화 상자의 동작을 제어하는 데 사용됩니다. 이 구조의 멤버는 직접 수정할 수 있습니다.

자세한 내용은 Windows SDK의 [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 구조를 참조하십시오.

## <a name="colechangesourcedialogisvalidsource"></a><a name="isvalidsource"></a>COle체인지소스대화상자::유효소스

이 함수를 호출하여 새 소스가 유효한지 확인합니다.

```
BOOL IsValidSource();
```

### <a name="return-value"></a>Return Value

새 소스가 유효한 경우 0이 아닌 0입니다.

### <a name="remarks"></a>설명

[DoModalIDOK를](#domodal) 반환한 후에만 이 함수를 호출합니다.

자세한 내용은 Windows SDK의 [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) 구조를 참조하십시오.

## <a name="see-also"></a>참고 항목

[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
