---
title: CMFCMenuButton 클래스
ms.date: 07/15/2019
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
- AFXMENUBUTTON/CMFCMenuButton::m_bDefaultClick
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
- CMFCMenuButton [MFC], m_bDefaultClick
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
ms.openlocfilehash: 929fc1c8166f249fe3babc724b2c0bcd9cb99676
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369677"
---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton 클래스

사용자가 선택한 메뉴에 팝업 메뉴와 보고서를 표시하는 단추입니다.

## <a name="syntax"></a>구문

```
class CMFCMenuButton : public CMFCButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC메뉴 버튼::CMFC메뉴버튼](#cmfcmenubutton)|`CMFCMenuButton` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|프레임워크에서 창 메시지를 전달하기 전에 번역하도록 호출됩니다. ( `CMFCButton::PreTranslateMessage`을 재정의합니다.)|
|[CMFC메뉴 버튼::크기토콘텐츠](#sizetocontent)|텍스트 및 이미지 크기에 따라 단추의 크기를 변경합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFC메뉴 버튼::m_bOSMenu](#m_bosmenu)|기본 시스템 팝업 메뉴를 표시할지 또는 [CContextMenuManager::TrackPopupMenu를](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)사용할지 지정합니다.|
|[CMFC메뉴 버튼:m_bRightArrow](#m_brightarrow)|팝업 메뉴가 단추 아래 또는 오른쪽에 표시되는지 여부를 지정합니다.|
|[CMFC메뉴 버튼:m_bStayPressed](#m_bstaypressed)|사용자가 단추를 해제한 후 메뉴 단추의 상태가 변경되는지 여부를 지정합니다.|
|[CMFC메뉴 버튼:m_hMenu](#m_hmenu)|연결된 Windows 메뉴의 핸들입니다.|
|[CMFC메뉴버튼:m_nMenuResult](#m_nmenuresult)|팝업 메뉴에서 선택한 항목을 나타내는 식별자입니다.|
|[CMFC메뉴 버튼:m_bDefaultClick](#m_bdefaultclick)| 기본(버튼 텍스트/이미지) 처리를 허용합니다.|

## <a name="remarks"></a>설명

클래스는 `CMFCMenuButton` [CMFCButton 클래스에서](../../mfc/reference/cmfcbutton-class.md) 파생되며, 이 클래스는 [CButton 클래스에서](../../mfc/reference/cbutton-class.md)파생됩니다. 따라서 코드에서 `CMFCMenuButton` 와 동일한 방식으로 사용할 수 `CButton`있습니다.

을 `CMFCMenuButton`만들 때 핸들을 연관된 팝업 메뉴로 전달해야 합니다. 다음으로 함수를 `CMFCMenuButton::SizeToContent`호출합니다. `CMFCMenuButton::SizeToContent`단추 크기가 팝업 창이 나타나는 위치(즉, 단추 의 아래 또는 오른쪽)를 가리키는 화살표를 포함하기에 충분한지 확인합니다.

## <a name="example"></a>예제

다음 예제에서는 단추에 연결 된 메뉴의 핸들을 설정 하는 방법을 보여 줍니다., 텍스트 및 이미지 크기에 따라 단추크기를 조정 하 고 프레임 워크에 의해 표시 되는 팝업 메뉴를 설정 합니다. 이 코드 조각은 새 [컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxmenubutton.h

## <a name="cmfcmenubuttoncmfcmenubutton"></a><a name="cmfcmenubutton"></a>CMFC메뉴 버튼::CMFC메뉴버튼

새 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) 개체를 생성합니다.

```
CMFCMenuButton();
```

## <a name="cmfcmenubuttonm_bosmenu"></a><a name="m_bosmenu"></a>CMFC메뉴 버튼::m_bOSMenu

프레임워크에 표시되는 팝업 메뉴를 나타내는 부울 멤버 변수입니다.

```
BOOL m_bOSMenu;
```

### <a name="remarks"></a>설명

TRUE인 경우 `m_bOSMenu` 프레임워크는 이 `TrackPopupMenu` 개체에 대해 상속된 메서드를 호출합니다. 그렇지 않으면 프레임워크에서 [CContextMenuManager::TrackPopupMenu를](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)호출합니다.

## <a name="cmfcmenubuttonm_brightarrow"></a><a name="m_brightarrow"></a>CMFC메뉴 버튼:m_bRightArrow

팝업 메뉴의 위치를 나타내는 부울 멤버 변수입니다.

```
BOOL m_bRightArrow;
```

### <a name="remarks"></a>설명

사용자가 메뉴 버튼을 누르면 응용 프로그램에 팝업 메뉴가 표시됩니다. 프레임워크는 버튼 아래 또는 버튼 오른쪽에 팝업 메뉴를 표시합니다. 또한 단추에는 팝업 메뉴가 표시되는 위치를 나타내는 작은 화살표가 있습니다. TRUE이면 `m_bRightArrow` 프레임워크에 팝업 메뉴가 단추 오른쪽에 표시됩니다. 그렇지 않으면 버튼 아래에 팝업 메뉴가 표시됩니다.

## <a name="cmfcmenubuttonm_bstaypressed"></a><a name="m_bstaypressed"></a>CMFC메뉴 버튼:m_bStayPressed

사용자가 팝업 메뉴에서 선택하는 동안 메뉴 단추를 눌렀는지 여부를 나타내는 부울 멤버 변수입니다.

```
BOOL m_bStayPressed;
```

### <a name="remarks"></a>설명

멤버가 `m_bStayPressed` FALSE이면 사용이 단추를 클릭할 때 메뉴 단추를 누르지 않습니다. 이 경우 프레임워크에는 팝업 메뉴만 표시됩니다.

멤버가 `m_bStayPressed` TRUE이면 사용자가 단추를 클릭할 때 메뉴 버튼을 누를 수 있습니다. 사용자가 팝업 메뉴를 닫을 때까지 선택하거나 취소하여 누른 상태로 유지됩니다.

## <a name="cmfcmenubuttonm_hmenu"></a><a name="m_hmenu"></a>CMFC메뉴 버튼:m_hMenu

연결된 메뉴의 핸들입니다.

```
HMENU m_hMenu;
```

### <a name="remarks"></a>설명

사용자가 메뉴 단추를 클릭할 때 이 멤버 변수로 표시된 메뉴가 프레임워크에 표시됩니다.

## <a name="cmfcmenubuttonm_nmenuresult"></a><a name="m_nmenuresult"></a>CMFC메뉴버튼:m_nMenuResult

사용자가 팝업 메뉴에서 선택하는 항목을 나타내는 정수입니다.

```
int m_nMenuResult;
```

### <a name="remarks"></a>설명

사용자가 선택하지 않고 메뉴를 취소하거나 오류가 발생하는 경우 이 멤버 변수의 값은 0입니다.

## <a name="cmfcmenubuttonm_bdefaultclick"></a><a name="m_bdefaultclick"></a>CMFC메뉴 버튼:m_bDefaultClick

단추에서 텍스트 또는 이미지를 기본으로 처리할 수 있습니다.

```
BOOL  m_bDefaultClick;
```

### <a name="remarks"></a>설명

m_bDefaultClick 거짓으로 설정하면 단추의 아무 곳이나 클릭하면 단추가 메뉴가 표시됩니다.

## <a name="cmfcmenubuttonm_nmenuresult"></a><a name="m_nmenuresult"></a>CMFC메뉴버튼:m_nMenuResult

사용자가 팝업 메뉴에서 선택하는 항목을 나타내는 정수입니다.

```
int m_nMenuResult;
```

### <a name="remarks"></a>설명

## <a name="cmfcmenubuttonpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFC메뉴버튼::P다시번역메시지

프레임워크에서 창 메시지를 전달하기 전에 번역하도록 호출됩니다.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
【인】 처리할 메시지가 포함된 [MSG](/windows/win32/api/winuser/ns-winuser-msg) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

메시지가 번역되어 전달되지 않아야 하는 경우 0이 아님을 의미합니다. 메시지가 번역되지 않고 디스패치해야 하는 경우 0입니다.

### <a name="remarks"></a>설명

## <a name="cmfcmenubuttonsizetocontent"></a><a name="sizetocontent"></a>CMFC메뉴 버튼::크기토콘텐츠

텍스트 크기와 이미지 크기에 따라 단추의 크기를 변경합니다.

```
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```

### <a name="parameters"></a>매개 변수

*bCalcOnly*<br/>
【인】 이 메서드가 단추크기를 조정하는지 여부를 나타내는 부울 매개 변수입니다.

### <a name="return-value"></a>Return Value

단추의 새 크기를 지정하는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.

### <a name="remarks"></a>설명

이 함수를 호출하고 *bCalcOnly가* TRUE인 경우 단추의 새 크기만 `SizeToContent` 계산합니다.

단추의 새 크기는 단추 텍스트, 이미지 및 화살표에 맞게 계산됩니다. 프레임 워크는 또한 가로 가장자리에 대 한 10 픽셀의 미리 정의 된 여백에 추가 하 고 5 세로 가장자리에 대 한 픽셀.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC버튼 클래스](../../mfc/reference/cmfcbutton-class.md)
