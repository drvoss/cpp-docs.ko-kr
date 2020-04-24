---
title: CMFC툴바 편집박스버튼 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
ms.openlocfilehash: 064ebe1c8fe377064d410d09e5ef60ed628df2f3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754004"
---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFC툴바 편집박스버튼 클래스

편집 [컨트롤(CEdit 클래스)이](../../mfc/reference/cedit-class.md)포함된 도구 모음 단추입니다.

## <a name="syntax"></a>구문

```
class CMFCToolBarEditBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCToolBar 편집 상자 단추:::CMFCToolBar 편집 상자 단추](#cmfctoolbareditboxbutton)|`CMFCToolBarEditBoxButton` 개체를 생성합니다.|
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCToolBar 편집 상자 버튼 ::수 있습니다](#canbestretched)|사용자 지정 하는 동안 단추를 늘릴 수 있는지 여부를 지정 합니다. [(CMFCToolBar 단추 재정의::캔스트라이드.)](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)|
|[CMFCToolBar 편집 상자 버튼::복사에서](#copyfrom)|다른 도구 모음 단추의 속성을 현재 단추에 복사합니다. [(CMFCToolBar 단추 재정의::복사에서.)](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom)|
|`CMFCToolBarEditBoxButton::`[CMFCToolBar 편집 상자 단추::만들기 편집](#createedit)|단추에 새 편집 컨트롤을 만듭니다.|
|`CMFCToolBarEditBoxButton::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFCToolBar 편집 상자 버튼::GetByCmd](#getbycmd)|지정된 명령 `CMFCToolBarEditBoxButton` ID가 있는 응용 프로그램의 첫 번째 개체를 검색합니다.|
|[CMFCToolBar 편집 상자 버튼::GetContentall](#getcontentsall)|지정된 명령 ID가 있는 첫 번째 편집 상자 도구 모음 컨트롤의 텍스트를 검색합니다.|
|[CMFCToolBar 편집 상자 단추::GetContextMenuID](#getcontextmenuid)|단추와 연결된 바로 가기 메뉴의 리소스 ID를 검색합니다.|
|[CMFCToolBar 편집 상자 버튼::GetEditBorder](#geteditborder)|편집 상자 단추의 편집 부분의 경계 사각형을 검색합니다.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBar 편집 상자 버튼::GetEditBox](#geteditbox)|단추에 포함된 편집 컨트롤에 대한 포인터를 반환합니다.|
|[CMFCToolBar 편집 상자 버튼::GetHwnd](#gethwnd)|도구 모음 단추와 연결된 창 핸들을 검색합니다. [(CMFCToolBar 단추 재정의::GetHwnd.)](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd)|
|[CMFCToolBar 편집 상자 버튼::Get무효화렉트](#getinvalidaterect)|다시 그려야 하는 단추의 클라이언트 영역영역을 검색합니다. [(CMFCToolBar 단추 재정의::Get무효화렉트.)](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect)|
|`CMFCToolBarEditBoxButton::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFCToolBar 편집 상자 버튼::하핫보더](#havehotborder)|사용자가 단추를 클릭할 때 단추의 테두리가 표시되는지 여부를 결정합니다. [(CMFCToolBar 단추 재정의::하핫보더.)](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder)|
|[CMFCToolBar 편집 상자 버튼 ::IsFlatmode](#isflatmode)|편집 상자 단추에 플랫 스타일이 있는지 여부를 결정합니다.|
|[CMFCToolBar 편집 상자 단추::알림 명령](#notifycommand)|단추에서 [WM_COMMAND](/windows/win32/menurc/wm-command) 메시지를 처리하는지 여부를 지정합니다. [(CMFCToolBar 단추 재정의::알림 명령.)](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)|
|[CMFCToolBar 편집 상자 버튼::OnAddTo 사용자 정의 페이지](#onaddtocustomizepage)|단추를 **사용자 지정** 대화 상자에 추가 될 때 프레임 워크에 의해 호출 됩니다. [(CMFCToolBar 단추 재정의::OnAddTo 사용자 지정 페이지.)](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)|
|`CMFCToolBarEditBoxButton::OnCalculateSize`|지정된 장치 컨텍스트 및 도킹 상태에 대한 단추 크기를 계산하기 위해 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::계산 크기.)](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)|
|[CMFCToolBar 편집 상자 버튼::에 변경 부모](#onchangeparentwnd)|단추를 새 도구 모음에 삽입할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnChangeParentWnd.)](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)|
|[CMFCToolBar 편집 상자 버튼::에 클릭](#onclick)|사용자가 마우스 단추를 클릭할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnClick.)](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)|
|[CMFCToolBar 편집 상자 버튼 ::온CtlColor](#onctlcolor)|상위 도구 모음에서 WM_CTLCOLOR 메시지를 처리할 때 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::OnCtlColor.)](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)|
|`CMFCToolBarEditBoxButton::OnDraw`|지정된 스타일과 옵션을 사용하여 단추를 그리는 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::온드로우.)](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw)|
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|**사용자 지정 대화** 상자의 명령 창에서 단추를 그리는 프레임워크에서 **호출합니다.** [(CMFCToolBar 단추 재정의:OnDrawOn 사용자 지정 목록.)](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)|
|[CMFCToolBar 편집 상자 버튼:::온글로벌폰트변경](#onglobalfontschanged)|전역 글꼴이 변경된 경우 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::온글로벌폰트 변경.)](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)|
|[CMFCToolBar 편집 상자 버튼::이동 중](#onmove)|상위 도구 모음이 이동할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnMove.)](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)|
|[CMFCToolBar 편집 상자 버튼::에 표시](#onshow)|단추를 표시 하거나 보이지 않는 될 때 프레임 워크에 의해 호출 됩니다. [(CMFCToolBar 단추 재정의::OnShow.)](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)|
|[CMFCToolBar 편집 상자 버튼::OnSize](#onsize)|상위 도구 모음의 크기 또는 위치를 변경하고 이 변경으로 인해 단추크기가 변경될 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnSize.)](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)|
|[CMFCToolBar 편집 상자 단추::업데이트 도구 팁](#onupdatetooltip)|상위 도구 모음이 도구 설명 텍스트를 업데이트할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarEditBoxButton::Serialize`|이 개체를 아카이브에서 읽거나 아카이브에 씁니다. [(CMFCToolBar 단추 재정의::직렬화.)](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)|
|`CMFCToolBarEditBoxButton::SetACCData`|제공된 `CAccessibilityData` 개체에 도구 모음 단추의 내게 필요한 옵션 데이터를 채웁니다. [(CMFCToolBar 단추 재정의::SetACCData.)](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata)|
|`CMFCToolBarEditBoxButton::`[CMFCToolBar 편집 상자 버튼::세트 콘텐츠](#setcontents)|단추의 편집 컨트롤에서 텍스트를 설정합니다.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBar 편집 상자 버튼::설정 콘텐츠모두](#setcontentsall)|지정된 명령 ID가 있는 편집 제어 단추를 찾아 해당 단추의 편집 컨트롤에서 텍스트를 설정합니다.|
|[CMFCToolBar 편집 상자 단추::설정 컨텍스트메뉴ID](#setcontextmenuid)|단추와 연결된 바로 가기 메뉴의 리소스 ID를 지정합니다.|
|[CMFCToolBar 편집 상자 버튼::세트플랫모드](#setflatmode)|응용 프로그램에서 편집 상자 단추의 플랫 스타일 모양을 지정합니다.|
|`CMFCToolBarEditBoxButton::`[CMFCToolBar 편집 상자 버튼::세트 스타일](#setstyle)|단추의 스타일을 지정합니다. [(CMFCToolBar 단추 재정의::세트 스타일.)](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)|

## <a name="remarks"></a>설명

도구 모음에 편집 상자 단추를 추가하려면 다음 단계를 따르세요.

1. 부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다.

2. 개체를 `CMFCToolBarEditBoxButton` 생성합니다.

3. AFX_WM_RESETTOOLBAR 메시지를 처리하는 메시지 처리기에서 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)을 사용하여 더미 단추를 새 콤보 상자 단추로 바꿉습니다.

자세한 내용은 [연습: 도구 모음에 컨트롤 넣기](../../mfc/walkthrough-putting-controls-on-toolbars.md)를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CMFCToolBarEditBoxButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 사용자가 사용자 지정 중에 단추를 늘릴 수 있도록 지정하고, 사용자가 단추를 클릭할 때 단추의 테두리가 표시되도록 지정하고, 텍스트 상자 컨트롤에서 텍스트를 설정하고, 응용 프로그램에서 편집 상자 단추의 플랫 스타일 모양을 지정하고, 도구 모음 편집 상자 컨트롤의 스타일을 지정하는 방법을 보여 주며, 단추의 테두리가 표시됩니다.

[!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

`CMFCToolBarEditBoxButton`

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbareditboxbutton.h

## <a name="cmfctoolbareditboxbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBar 편집 상자 버튼 ::수 있습니다

사용자 지정 하는 동안 단추를 늘릴 수 있는지 여부를 지정 합니다.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Return Value

이 메서드는 TRUE를 반환합니다.

### <a name="remarks"></a>설명

기본적으로 프레임워크는 사용자가 사용자 지정 하는 동안 도구 모음 단추를 늘릴 수 없습니다. 이 메서드는 사용자가 사용자 지정 하는 동안 편집 상자 도구 모음 단추를 늘릴 수 있도록 기본 클래스 구현 [(CMFCToolBarButton::CanBeStretched)를](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)확장 합니다.

## <a name="cmfctoolbareditboxbuttoncmfctoolbareditboxbutton"></a><a name="cmfctoolbareditboxbutton"></a>CMFCToolBar 편집 상자 단추:::CMFCToolBar 편집 상자 단추

[CMFCToolBar편집상자단추](../../mfc/reference/cmfctoolbareditboxbutton-class.md) 개체를 생성합니다.

```
CMFCToolBarEditBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=ES_AUTOHSCROLL,
    int iWidth=0);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
【인】 컨트롤 ID를 지정합니다.

*아이 이미지*<br/>
【인】 도구 모음 이미지의 0기반 인덱스를 지정합니다. 이미지는 CMFCToolBar 클래스클래스가 유지 관리하는 [CMFCToolBarImages 클래스](../../mfc/reference/cmfctoolbarimages-class.md) [개체에](../../mfc/reference/cmfctoolbar-class.md) 있습니다.

*dwStyle*<br/>
【인】 편집 컨트롤 스타일을 지정합니다.

*아이 폭*<br/>
【인】 편집 컨트롤의 픽셀 너비를 지정합니다.

### <a name="remarks"></a>설명

기본 생성자는 편집 컨트롤 스타일을 다음 조합으로 설정합니다.

WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL

컨트롤의 기본 너비는 150픽셀입니다.

## <a name="cmfctoolbareditboxbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBar 편집 상자 버튼::복사에서

다른 도구 모음 단추의 속성을 현재 단추에 복사합니다.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
【인】 복사할 소스 단추에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 다른 도구 모음 단추를 이 도구 모음 단추에 복사합니다. *src는* 유형이어야합니다 `CMFCToolBarEditBoxButton`.

## <a name="cmfctoolbareditboxbuttoncreateedit"></a><a name="createedit"></a>CMFCToolBar 편집 상자 단추::만들기 편집

단추에 새 편집 컨트롤을 만듭니다.

```
virtual CEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 편집 컨트롤의 상위 창을 지정합니다. NULL이 아니어야 합니다.

*rect*<br/>
【인】 편집 컨트롤의 크기와 위치를 지정합니다.

### <a name="return-value"></a>Return Value

새로 생성된 편집 컨트롤에 대한 포인터입니다. 컨트롤의 생성 및 첨부 파일이 실패하면 NULL입니다.

### <a name="remarks"></a>설명

두 단계로 `CMFCToolBarEditBoxButton` 객체를 생성합니다. 먼저 생성자 호출 한 `CreateEdit`다음 Windows 편집 컨트롤을 만들고 `CMFCToolBarEditBoxButton` 개체에 연결 하는 을 호출 합니다.

## <a name="cmfctoolbareditboxbuttongetbycmd"></a><a name="getbycmd"></a>CMFCToolBar 편집 상자 버튼::GetByCmd

지정된 명령 `CMFCToolBarEditBoxButton` ID가 있는 응용 프로그램의 첫 번째 개체를 검색합니다.

```
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 검색할 단추의 명령 ID입니다.

### <a name="return-value"></a>Return Value

지정된 `CMFCToolBarEditBoxButton` 명령 ID가 있는 응용 프로그램의 첫 번째 개체 또는 NULL(해당 개체가 없는 경우)입니다.

### <a name="remarks"></a>설명

이 공유 유틸리티 방법은 [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) 및 [CMFCToolBarEditBoxButton::GetContentsAll모든](#getcontentsall) 지정된 명령 ID가 있는 첫 번째 편집 상자 도구 모음 컨트롤의 텍스트를 설정하거나 가져옵니다.

## <a name="cmfctoolbareditboxbuttongetcontentsall"></a><a name="getcontentsall"></a>CMFCToolBar 편집 상자 버튼::GetContentall

지정된 명령 ID가 있는 첫 번째 편집 상자 도구 모음 컨트롤의 텍스트를 검색합니다.

```
static CString __stdcall GetContentsAll(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 내용을 검색할 단추의 명령 ID입니다.

### <a name="return-value"></a>Return Value

지정된 `CString` 명령 ID가 있는 첫 번째 편집 상자 도구 모음 컨트롤의 텍스트가 포함된 개체입니다.

### <a name="remarks"></a>설명

이 메서드는 지정된 명령 `CMFCToolBarEditBoxButton` ID가 있는 개체가 없는 경우 빈 문자열을 반환합니다.

## <a name="cmfctoolbareditboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>CMFCToolBar 편집 상자 단추::GetContextMenuID

단추와 연결된 바로 가기 메뉴의 리소스 ID를 검색합니다.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Return Value

단추에 연결된 바로 가기 메뉴가 없는 경우 단추 또는 0과 연결된 바로 가기 메뉴의 리소스 ID입니다.

### <a name="remarks"></a>설명

프레임워크는 리소스 ID를 사용하여 사용자가 단추를 마우스 오른쪽 단추를 클릭할 때 바로 가기 메뉴를 만듭니다.

## <a name="cmfctoolbareditboxbuttongeteditborder"></a><a name="geteditborder"></a>CMFCToolBar 편집 상자 버튼::GetEditBorder

편집 상자 단추의 편집 부분의 경계 사각형을 검색합니다.

```
virtual void GetEditBorder(CRect& rectBorder);
```

### <a name="parameters"></a>매개 변수

*직류 국경*<br/>
【아웃】 경계 사각형을 `CRect` 받는 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드는 클라이언트 좌표에서 편집 컨트롤의 경계 사각형을 검색합니다. 각 방향의 사각형 크기를 1픽셀씩 확장합니다.

[CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) 메서드는 개체 주위에 테두리를 그릴 `CMFCToolBarEditBoxButton` 때 이 메서드를 호출합니다.

## <a name="cmfctoolbareditboxbuttongeteditbox"></a><a name="geteditbox"></a>CMFCToolBar 편집 상자 버튼::GetEditBox

단추에 포함된 [CEdit 클래스](../../mfc/reference/cedit-class.md) 컨트롤에 대한 포인터를 반환합니다.

```
CEdit* GetEditBox() const;
```

### <a name="return-value"></a>Return Value

단추에 포함 된 [CEdit 클래스](../../mfc/reference/cedit-class.md) 컨트롤에 대 한 포인터입니다. `CEdit` 컨트롤이 아직 만들어지지 않은 경우 NULL입니다.

### <a name="remarks"></a>설명

`CEdit` [CMFCToolBar편집상자 단추::만들기 편집을](#createedit)호출하여 컨트롤을 만듭니다.

## <a name="cmfctoolbareditboxbuttongethwnd"></a><a name="gethwnd"></a>CMFCToolBar 편집 상자 버튼::GetHwnd

도구 모음 단추와 연결된 창 핸들을 검색합니다.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Return Value

단추와 연결된 창 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 편집 상자 단추의 편집 컨트롤 부분의 창 핸들을 반환 하 여 [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) 메서드를 재정의 합니다.

## <a name="cmfctoolbareditboxbuttongetinvalidaterect"></a><a name="getinvalidaterect"></a>CMFCToolBar 편집 상자 버튼::Get무효화렉트

다시 그려야 하는 단추의 클라이언트 영역영역을 검색합니다.

```
virtual const CRect GetInvalidateRect() const;
```

### <a name="return-value"></a>Return Value

다시 `CRect` 그려야 하는 영역을 지정하는 개체입니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 [합니다CMFCToolBarButton::GetInvalidateRect,](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect)지역에 텍스트 레이블의 영역을 포함 하 여.

## <a name="cmfctoolbareditboxbuttonhavehotborder"></a><a name="havehotborder"></a>CMFCToolBar 편집 상자 버튼::하핫보더

사용자가 단추를 클릭할 때 단추의 테두리가 표시되는지 여부를 결정합니다.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Return Value

버튼을 선택하면 테두리가 표시되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 하는 [CMFCToolBarButton::HaveHotBorder,](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder)컨트롤이 표시 되는 경우 비 영값을 반환 하 여.

## <a name="cmfctoolbareditboxbuttonisflatmode"></a><a name="isflatmode"></a>CMFCToolBar 편집 상자 버튼 ::IsFlatmode

편집 상자 단추에 플랫 스타일이 있는지 여부를 결정합니다.

```
static BOOL __stdcall IsFlatMode();
```

### <a name="return-value"></a>Return Value

버튼이 플랫 스타일을 가지고 있는 경우 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본적으로 편집 상자 단추는 플랫 스타일을 갖습니다. [CMFCToolBar 편집 상자 단추::SetFlatMode](#setflatmode) 메서드를 사용 하 여 응용 프로그램에 대 한 플랫 스타일 모양을 변경 합니다.

## <a name="cmfctoolbareditboxbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBar 편집 상자 단추::알림 명령

단추에서 [WM_COMMAND](/windows/win32/menurc/wm-command) 메시지를 처리하는지 여부를 지정합니다.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>매개 변수

*iNotifyCode*<br/>
【인】 명령과 연결된 알림 메시지입니다.

### <a name="return-value"></a>Return Value

TRUE 단추WM_COMMAND 메시지를 처리 하는 경우 또는 FALSE 메시지를 상위 도구 모음에서 처리 해야 합니다 나타냅니다.

### <a name="remarks"></a>설명

프레임워크는 부모 창에 [WM_COMMAND](/windows/win32/menurc/wm-command) 메시지를 보내려고 할 때 이 메서드를 호출합니다.

이 메서드는 [EN_UPDATE](/windows/win32/Controls/en-update) 알림을 처리 하 여 기본 클래스 구현 [(CMFCToolBarButton::NotifyCommand)를](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)확장 합니다. 이 개체와 동일한 명령 ID를 가진 각 편집 상자에 대해 텍스트 레이블을 이 개체의 텍스트 레이블로 설정합니다.

## <a name="cmfctoolbareditboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBar 편집 상자 버튼::OnAddTo 사용자 정의 페이지

단추를 **사용자 지정** 대화 상자에 추가 될 때 프레임 워크에 의해 호출 됩니다.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 [(CMFCToolBarButton::OnAddToCustomizePage)](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)이 개체와 동일한 명령 ID를 가지고 있는 모든 도구 모음에서 편집 상자 컨트롤에서 속성을 복사 하 여. 이 메서드는 이 개체와 동일한 명령 ID를 사용하는 편집 상자 컨트롤이 있는 도구 모음이 없는 경우 아무 작업도 수행하지 않습니다.

**사용자 지정** 대화 상자에 대한 자세한 내용은 [CMFCToolBar사용자 지정 Dialog 클래스](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)를 참조하십시오.

## <a name="cmfctoolbareditboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBar 편집 상자 버튼::에 변경 부모

단추를 새 도구 모음에 삽입할 때 프레임워크에서 호출됩니다.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 새 부모 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 내부 `CEdit` 개체를 다시 만들어 기본 클래스 구현(CMFCToolBarButton::OnChangeParentWnd)을 재정의합니다. [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)

## <a name="cmfctoolbareditboxbuttononclick"></a><a name="onclick"></a>CMFCToolBar 편집 상자 버튼::에 클릭

사용자가 마우스 단추를 클릭할 때 프레임워크에서 호출됩니다.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 하지 않는.

*bDelay*<br/>
【인】 하지 않는.

### <a name="return-value"></a>Return Value

버튼이 클릭 메시지를 처리하는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 내부 `CEdit` 개체가 표시되는 경우 0이 아닌 값을 반환하여 기본 클래스 구현(CMFCToolBarButton::OnClick)을 재정의합니다. [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)

## <a name="cmfctoolbareditboxbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBar 편집 상자 버튼 ::온CtlColor

상위 도구 모음에서 WM_CTLCOLOR 메시지를 처리할 때 프레임워크에서 호출합니다.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 단추를 표시 하는 장치 컨텍스트입니다.

*nCtlColor*<br/>
【인】 하지 않는.

### <a name="return-value"></a>Return Value

전역 창 브러시의 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 제공된 장치 컨텍스트의 텍스트 와 배경 색을 전역 텍스트 및 배경 색으로 각각 설정 하여 기본 클래스 [구현(CMFCToolBarButton::OnCtlColor)을](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)재정의합니다.

응용 프로그램에서 사용할 수 있는 전역 옵션에 대한 자세한 내용은 [AFX_GLOBAL_DATA Structure](../../mfc/reference/afx-global-data-structure.md)를 참조하십시오.

## <a name="cmfctoolbareditboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBar 편집 상자 버튼:::온글로벌폰트변경

전역 글꼴이 변경된 경우 프레임워크에서 호출합니다.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 [(CMFCToolBarButton::OnGlobalFonts변경)](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)전역 글꼴의 컨트롤의 글꼴을 변경 하 여.

응용 프로그램에서 사용할 수 있는 전역 옵션에 대한 자세한 내용은 [AFX_GLOBAL_DATA Structure](../../mfc/reference/afx-global-data-structure.md)를 참조하십시오.

## <a name="cmfctoolbareditboxbuttononmove"></a><a name="onmove"></a>CMFCToolBar 편집 상자 버튼::이동 중

상위 도구 모음이 이동할 때 프레임워크에서 호출됩니다.

```
virtual void OnMove();
```

### <a name="remarks"></a>설명

이 메서드는 내부 `CEdit` 개체의 위치를 업데이트 하여 기본 클래스 구현(CMFCToolBarButton::OnMove)을 재정의합니다. [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)

## <a name="cmfctoolbareditboxbuttononshow"></a><a name="onshow"></a>CMFCToolBar 편집 상자 버튼::에 표시

단추를 표시 하거나 보이지 않는 될 때 프레임 워크에 의해 호출 됩니다.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
【인】 단추를 볼 수 있는지 여부를 지정합니다. 이 매개 변수가 TRUE이면 단추가 표시됩니다. 그렇지 않으면 단추가 표시되지 않습니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 [(CMFCToolBarButton::OnShow)](../../mfc/reference/cmfctoolbarbutton-class.md#onshow) *bShow* TRUE 인 경우 단추를 표시 하 여. 그렇지 않으면 이 메서드는 단추를 숨깁니다.

## <a name="cmfctoolbareditboxbuttononsize"></a><a name="onsize"></a>CMFCToolBar 편집 상자 버튼::OnSize

상위 도구 모음의 크기 또는 위치를 변경하고 이 변경으로 인해 단추크기가 변경될 때 프레임워크에서 호출됩니다.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>매개 변수

*아이 사이즈*<br/>
【인】 단추의 새 너비(픽셀)입니다.

### <a name="remarks"></a>설명

이 메서드는 내부 `CEdit` 개체의 크기와 위치를 업데이트하여 기본 클래스 [구현인 CMFCToolBarButton::OnSize를](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)재정의합니다.

## <a name="cmfctoolbareditboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBar 편집 상자 단추::업데이트 도구 팁

상위 도구 모음이 도구 설명 텍스트를 업데이트할 때 프레임워크에서 호출됩니다.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 하지 않는.

*아이 버튼 인덱스*<br/>
【인】 하지 않는.

*wndToolTip*<br/>
【인】 도구 설명 텍스트를 표시하는 컨트롤입니다.

*Str*<br/>
【아웃】 업데이트된 도구 설명 텍스트를 받는 `CString` 개체입니다.

### <a name="return-value"></a>Return Value

메서드가 도구 설명 텍스트를 업데이트하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 단추의 편집 부분과 연결된 도구 설명 텍스트를 표시하여 기본 클래스 [구현(CMFCToolBarButton::OnUpdateToolTip)을](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)확장합니다. 내부 `CEdit` 개체가 NULL이거나 `CEdit` 개체의 창 핸들이 기존 창을 식별하지 않는 경우 이 메서드는 아무 작업도 수행하지 않고 FALSE를 반환합니다.

## <a name="cmfctoolbareditboxbuttonsetcontents"></a><a name="setcontents"></a>CMFCToolBar 편집 상자 버튼::세트 콘텐츠

텍스트 상자 컨트롤에서 텍스트를 설정합니다.

```
virtual void SetContents(const CString& sContents);
```

### <a name="parameters"></a>매개 변수

*scontents*<br/>
【인】 설정할 새 텍스트를 지정합니다.

## <a name="cmfctoolbareditboxbuttonsetcontentsall"></a><a name="setcontentsall"></a>CMFCToolBar 편집 상자 버튼::설정 콘텐츠모두

지정된 명령 ID가 있는 [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) 개체를 찾아 텍스트 상자 내에서 지정된 텍스트를 설정합니다.

```
static BOOL SetContentsAll(
    UINT uiCmd,
    const CString& strContents);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 텍스트가 변경될 컨트롤의 명령 ID를 지정합니다.

*스트콘텐츠*<br/>
【인】 설정할 새 텍스트를 지정합니다.

### <a name="return-value"></a>Return Value

텍스트가 설정된 경우 0이 아닙니다. 지정된 명령 `CMFCToolBarEditBoxButton` ID가 있는 컨트롤이 없는 경우 0입니다.

## <a name="cmfctoolbareditboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>CMFCToolBar 편집 상자 단추::설정 컨텍스트메뉴ID

단추와 연결된 바로 가기 메뉴의 리소스 ID를 지정합니다.

```cpp
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 바로 가기 메뉴의 리소스 ID입니다.

### <a name="remarks"></a>설명

프레임워크는 리소스 ID를 사용하여 사용자가 도구 모음 단추를 마우스 오른쪽 단추로 클릭할 때 바로 가기 메뉴를 만듭니다.

## <a name="cmfctoolbareditboxbuttonsetflatmode"></a><a name="setflatmode"></a>CMFCToolBar 편집 상자 버튼::세트플랫모드

응용 프로그램에서 편집 상자 단추의 플랫 스타일 모양을 지정합니다.

```
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```

### <a name="parameters"></a>매개 변수

*b플랫*<br/>
【인】 편집 상자 단추의 플랫 스타일입니다. 이 매개변수가 TRUE이면 플랫 스타일 모양이 활성화됩니다. 그렇지 않으면 플랫 스타일 모양이 비활성화됩니다.

### <a name="remarks"></a>설명

편집 상자 단추의 기본 플랫 스타일은 TRUE입니다. [CMFCToolBar편집박스버튼::IsFlatMode](#isflatmode) 방법을 사용하여 응용 프로그램의 플랫 스타일 모양을 검색합니다.

## <a name="cmfctoolbareditboxbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBar 편집 상자 버튼::세트 스타일

도구 모음 편집 상자 컨트롤의 스타일을 지정합니다.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*nStyle*<br/>
【인】 설정할 새 스타일입니다.

### <a name="remarks"></a>설명

이 메서드는 [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) *nStyle응용* 프로그램이 사용자 지정 모드에 있을 때 텍스트 상자를 비활성화하고 응용 프로그램이 사용자 지정 모드에 없을 때 활성화합니다(CMFCToolBar:SetCustomizeMode 및 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)참조). [CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) 유효한 스타일 플래그 목록은 [도구 모음 컨트롤 스타일을](../../mfc/reference/toolbar-control-styles.md) 참조하십시오.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CEdit 클래스](../../mfc/reference/cedit-class.md)<br/>
[CMFC툴바::대체 버튼](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)
