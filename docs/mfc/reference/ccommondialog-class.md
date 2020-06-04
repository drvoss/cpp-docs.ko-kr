---
title: CCommonDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
ms.openlocfilehash: 853a4756df3b70f4f33deb7159b4d1aee610092c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369440"
---
# <a name="ccommondialog-class"></a>CCommonDialog 클래스

Windows 공용 대화 상자의 기능을 캡슐화하는 클래스의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CCommonDialog : public CDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C커먼디아로그::C커먼디아로그](#ccommondialog)|`CCommonDialog` 개체를 생성합니다.|

## <a name="remarks"></a>설명

다음 클래스는 Windows 공통 대화 상자의 기능을 캡슐화합니다.

- [CFileDialog](../../mfc/reference/cfiledialog-class.md)

- [CFontDialog](../../mfc/reference/cfontdialog-class.md)

- [CColorDialog](../../mfc/reference/ccolordialog-class.md)

- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)

- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)

- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)

- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)

- [COleDialog](../../mfc/reference/coledialog-class.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CCommonDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

## <a name="ccommondialogccommondialog"></a><a name="ccommondialog"></a>C커먼디아로그::C커먼디아로그

`CCommonDialog` 개체를 생성합니다.

```
explicit CCommonDialog(CWnd* pParentWnd);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
대화 상자 개체가 속한 상위 또는 소유자 창 [개체(CWnd](../../mfc/reference/cwnd-class.md)형식)를 가리킵니다. NULL인 경우 대화 상자 개체의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

### <a name="remarks"></a>설명

전체 정보는 [CDialog::CDialog를](../../mfc/reference/cdialog-class.md#cdialog) 참조하십시오.

## <a name="see-also"></a>참고 항목

[클리언로그 클래스](../../mfc/reference/cdialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFile Dialog 클래스](../../mfc/reference/cfiledialog-class.md)<br/>
[CFontDialog 클래스](../../mfc/reference/cfontdialog-class.md)<br/>
[CColorDialog 클래스](../../mfc/reference/ccolordialog-class.md)<br/>
[CPageSetupDialog 클래스](../../mfc/reference/cpagesetupdialog-class.md)<br/>
[CPrintDialog 클래스](../../mfc/reference/cprintdialog-class.md)<br/>
[CFindReplaceDialog 클래스](../../mfc/reference/cfindreplacedialog-class.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)
