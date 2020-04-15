---
title: CMFCToolBarDateTimeCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
helpviewer_keywords:
- CMFCToolBarDateTimeCtrl [MFC], CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], CanBeStretched
- CMFCToolBarDateTimeCtrl [MFC], CopyFrom
- CMFCToolBarButton [MFC], ExportToMenuButton
- CMFCToolBarDateTimeCtrl [MFC], GetByCmd
- CMFCToolBarDateTimeCtrl [MFC], GetDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], GetHwnd
- CMFCToolBarDateTimeCtrl [MFC], GetTime
- CMFCToolBarDateTimeCtrl [MFC], GetTimeAll
- CMFCToolBarDateTimeCtrl [MFC], HaveHotBorder
- CMFCToolBarDateTimeCtrl [MFC], NotifyCommand
- CMFCToolBarDateTimeCtrl [MFC], OnAddToCustomizePage
- CMFCToolBarDateTimeCtrl [MFC], OnChangeParentWnd
- CMFCToolBarDateTimeCtrl [MFC], OnClick
- CMFCToolBarDateTimeCtrl [MFC], OnCtlColor
- CMFCToolBarDateTimeCtrl [MFC], OnGlobalFontsChanged
- CMFCToolBarDateTimeCtrl [MFC], OnMove
- CMFCToolBarDateTimeCtrl [MFC], OnShow
- CMFCToolBarDateTimeCtrl [MFC], OnUpdateToolTip
- CMFCToolBarDateTimeCtrl [MFC], SetTime
- CMFCToolBarDateTimeCtrl [MFC], SetTimeAll
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
ms.openlocfilehash: 9aebd55f19a6687554d8d8378ef84ed5932025a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372171"
---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl 클래스

날짜 및 시간 선택기 컨트롤이 포함된 도구 모음 단추입니다.

## <a name="syntax"></a>구문

```
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCToolBarDate타임Ctrl:::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|`CMFCToolBarDateTimeCtrl` 개체를 생성합니다.|
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCToolBarDate타임Ctrl::캔스트레치](#canbestretched)|사용자 지정 하는 동안 단추를 늘릴 수 있는지 여부를 지정 합니다. [(CMFCToolBar 단추 재정의::캔스트라이드.)](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)|
|[CMFCToolBarDateTimeCtrl::복사에서](#copyfrom)|다른 도구 모음 단추의 속성을 현재 단추에 복사합니다. [(CMFCToolBar 단추 재정의::복사에서.)](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|다음에 사용하도록 예약됩니다.|
|[CMFCToolBar 단추::내보내기 메뉴 단추](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|도구 모음 단추에서 메뉴로 텍스트를 복사합니다.|
|`CMFCToolBarDateTimeCtrl::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFCToolBarDate타임Ctrl::GetByCmd](#getbycmd)|지정된 명령 `CMFCToolBarDateTimeCtrl` ID가 있는 응용 프로그램의 첫 번째 개체를 검색합니다.|
|[CMFCToolBarDate타임Ctrl::GetDateTimeCtrl](#getdatetimectrl)|날짜 및 시간 선택기 컨트롤에 대한 포인터를 반환합니다.|
|[CMFCToolBarDate타임Ctrl::GetHwnd](#gethwnd)|도구 모음 단추와 연결된 창 핸들을 검색합니다. [(CMFCToolBar 단추 재정의::GetHwnd.)](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd)|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFCToolBarDate타임Ctrl::GetTime](#gettime)|날짜 및 시간 선택기 컨트롤에서 선택한 시간을 가져옵니다 및 지정 된 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 두고.|
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|지정된 명령 ID가 있는 시간 선택 기 제어 단추에서 선택한 시간을 반환합니다.|
|[CMFC툴바데이트타임트rl::하핫보더](#havehotborder)|사용자가 단추를 선택할 때 단추의 테두리가 표시되는지 여부를 결정합니다. [(CMFCToolBar 단추 재정의::하핫보더.)](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder)|
|[CMFCToolBarDate시간Ctrl::알림 명령](#notifycommand)|단추에서 [WM_COMMAND](/windows/win32/menurc/wm-command) 메시지를 처리하는지 여부를 지정합니다. [(CMFCToolBar 단추 재정의::알림 명령.)](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)|
|[CMFCToolBarDate타임Ctrl::OnAddTo 사용자 정의 페이지](#onaddtocustomizepage)|단추를 **사용자 지정** 대화 상자에 추가 될 때 프레임 워크에 의해 호출 됩니다. [(CMFCToolBar 단추 재정의::OnAddTo 사용자 지정 페이지.)](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|지정된 장치 컨텍스트 및 도킹 상태에 대한 단추 크기를 계산하기 위해 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::계산 크기.)](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)|
|[CMFCToolBarDate타임Ctrl::OnChangeParentWnd](#onchangeparentwnd)|단추를 새 도구 모음에 삽입할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnChangeParentWnd.)](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)|
|[CMFCToolBarDate시간Ctrl::OnClick](#onclick)|사용자가 컨트롤을 클릭할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnClick.)](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)|
|[CMFCToolBarDate타임Ctrl::온CtlColor](#onctlcolor)|상위 도구 모음에서 WM_CTLCOLOR 메시지를 처리할 때 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::OnCtlColor.)](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)|
|`CMFCToolBarDateTimeCtrl::OnDraw`|지정된 스타일과 옵션을 사용하여 단추를 그리는 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::온드로우.)](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|**사용자 지정 대화** 상자의 명령 창에서 단추를 그리는 프레임워크에서 **호출합니다.** [(CMFCToolBar 단추 재정의:OnDrawOn 사용자 지정 목록.)](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)|
|[CMFCToolBarDate타임Ctrl:::온글로벌폰트변경](#onglobalfontschanged)|전역 글꼴이 변경된 경우 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::온글로벌폰트 변경.)](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)|
|[CMFCToolBarDate타임Ctrl::OnMove](#onmove)|상위 도구 모음이 이동할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnMove.)](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)|
|[CMFC툴바데이트타임트럴::온쇼](#onshow)|단추를 표시 하거나 보이지 않는 될 때 프레임 워크에 의해 호출 됩니다. [(CMFCToolBar 단추 재정의::OnShow.)](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)|
|`CMFCToolBarDateTimeCtrl::OnSize`|상위 도구 모음의 크기 또는 위치를 변경하고 이 변경으로 인해 단추크기가 변경될 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnSize.)](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)|
|[CMFCToolBarDate타임Ctrl::OnUpdateToolTip](#onupdatetooltip)|상위 도구 모음이 도구 설명 텍스트를 업데이트할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarDateTimeCtrl::Serialize`|아카이브에서 이 개체를 읽거나 아카이브에 [기록합니다(CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)재사용.)|
|`CMFCToolBarDateTimeCtrl::SetStyle`|도구 모음 단추의 스타일을 설정합니다. [(CMFCToolBar 단추 재정의::세트 스타일.)](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)|
|[CMFCToolBarDate시간Ctrl::설정 시간](#settime)|시간 선택기 컨트롤에서 시간과 날짜를 설정합니다.|
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|지정된 명령 ID가 있는 시간 선택 기 컨트롤의 모든 인스턴스에서 시간과 날짜를 설정합니다.|

## <a name="remarks"></a>설명

날짜 및 시간 선택기 컨트롤을 사용하는 방법에 대한 예제는 ToolbarDateTimePicker 샘플 프로젝트를 참조하십시오. 도구 모음에 컨트롤 단추를 추가하는 방법에 대한 자세한 내용은 [연습: 도구 모음에 컨트롤 넣기](../../mfc/walkthrough-putting-controls-on-toolbars.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFC툴바데이트타임Ctrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbardatetimectrl.h

## <a name="cmfctoolbardatetimectrlcanbestretched"></a><a name="canbestretched"></a>CMFCToolBarDate타임Ctrl::캔스트레치

사용자 지정 하는 동안 단추를 늘릴 수 있는지 여부를 지정 합니다.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Return Value

이 메서드는 TRUE를 반환합니다.

### <a name="remarks"></a>설명

기본적으로 프레임워크는 사용자가 사용자 지정 하는 동안 도구 모음 단추를 늘릴 수 없습니다. 이 메서드는 사용자가 사용자 지정 하는 동안 날짜 및 시간 도구 모음 단추를 늘릴 수 있도록 기본 클래스 구현 [(CMFCToolBarButton::CanBeStretched)를](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)확장 합니다.

## <a name="cmfctoolbardatetimectrlcmfctoolbardatetimectrl"></a><a name="cmfctoolbardatetimectrl"></a>CMFCToolBarDate타임Ctrl:::CMFCToolBarDateTimeCtrl

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) 개체를 만들고 초기화합니다.

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
【인】 컨트롤 ID입니다.

*아이 이미지*<br/>
【인】 도구 모음 개체의 이미지 인덱스입니다. `CMFCToolBarImages`

*dwStyle*<br/>
【인】 사용자가 단추를 `CMFCToolBarDateTimeCtrlImpl` 클릭할 때 생성되는 창의 스타일입니다.

*아이 폭*<br/>
【인】 컨트롤의 너비(픽셀)입니다.

### <a name="remarks"></a>설명

이 개체는 시스템 날짜 및 시간으로 초기화됩니다. 내부 `CMFCToolBarDateTimeCtrlImpl` 객체의 창 스타일에는 *dwStyle* 매개 변수와 WS_CHILD 및 WS_VISIBLE 스타일이 포함됩니다. 을 사용하여 `CMFCToolBarDateTimeCtrl::SetStyle`이러한 스타일을 변경할 수 없습니다. 컨트롤의 스타일을 변경하는 데 사용합니다. `SetStyle` `CMFCToolBarDateTimeCtrl`

### <a name="example"></a>예제

다음 예제에서는 `CMFCToolBarDateTimeCtrl` 클래스의 개체를 생성 하는 방법을 보여 줍니다. 이 코드 조각은 도구 [모음 날짜 시간 선택기 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

## <a name="cmfctoolbardatetimectrlcopyfrom"></a><a name="copyfrom"></a>CMFCToolBarDateTimeCtrl::복사에서

다른 도구 모음 단추의 속성을 현재 단추에 복사합니다.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>매개 변수

*Src*<br/>
【인】 복사할 소스 단추에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 다른 도구 모음 단추를 이 도구 모음 단추에 복사합니다. *src는* 유형이어야합니다 `CMFCToolBarDateTimeCtrl`.

## <a name="cmfctoolbardatetimectrlexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolBarDate타임Ctrl::내보내기 메뉴 단추

도구 모음 단추에서 메뉴로 텍스트를 복사합니다.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>매개 변수

*메뉴 버튼*<br/>
【인】 대상 메뉴 단추에 대한 참조입니다.

### <a name="return-value"></a>Return Value

이 메서드는 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 컨트롤의 명령 ID와 연결 된 문자열 리소스를 로드 하 여 기본 클래스 구현 [(CMFCToolBarButton::ExportToMenuButton)를](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)재정의 합니다. 문자열 리소스에 대한 자세한 내용은 [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring)을 참조하십시오.

## <a name="cmfctoolbardatetimectrlgetbycmd"></a><a name="getbycmd"></a>CMFCToolBarDate타임Ctrl::GetByCmd

지정된 명령 `CMFCToolBarDateTimeCtrl` ID가 있는 응용 프로그램의 첫 번째 개체를 검색합니다.

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 검색할 단추의 명령 ID입니다.

### <a name="return-value"></a>Return Value

지정된 `CMFCToolBarDateTimeCtrl` 명령 ID가 있는 응용 프로그램의 첫 번째 `CMFCToolBarDateTimeCtrl` 개체 또는 지정된 명령 ID가 있는 개체가 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 공유 유틸리티 메서드는 [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) 및 [CMFCToolBarDateTimeCtrl::GetTimeAll과](#gettimeall) 같은 메서드에서 사용되며 지정된 명령 ID가 있는 시간 선택기 컨트롤의 모든 인스턴스의 시간과 날짜를 설정하거나 가져옵니다.

## <a name="cmfctoolbardatetimectrlgetdatetimectrl"></a><a name="getdatetimectrl"></a>CMFCToolBarDate타임Ctrl::GetDateTimeCtrl

날짜 및 시간 선택기 컨트롤에 대한 포인터를 반환합니다.

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>Return Value

날짜 및 시간 선택기 컨트롤에 대한 포인터; 또는 NULL 컨트롤이 없는 경우

### <a name="remarks"></a>설명

도구 `CMFCToolBarDateTimeCtrl` 모음에 개체를 `m_pWndDateTime` 삽입할 때 `CMFCToolBarDateTimeCtrl` 클래스는 데이터 멤버를 초기화합니다.

## <a name="cmfctoolbardatetimectrlgethwnd"></a><a name="gethwnd"></a>CMFCToolBarDate타임Ctrl::GetHwnd

도구 모음 단추와 연결된 창 핸들을 검색합니다.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Return Value

날짜 및 시간 도구 모음 단추와 연결된 창 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 [CMFCToolBarButton::GetHwnd 메서드를 재정의합니다.](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd)

## <a name="cmfctoolbardatetimectrlgettime"></a><a name="gettime"></a>CMFCToolBarDate타임Ctrl::GetTime

연결된 날짜 및 시간 선택기 컨트롤에서 선택한 시간을 가져옵니다 및 지정된 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 넣습니다.

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>매개 변수

*timeDest*<br/>
【아웃】 첫 번째 오버로드에서 시스템 시간 정보를 수신하는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 개체입니다. 두 번째 오버로드에서 시스템 시간 정보를 수신하는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체입니다.

*p시간*<br/>
【아웃】 시스템 시간 정보를 수신하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다. NULL이 아니어야 합니다.

### <a name="return-value"></a>Return Value

첫 번째 오버로드에서 시간이 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 개체에 성공적으로 기록된 경우 0이 아닌 경우 그렇지 않으면 0. 두 번째 및 세 번째 오버로드에서 반환 값은 [NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) 구조에 설정된 dwFlag 멤버와 동일한 DWORD입니다.

### <a name="remarks"></a>설명

메서드는 날짜 및 시간 선택기가 날짜 및 시간으로 설정되어 있는지 여부를 표시하도록 [NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) 구조 멤버 dwFlags를 설정합니다. 값이 GDT_NONE 같으면 컨트롤이 `no date` 상태로 설정되고 DTS_SHOWNONE 스타일을 사용합니다. 반환된 값이 GDT_VALID 같으면 시스템 시간이 대상 위치에 성공적으로 저장됩니다.

## <a name="cmfctoolbardatetimectrlgettimeall"></a><a name="gettimeall"></a>CMFCToolBarDateTimeCtrl::GetTimeAll

지정된 명령 ID가 있는 시간 선택기 제어 단추에서 사용자가 선택한 시간을 반환합니다.

```
static BOOL GetTimeAll(
    UINT uiCmd,
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeDest);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 도구 모음 단추의 명령 ID를 지정합니다.

*timeDest*<br/>
【아웃】 첫 번째 오버로드에서 시스템 시간 정보를 수신하는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 개체입니다. 두 번째 오버로드에서 시스템 시간 정보를 수신하는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체입니다.

*p시간*<br/>
【아웃】 시스템 시간 정보를 수신하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다. NULL이 아니어야 합니다.

### <a name="return-value"></a>Return Value

프레임워크에서 명령 ID *uiCmd와*일치하는 도구 모음 단추를 찾을 수 없는 경우 반환 값은 첫 번째 오버로드에서 0이고 다른 오버로드에서 GDT_NONE. 도구 모음 단추를 찾은 경우 반환 값은 해당 단추의 [CMFCToolBarDateTimeCtrl::GetTime에](#gettime) 대한 호출에서 반환 값과 동일합니다. 단추를 찾을 때 반환 값이 0 또는 GDT_NONE 발생할 수 `GetTime` 있습니다., 다른 이유로 유효한 날짜를 반환 하지 않은 호출을 나타냅니다.

### <a name="remarks"></a>설명

이 메서드는 지정된 명령 ID를 가지고 있고 해당 단추에서 [CMFCToolBarDateTimeCtrl::GetTime](#gettime) 메서드를 호출하는 도구 모음 단추를 찾습니다.

## <a name="cmfctoolbardatetimectrlhavehotborder"></a><a name="havehotborder"></a>CMFC툴바데이트타임트rl::하핫보더

사용자가 단추를 선택할 때 단추의 테두리가 표시되는지 여부를 결정합니다.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Return Value

버튼을 선택하면 테두리가 표시되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 컨트롤이 표시 되는 경우 비영 값을 반환 합니다.

## <a name="cmfctoolbardatetimectrlnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarDate시간Ctrl::알림 명령

단추에서 [WM_COMMAND](/windows/win32/menurc/wm-command) 메시지를 처리하는지 여부를 지정합니다.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>매개 변수

*iNotifyCode*<br/>
【인】 명령과 연결된 알림 메시지입니다.

### <a name="return-value"></a>Return Value

TRUE 단추WM_COMMAND 메시지를 처리 하는 경우 또는 FALSE 메시지를 상위 도구 모음에서 처리 해야 함을 나타냅니다.

### <a name="remarks"></a>설명

프레임워크는 부모 창에 [WM_COMMAND](/windows/win32/menurc/wm-command) 메시지를 보내려고 할 때 이 메서드를 호출합니다.

이 메서드는 [DTN_DATETIMECHANGE](/windows/win32/Controls/dtn-datetimechange) 알림을 처리 하 여 기본 클래스 구현 [(CMFCToolBarButton::NotifyCommand)를](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)확장 합니다. 내부 시간 상태를 업데이트하고 동일한 명령 `CMFCToolBarDateTimeCtrl` ID를 가진 모든 개체의 시간 속성을 업데이트합니다.

## <a name="cmfctoolbardatetimectrlonaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarDate타임Ctrl::OnAddTo 사용자 정의 페이지

단추를 **사용자 지정** 대화 상자에 추가 될 때 프레임 워크에 의해 호출 됩니다.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장, [CMFCToolBarButton::OnAddToCustomizePage,](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)이 개체와 동일한 명령 ID를 가지고 있는 모든 도구 모음에서 첫 번째 날짜 및 시간 컨트롤에서 속성을 복사 하 여. 이 메서드는 이 개체와 동일한 명령 ID를 사용하는 날짜 및 시간 컨트롤이 있는 도구 모음이 없는 경우 아무 작업도 수행하지 않습니다.

**사용자 지정** 대화 상자에 대한 자세한 내용은 [CMFCToolBar사용자 지정 Dialog 클래스](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)를 참조하십시오.

## <a name="cmfctoolbardatetimectrlonchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarDate타임Ctrl::OnChangeParentWnd

단추를 새 도구 모음에 삽입할 때 프레임워크에서 호출됩니다.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 새 부모 창입니다.

### <a name="remarks"></a>설명

이 메서드는 내부 `CMFCToolBarDateTimeCtrlImpl` 개체를 다시 만들어 기본 클래스 구현(CMFCToolBarButton::OnChangeParentWnd)을 재정의합니다. [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)

## <a name="cmfctoolbardatetimectrlonclick"></a><a name="onclick"></a>CMFCToolBarDate시간Ctrl::OnClick

사용자가 컨트롤을 클릭할 때 프레임워크에서 호출됩니다.

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

이 메서드는 기본 클래스 구현, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), 내부 `CMFCToolBarDateTimeCtrlImpl` 개체가 표시 되는 경우 비영값을 반환 하 여 재정의 합니다.

## <a name="cmfctoolbardatetimectrlonctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarDate타임Ctrl::온CtlColor

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

프레임워크가 단추의 배경을 그리는 데 사용하는 전역 브러시에 대한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현, [CMFCToolBarButton::OnCtlColor,](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)제공된 장치 컨텍스트의 텍스트 및 배경 색을 전역 텍스트 및 배경 색으로 각각 설정 하여 재정의합니다.

응용 프로그램에서 사용할 수 있는 전역 옵션에 대한 자세한 내용은 [AFX_GLOBAL_DATA Structure](../../mfc/reference/afx-global-data-structure.md)를 참조하십시오.

## <a name="cmfctoolbardatetimectrlonglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarDate타임Ctrl:::온글로벌폰트변경

전역 글꼴이 변경된 경우 프레임워크에서 호출합니다.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 [(CMFCToolBarButton::OnGlobalFonts변경)](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)전역 글꼴의 컨트롤의 글꼴을 변경 하 여.

응용 프로그램에서 사용할 수 있는 전역 옵션에 대한 자세한 내용은 [AFX_GLOBAL_DATA Structure](../../mfc/reference/afx-global-data-structure.md)를 참조하십시오.

## <a name="cmfctoolbardatetimectrlonmove"></a><a name="onmove"></a>CMFCToolBarDate타임Ctrl::OnMove

상위 도구 모음이 이동할 때 프레임워크에서 호출됩니다.

```
virtual void OnMove();
```

### <a name="remarks"></a>설명

이 메서드는 내부 `CMFCToolBarDateTimeCtrlImpl` 개체의 위치를 업데이트하여 기본 클래스 구현(CMFCToolBarButton::OnMove)을 재정의합니다. [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)

## <a name="cmfctoolbardatetimectrlonshow"></a><a name="onshow"></a>CMFC툴바데이트타임트럴::온쇼

단추를 표시 하거나 보이지 않는 될 때 프레임 워크에 의해 호출 됩니다.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
【인】 단추를 볼 수 있는지 여부를 지정합니다. 이 매개 변수가 TRUE이면 단추가 표시됩니다. 그렇지 않으면 단추가 표시되지 않습니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 [(CMFCToolBarButton::OnShow)](../../mfc/reference/cmfctoolbarbutton-class.md#onshow) *bShow* TRUE 인 경우 단추를 표시 하 여. 그렇지 않으면 이 메서드는 단추를 숨깁니다.

## <a name="cmfctoolbardatetimectrlonsize"></a><a name="onsize"></a>CMFCToolBarDate타임Ctrl::OnSize

상위 도구 모음의 크기 또는 위치를 변경하고 이 변경으로 인해 단추크기가 변경될 때 프레임워크에서 호출됩니다.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>매개 변수

*아이 사이즈*<br/>
【인】 단추의 새 너비(픽셀)입니다.

### <a name="remarks"></a>설명

이 메서드는 내부 `CMFCToolBarDateTimeCtrlImpl` 개체의 크기와 위치를 업데이트하여 기본 클래스 구현(CMFCToolBarButton::OnSize)을 재정의합니다. [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)

## <a name="cmfctoolbardatetimectrlonupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarDate타임Ctrl::OnUpdateToolTip

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
【인】 상위 창입니다.

*아이 버튼 인덱스*<br/>
【인】 상위 단추 컬렉션에서 단추의 0 기반 인덱스입니다.

*wndToolTip*<br/>
【인】 도구 설명 텍스트를 표시하는 컨트롤입니다.

*Str*<br/>
【아웃】 업데이트된 도구 설명 텍스트를 받는 `CString` 개체입니다.

### <a name="return-value"></a>Return Value

메서드가 도구 설명 텍스트를 업데이트하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 단추와 연결 된 도구 설명 텍스트를 표시 하 여 기본 클래스 구현 [(CMFCToolBarButton::OnUpdateToolTip)를](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)확장 합니다. 단추를 가로로 도킹되지 않은 경우 이 메서드는 아무 것도 수행하지 않고 FALSE를 반환합니다.

## <a name="cmfctoolbardatetimectrlsettime"></a><a name="settime"></a>CMFCToolBarDate시간Ctrl::설정 시간

시간 선택기 컨트롤에서 시간과 날짜를 설정합니다.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>매개 변수

*시간새*<br/>
【인】 첫 번째 버전에서는 컨트롤이 설정되는 시간을 포함하는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 개체에 대한 참조입니다. 두 번째 버전에서는 컨트롤을 설정할 시간을 포함하는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 포인터입니다.

*pTimeNew*<br/>
【인】 컨트롤을 설정할 시간을 포함하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

[CDateTimeCtrl::SetTime을](../../mfc/reference/cdatetimectrl-class.md#settime)호출하여 날짜 및 시간 선택기 컨트롤의 시간을 설정합니다.

## <a name="cmfctoolbardatetimectrlsettimeall"></a><a name="settimeall"></a>CMFCToolBarDateTimeCtrl::SetTimeAll

지정된 명령 ID가 있는 시간 선택 기 컨트롤의 모든 인스턴스에서 시간과 날짜를 설정합니다.

```
static BOOL SetTimeAll(
    UINT uiCmd,
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 도구 모음 단추의 명령 ID를 지정합니다.

*시간새*<br/>
【인】 첫 번째 버전에서는 컨트롤이 설정되는 시간을 포함하는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 개체입니다. 두 번째 버전에서는 컨트롤을 설정할 시간을 포함하는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 포인터입니다.

*pTimeNew*<br/>
【인】 컨트롤을 설정할 시간을 포함하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정된 명령 ID가 있는 도구 모음 단추를 찾고 [CMFCToolBarDateTimeCtrl::SetTime을](#settime)호출하여 날짜 및 시간 선택기 컨트롤의 시간을 설정합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)
