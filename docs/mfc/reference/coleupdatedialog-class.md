---
title: COleUpdateDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
ms.openlocfilehash: 9e2c7a8d79ebf5e6483a06354b280e474d7b8e61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374844"
---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog 클래스

OLE 편집 링크 대화 상자의 특별한 경우에 사용됩니다. 예를 들어, 문서에서 기존에 연결되거나 포함된 개체만 업데이트할 경우에 사용해야 합니다.

## <a name="syntax"></a>구문

```
class COleUpdateDialog : public COleLinksDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|`COleUpdateDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleUpdate디아로그::DoModal](#domodal)|업데이트 모드에서 링크 편집 대화 상자를 **표시합니다.**|

## <a name="remarks"></a>설명

OLE 관련 대화 상자에 대한 자세한 내용은 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

[COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

`COleUpdateDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

## <a name="coleupdatedialogcoleupdatedialog"></a><a name="coleupdatedialog"></a>COleUpdateDialog::COleUpdateDialog

`COleUpdateDialog` 개체를 생성합니다.

```
explicit COleUpdateDialog(
    COleDocument* pDoc,
    BOOL bUpdateLinks = TRUE,
    BOOL bUpdateEmbeddings = FALSE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*pDoc*<br/>
업데이트해야 할 수 있는 링크가 포함된 문서를 가리킵니다.

*b업데이트링크*<br/>
연결된 개체를 업데이트할지 여부를 결정하는 플래그입니다.

*b업데이트엠베딩*<br/>
포함된 개체를 업데이트할지 여부를 결정하는 플래그입니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 부모 `CWnd`또는 소유자 창 개체(형식)를 가리킵니다. NULL이면 대화 상자의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

### <a name="remarks"></a>설명

이 함수는 `COleUpdateDialog` 개체만 생성합니다. 대화 상자를 표시하려면 [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal)을 호출합니다. 이 클래스는 기존 `COleLinksDialog` 링크된 항목이나 포함된 항목만 업데이트하려는 대신 사용해야 합니다.

## <a name="coleupdatedialogdomodal"></a><a name="domodal"></a>COleUpdate디아로그::DoModal

업데이트 모드에서 링크 편집 대화 상자를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

대화 상자의 완료 상태입니다. 해당 값은

- 대화 상자가 성공적으로 반환된 경우 IDOK입니다.

- IDCANCEL 현재 문서에 연결 된 또는 포함 된 항목 업데이트 해야 하는 경우.

- IDABORT 에러가 발생한 경우. IDABORT가 반환되는 경우 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 멤버 함수를 호출하여 발생한 오류 유형에 대한 자세한 정보를 얻습니다. 가능한 오류 목록은 Windows SDK의 [OleUIEditLinks](/windows/win32/api/oledlg/nf-oledlg-oleuieditlinksw) 함수를 참조하십시오.

### <a name="remarks"></a>설명

사용자가 취소 단추를 선택하지 않으면 모든 링크 및/또는 포함이 업데이트됩니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 클라이언트](../../overview/visual-cpp-samples.md)<br/>
[COleLinks대화단 클래스](../../mfc/reference/colelinksdialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleLinks대화단 클래스](../../mfc/reference/colelinksdialog-class.md)
