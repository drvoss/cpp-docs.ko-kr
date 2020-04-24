---
title: CHtmlEditView 클래스
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
ms.openlocfilehash: 20d4586c1ae45e5f3f56c0adbb1ecb1757084fd7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752326"
---
# <a name="chtmleditview-class"></a>CHtmlEditView 클래스

MFC의 문서/뷰 아키텍처 컨텍스트 내에서 WebBrowser 편집 플랫폼의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|`CHtmlEditView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CHtmlEditView::만들기](#create)|새 창 개체를 만듭니다.|
|[CHtmlEditView::GetDHtml문서](#getdhtmldocument)|현재 `IHTMLDocument2` 문서의 인터페이스를 반환합니다.|
|[CHtmlEditView::GetStart문서](#getstartdocument)|이 보기에 대 한 기본 문서의 이름을 검색합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CHtmlView](../../mfc/reference/chtmlview-class.md)

`CHtmlEditView`

## <a name="requirements"></a>요구 사항

**헤더:** afxhtml.h

## <a name="chtmleditviewchtmleditview"></a><a name="chtmleditview"></a>CHtmlEditView::CHtmlEditView

`CHtmlEditView` 개체를 생성합니다.

```
CHtmlEditView();
```

## <a name="chtmleditviewcreate"></a><a name="create"></a>CHtmlEditView::만들기

새 창 개체를 만듭니다.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
Windows 클래스의 이름을 지정하는 null 종료된 문자 문자열을 가리킵니다. 클래스 이름은 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 글로벌 함수 또는 `RegisterClass` Windows 함수에 등록된 모든 이름일 수 있습니다. NULL인 경우 미리 정의된 기본 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 특성을 사용합니다.

*lpszWindowName*<br/>
창 이름을 나타내는 null 종료된 문자 문자열을 가리킵니다.

*dwStyle*<br/>
창 스타일 특성을 지정합니다. 기본적으로 WS_VISIBLE 및 WS_CHILD Windows 스타일이 설정됩니다.

*rect*<br/>
창의 크기와 위치를 지정하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다. *rectDefault* 값을 사용하면 Windows에서 새 창의 크기와 위치를 지정할 수 있습니다.

*pParentWnd*<br/>
컨트롤의 상위 창에 대한 포인터입니다.

*nID*<br/>
뷰의 ID 번호입니다. 기본적으로 AFX_IDW_PANE_FIRST 설정합니다.

*pContext*<br/>
[CCreateContext에](../../mfc/reference/ccreatecontext-structure.md)대한 포인터 . 기본적으로 NULL입니다.

### <a name="remarks"></a>설명

또한 이 메서드는 포함된 WebBrowser `Navigate` 메서드를 호출하여 기본 문서를 로드합니다(CHtmlEditView::GetStartDocument 참조). [CHtmlEditView::GetStartDocument](#getstartdocument)

## <a name="chtmleditviewgetdhtmldocument"></a><a name="getdhtmldocument"></a>CHtmlEditView::GetDHtml문서

현재 `IHTMLDocument2` 문서의 인터페이스를 반환합니다.

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>매개 변수

*ppDocument*<br/>
[IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) 인터페이스입니다.

## <a name="chtmleditviewgetstartdocument"></a><a name="getstartdocument"></a>CHtmlEditView::GetStart문서

이 보기에 대 한 기본 문서의 이름을 검색합니다.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>참조

[HTML편집 샘플](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
