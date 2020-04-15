---
title: 콜레컨디에이치다이언 클래스
ms.date: 11/04/2016
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
ms.openlocfilehash: 6d6690b8d06df29ce9fcd323eb8724009ee3cca9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366175"
---
# <a name="coleconvertdialog-class"></a>콜레컨디에이치다이언 클래스

자세한 내용은 Windows SDK의 [OLEUICONVERT](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) 구조를 참조하십시오.

## <a name="syntax"></a>구문

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|`COleConvertDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleConvertDialog::Doconvert](#doconvert)|대화 상자에 지정된 변환을 수행합니다.|
|[콜레컨디언디언: :D오모달](#domodal)|OLE 변경 항목 대화 상자를 표시합니다.|
|[COleConvertDialog::GetClassID](#getclassid)|선택한 항목과 연결된 CLSID를 가져옵니다.|
|[COleConvertDialog::GetDraw측면](#getdrawaspect)|항목을 아이콘으로 그릴지 여부를 지정합니다.|
|[COleConvertDialog::겟이니콘메타파일](#geticonicmetafile)|이 항목의 상징적인 형식과 연결된 메타파일에 대한 핸들을 가져옵니다.|
|[COleConvert Dialog::GetselectionType](#getselectiontype)|선택한 유형의 선택 유형을 가져옵니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[COleConvertDialog::m_cv](#m_cv)|대화 상자의 동작을 제어하는 구조입니다.|

## <a name="remarks"></a>설명

> [!NOTE]
> 응용 프로그램 마법사에서 생성한 컨테이너 코드는 이 클래스를 사용합니다.

OLE 관련 대화 상자에 대한 자세한 내용은 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

## <a name="coleconvertdialogcoleconvertdialog"></a><a name="coleconvertdialog"></a>COleConvertDialog::COleConvertDialog

`COleConvertDialog` 개체만 생성합니다.

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
변환하거나 활성화할 항목을 가리킵니다.

*dwFlags*<br/>
비트별 또는 연산자를 사용하여 결합된 다음 값의 수를 포함하는 생성 플래그:

- CF_SELECTCONVERTTO 대화 상자가 호출될 때 라디오로 변환 단추가 처음에 선택되도록 지정합니다. 이것이 기본값입니다.

- CF_SELECTACTIVATEAS 대화 상자가 호출될 때 라디오 활성화 버튼이 처음에 선택되도록 지정합니다.

- CF_SETCONVERTDEFAULT `clsidConvertDefault` `m_cv` 변환 라디오 단추를 선택할 때 구조체의 구성원이 CLSID를 지정한 클래스가 클래스 목록 상자의 기본 선택으로 사용되도록 지정합니다.

- CF_SETACTIVATEDEFAULT `clsidActivateDefault` `m_cv` 활성화 라디오 단추를 선택할 때 구조체의 구성원이 CLSID를 지정한 클래스가 클래스 목록 상자의 기본 선택으로 사용되도록 지정합니다.

- CF_SHOWHELPBUTTON 대화 상자가 호출될 때 도움말 버튼이 표시되도록 지정합니다.

*pClassID*<br/>
변환하거나 활성화할 항목의 CLSID를 가리킵니다. NULL이면 *pItem과* 연결된 CLSID가 사용됩니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 부모 `CWnd`또는 소유자 창 개체(형식)를 가리킵니다. NULL인 경우 대화 상자의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

### <a name="remarks"></a>설명

대화 상자를 표시하려면 [DoModal](#domodal) 함수를 호출합니다.

자세한 내용은 [CLSID 키](/windows/win32/com/clsid-key-hklm) 및 [OLEUICONVERT](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) 구조를 참조하십시오.

## <a name="coleconvertdialogdoconvert"></a><a name="doconvert"></a>COleConvertDialog::Doconvert

[DoModal에서](#domodal)성공적으로 반환 한 후이 함수를 호출하여 [COleClientItem](../../mfc/reference/coleclientitem-class.md)형식의 개체를 변환하거나 활성화합니다.

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
변환하거나 활성화할 항목을 가리킵니다. NULL이 될 수 없습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

대화 전환 상자에서 사용자가 선택한 정보에 따라 항목이 변환되거나 활성화됩니다.

## <a name="coleconvertdialogdomodal"></a><a name="domodal"></a>콜레컨디언디언: :D오모달

이 함수를 호출하여 OLE 변환 대화 상자를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

대화 상자의 완료 상태입니다. 해당 값은

- 대화 상자가 성공적으로 표시되는 경우 IDOK입니다.

- 사용자가 대화 상자를 취소한 경우 IDCANCEL입니다.

- IDABORT 에러가 발생한 경우. IDABORT가 반환되는 경우 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 멤버 함수를 호출하여 발생한 오류 유형에 대한 자세한 정보를 얻습니다. 가능한 오류 목록은 Windows SDK의 [OleUIConvert](/windows/win32/api/oledlg/nf-oledlg-oleuiconvertw) 함수를 참조하십시오.

### <a name="remarks"></a>설명

[m_cv](#m_cv) 구조의 멤버를 설정하여 다양한 대화 상자 컨트롤을 초기화하려면 호출하기 `DoModal`전에 이 작업을 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

IDOK를 반환하는 경우 `DoModal` 다른 멤버 함수를 호출하여 사용자가 대화 상자에 입력한 설정 이나 정보를 검색할 수 있습니다.

## <a name="coleconvertdialoggetclassid"></a><a name="getclassid"></a>COleConvertDialog::GetClassID

변환 대화 상자에서 선택한 항목과 연결된 CLSID를 얻으려면 이 함수를 호출합니다.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Return Value

변환 대화 상자에서 선택된 항목과 연결된 CLSID입니다.

### <a name="remarks"></a>설명

[DoModalIDOK를](#domodal) 반환한 후에만 이 함수를 호출합니다.

자세한 내용은 Windows SDK의 [CLSID 키를](/windows/win32/com/clsid-key-hklm) 참조하십시오.

## <a name="coleconvertdialoggetdrawaspect"></a><a name="getdrawaspect"></a>COleConvertDialog::GetDraw측면

이 함수를 호출하여 선택한 항목을 아이콘으로 표시하도록 선택했는지 확인합니다.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Return Value

개체를 렌더링하는 데 필요한 메서드입니다.

- 아이콘으로 표시 확인란이 선택되지 않은 경우 DVASPECT_CONTENT 반환됨.

- 아이콘으로 표시 확인란을 선택하면 DVASPECT_ICON 반환됩니다.

### <a name="remarks"></a>설명

[DoModalIDOK를](#domodal) 반환한 후에만 이 함수를 호출합니다.

드로잉 측면에 대한 자세한 내용은 Windows SDK의 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 데이터 구조를 참조하십시오.

## <a name="coleconvertdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COleConvertDialog::겟이니콘메타파일

선택한 항목의 상징적인 측면을 포함하는 메타파일에 대한 핸들을 얻으려면 이 함수를 호출합니다.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Return Value

확인을 선택하여 대화 상자를 해제할 때 아이콘으로 표시 확인란을 선택한 경우 선택한 항목의 상징적인 측면을 포함하는 메타파일핸들입니다. 그렇지 않으면 NULL.

## <a name="coleconvertdialoggetselectiontype"></a><a name="getselectiontype"></a>COleConvert Dialog::GetselectionType

이 함수를 호출하여 변환 대화 상자에서 선택한 변환 유형을 결정합니다.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Return Value

선택 유형이 만들어집니다.

### <a name="remarks"></a>설명

반환 형식 값은 `Selection` `COleConvertDialog` 클래스에서 선언된 열거형 유형에 의해 지정됩니다.

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

이러한 값에 대한 간략한 설명은 다음과 같습니다.

- `COleConvertDialog::noConversion`대화 상자가 취소되었거나 사용자가 변환을 선택하지 않은 경우 반환됩니다. IDOK를 반환하는 경우 `COleConvertDialog::DoModal` 사용자가 이전에 선택한 아이콘과 다른 아이콘을 선택했을 수 있습니다.

- `COleConvertDialog::convertItem`라디오로 변환 단추를 선택한 경우 반환된 사용자는 변환할 다른 `DoModal` 항목을 선택하고 IDOK를 반환했습니다.

- `COleConvertDialog::activateAs`라디오 활성화 단추를 선택한 경우 반환된 경우 사용자가 활성화할 `DoModal` 다른 항목을 선택하고 IDOK를 반환했습니다.

## <a name="coleconvertdialogm_cv"></a><a name="m_cv"></a>COleConvertDialog::m_cv

변환 대화 상자의 동작을 제어하는 데 사용되는 OLEUICONVERT 형식의 구조입니다.

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>설명

이 구조의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.

자세한 내용은 Windows SDK의 [OLEUICONVERT](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) 구조를 참조하십시오.

## <a name="see-also"></a>참고 항목

[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
