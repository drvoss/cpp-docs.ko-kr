---
title: COleLinks대화단 클래스
ms.date: 11/04/2016
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
ms.openlocfilehash: f120678c822749c8f27c3c56c95fcdd54647aca3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374929"
---
# <a name="colelinksdialog-class"></a>COleLinks대화단 클래스

OLE 링크 편집 대화 상자에 사용합니다.

## <a name="syntax"></a>구문

```
class COleLinksDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|`COleLinksDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleLinksDialog::DoModal](#domodal)|OLE 링크 편집 대화 상자를 표시합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[COleLinksDialog::m_el](#m_el)|대화 상자의 동작을 제어하는 OLEUIEDITLINKS 형식의 구조입니다.|

## <a name="remarks"></a>설명

이 대화 상자를 `COleLinksDialog` 호출할 때 클래스의 개체를 만듭니다. `COleLinksDialog` 개체를 생성 한 후에는 [m_el](#m_el) 구조를 사용하여 대화 상자에서 컨트롤의 값 또는 상태를 초기화할 수 있습니다. 구조는 `m_el` OLEUIEDITLINKS 형식입니다. 이 대화 상자 클래스 사용에 대 한 자세한 내용은 [DoModal](#domodal) 멤버 함수를 참조 하십시오.

> [!NOTE]
> 응용 프로그램 마법사에서 생성한 컨테이너 코드는 이 클래스를 사용합니다.

자세한 내용은 Windows SDK의 [OLEUIEDITLINKS](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) 구조를 참조하십시오.

OLE 관련 대화 상자에 대한 자세한 내용은 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleLinksDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

## <a name="colelinksdialogdomodal"></a><a name="domodal"></a>코올링크스디아로그::DoModal

OLE 링크 편집 대화 상자를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

대화 상자의 완료 상태입니다. 해당 값은

- 대화 상자가 성공적으로 표시되는 경우 IDOK입니다.

- 사용자가 대화 상자를 취소한 경우 IDCANCEL입니다.

- IDABORT 에러가 발생한 경우. IDABORT가 반환되면 멤버 `COleDialog::GetLastError` 함수를 호출하여 발생한 오류 유형에 대한 자세한 정보를 가져옵니다. 가능한 오류 목록은 Windows SDK의 [OleUIEditLinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) 함수를 참조하십시오.

### <a name="remarks"></a>설명

[m_el](#m_el) 구조체의 멤버를 설정하여 다양한 대화 상자 컨트롤을 초기화하려면 호출하기 `DoModal`전에 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

## <a name="colelinksdialogcolelinksdialog"></a><a name="colelinksdialog"></a>COleLinks대화문::COleLinks대화문

`COleLinksDialog` 개체를 생성합니다.

```
COleLinksDialog (
    COleDocument* pDoc,
    CView* pView,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*pDoc*<br/>
편집할 링크가 포함된 OLE 문서를 가리킵니다.

*pView*<br/>
*pDoc의*현재 뷰를 가리킵니다.

*dwFlags*<br/>
0 또는 ELF_SHOWHELP 포함하는 만들기 플래그로 대화 상자가 표시될 때 도움말 버튼이 표시될지 여부를 지정합니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 부모 `CWnd`또는 소유자 창 개체(형식)를 가리킵니다. NULL인 경우 대화 상자의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

### <a name="remarks"></a>설명

이 함수는 `COleLinksDialog` 개체만 생성합니다. 대화 상자를 표시하려면 [DoModal](#domodal) 함수를 호출합니다.

## <a name="colelinksdialogm_el"></a><a name="m_el"></a>COleLinks대화문::m_el

링크 편집 대화 상자의 동작을 제어하는 데 사용되는 OLEUIEDITLINKS 형식의 구조입니다.

```
OLEUIEDITLINKS m_el;
```

### <a name="remarks"></a>설명

이 구조의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.

자세한 내용은 Windows SDK의 [OLEUIEDITLINKS](/windows/win32/api/oledlg/ns-oledlg-oleuieditlinksw) 구조를 참조하십시오.

## <a name="see-also"></a>참고 항목

[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
