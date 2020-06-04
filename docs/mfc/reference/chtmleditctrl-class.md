---
title: CHtmlEditCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
helpviewer_keywords:
- CHtmlEditCtrl [MFC], CHtmlEditCtrl
- CHtmlEditCtrl [MFC], Create
- CHtmlEditCtrl [MFC], GetDHtmlDocument
- CHtmlEditCtrl [MFC], GetStartDocument
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
ms.openlocfilehash: 05063c62e9f7a5d88d3fecde842f979725200f98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366849"
---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl 클래스

MFC 창에서 WebBrowser ActiveX 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CHtmlEditCtrl: public CWnd,
    public CHtmlEditCtrlBase<CHtmlEditCtrl>
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|`CHtmlEditCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CHtmlEditCtrl::만들기](#create)|WebBrowser ActiveX 컨트롤을 만들고 개체에 `CHtmlEditCtrl` 연결합니다. 이 기능은 WebBrowser ActiveX 컨트롤을 편집 모드로 자동 전환합니다.|
|[CHtmlEditCtrl::GetDHtml문서](#getdhtmldocument)|포함된 WebBrowser 컨트롤에 현재 로드된 문서에서 [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) 인터페이스를 검색합니다.|
|[CHtmlEditCtrl::GetStart문서](#getstartdocument)|포함된 WebBrowser 컨트롤에 로드할 기본 문서의 URL을 검색합니다.|

## <a name="remarks"></a>설명

호스팅된 WebBrowser 컨트롤은 생성된 후 자동으로 편집 모드로 전환됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHtmlEditCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxhtml.h

## <a name="chtmleditctrlchtmleditctrl"></a><a name="chtmleditctrl"></a>CHtmlEditCtrl::CHtmlEditCtrl

`CHtmlEditCtrl` 개체를 생성합니다.

```
CHtmlEditCtrl();
```

## <a name="chtmleditctrlcreate"></a><a name="create"></a>CHtmlEditCtrl::만들기

WebBrowser ActiveX 컨트롤을 만들고 개체에 `CHtmlEditCtrl` 연결합니다. WebBrowser ActiveX 컨트롤은 자동으로 기본 문서로 이동한 다음 이 함수에 의해 편집 모드에 배치됩니다.

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszWindowName*<br/>
이 매개 변수는 사용되지 않습니다.

*dwStyle*<br/>
이 매개 변수는 사용되지 않습니다.

*rect*<br/>
컨트롤의 크기와 위치를 지정합니다.

*pParentWnd*<br/>
컨트롤의 상위 창을 지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
컨트롤의 ID를 지정합니다.

*pContext*<br/>
이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="chtmleditctrlgetdhtmldocument"></a><a name="getdhtmldocument"></a>CHtmlEditCtrl::GetDHtml문서

포함된 WebBrowser 컨트롤에 현재 로드된 문서에서 [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) 인터페이스를 검색합니다.

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>매개 변수

*ppDocument*<br/>
문서 인터페이스입니다.

## <a name="chtmleditctrlgetstartdocument"></a><a name="getstartdocument"></a>CHtmlEditCtrl::GetStart문서

포함된 WebBrowser 컨트롤에 로드할 기본 문서의 URL을 검색합니다.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)
