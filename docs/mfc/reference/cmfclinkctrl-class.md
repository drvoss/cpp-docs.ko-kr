---
title: CMFCLinkCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
ms.openlocfilehash: 79edff8be6e2c37baa938fc5b624253932609e17
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754251"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl 클래스

클래스는 `CMFCLinkCtrl` 단추를 하이퍼링크로 표시하고 단추를 클릭하면 링크의 대상을 호출합니다.

## <a name="syntax"></a>구문

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCLinkCtrl:::SetURL](#seturl)|지정된 URL을 단추 텍스트로 표시합니다.|
|[CMFCLinkCtrl:::세URL 프리픽스](#seturlprefix)|URL의 암시적 프로토콜(예: "http:")을 설정합니다.|
|[CMFCLinkCtrl::크기토콘텐츠](#sizetocontent)|단추 텍스트 또는 비트맵을 포함하도록 단추크기를 조정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFCLinkCtrl:::온드로우 포커스렉트](#ondrawfocusrect)|단추의 포커스 사각형이 그려지기 전에 프레임워크에서 호출됩니다.|

## <a name="remarks"></a>설명

`CMFCLinkCtrl` 클래스에서 파생된 단추를 클릭하면 프레임워크는 단추의 URL을 매개 변수로 `ShellExecute` 메서드에 전달합니다. 그런 `ShellExecute` 다음 메서드는 URL의 대상을 엽니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCLinkCtrl` 개체의 크기를 설정하는 방법과 `CMFCLinkCtrl` 개체에서 URL 및 도구 설명을 설정하는 방법을 보여 줍니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxlinkctrl.h

## <a name="cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCLinkCtrl:::온드로우 포커스렉트

단추의 포커스 사각형이 그려지기 전에 프레임워크에서 호출됩니다.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rectClient*<br/>
【인】 링크 컨트롤을 바인딩하는 사각형입니다.

### <a name="remarks"></a>설명

고유한 코드를 사용하여 단추의 포커스 사각형을 그리려는 경우 이 메서드를 재정의합니다.

## <a name="cmfclinkctrlseturl"></a><a name="seturl"></a>CMFCLinkCtrl:::SetURL

지정된 URL을 단추 텍스트로 표시합니다.

```cpp
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>매개 변수

*lpszURL*<br/>
【인】 표시할 단추 텍스트입니다.

### <a name="remarks"></a>설명

## <a name="cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a>CMFCLinkCtrl:::세URL 프리픽스

URL의 암시적 프로토콜(예: "http:")을 설정합니다.

```cpp
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>매개 변수

*lpsz사전수정*<br/>
【인】 URL 프로토콜의 접두사입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 URL 접두사를 설정합니다. 접두사는 단추의 얼굴에 표시되지 않지만 URL의 대상을 탐색하는 데 사용할 수 있습니다.

## <a name="cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a>CMFCLinkCtrl::크기토콘텐츠

단추 텍스트 또는 비트맵을 포함하도록 단추크기를 조정합니다.

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>매개 변수

*bV 센터*<br/>
【인】 TRUE 는 링크 컨트롤의 위쪽과 아래쪽 사이에 단추 텍스트와 비트맵을 세로로 가운데에 배치합니다. 그렇지 않으면 false입니다. 기본값은 FALSE입니다.

*bH센터*<br/>
【인】 TRUE 는 링크 컨트롤의 왼쪽과 오른쪽 사이에 단추 텍스트와 비트맵을 가로로 가운데에 두는 것입니다. 그렇지 않으면 false입니다. 기본값은 FALSE입니다.

### <a name="return-value"></a>Return Value

링크 컨트롤의 새 크기를 포함하는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[클링Ctrl 클래스](../../mfc/reference/clinkctrl-class.md)<br/>
[CMFC버튼 클래스](../../mfc/reference/cmfcbutton-class.md)
