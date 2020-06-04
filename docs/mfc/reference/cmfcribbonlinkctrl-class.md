---
title: CMFC리본링크트르 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CopyFrom
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetCompactSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetRegularSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetToolTipText
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::IsDrawTooltipImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDraw
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDrawMenuImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnMouseMove
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnSetIcon
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OpenLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::SetLink
helpviewer_keywords:
- CMFCRibbonLinkCtrl [MFC], CMFCRibbonLinkCtrl
- CMFCRibbonLinkCtrl [MFC], CopyFrom
- CMFCRibbonLinkCtrl [MFC], GetCompactSize
- CMFCRibbonLinkCtrl [MFC], GetLink
- CMFCRibbonLinkCtrl [MFC], GetRegularSize
- CMFCRibbonLinkCtrl [MFC], GetToolTipText
- CMFCRibbonLinkCtrl [MFC], IsDrawTooltipImage
- CMFCRibbonLinkCtrl [MFC], OnDraw
- CMFCRibbonLinkCtrl [MFC], OnDrawMenuImage
- CMFCRibbonLinkCtrl [MFC], OnMouseMove
- CMFCRibbonLinkCtrl [MFC], OnSetIcon
- CMFCRibbonLinkCtrl [MFC], OpenLink
- CMFCRibbonLinkCtrl [MFC], SetLink
ms.assetid: 77ae1941-e0ab-4a9d-911e-1752d34c079b
ms.openlocfilehash: 3c0cbe843aac172464683288d61e2aec2af60b68
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753563"
---
# <a name="cmfcribbonlinkctrl-class"></a>CMFC리본링크트르 클래스

리본에 배치되는 하이퍼링크를 구현합니다. 하이퍼링크를 클릭하면 웹 페이지가 열립니다.
자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCRibbonLinkCtrl : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl](#cmfcribbonlinkctrl)|`CMFCRibbonLinkCtrl` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCRibbonLinkCtrl::CopyFrom](#copyfrom)|( `CMFCRibbonButton::CopyFrom`을 재정의합니다.)|
|[CMFCRibbonLinkCtrl::GetCompactSize](#getcompactsize)|[(CMFC 리본 단추 재정의::GetCompactSize.)](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize)|
|[CMFCRibbonLinkCtrl::GetLink](#getlink)|하이퍼링크의 값을 반환합니다.|
|[CMFCRibbonLinkCtrl::GetRegularSize](#getregularsize)|[(CMFC 리본 단추 재정의::GetRegularSize.)](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize)|
|[CMFCRibbonLinkCtrl::GetToolTipText](#gettooltiptext)|[(CMFC 리본 단추 재정의::GetToolTipText.)](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext)|
|[CMFCRibbonLinkCtrl::IsDrawTooltipImage](#isdrawtooltipimage)|( `CMFCRibbonButton::IsDrawTooltipImage`을 재정의합니다.)|
|[CMFCRibbonLinkCtrl::OnDraw](#ondraw)|[(CMFC 리본 단추 재정의::온드로우.)](../../mfc/reference/cmfcribbonbutton-class.md#ondraw)|
|[CMFCRibbonLinkCtrl::OnDrawMenuImage](#ondrawmenuimage)|[(CMFC 리본베이스 요소 재정의::온드로우 메뉴이미지.)](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage)|
|[CMFCRibbonLinkCtrl::OnMouseMove](#onmousemove)|( `CMFCRibbonButton::OnMouseMove`을 재정의합니다.)|
|[CMFCRibbonLinkCtrl::OnSetIcon](#onseticon)||
|[CMFCRibbonLinkCtrl::OpenLink](#openlink)|하이퍼링크에 지정된 웹 페이지를 엽니다.|
|[CMFCRibbonLinkCtrl::SetLink](#setlink)|하이퍼링크의 값을 설정합니다.|

## <a name="remarks"></a>설명

하이퍼링크를 만든 후 [CMFCRibbonPanel::Add를](../../mfc/reference/cmfcribbonpanel-class.md#add)호출하여 패널에 추가합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[Cobject](../../mfc/reference/cobject-class.md)\
❏&nbsp;[CMFC리본베이스요소](../../mfc/reference/cmfcribbonbaseelement-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CMFC 리본 버튼](../../mfc/reference/cmfcribbonbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CMFC리본링크트르](../../mfc/reference/cmfcribbonlinkctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afx리본링크트르.h

## <a name="cmfcribbonlinkctrlcmfcribbonlinkctrl"></a><a name="cmfcribbonlinkctrl"></a>CMFC리본링크트르::CMFC리본링크트르

[CMFC리본링크Ctrl](../../mfc/reference/cmfcribbonlinkctrl-class.md) 개체를 생성하고 초기화합니다.

```
CMFCRibbonLinkCtrl(
    UINT nID,
    LPCTSTR lpszText,
    LPCTSTR lpszLink);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 링크 컨트롤을 클릭할 때 실행되는 명령 ID를 지정합니다.

*lpszText*<br/>
【인】 링크 컨트롤에 표시할 레이블을 지정합니다.

*lpszLink*<br/>
【인】 링크 컨트롤과 연결된 하이퍼링크를 지정합니다.

### <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonLinkCtrl` 클래스의 생성자 사용 방법을 보여 줍니다. 이 코드 조각은 리본 [가젯 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]

## <a name="cmfcribbonlinkctrlcopyfrom"></a><a name="copyfrom"></a>CMFC리본링크트르::복사에서

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>매개 변수

【인】 *src*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcribbonlinkctrlgetcompactsize"></a><a name="getcompactsize"></a>CMFC리본링크트르::겟컴팩트사이즈

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonlinkctrlgetlink"></a><a name="getlink"></a>CMFC리본링크트르::겟링크

하이퍼링크의 값을 반환합니다.

```
LPCTSTR GetLink() const;
```

### <a name="return-value"></a>Return Value

하이퍼링크의 현재 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribbonlinkctrlgetregularsize"></a><a name="getregularsize"></a>CMFC리본링크트르::일반 크기 얻기

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonlinkctrlgettooltiptext"></a><a name="gettooltiptext"></a>CMFC리본링크트르::겟툴팁텍스트

```
virtual CString GetToolTipText() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonlinkctrlondrawmenuimage"></a><a name="ondrawmenuimage"></a>CMFC리본링크트르::온드로우메뉴이미지

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>매개 변수

【인】 *CDC&#42;*<br/>
【인】 *트렉트 (주)*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonlinkctrlisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>CMFC리본링크트르::이스드툴팁이미지

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonlinkctrlondraw"></a><a name="ondraw"></a>CMFC리본링크트르::온드로우

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcribbonlinkctrlonmousemove"></a><a name="onmousemove"></a>CMFC리본링크트르::온마우스무브

```
virtual void OnMouseMove(CPoint point);
```

### <a name="parameters"></a>매개 변수

【인】 *점*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcribbonlinkctrlonseticon"></a><a name="onseticon"></a>CMFC리본링크트르::온세티콘

```
virtual void OnSetIcon();
```

### <a name="remarks"></a>설명

## <a name="cmfcribbonlinkctrlopenlink"></a><a name="openlink"></a>CMFC리본링크트르::오픈링크

하이퍼링크에 지정된 웹 페이지를 엽니다.

```
BOOL OpenLink();
```

### <a name="return-value"></a>Return Value

연결된 웹 페이지가 성공적으로 열려 있는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

개체와 연결된 하이퍼링크를 사용하여 웹 `CMFCRibbonLinkCtrl` 페이지를 엽니다.

## <a name="cmfcribbonlinkctrlsetlink"></a><a name="setlink"></a>CMFC리본링크트르::세트링크

하이퍼링크의 값을 설정합니다.

```cpp
void SetLink(LPCTSTR lpszLink);
```

### <a name="parameters"></a>매개 변수

*lpszLink*<br/>
【인】 하이퍼링크 텍스트를 지정합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본버튼 클래스](../../mfc/reference/cmfcribbonbutton-class.md)
