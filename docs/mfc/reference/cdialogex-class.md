---
title: 클리클로덱스 클래스
ms.date: 11/04/2016
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
ms.openlocfilehash: 717e560035d42957c16168097577d0c8c589e3c7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753357"
---
# <a name="cdialogex-class"></a>클리클로덱스 클래스

`CDialogEx` 클래스는 대화 상자의 배경 색과 배경 이미지를 지정합니다.

## <a name="syntax"></a>구문

```
class CDialogEx : public CDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDialogEx::CDialogEx](#cdialogex)|`CDialogEx` 개체를 생성합니다.|
|`CDialogEx::~CDialogEx`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|대화 상자의 배경 색을 설정합니다.|
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|대화 상자의 배경 이미지를 설정합니다.|

## <a name="remarks"></a>설명

`CDialogEx` 클래스를 사용하려면 `CDialogEx` 클래스 대신 `CDialog` 클래스에서 대화 상자 클래스를 파생합니다.

대화 상자 이미지는 리소스 파일에 저장됩니다. 프레임워크는 리소스 파일에서 로드되는 모든 이미지를 자동으로 삭제합니다. 현재 배경 이미지를 프로그래밍 방식으로 삭제하려면 [CDialogEx::SetBackgroundImage](#setbackgroundimage) 메서드를 `OnDestroy` 호출하거나 이벤트 처리기를 구현합니다. [CDialogEx::SetBackgroundImage](#setbackgroundimage) 메서드를 호출할 때 `HBITMAP` 매개 변수를 이미지 핸들로 전달합니다. `CDialogEx` 개체가 이미지의 소유권을 갖게 되며 `m_bAutoDestroyBmp` 플래그가 `TRUE`이면 삭제합니다.

개체는 `CDialogEx` [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 개체의 부모일 수 있습니다. [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 개체가 `CDialogEx::SetActiveMenu` 열릴 때 [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 개체메서드를 호출합니다. 그런 다음 `CDialogEx` [CMFCPopUpMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 개체가 닫혀있을 때까지 개체가 모든 메뉴 이벤트를 처리합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxdialogex.h

## <a name="cdialogexcdialogex"></a><a name="cdialogex"></a>CDialogEx::CDialogEx

`CDialogEx` 개체를 생성합니다.

```
CDialogEx(
    UINT nIDTemplate,
    CWnd* pParent=NULL);

CDialogEx(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd=NULL);
```

### <a name="parameters"></a>매개 변수

*nIDTemplate*<br/>
【인】 대화 상자 템플릿의 리소스 ID입니다.

*lpszTemplateName*<br/>
【인】 대화 상자 템플릿의 리소스 이름입니다.

*pParent*<br/>
【인】 상위 창에 대한 포인터입니다. 기본값은 NULL입니다.

*pParentWnd*<br/>
【인】 상위 창에 대한 포인터입니다. 기본값은 NULL입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cdialogexsetbackgroundcolor"></a><a name="setbackgroundcolor"></a>CDialogEx::설정배경색

대화 상자의 배경 색을 설정합니다.

```cpp
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 RGB 색상 값입니다.

*bRepaint*<br/>
【인】 TRUE는 즉시 화면을 업데이트합니다. 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

## <a name="cdialogexsetbackgroundimage"></a><a name="setbackgroundimage"></a>CDialogEx::설정배경이미지

대화 상자의 배경 이미지를 설정합니다.

```cpp
void SetBackgroundImage(
    HBITMAP hBitmap,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bAutoDestroy=TRUE,
    BOOL bRepaint=TRUE);

BOOL SetBackgroundImage(
    UINT uiBmpResId,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>매개 변수

*hBitmap*<br/>
【인】 배경 이미지에 대한 핸들입니다.

*uiBmpResId*<br/>
【인】 배경 이미지의 리소스 ID입니다.

*location*<br/>
【인】 이미지의 `CDialogEx::BackgroundLocation` 위치를 지정하는 값 중 하나입니다. 유효한 값에는 BACKGR_TILE, BACKGR_TOPLEFT, BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT 및 BACKGR_BOTTOMRIGHT 포함됩니다. 기본값은 BACKGR_TILE.

*b오토파괴*<br/>
【인】 TRUE는 자동으로 배경 이미지를 파괴; 그렇지 않으면 false입니다.

*bRepaint*<br/>
【인】 TRUE는 대화 상자를 즉시 다시 그릴 수 있습니다. 그렇지 않으면 false입니다.

### <a name="return-value"></a>Return Value

두 번째 메서드에서는 메서드가 성공하면 TRUE 구문과 오버로드됩니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

지정한 이미지는 대화 상자 클라이언트 영역에 맞게 늘어나지 않습니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC팝메뉴 클래스](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[C컨텍스트 메뉴관리자 클래스](../../mfc/reference/ccontextmenumanager-class.md)
