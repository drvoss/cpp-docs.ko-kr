---
title: 콜레파페스 스페셜디아로그 클래스
ms.date: 11/04/2016
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
helpviewer_keywords:
- COlePasteSpecialDialog [MFC], COlePasteSpecialDialog
- COlePasteSpecialDialog [MFC], AddFormat
- COlePasteSpecialDialog [MFC], AddLinkEntry
- COlePasteSpecialDialog [MFC], AddStandardFormats
- COlePasteSpecialDialog [MFC], CreateItem
- COlePasteSpecialDialog [MFC], DoModal
- COlePasteSpecialDialog [MFC], GetDrawAspect
- COlePasteSpecialDialog [MFC], GetIconicMetafile
- COlePasteSpecialDialog [MFC], GetPasteIndex
- COlePasteSpecialDialog [MFC], GetSelectionType
- COlePasteSpecialDialog [MFC], m_ps
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
ms.openlocfilehash: 47fb421ef9dedcae7f92d33f55988dbbc2ea452d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753822"
---
# <a name="colepastespecialdialog-class"></a>콜레파페스 스페셜디아로그 클래스

OLE 선택하여 붙여넣기 대화 상자에 사용합니다.

## <a name="syntax"></a>구문

```
class COlePasteSpecialDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레파페스 스페셜디언로그::콜레파페스스페셜디아로그](#colepastespecialdialog)|`COlePasteSpecialDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COlePaste 스페셜 디아로그::추가 형식](#addformat)|응용 프로그램에서 붙여넣기할 수 있는 형식 목록에 사용자 지정 형식을 추가합니다.|
|[콜레파페테 스페셜디언로그::애드링크엔트리](#addlinkentry)|지원되는 클립보드 형식 목록에 새 항목을 추가합니다.|
|[COlePaste 스페셜 디올로그::추가 표준 형식](#addstandardformats)|응용 프로그램에서 붙여넣기할 수 있는 형식 목록에 CF_BITMAP, CF_DIB, CF_METAFILEPICT 및 선택적으로 CF_LINKSOURCE 추가합니다.|
|[콜레파페테 스페셜 디월로그::만들기항목](#createitem)|지정된 형식을 사용하여 컨테이너 문서에서 항목을 만듭니다.|
|[콜레파페테스페셜디아로그::D오모달](#domodal)|OLE 붙여넣기 특별 대화 상자를 표시합니다.|
|[콜레파페테 스페셜디언로그::GetDraw측면](#getdrawaspect)|항목을 아이콘으로 그릴지 여부를 알려줍니다.|
|[콜레파페테 스페셜디아로그::겟이닉메타파일](#geticonicmetafile)|이 항목의 상징적인 형식과 연결된 메타파일에 대한 핸들을 가져옵니다.|
|[콜레파페테 스페셜디언로그::겟페이스트인덱스](#getpasteindex)|사용자가 선택한 사용 가능한 붙여넣기 옵션의 인덱스를 가져옵니다.|
|[콜레파페테 스페셜 디월로그::GetselectionType](#getselectiontype)|선택한 유형의 선택 유형을 가져옵니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[콜레파페테스페셜디아로그::m_ps](#m_ps)|대화 상자의 기능을 제어하는 OLEUIPASTESPECIAL 형식의 구조입니다.|

## <a name="remarks"></a>설명

이 대화 상자를 `COlePasteSpecialDialog` 호출할 때 클래스의 개체를 만듭니다. 개체를 `COlePasteSpecialDialog` 생성한 후 [AddFormat](#addformat) 및 [AddStandardFormat 멤버 함수를](#addstandardformats) 사용하여 대화 상자에 클립보드 형식을 추가할 수 있습니다. [m_ps](#m_ps) 구조를 사용하여 대화 상자에서 컨트롤의 값이나 상태를 초기화할 수도 있습니다. 구조는 `m_ps` 올레우이파스에스페셜 타입입니다.

자세한 내용은 Windows SDK의 [OLEUIPASTESPECIAL](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw) 구조를 참조하십시오.

OLE 관련 대화 상자에 대한 자세한 내용은 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePasteSpecialDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

## <a name="colepastespecialdialogaddformat"></a><a name="addformat"></a>COlePaste 스페셜 디아로그::추가 형식

이 함수를 호출하여 붙여넣기 특수 작업에서 응용 프로그램에서 지원할 수 있는 형식 목록에 새 형식을 추가합니다.

```cpp
void AddFormat(
    const FORMATETC& formatEtc,
    LPTSTR lpszFormat,
    LPTSTR lpszResult,
    DWORD flags);

void AddFormat(
    UINT cf,
    DWORD tymed,
    UINT nFormatID,
    BOOL bEnableIcon,
    BOOL bLink);
```

### <a name="parameters"></a>매개 변수

*Fmt*<br/>
추가할 데이터 형식에 대한 참조입니다.

*lpszFormat*<br/>
사용자에게 형식을 설명하는 문자열입니다.

*lpsz결과*<br/>
대화 상자에서 이 형식을 선택한 경우 결과를 설명하는 문자열입니다.

*플래그*<br/>
이 형식에 사용할 수 있는 다른 연결 및 포함 옵션입니다. 이 플래그는 OLEUIPASTEFLAG 활성화 된 형식에서 하나 이상의 서로 다른 값의 비트 조합입니다.

*Cf*<br/>
추가할 클립보드 형식입니다.

*타이드*<br/>
이 형식으로 사용할 수 있는 미디어 유형입니다. 이는 TYMED 수거된 형식의 하나 이상의 값을 약간 조합한 것입니다.

*nFormatID*<br/>
이 형식을 식별하는 문자열의 ID입니다. 이 문자열의 형식은 '\n' 문자로 구분된 두 개의 별도 문자열입니다. 첫 번째 문자열은 *lpstrFormat* 매개 변수에서 전달되는 문자열과 동일하며 두 번째 문자열은 *lpstrResult* 매개 변수와 동일합니다.

*bEnableIcon*<br/>
목록 상자에서 이 형식을 선택할 때 아이콘으로 표시 확인란이 활성화되어 있는지 여부를 결정하는 플래그입니다.

*깜박*<br/>
목록 상자에서 이 형식을 선택할 때 붙여넣기 링크 라디오 버튼이 활성화되어 있는지 여부를 결정하는 플래그입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 응용 프로그램이 시스템에 등록한 CF_TEXT 또는 CF_TIFF 또는 사용자 지정 형식과 같은 표준 형식을 추가할 수 있습니다. 응용 프로그램에 데이터 개체를 붙여넣는 방법에 대한 자세한 내용은 [데이터 개체 및 데이터 원본: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)문서를 참조하십시오.

자세한 내용은 Windows SDK의 [TYMED](/windows/win32/api/objidl/ne-objidl-tymed) 열거 형 및 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 참조하십시오.

자세한 내용은 Windows SDK의 [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) 활성화 된 형식을 참조하십시오.

## <a name="colepastespecialdialogaddlinkentry"></a><a name="addlinkentry"></a>콜레파페테 스페셜디언로그::애드링크엔트리

지원되는 클립보드 형식 목록에 새 항목을 추가합니다.

```
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```

### <a name="parameters"></a>매개 변수

*Cf*<br/>
추가할 클립보드 형식입니다.

### <a name="return-value"></a>Return Value

새 링크 항목에 대한 정보를 포함하는 [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) 구조입니다.

## <a name="colepastespecialdialogaddstandardformats"></a><a name="addstandardformats"></a>COlePaste 스페셜 디올로그::추가 표준 형식

이 함수를 호출하여 응용 프로그램이 붙여넣기 특수 작업에서 지원할 수 있는 형식 목록에 다음 클립보드 형식을 추가합니다.

```cpp
void AddStandardFormats(BOOL bEnableLink = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnableLink*<br/>
응용 프로그램에서 붙여넣기할 수 있는 형식 목록에 CF_LINKSOURCE 추가할지 여부를 결정하는 플래그입니다.

### <a name="remarks"></a>설명

- CF_BITMAP

- CF_DIB

- CF_METAFILEPICT

- **"임베디드 오브젝트"**

- (선택 사항) **"링크 소스"**

이러한 형식은 포함 및 연결을 지원하는 데 사용됩니다.

## <a name="colepastespecialdialogcolepastespecialdialog"></a><a name="colepastespecialdialog"></a>콜레파페스 스페셜디언로그::콜레파페스스페셜디아로그

`COlePasteSpecialDialog` 개체를 생성합니다.

```
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,
    COleDataObject* pDataObject = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
생성 플래그는 비트와이즈-OR 연산을 사용하여 결합된 다음 플래그의 수를 포함합니다.

- PSF_SELECTPASTE 대화 상자가 호출될 때 처음에 붙여넣기 라디오 단추가 선택되도록 지정합니다. PSF_SELECTPASTELINK 함께 사용할 수 없습니다. 이것이 기본값입니다.

- PSF_SELECTPASTELINK 대화 상자가 호출될 때 붙여넣기 링크 라디오 단추가 처음에 선택되도록 지정합니다. PSF_SELECTPASTE 함께 사용할 수 없습니다.

- PSF_CHECKDISPLAYASICON 대화 상자가 호출될 때 아이콘으로 표시 확인란이 처음에 선택되도록 지정합니다.

- PSF_SHOWHELP 대화 상자가 호출될 때 도움말 버튼이 표시되도록 지정합니다.

*pDataObject*<br/>
붙여넣기를 위해 [COleDataObject를](../../mfc/reference/coledataobject-class.md) 가리킵니다. 이 값이 NULL이면 클립보드에서 을 `COleDataObject` 가져옵니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 부모 `CWnd`또는 소유자 창 개체(형식)를 가리킵니다. NULL인 경우 대화 상자의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

### <a name="remarks"></a>설명

이 함수는 `COlePasteSpecialDialog` 개체만 생성합니다. 대화 상자를 표시하려면 [DoModal](#domodal) 함수를 호출합니다.

자세한 내용은 Windows SDK의 [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) 활성화 된 형식을 참조하십시오.

## <a name="colepastespecialdialogcreateitem"></a><a name="createitem"></a>콜레파페테 스페셜 디월로그::만들기항목

특수 대화 상자에서 선택한 새 항목을 만듭니다.

```
BOOL CreateItem(COleClientItem* pNewItem);
```

### <a name="parameters"></a>매개 변수

*pNewItem*<br/>
인스턴스를 `COleClientItem` 가리킵니다. NULL이 될 수 없습니다.

### <a name="return-value"></a>Return Value

항목이 성공적으로 생성된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 [DoModal이](#domodal) IDOK를 반환한 후에만 호출되어야 합니다.

## <a name="colepastespecialdialogdomodal"></a><a name="domodal"></a>콜레파페테스페셜디아로그::D오모달

OLE 붙여넣기 특별 대화 상자를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

대화 상자의 완료 상태입니다. 해당 값은

- 대화 상자가 성공적으로 표시되는 경우 IDOK입니다.

- 사용자가 대화 상자를 취소한 경우 IDCANCEL입니다.

- IDABORT 에러가 발생한 경우. IDABORT가 반환되면 멤버 `COleDialog::GetLastError` 함수를 호출하여 발생한 오류 유형에 대한 자세한 정보를 가져옵니다. 가능한 오류 목록을 보려면 Windows SDK의 [OleUIPaste특수](/windows/win32/api/oledlg/nf-oledlg-oleuipastespecialw) 기능을 참조하십시오.

### <a name="remarks"></a>설명

[m_ps](#m_ps) 구조의 멤버를 설정하여 다양한 대화 상자 컨트롤을 초기화하려면 호출하기 `DoModal`전에 이 작업을 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

IDOK를 반환하는 경우 `DoModal` 다른 멤버 함수를 호출하여 사용자가 대화 상자에 입력한 설정 또는 정보를 검색할 수 있습니다.

## <a name="colepastespecialdialoggetdrawaspect"></a><a name="getdrawaspect"></a>콜레파페테 스페셜디언로그::GetDraw측면

사용자가 선택한 항목을 아이콘으로 표시하도록 선택했는지 여부를 결정합니다.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Return Value

개체를 렌더링하는 데 필요한 메서드입니다.

- DVASPECT_CONTENT 아이콘으로 표시 확인란이 대화 상자를 해제할 때 선택되지 않은 경우 반환됩니다.

- DVASPECT_ICON 아이콘으로 표시 확인란이 대화 상자를 해제할 때 선택된 경우 반환됩니다.

### <a name="remarks"></a>설명

[DoModal이 IDOK를](#domodal) 반환한 후에만 이 함수를 호출합니다.

드로잉 측면에 대한 자세한 내용은 Windows SDK의 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 참조하십시오.

## <a name="colepastespecialdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>콜레파페테 스페셜디아로그::겟이닉메타파일

사용자가 선택한 항목과 연결된 메타파일을 가져옵니다.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Return Value

**확인을**선택하여 대화 상자를 해제할 때 아이콘으로 표시 확인란을 선택한 경우 선택한 항목의 상징적인 측면을 포함하는 메타파일핸들; 그렇지 않으면 NULL.

## <a name="colepastespecialdialoggetpasteindex"></a><a name="getpasteindex"></a>콜레파페테 스페셜디언로그::겟페이스트인덱스

선택한 항목과 연결된 인덱스 값을 가져옵니다.

```
int GetPasteIndex() const;
```

### <a name="return-value"></a>Return Value

사용자가 선택한 구조의 `OLEUIPASTEENTRY` 배열로 인덱스입니다. 붙여넣기 작업을 수행할 때 선택한 인덱스에 해당하는 형식을 사용해야 합니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [OLEUIPASTEENTRY](/windows/win32/api/oledlg/ns-oledlg-oleuipasteentryw) 구조를 참조하십시오.

## <a name="colepastespecialdialoggetselectiontype"></a><a name="getselectiontype"></a>콜레파페테 스페셜 디월로그::GetselectionType

사용자가 선택한 유형을 결정합니다.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Return Value

만든 선택 유형을 반환합니다.

### <a name="remarks"></a>설명

반환 형식 값은 `Selection` `COlePasteSpecialDialog` 클래스에서 선언된 열거형 유형에 의해 지정됩니다.

```
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };
```

이러한 값의 간략한 삭제는 다음과 같습니다.

- `COlePasteSpecialDialog::pasteLink`붙여 넣기 링크 라디오 버튼이 선택되었고 선택한 형식이 표준 OLE 형식이었습니다.

- `COlePasteSpecialDialog::pasteNormal`붙여 넣기 라디오 버튼이 선택되었고 선택한 형식이 표준 OLE 형식이었습니다.

- `COlePasteSpecialDialog::pasteOther`선택한 형식은 표준 OLE 형식이 아닙니다.

- `COlePasteSpecialDialog::pasteStatic`선택한 형식은 메타파일이었습니다.

## <a name="colepastespecialdialogm_ps"></a><a name="m_ps"></a>콜레파페테스페셜디아로그::m_ps

붙여넣기 특수 대화 상자의 동작을 제어하는 데 사용되는 OLEUIPASTESPECIAL 형식의 구조입니다.

```
OLEUIPASTESPECIAL m_ps;
```

### <a name="remarks"></a>설명

이 구조의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.

자세한 내용은 Windows SDK의 [OLEUIPASTESPECIAL](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw) 구조를 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 클라이언트](../../overview/visual-cpp-samples.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
