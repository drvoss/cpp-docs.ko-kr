---
title: COle인서삽입디아로그 클래스
ms.date: 11/04/2016
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
ms.openlocfilehash: b5de4ff5daa80e1d8727444a4cfd275597e18c08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374967"
---
# <a name="coleinsertdialog-class"></a>COle인서삽입디아로그 클래스

OLE 개체 삽입 대화 상자에 사용합니다.

## <a name="syntax"></a>구문

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COle인서열디온::COle인서열](#coleinsertdialog)|`COleInsertDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleInsertDialog::CreateItem](#createitem)|대화 상자에서 선택한 항목을 만듭니다.|
|[COleInsertDialog::DoModal](#domodal)|OLE 객체 삽입 대화 상자를 표시합니다.|
|[COleInsertDialog::GetClassID](#getclassid)|선택한 항목과 연결된 CLSID를 가져옵니다.|
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|항목을 아이콘으로 그릴지 여부를 알려줍니다.|
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|이 항목의 상징적인 형식과 연결된 메타파일에 대한 핸들을 가져옵니다.|
|[COleInsertDialog::GetPathName](#getpathname)|대화 상자에서 선택한 파일에 대한 전체 경로를 가져옵니다.|
|[COleInsertDialog::GetSelectionType](#getselectiontype)|선택한 개체의 형식을 가져옵니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[COleInsertDialog::m_io](#m_io)|대화 상자의 동작을 제어하는 OLEUIINSERTOBJECT 형식의 구조입니다.|

## <a name="remarks"></a>설명

이 대화 상자를 `COleInsertDialog` 호출할 때 클래스의 개체를 만듭니다. `COleInsertDialog` 개체를 생성한 후에는 [m_io](#m_io) 구조를 사용하여 대화 상자에서 컨트롤의 값 또는 상태를 초기화할 수 있습니다. 구조는 `m_io` OLEUIINSERTOBJECT 형식입니다. 이 대화 상자 클래스 사용에 대 한 자세한 내용은 [DoModal](#domodal) 멤버 함수를 참조 하십시오.

> [!NOTE]
> 응용 프로그램 마법사에서 생성한 컨테이너 코드는 이 클래스를 사용합니다.

자세한 내용은 Windows SDK의 [OLEUIINSERTOBJECT](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) 구조를 참조하십시오.

OLE 관련 대화 상자에 대한 자세한 내용은 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

## <a name="coleinsertdialogcoleinsertdialog"></a><a name="coleinsertdialog"></a>COle인서열디온::COle인서열

이 함수는 `COleInsertDialog` 개체만 생성합니다.

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
비트wise-OR 연산자를 사용하여 결합할 다음 값의 수를 포함 하는 만들기 플래그:

- IOF_SHOWHELP 대화 상자가 호출될 때 도움말 버튼이 표시되도록 지정합니다.

- IOF_SELECTCREATENEW 대화 상자가 호출될 때 새 라디오 만들기 버튼이 처음에 선택되도록 지정합니다. 기본값이며 IOF_SELECTCREATEFROMFILE 함께 사용할 수 없습니다.

- IOF_SELECTCREATEFROMFILE 대화 상자가 호출될 때 파일에서 만들기 라디오 단추를 처음에 선택되도록 지정합니다. IOF_SELECTCREATENEW 함께 사용할 수 없습니다.

- IOF_CHECKLINK 대화 상자가 호출될 때 처음에 링크 확인란이 선택되도록 지정합니다.

- IOF_DISABLELINK 대화 상자가 호출될 때 링크 확인란을 사용하지 않도록 설정하지 않도록 지정합니다.

- IOF_CHECKDISPLAYASICON 아이콘으로 표시 확인란이 처음에 선택되고 현재 아이콘이 표시되며 대화 상자가 호출될 때 아이콘 변경 버튼이 활성화되도록 지정합니다.

- IOF_VERIFYSERVERSEXIST 대화 상자가 표시되기 전에 등록 데이터베이스에 지정된 서버가 있는지 확인하여 목록 상자에 추가하는 클래스의 유효성을 검사하도록 지정합니다. 이 플래그를 설정하면 성능이 크게 저하될 수 있습니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 부모 `CWnd`또는 소유자 창 개체(형식)를 가리킵니다. NULL인 경우 대화 상자 개체의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

### <a name="remarks"></a>설명

대화 상자를 표시하려면 [DoModal](#domodal) 함수를 호출합니다.

## <a name="coleinsertdialogcreateitem"></a><a name="createitem"></a>COle인서열디아로그::만들기항목

[DoModalIDOK를](#domodal) 반환 하는 경우에 만 형식 [COleClientItem의](../../mfc/reference/coleclientitem-class.md) 개체를 만들려면이 함수를 호출 합니다.

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
작성할 항목을 가리킵니다.

### <a name="return-value"></a>Return Value

항목이 생성된 경우 영하지 않습니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수를 `COleClientItem` 호출하려면 먼저 개체를 할당해야 합니다.

## <a name="coleinsertdialogdomodal"></a><a name="domodal"></a>콜레인서인디아그::D오모달

이 함수를 호출하여 OLE 개체 삽입 대화 상자를 표시합니다.

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
해당 값은

`COleInsertDialog::DocObjectsOnly`DocObjects만 삽입합니다.

`COleInsertDialog::ControlsOnly`ActiveX 컨트롤만 삽입합니다.

0은 DocObject나 ActiveX 컨트롤을 삽입하지 않습니다. 이 값은 위에 나열된 첫 번째 프로토타입과 동일한 구현을 초래합니다.

### <a name="return-value"></a>Return Value

대화 상자의 완료 상태입니다. 해당 값은

- 대화 상자가 성공적으로 표시되는 경우 IDOK입니다.

- 사용자가 대화 상자를 취소한 경우 IDCANCEL입니다.

- IDABORT 에러가 발생한 경우. IDABORT가 반환되는 경우 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 멤버 함수를 호출하여 발생한 오류 유형에 대한 자세한 정보를 얻습니다. 가능한 오류 목록은 Windows SDK의 [OleUIInsertObject](/windows/win32/api/oledlg/nf-oledlg-oleuiinsertobjectw) 함수를 참조하십시오.

### <a name="remarks"></a>설명

[m_io](#m_io) 구조체의 멤버를 설정하여 다양한 대화 상자 컨트롤을 초기화하려면 호출하기 `DoModal`전에 이 작업을 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

IDOK를 반환하는 경우 `DoModal` 다른 멤버 함수를 호출하여 사용자가 대화 상자에 입력한 설정 또는 정보를 검색할 수 있습니다.

## <a name="coleinsertdialoggetclassid"></a><a name="getclassid"></a>COle인서트디아로그::겟클래스ID

[DoModal이](#domodal) IDOK를 반환하고 선택 유형이 있는 경우에만 선택한 항목과 `COleInsertDialog::createNewItem`연결된 CLSID를 얻으려면 이 함수를 호출합니다.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Return Value

선택한 항목과 연결된 CLSID를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [CLSID 키를](/windows/win32/com/clsid-key-hklm) 참조하십시오.

## <a name="coleinsertdialoggetdrawaspect"></a><a name="getdrawaspect"></a>COle인서열디아로그::GetDraw측면

이 함수를 호출하여 선택한 항목을 아이콘으로 표시하도록 선택한 지 확인합니다.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Return Value

개체를 렌더링하는 데 필요한 메서드입니다.

- 아이콘으로 표시 확인란이 선택되지 않은 경우 DVASPECT_CONTENT 반환됨.

- 아이콘으로 표시 확인란을 선택하면 DVASPECT_ICON 반환됩니다.

### <a name="remarks"></a>설명

[DoModalIDOK를](#domodal) 반환 하는 경우에이 함수를 호출 합니다.

드로잉 측면에 대한 자세한 내용은 Windows SDK의 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 데이터 구조를 참조하십시오.

## <a name="coleinsertdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COle인서인디아로그::겟이닉메타파일

선택한 항목의 상징적인 측면을 포함하는 메타파일에 대한 핸들을 얻으려면 이 함수를 호출합니다.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Return Value

**확인을**선택하여 대화 상자를 해제할 때 아이콘으로 표시 확인란을 선택한 경우 선택한 항목의 상징적인 측면을 포함하는 메타파일 핸들입니다. 그렇지 않으면 NULL.

## <a name="coleinsertdialoggetpathname"></a><a name="getpathname"></a>COle인서열디아로그::겟패스네임

[DoModal이](#domodal) IDOK를 반환하고 선택 유형이 없는 경우에만 선택한 파일의 `COleInsertDialog::createNewItem`전체 경로를 얻으려면 이 함수를 호출합니다.

```
CString GetPathName() const;
```

### <a name="return-value"></a>Return Value

대화 상자에서 선택한 파일의 전체 경로입니다. 선택 유형이 `createNewItem`있는 경우 이 함수는 릴리스 모드에서 의미가 없는 `CString` 함수를 반환하거나 디버그 모드에서 어설션을 일으킵니다.

## <a name="coleinsertdialoggetselectiontype"></a><a name="getselectiontype"></a>COle인서열::GetselectionType

이 함수를 호출하여 **확인을**선택하여 개체 삽입 대화 상자를 해제할 때 선택 유형을 선택합니다.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Return Value

선택 유형이 만들어집니다.

### <a name="remarks"></a>설명

반환 형식 값은 `Selection` `COleInsertDialog` 클래스에서 선언된 열거형 유형에 의해 지정됩니다.

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

이러한 값에 대한 간략한 설명은 다음과 같습니다.

- `COleInsertDialog::createNewItem`새 라디오 만들기 버튼이 선택되었습니다.

- `COleInsertDialog::insertFromFile`파일에서 전송하기 라디오 만들기 단추를 선택하고 링크 확인란을 선택하지 않았습니다.

- `COleInsertDialog::linkToFile`파일에서 전송하기 라디오 만들기 단추를 선택하고 링크 확인란을 선택했습니다.

## <a name="coleinsertdialogm_io"></a><a name="m_io"></a>콜레인서삽입디아로그::m_io

개체 삽입 대화 상자의 동작을 제어하는 데 사용되는 OLEUIINSERTOBJECT 형식의 구조입니다.

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>설명

이 구조의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.

자세한 내용은 Windows SDK의 [OLEUIINSERTOBJECT](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) 구조를 참조하십시오.

## <a name="see-also"></a>참고 항목

[MFC 샘플 클라이언트](../../overview/visual-cpp-samples.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
