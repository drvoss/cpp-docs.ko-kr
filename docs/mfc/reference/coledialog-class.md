---
title: COleDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: 6a1983d426e97dd8063aee2857dc36557aa20677
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366090"
---
# <a name="coledialog-class"></a>COleDialog 클래스

OLE 대화 상자에 공통적인 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleDialog::GetLastError](#getlasterror)|대화 상자에서 반환된 오류 코드를 가져옵니다.|

## <a name="remarks"></a>설명

Microsoft 재단 클래스 라이브러리는 다음에서 `COleDialog`파생된 여러 클래스를 제공합니다.

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

OLE 관련 대화 상자에 대한 자세한 내용은 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

## <a name="coledialoggetlasterror"></a><a name="getlasterror"></a>COleDialog::GetLastError

IDABORT를 반환할 때 `GetLastError` `DoModal` 추가 오류 정보를 얻으려면 멤버 함수를 호출합니다.

```
UINT GetLastError() const;
```

### <a name="return-value"></a>Return Value

반환되는 `GetLastError` 오류 코드는 표시되는 특정 대화 상자에 따라 다릅니다.

### <a name="remarks"></a>설명

특정 `DoModal` 오류 메시지에 대한 자세한 내용은 파생 클래스의 멤버 함수를 참조하십시오.

## <a name="see-also"></a>참고 항목

[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
