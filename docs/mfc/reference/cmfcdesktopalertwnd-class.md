---
title: CMFCDesktopAlertWnd Class
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
ms.openlocfilehash: cf453b6e69f012bedaf0bd91b5eaf11f7caffa12
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752453"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class

클래스는 `CMFCDesktopAlertWnd` 이벤트에 대해 사용자에게 알리기 위해 화면에 나타나는 모덜리스 대화 상자의 기능을 구현합니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCDesktopAlertWnd : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC데스크톱경고::만들기](#create)|데스크톱 경고 창을 만들고 초기화합니다.|
|[CMFC데스크톱경고::겟애니메이션스피드](#getanimationspeed)|애니메이션 속도를 반환합니다.|
|[CMFC데스크톱경고::겟애니메이션타입](#getanimationtype)|애니메이션 형식을 반환합니다.|
|[CMFC데스크톱 경고::GetAutoCloseTime](#getautoclosetime)|자동 닫기 시간 시간을 반환합니다.|
|[CMFC데스크톱경고::겟캡션높이](#getcaptionheight)|캡션의 높이를 반환합니다.|
|[CMFC데스크톱경고::GetDialogSize](#getdialogsize)||
|[CMFC데스크톱 경고::겟라스트포스](#getlastpos)|화면에서 바탕 화면 경고 창의 마지막 유효한 위치를 반환합니다.|
|[CMFC데스크톱경고::투명성 얻기](#gettransparency)|투명도 수준을 반환합니다.|
|[CMFC데스크톱경고::하스스몰 캡션](#hassmallcaption)|데스크톱 경고 창이 작은 캡션으로 표시되는지 여부를 결정합니다.|
|[CMFC데스크톱 경고::OnBeforeShow](#onbeforeshow)||
|[CMFC데스크톱 경고::온클릭링크버튼](#onclicklinkbutton)|사용자가 데스크톱 경고 메뉴에 있는 링크 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CMFC데스크톱경고::온커맨드](#oncommand)|프레임워크는 사용자가 메뉴에서 항목을 선택하거나, 자식 컨트롤이 알림 메시지를 보낼 때 또는 가속기 키 입력이 번역될 때 이 멤버 함수를 호출합니다. [(CWnd 재정의::OnCommand.)](../../mfc/reference/cwnd-class.md#oncommand)|
|[CMFC데스크톱 경고::온드로우](#ondraw)||
|[CMFC데스크톱경고: :P로세스커맨드](#processcommand)||
|[CMFC데스크톱경고::셋애니메이션스피드](#setanimationspeed)|새 애니메이션 속도를 설정합니다.|
|[CMFC데스크톱경고::세트애니메이션타입](#setanimationtype)|애니메이션 유형을 설정합니다.|
|[CMFC데스크톱 경고::SetAutoCloseTime](#setautoclosetime)|자동 닫기 시간 시간을 설정합니다.|
|[CMFC데스크톱 경고::세트캡션](#setsmallcaption)|작은 캡션과 일반 캡션 간에 전환합니다.|
|[CMFC데스크톱경고::설정투명도](#settransparency)|투명도 수준을 설정합니다.|

## <a name="remarks"></a>설명

데스크톱 경고 창은 투명할 수 있고 애니메이션 효과와 함께 나타날 수 있으며( 지정된 지연 후 또는 사용자가 닫기 단추를 클릭하여 해제할 때) 사라질 수 있습니다.

데스크톱 경고 창에는 아이콘, 메시지 텍스트(레이블) 및 링크가 포함된 기본 대화 상자도 포함될 수 있습니다. 또는 데스크톱 경고 창에 응용 프로그램의 리소스에서 사용자 지정 대화 상자가 포함될 수 있습니다.

두 단계로 데스크톱 경고 창을 만듭니다. 먼저 생성자 호출하여 개체를 생성합니다. `CMFCDesktopAlertWnd` 둘째, [CMFCDesktopAlertWnd::Create](#create) 멤버 함수를 호출하여 창을 만들고 `CMFCDesktopAlertWnd` 개체에 연결합니다.

개체는 `CMFCDesktopAlertWnd` 데스크톱 경고 창의 클라이언트 영역을 채우는 특수 자식 대화 상자를 만듭니다. 대화 상자에 배치된 모든 컨트롤을 제어합니다.

팝업 창에 사용자 지정 대화 상자를 표시하려면 다음 단계를 따르세요.

1. `CMFCDesktopAlertDialog`에서 클래스를 파생합니다.

1. 리소스에서 자식 대화 상자 템플릿을 만듭니다.

1. [CMFCDesktopAlertWnd::대화](#create) 상자 템플릿의 리소스 ID와 파생 된 클래스의 런타임 클래스 정보에 대 한 포인터를 사용 하 여 만들기

1. 사용자 지정 대화 상자를 프로그래밍하여 호스팅된 컨트롤에서 오는 모든 알림을 처리하거나 호스팅된 컨트롤을 프로그래밍하여 이러한 알림을 직접 처리합니다.

다음 기능을 사용하여 데스크톱 경고 창의 동작을 제어합니다.

- [CMFCDesktopAlertWnd::SetAnimationType을](#setanimationtype)호출하여 애니메이션 유형을 설정합니다. 유효한 옵션에는 전개, 슬라이드 및 페이드가 포함됩니다.

- [CMFCDesktopAlertWnd::SetAnimationSpeed를](#setanimationspeed)호출하여 애니메이션 프레임 속도를 설정합니다.

- [CMFCDesktopAlertWnd::Set투명도를](#settransparency)호출하여 투명도 수준을 설정합니다.

- [CMFCDesktopAlertWnd::SetSmallCaption을](#setsmallcaption)호출하여 캡션의 크기를 작게 변경합니다. 작은 캡션은 7 픽셀 높이입니다.

## <a name="example"></a>예제

다음 예제에서는 클래스에서 다양한 메서드를 `CMFCDesktopAlertWnd` 사용하여 개체를 `CMFCDesktopAlertWnd` 구성하는 방법을 보여 줍니다. 이 예제에서는 애니메이션 유형을 설정하고, 팝업 창의 투명도를 설정하고, 경고 창에 작은 캡션이 표시되도록 지정하고, 경고 창이 자동으로 닫히기 전에 경과되는 시간을 설정하는 방법을 보여 줍니다. 또한 이 예제에서는 데스크톱 경고 창을 만들고 초기화하는 방법을 보여 줍니다. 이 코드 조각은 데스크톱 [경고 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDesktopAlertWnd.h

## <a name="cmfcdesktopalertwndcreate"></a><a name="create"></a>CMFC데스크톱경고::만들기

데스크톱 경고 창을 만들고 초기화합니다.

```
virtual BOOL Create(
    CWnd* pWndOwner,
    UINT uiDlgResID,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1),
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

virtual BOOL Create(
    CWnd* pWndOwner,
    CMFCDesktopAlertWndInfo& params,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1));
```

### <a name="parameters"></a>매개 변수

*pWnd소유자*<br/>
【인, 아웃】 경고 창의 소유자를 지정합니다. 그러면 해당 소유자는 데스크톱 경고 창에 대한 모든 알림을 받게 됩니다. 이 값은 NULL일 수 없습니다.

*uiDlgResID*<br/>
【인】 경고 창의 리소스 ID를 지정합니다.

*Hmenu*<br/>
【인】 사용자가 메뉴 단추를 클릭할 때 표시되는 메뉴를 지정합니다. NULL이면 메뉴 단추가 표시되지 않습니다.

*ptPos*<br/>
【인】 화면 좌표를 사용하여 경고 창이 표시되는 초기 위치를 지정합니다. 이 매개 변수가 (-1, -1)이면 경고 창이 화면의 오른쪽 아래 모서리에 표시됩니다.

*pRTIDlgBar*<br/>
【인】 경고 창의 클라이언트 영역을 포함하는 사용자 지정 대화 상자 클래스에 대한 런타임 클래스 정보입니다.

*params*<br/>
【인】 경고 창을 만드는 데 사용되는 매개 변수를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 경고 창이 성공적으로 생성된 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 경고 창을 만듭니다. 경고 창의 클라이언트 영역에는 사용자에게 표시되는 모든 컨트롤을 호스트하는 자식 대화 상자가 포함되어 있습니다.

첫 번째 메서드 오버로드는 응용 프로그램의 리소스에서 로드되는 자식 대화 상자를 포함하는 경고 창을 만듭니다. 첫 번째 메서드 오버로드는 사용자 지정 대화 상자 클래스에 대한 런타임 클래스 정보를 지정할 수도 있습니다.

두 번째 메서드 오버로드는 기본 컨트롤을 포함하는 경고 창을 만듭니다. [CMFCDesktopAlertWndInfo 클래스를](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)수정하여 표시할 컨트롤을 지정할 수 있습니다.

## <a name="cmfcdesktopalertwndgetanimationspeed"></a><a name="getanimationspeed"></a>CMFC데스크톱경고::겟애니메이션스피드

애니메이션 속도를 반환합니다.

```
UINT GetAnimationSpeed() const;
```

### <a name="return-value"></a>Return Value

경고 창의 애니메이션 속도(밀리초)입니다.

### <a name="remarks"></a>설명

애니메이션 속도는 경고 창이 열리고 닫히는 속도를 설명합니다.

## <a name="cmfcdesktopalertwndgetanimationtype"></a><a name="getanimationtype"></a>CMFC데스크톱경고::겟애니메이션타입

애니메이션 형식을 반환합니다.

```
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```

### <a name="return-value"></a>Return Value

다음 애니메이션 유형 중 하나:

- NO_ANIMATION

- 전개

- 슬라이드

- 페이드

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndgetautoclosetime"></a><a name="getautoclosetime"></a>CMFC데스크톱 경고::GetAutoCloseTime

자동 닫기 시간 시간을 반환합니다.

```
int GetAutoCloseTime() const;
```

### <a name="return-value"></a>Return Value

시간(밀리초)이 면 경고 창이 자동으로 닫힙입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 경고 창이 자동으로 닫히기 전에 경과 해야 하는 시간을 결정 합니다.

## <a name="cmfcdesktopalertwndgetcaptionheight"></a><a name="getcaptionheight"></a>CMFC데스크톱경고::겟캡션높이

캡션의 높이를 반환합니다.

```
virtual int GetCaptionHeight();
```

### <a name="return-value"></a>Return Value

캡션의 높이(픽셀 단위)입니다.

### <a name="remarks"></a>설명

이 메서드는 파생 된 클래스에서 재정의할 수 있습니다. 기본 구현 중 하나: 팝업 창에 작은 캡션또는 Windows API 함수에서 `GetSystemMetrics(SM_CYSMCAPTION)`가져온 값을 표시 해야 하는 경우 작은 캡션 높이 값 (7 픽셀)를 반환 합니다.

## <a name="cmfcdesktopalertwndgetlastpos"></a><a name="getlastpos"></a>CMFC데스크톱 경고::겟라스트포스

화면에서 바탕 화면 경고 창의 마지막 위치를 반환합니다.

```
CPoint GetLastPos() const;
```

### <a name="return-value"></a>Return Value

화면 좌표의 점입니다.

### <a name="remarks"></a>설명

이 메서드는 화면에 경고 창의 마지막 유효한 위치를 반환 합니다.

## <a name="cmfcdesktopalertwndgettransparency"></a><a name="gettransparency"></a>CMFC데스크톱경고::투명성 얻기

투명도 수준을 반환합니다.

```
BYTE GetTransparency() const;
```

### <a name="return-value"></a>Return Value

0에서 255 사이의 투명도 수준(포함)입니다. 값이 클수록 창이 더 불투명해지다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 경고 창의 현재 투명도 수준을 검색합니다.

## <a name="cmfcdesktopalertwndhassmallcaption"></a><a name="hassmallcaption"></a>CMFC데스크톱경고::하스스몰 캡션

데스크톱 경고 창에 작은 캡션이 있는지 또는 일반 크기의 캡션이 있는지 여부를 결정합니다.

```
BOOL HasSmallCaption() const;
```

### <a name="return-value"></a>Return Value

TRUE 팝업 창이 작은 캡션으로 표시되는 경우 팝업 창이 일반 크기의 캡션으로 표시되는 경우 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 팝업 창에 작은 캡션이 있는지 또는 일반 크기의 캡션이 있는지 확인합니다. 기본적으로 작은 캡션은 7픽셀 높이입니다. Windows API 함수를 `GetSystemMetrics(SM_CYCAPTION)`호출하여 일반 크기 캡션의 높이를 가져올 수 있습니다.

## <a name="cmfcdesktopalertwndonbeforeshow"></a><a name="onbeforeshow"></a>CMFC데스크톱 경고::OnBeforeShow

```
virtual BOOL OnBeforeShow(CPoint&);
```

### <a name="parameters"></a>매개 변수

【인】 *포인트&*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcdesktopalertwndonclicklinkbutton"></a><a name="onclicklinkbutton"></a>CMFC데스크톱 경고::온클릭링크버튼

사용자가 데스크톱 경고 메뉴에 있는 링크 단추를 클릭할 때 프레임워크에서 호출됩니다.

```
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```

### <a name="parameters"></a>매개 변수

*uiCmdID*<br/>
【인】 이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>Return Value

항상 FALSE입니다.

### <a name="remarks"></a>설명

사용자가 경고 창에서 링크를 클릭할 때 알림을 받으면 파생 클래스에서 이 메서드를 재정의합니다.

## <a name="cmfcdesktopalertwndoncommand"></a><a name="oncommand"></a>CMFC데스크톱경고::온커맨드

```
virtual BOOL OnCommand(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

【인】 *wParam*<br/>

【인】 *l파라임*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcdesktopalertwndondraw"></a><a name="ondraw"></a>CMFC데스크톱 경고::온드로우

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcdesktopalertwndprocesscommand"></a><a name="processcommand"></a>CMFC데스크톱경고: :P로세스커맨드

```
BOOL ProcessCommand(HWND hwnd);
```

### <a name="parameters"></a>매개 변수

【인】 *hwnd*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcdesktopalertwndsetanimationspeed"></a><a name="setanimationspeed"></a>CMFC데스크톱경고::셋애니메이션스피드

새 애니메이션 속도를 설정합니다.

```cpp
void SetAnimationSpeed(UINT nSpeed);
```

### <a name="parameters"></a>매개 변수

*n 속도*<br/>
【인】 새 애니메이션 속도를 밀리초 단위로 지정합니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 경고 창의 애니메이션 속도를 설정합니다. 기본 애니메이션 속도는 30밀리초입니다.

## <a name="cmfcdesktopalertwndsetanimationtype"></a><a name="setanimationtype"></a>CMFC데스크톱경고::세트애니메이션타입

애니메이션 유형을 설정합니다.

```cpp
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```

### <a name="parameters"></a>매개 변수

*type*<br/>
【인】 애니메이션 유형을 지정합니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 애니메이션 유형을 설정합니다. 다음 값 중 하나를 지정할 수 있습니다.

- NO_ANIMATION

- 전개

- 슬라이드

- 페이드

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndsetautoclosetime"></a><a name="setautoclosetime"></a>CMFC데스크톱 경고::SetAutoCloseTime

자동 닫기 시간 시간을 설정합니다.

```cpp
void SetAutoCloseTime(int nTime);
```

### <a name="parameters"></a>매개 변수

*n시간*<br/>
【인】 경고 창이 자동으로 닫히기 전에 경과하는 시간(밀리초)입니다.

### <a name="remarks"></a>설명

사용자가 창과 상호 작용하지 않으면 지정된 시간 이후에 경고 창이 자동으로 닫힙니까.

## <a name="cmfcdesktopalertwndsetsmallcaption"></a><a name="setsmallcaption"></a>CMFC데스크톱 경고::세트캡션

작은 캡션과 일반 크기 캡션 간에 전환합니다.

```cpp
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```

### <a name="parameters"></a>매개 변수

*b스몰 캡션*<br/>
【인】 TRUE는 경고 창에 작은 캡션을 표시하도록 지정합니다. 그렇지 않으면 FALSE경고 창에 일반 크기 캡션이 표시되도록 지정합니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 작은 또는 일반 크기의 캡션을 표시합니다. 기본적으로 작은 캡션은 7픽셀 높이입니다. Windows API 함수를 `GetSystemMetrics(SM_CYCAPTION)`호출하여 일반 캡션의 크기를 가져올 수 있습니다.

## <a name="cmfcdesktopalertwndsettransparency"></a><a name="settransparency"></a>CMFC데스크톱경고::설정투명도

팝업 창의 투명도 수준을 설정합니다.

```cpp
void SetTransparency(BYTE nTransparency);
```

### <a name="parameters"></a>매개 변수

*n투명도*<br/>
【인】 투명도 수준을 지정합니다. 이 값은 0에서 255 사이여야 합니다( 포함). 값이 클수록 창이 더 불투명해지다.

### <a name="remarks"></a>설명

이 함수를 호출하여 팝업 창의 투명도 수준을 설정합니다.

## <a name="cmfcdesktopalertwndgetdialogsize"></a><a name="getdialogsize"></a>CMFC데스크톱경고::GetDialogSize

```
virtual CSize GetDialogSize();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC데스크탑경고폰드정보 클래스](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CMFC데스크탑경고디아로그 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)
