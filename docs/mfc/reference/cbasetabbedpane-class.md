---
title: CBaseTabbedPane 클래스
ms.date: 11/04/2016
f1_keywords:
- CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::AddTab
- AFXBASETABBEDPANE/CBaseTabbedPane::AllowDestroyEmptyTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::ApplyRestoredTabInfo
- AFXBASETABBEDPANE/CBaseTabbedPane::CanFloat
- AFXBASETABBEDPANE/CBaseTabbedPane::CanSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::ConvertToTabbedDocument
- AFXBASETABBEDPANE/CBaseTabbedPane::DetachPane
- AFXBASETABBEDPANE/CBaseTabbedPane::EnableSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::FillDefaultTabsOrderArray
- AFXBASETABBEDPANE/CBaseTabbedPane::FindBarByTabNumber
- AFXBASETABBEDPANE/CBaseTabbedPane::FindPaneByID
- AFXBASETABBEDPANE/CBaseTabbedPane::FloatTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetDefaultTabsOrder
- AFXBASETABBEDPANE/CBaseTabbedPane::GetFirstVisibleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetMinSize
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneIcon
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneList
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabArea
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::GetUnderlyingWindow
- AFXBASETABBEDPANE/CBaseTabbedPane::GetVisibleTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::HasAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::IsHideSingleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::RecalcLayout
- AFXBASETABBEDPANE/CBaseTabbedPane::RemovePane
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoDestroy
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::ShowTab
helpviewer_keywords:
- CBaseTabbedPane [MFC], AddTab
- CBaseTabbedPane [MFC], AllowDestroyEmptyTabbedPane
- CBaseTabbedPane [MFC], ApplyRestoredTabInfo
- CBaseTabbedPane [MFC], CanFloat
- CBaseTabbedPane [MFC], CanSetCaptionTextToTabName
- CBaseTabbedPane [MFC], ConvertToTabbedDocument
- CBaseTabbedPane [MFC], DetachPane
- CBaseTabbedPane [MFC], EnableSetCaptionTextToTabName
- CBaseTabbedPane [MFC], FillDefaultTabsOrderArray
- CBaseTabbedPane [MFC], FindBarByTabNumber
- CBaseTabbedPane [MFC], FindPaneByID
- CBaseTabbedPane [MFC], FloatTab
- CBaseTabbedPane [MFC], GetDefaultTabsOrder
- CBaseTabbedPane [MFC], GetFirstVisibleTab
- CBaseTabbedPane [MFC], GetMinSize
- CBaseTabbedPane [MFC], GetPaneIcon
- CBaseTabbedPane [MFC], GetPaneList
- CBaseTabbedPane [MFC], GetTabArea
- CBaseTabbedPane [MFC], GetTabsNum
- CBaseTabbedPane [MFC], GetUnderlyingWindow
- CBaseTabbedPane [MFC], GetVisibleTabsNum
- CBaseTabbedPane [MFC], HasAutoHideMode
- CBaseTabbedPane [MFC], IsHideSingleTab
- CBaseTabbedPane [MFC], RecalcLayout
- CBaseTabbedPane [MFC], RemovePane
- CBaseTabbedPane [MFC], SetAutoDestroy
- CBaseTabbedPane [MFC], SetAutoHideMode
- CBaseTabbedPane [MFC], ShowTab
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
ms.openlocfilehash: b3ae0d69c385ba89cf75d682ce12c6f1f4e5112f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752974"
---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane 클래스

[CDockablePane Class](../../mfc/reference/cdockablepane-class.md) 의 기능을 확장하여 탭 창 만들기를 지원합니다.

## <a name="syntax"></a>구문

```
class CBaseTabbedPane : public CDockablePane
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CBaseTabbedPane::CBaseTabbedPane`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CBaseTabbedPane::추가 탭](#addtab)|탭된 창에 새 탭을 추가합니다.|
|[CBaseTabbedPane::허용파괴빈탭판](#allowdestroyemptytabbedpane)|빈 탭창을 파기할 수 있는지 여부를 지정합니다.|
|[CBaseTabbedPane::적용복원탭정보](#applyrestoredtabinfo)|레지스트리에서 로드된 탭 설정을 탭창에 적용합니다.|
|[CBaseTabbedPane::캔플로트](#canfloat)|창이 부동할 수 있는지 여부를 결정합니다. [(CBasePane 재정의::캔플로팅.)](../../mfc/reference/cbasepane-class.md#canfloat)|
|[CBaseTabbedPane::캔세트캡션텍스트To탭네임](#cansetcaptiontexttotabname)|탭된 창의 캡션이 활성 탭과 동일한 텍스트를 표시할지 여부를 결정합니다.|
|[CBaseTabbedPane::변환토탭문서](#converttotabbeddocument)|[(CDockablePane 재정의::변환토탭문서.)](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument)|
|[CBaseTabbedPane::D에타흐파네](#detachpane)|하나 이상의 도킹 가능한 창을 MDI 탭 된 문서로 변환합니다.|
|[CBaseTabbedPane::인에이블세트캡션텍스트토탭네이름](#enablesetcaptiontexttotabname)|탭된 창이 활성 탭의 레이블 텍스트와 캡션 텍스트를 동기화하는 기능을 활성화하거나 사용하지 않도록 설정합니다.|
|[CBaseTabbedPane::채우기기본탭순서배열](#filldefaulttabsorderarray)|내부 탭 순서를 기본 상태로 복원합니다.|
|[CBaseTabbedPane::찾기바비탭번호](#findbarbytabnumber)|탭이 0기반 탭 인덱스로 식별될 때 탭에 있는 창을 반환합니다.|
|||
|[CBaseTabbedPane::찾기파인비ID](#findpanebyid)|창 ID로 식별된 창을 반환합니다.|
|[CBaseTabbedPane::플로트탭](#floattab)|창이 현재 분리 가능한 탭에 있는 경우에만 창을 부동합니다.|
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|창에서 탭의 기본 순서를 반환합니다.|
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|첫 번째 표시된 탭에 대한 포인터를 검색합니다.|
|[CBaseTabbedPane::GetMinSize](#getminsize)|창에 대해 허용되는 최소 크기를 검색합니다. [(재정의 CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|창 아이콘에 핸들을 반환합니다. [(재정의 CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|
|[CBaseTabbedPane::GetPaneList](#getpanelist)|탭된 창에 포함된 창 목록을 반환합니다.|
|[CBaseTabbedPane::GetTabarea](#gettabarea)|위쪽 및 아래쪽 탭 영역에 대한 경계 사각형을 반환합니다.|
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|탭 창에서 탭 수를 반환합니다.|
|[CBaseTabbedPane::GetBaseWindow](#getunderlyingwindow)|기본(래핑) 탭 창을 가져옵니다.|
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|표시된 탭 수를 반환합니다.|
|[CBaseTabbedPane::하스오토하이드모드](#hasautohidemode)|탭된 창을 자동 숨기기 모드로 전환할 수 있는지 여부를 결정합니다.|
|[CBaseTabbedPane::이하이드싱글탭](#ishidesingletab)|탭이 하나만 표시되는 경우 탭창이 숨겨져 있는지 여부를 결정합니다.|
|`CBaseTabbedPane::LoadSiblingPaneIDs`|직렬화 하는 동안 내부적으로 사용 됩니다.|
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|창에 대한 레이아웃 정보를 다시 계산합니다. [(재정의 CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|
|[CBaseTabbedPane::제거파네](#removepane)|탭된 창에서 창을 제거합니다.|
|`CBaseTabbedPane::SaveSiblingBarIDs`|직렬화 하는 동안 내부적으로 사용 됩니다.|
|`CBaseTabbedPane::Serialize`|[(CDockablePane 재정의::직렬화.)](cdockablepane-class.md)|
|`CBaseTabbedPane::SerializeTabWindow`|직렬화 하는 동안 내부적으로 사용 됩니다.|
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|탭된 컨트롤 막대가 자동으로 소멸될지 여부를 결정합니다.|
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|도킹 창을 표시된 모드와 자동 숨기기 모드 간에 전환합니다. [(디도킹파인 재정의::SetAutoHideMode.)](../../mfc/reference/cdockablepane-class.md#setautohidemode)|
|[CBaseTabbedPane::쇼탭](#showtab)|탭을 표시하거나 숨깁니다.|

## <a name="remarks"></a>설명

이 클래스는 추상 클래스이며 인스턴스화할 수 없습니다. 모든 종류의 탭된 창에 공통적인 서비스를 구현합니다.

현재 라이브러리에는 [CTabbedPane 클래스와](../../mfc/reference/ctabbedpane-class.md) [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)클래스의 두 가지 파생 탭 창 클래스가 포함되어 있습니다.

`CBaseTabbedPane` 개체는 [CMFCBaseTabCtrl 클래스](../../mfc/reference/cmfcbasetabctrl-class.md) 개체에 대한 포인터를 래핑합니다. [CMFCBaseTabCtrl 클래스는](../../mfc/reference/cmfcbasetabctrl-class.md) 탭된 창의 자식 창이 됩니다.

탭된 창을 만드는 방법에 대한 자세한 내용은 [CDockablePane 클래스,](../../mfc/reference/cdockablepane-class.md) [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md)및 [CMFCOutlookBar 클래스를](../../mfc/reference/cmfcoutlookbar-class.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

`CBaseTabbedPane`

## <a name="requirements"></a>요구 사항

**헤더:** afxBaseTabbedPane.h

## <a name="cbasetabbedpaneaddtab"></a><a name="addtab"></a>CBaseTabbedPane::추가 탭

탭된 창에 새 탭을 추가합니다.

```
virtual BOOL AddTab(
    CWnd* pNewBar,
    BOOL bVisible = TRUE,
    BOOL bSetActive = TRUE,
    BOOL bDetachable = TRUE);
```

### <a name="parameters"></a>매개 변수

*p뉴바*<br/>
【인, 아웃】 추가할 창에 대한 포인터입니다. 이 메서드를 호출한 후 이 포인터가 잘못 될 수 있습니다. 자세한 내용은 주의 섹션을 참조하세요.

*bVisible*<br/>
【인】 TRUE 탭을 표시하려면 그렇지 않으면 false입니다.

*bSetActive*<br/>
【인】 TRUE 탭을 활성 탭으로 만듭니다. 그렇지 않으면 false입니다.

*bDetachable*<br/>
【인】 TRUE탭을 분리가능하게 만들기 위해; 그렇지 않으면 false입니다.

### <a name="return-value"></a>Return Value

TRUE 창이 탭으로 성공적으로 추가되었고 그 과정에서 소멸되지 않은 경우. FALSE 추가 창이 형식의 `CBaseTabbedPane`개체인 경우 false 입니다. 자세한 내용은 주의 섹션을 참조하세요.

### <a name="remarks"></a>설명

탭된 창에 창을 새 탭으로 추가하려면 이 메서드를 호출합니다. *pNewBar가* 형식의 `CBaseTabbedPane`개체를 가리키면 모든 탭이 탭된 창에 복사된 다음 *pNewBar가* 소멸됩니다. 따라서 *pNewBar는* 잘못된 포인터가 되므로 사용해서는 안 됩니다.

## <a name="cbasetabbedpaneallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a>CBaseTabbedPane::허용파괴빈탭판

빈 탭창을 파기할 수 있는지 여부를 지정합니다.

```
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Return Value

빈 탭 창을 파괴 할 수있는 경우 TRUE; 그렇지 않으면 false입니다. 기본 구현은 항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

빈 탭된 창을 삭제할 수 없는 경우 프레임워크는 창을 대신 숨깁니다.

## <a name="cbasetabbedpaneapplyrestoredtabinfo"></a><a name="applyrestoredtabinfo"></a>CBaseTabbedPane::적용복원탭정보

레지스트리에서 탭 설정을 로드하고 탭된 창에 적용합니다.

```
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```

### <a name="parameters"></a>매개 변수

*bUseTabIndexes*<br/>
【인】 이 매개 변수는 프레임워크에서 내부적으로 사용됩니다.

### <a name="remarks"></a>설명

이 메서드는 레지스트리에서 도킹 상태 정보를 다시 로드할 때 프레임워크에서 호출됩니다. 이 메서드는 탭창의 탭 순서 및 탭 이름에 대한 정보를 가져옵니다.

## <a name="cbasetabbedpanecanfloat"></a><a name="canfloat"></a>CBaseTabbedPane::캔플로트

탭된 창이 부동할 수 있는지 여부를 지정합니다.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Return Value

TRUE 창이 부동 할 수 있는 경우; 그렇지 않으면 false입니다.

## <a name="cbasetabbedpanecansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a>CBaseTabbedPane::캔세트캡션텍스트To탭네임

탭된 창의 캡션이 활성 탭과 동일한 텍스트를 표시할지 여부를 결정합니다.

```
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Return Value

TRUE 탭창의 캡션 텍스트가 활성 탭의 텍스트로 설정된 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 탭된 창 캡션에 표시된 텍스트가 활성 탭의 레이블을 복제하는지 여부를 확인하는 데 사용됩니다. [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)을 호출하여 이 기능을 활성화하거나 비활성화할 수 있습니다.

## <a name="cbasetabbedpaneconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CBaseTabbedPane::변환토탭문서

하나 이상의 도킹 가능한 창을 MDI 탭 된 문서로 변환합니다.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>매개 변수

*bActiveTab전용*<br/>
【인】 탭된 창을 변환할 때 TRUE를 지정하여 활성 탭만 변환합니다.

## <a name="cbasetabbedpanedetachpane"></a><a name="detachpane"></a>CBaseTabbedPane::D에타흐파네

탭된 창에서 창을 분리합니다.

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 창을 분리할 포인터입니다.

*bHide*<br/>
【인】 프레임워크가 분리된 후 창을 숨길지 여부를 지정하는 부울 매개 변수입니다.

### <a name="return-value"></a>Return Value

TRUE 프레임워크가 창을 성공적으로 분리하는 경우 false *pBar가* NULL이거나 탭된 창에 없는 창을 참조하는 경우 false입니다.

### <a name="remarks"></a>설명

가능하면 프레임워크가 분리된 창을 부동시뜨입니다. 자세한 내용은 [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)을 참조하십시오.

## <a name="cbasetabbedpaneenablesetcaptiontexttotabname"></a><a name="enablesetcaptiontexttotabname"></a>CBaseTabbedPane::인에이블세트캡션텍스트토탭네이름

탭된 창이 활성 탭의 레이블 텍스트와 캡션 텍스트를 동기화하는 기능을 활성화하거나 사용하지 않도록 설정합니다.

```
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE 탭 창 캡션을 활성 탭 캡션과 동기화합니다. 그렇지 않으면 false입니다.

## <a name="cbasetabbedpanefilldefaulttabsorderarray"></a><a name="filldefaulttabsorderarray"></a>CBaseTabbedPane::채우기기본탭순서배열

내부 탭 순서를 기본 상태로 복원합니다.

```cpp
void FillDefaultTabsOrderArray();
```

### <a name="remarks"></a>설명

이 메서드는 프레임워크가 Outlook 막대를 초기 상태로 복원할 때 호출됩니다.

## <a name="cbasetabbedpanefindpanebyid"></a><a name="findpanebyid"></a>CBaseTabbedPane::찾기파인비ID

창 ID로 식별된 창을 반환합니다.

```
virtual CWnd* FindPaneByID(UINT uBarID);
```

### <a name="parameters"></a>매개 변수

*uBarID*<br/>
【인】 찾을 창의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

창이 발견된 경우 창에 대한 포인터입니다. 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

이 메서드는 창의 모든 탭을 비교 하 고 *uBarID* 매개 변수에 의해 지정 된 ID와 하나를 반환 합니다.

## <a name="cbasetabbedpanefindbarbytabnumber"></a><a name="findbarbytabnumber"></a>CBaseTabbedPane::찾기바비탭번호

탭에 있는 창을 반환합니다.

```
virtual CWnd* FindBarByTabNumber(
    int nTabNum,
    BOOL bGetWrappedBar = FALSE);
```

### <a name="parameters"></a>매개 변수

*nTabNum*<br/>
【인】 검색할 탭의 0기반 인덱스를 지정합니다.

*bGetWrappedBar*<br/>
【인】 TRUE창 자체 대신 창의 기본(래핑) 창을 반환합니다. 그렇지 않으면 거짓. 이는 [CDockablePaneAdapter에서](../../mfc/reference/cdockablepaneadapter-class.md)파생된 창에만 적용됩니다.

### <a name="return-value"></a>Return Value

창이 발견되면 검색중인 창에 대한 유효한 포인터가 반환됩니다. 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

nTabNum 매개 변수에 의해 지정된 탭에 있는 창을 검색하려면 이 메서드를 *호출합니다.*

## <a name="cbasetabbedpanefloattab"></a><a name="floattab"></a>CBaseTabbedPane::플로트탭

창이 현재 분리 가능한 탭에 있는 경우에만 창을 부동합니다.

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인, 아웃】 부동 창에 대한 포인터입니다.

*nTabID*<br/>
【인】 float 탭의 0기반 인덱스를 지정합니다.

*dockMethod*<br/>
【인】 창을 플로트로 만드는 데 사용할 방법을 지정합니다. 자세한 내용은 주의 섹션을 참조하세요.

*bHide*<br/>
【인】 부동 하기 전에 창을 숨기기 위해 TRUE; 그렇지 않으면 false입니다.

### <a name="return-value"></a>Return Value

창이 떠 있는 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 현재 분리 가능한 탭에 있는 창을 플로팅합니다.

창을 프로그래밍 방식으로 분리하려면 *dockMethod* 매개 변수에 대한 DM_SHOW 지정합니다. 창을 이전에 떠 있던 위치와 동일한 위치에 부동하려면 *DM_DBL_CLICK dockMethod* 매개 변수로 지정합니다.

## <a name="cbasetabbedpanegetdefaulttabsorder"></a><a name="getdefaulttabsorder"></a>CBaseTabbedPane::GetDefaultTabsOrder

창에서 탭의 기본 순서를 반환합니다.

```
const CArray<int,int>& GetDefaultTabsOrder();
```

### <a name="return-value"></a>Return Value

창의 기본 탭 순서를 지정하는 `CArray` 개체입니다.

### <a name="remarks"></a>설명

Outlook 막대가 초기 상태로 재설정될 때 프레임워크는 이 메서드를 호출합니다.

## <a name="cbasetabbedpanegetfirstvisibletab"></a><a name="getfirstvisibletab"></a>CBaseTabbedPane::GetFirstVisibleTab

첫 번째 표시된 탭에 대한 포인터를 검색합니다.

```
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```

### <a name="parameters"></a>매개 변수

*iTabNum*<br/>
【인】 정수에 대한 참조입니다. 이 메서드는 첫 번째 표시된 탭의 0 기반 인덱스를 이 매개 변수에 기록하거나 표시된 탭을 찾을 수 없는 경우 -1을 씁니다.

### <a name="return-value"></a>Return Value

성공하면 첫 번째 표시된 탭에 대한 포인터입니다. 그렇지 않으면 NULL이 됩니다.

## <a name="cbasetabbedpanegetminsize"></a><a name="getminsize"></a>CBaseTabbedPane::GetMinSize

창에 대해 허용되는 최소 크기를 검색합니다.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>매개 변수

*size*<br/>
【아웃】 허용되는 `CSize` 최소 크기로 채워진 개체입니다.

### <a name="remarks"></a>설명

최소 창 크기의 일관된 처리가 활성 상태인 [경우(CPane::m_bHandleMinSize),](../../mfc/reference/cpane-class.md#m_bhandleminsize) *크기는* 활성 탭에 허용되는 최소 크기로 채워져 있습니다. 그렇지 않으면 *크기는* [CPane::GetMinSize의](../../mfc/reference/cpane-class.md#getminsize)반환 값으로 채워져 있습니다.

## <a name="cbasetabbedpanegetpaneicon"></a><a name="getpaneicon"></a>CBaseTabbedPane::GetPaneIcon

창에 대해 허용되는 최소 크기를 검색합니다.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>매개 변수

*size*<br/>
【아웃】 허용되는 `CSize` 최소 크기로 채워진 개체입니다.

### <a name="remarks"></a>설명

최소 창 크기의 일관된 처리가 활성 상태인 [경우(CPane::m_bHandleMinSize),](../../mfc/reference/cpane-class.md#m_bhandleminsize) *크기는* 활성 탭에 허용되는 최소 크기로 채워져 있습니다. 그렇지 않으면 *크기는* [CPane::GetMinSize의](../../mfc/reference/cpane-class.md#getminsize)반환 값으로 채워져 있습니다.

## <a name="cbasetabbedpanegetpanelist"></a><a name="getpanelist"></a>CBaseTabbedPane::GetPaneList

탭된 창에 포함된 창 목록을 반환합니다.

```
virtual void GetPaneList(
    CObList& lst,
    CRuntimeClass* pRTCFilter = NULL);
```

### <a name="parameters"></a>매개 변수

*순*<br/>
【아웃】 탭된 창에 포함된 창으로 채워진 A입니다. `CObList`

*pRTC필터*<br/>
【인】 NULL이 아닌 경우 반환된 목록에는 지정된 런타임 클래스에 포함된 창만 포함됩니다.

## <a name="cbasetabbedpanegettabarea"></a><a name="gettabarea"></a>CBaseTabbedPane::GetTabarea

위쪽 및 아래쪽 탭 영역에 대한 경계 사각형을 반환합니다.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const = 0;
```

### <a name="parameters"></a>매개 변수

*rectTabAreaTop*<br/>
【아웃】 위쪽 탭 영역의 화면 좌표를 받습니다.

*rectTabAreaBottom*<br/>
【아웃】 아래쪽 탭 영역의 화면 좌표를 받습니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 위쪽 및 아래쪽 탭 영역에 대한 화면 좌표에서 경계 사각형을 결정합니다.

## <a name="cbasetabbedpanegettabsnum"></a><a name="gettabsnum"></a>CBaseTabbedPane::GetTabsNum

탭 창에서 탭 수를 반환합니다.

```
virtual int GetTabsNum() const;
```

### <a name="return-value"></a>Return Value

탭된 창의 탭 수입니다.

## <a name="cbasetabbedpanegetunderlyingwindow"></a><a name="getunderlyingwindow"></a>CBaseTabbedPane::GetBaseWindow

기본(래핑) 탭 창을 가져옵니다.

```
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```

### <a name="return-value"></a>Return Value

기본 탭 창에 대한 포인터입니다.

## <a name="cbasetabbedpanegetvisibletabsnum"></a><a name="getvisibletabsnum"></a>CBaseTabbedPane::GetVisibleTabsNum

표시되는 탭 수를 반환합니다.

```
virtual int GetVisibleTabsNum() const;
```

### <a name="return-value"></a>Return Value

0보다 크거나 같을 표시되는 탭 수입니다.

### <a name="remarks"></a>설명

탭된 창에 표시되는 탭 수를 확인하려면 이 메서드를 호출합니다.

## <a name="cbasetabbedpanehasautohidemode"></a><a name="hasautohidemode"></a>CBaseTabbedPane::하스오토하이드모드

탭 창을 자동 숨기기 모드로 전환할 수 있는지 여부를 결정합니다.

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Return Value

창을 자동 숨기기 모드로 전환할 수 있는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

자동 숨기기 모드를 사용하지 않도록 설정하면 탭된 창 캡션에 핀 단추가 표시되지 않습니다.

## <a name="cbasetabbedpaneishidesingletab"></a><a name="ishidesingletab"></a>CBaseTabbedPane::이하이드싱글탭

탭이 하나만 표시되는 경우 탭창이 숨겨져 있는지 여부를 결정합니다.

```
virtual BOOL IsHideSingleTab() const;
```

### <a name="return-value"></a>Return Value

TRUE 탭이 하나만 표시되는 경우 탭 창이 표시되지 않는 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

하나의 탭만 열려 있기 때문에 창이 표시되지 않으면 이 메서드를 호출하여 탭된 창이 제대로 작동하는지 확인할 수 있습니다.

## <a name="cbasetabbedpaneremovepane"></a><a name="removepane"></a>CBaseTabbedPane::제거파네

탭된 창에서 창을 제거합니다.

```
virtual BOOL RemovePane(CWnd* pBar);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인, 아웃】 탭된 창에서 제거할 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 탭창에서 창이 성공적으로 제거되었고 탭된 창이 여전히 유효한 경우 FALSE 탭된 창에서 마지막 창이 제거되고 탭된 창이 소멸될 경우 false입니다. 반환 값이 FALSE이면 탭된 창을 더 이상 사용하지 마십시오.

### <a name="remarks"></a>설명

탭된 창에서 *pBar* 매개 변수에 의해 지정된 창을 제거하려면 이 메서드를 호출합니다.

## <a name="cbasetabbedpanesetautodestroy"></a><a name="setautodestroy"></a>CBaseTabbedPane::SetAutoDestroy

탭된 컨트롤 막대가 자동으로 소멸될지 여부를 결정합니다.

```cpp
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*b오토파괴*<br/>
【인】 TRUE 탭된 창이 동적으로 만들어졌고 해당 창을 제어하지 않는 경우 입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

탭된 창을 동적으로 만들고 수명을 제어하지 않는 경우 자동 소멸 모드를 TRUE로 설정합니다. 자동 파괴 모드가 TRUE이면 탭된 창이 프레임워크에 의해 자동으로 소멸됩니다.

## <a name="cbasetabbedpaneshowtab"></a><a name="showtab"></a>CBaseTabbedPane::쇼탭

탭을 표시하거나 숨깁니다.

```
virtual BOOL ShowTab(
    CWnd* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
【인】 표시하거나 숨길 창에 대한 포인터입니다.

*bShow*<br/>
【인】 창을 표시하는 TRUE; 창을 숨기기 위해 FALSE입니다.

*bDelay*<br/>
【인】 TRUE 탭 레이아웃의 조정을 지연; 그렇지 않으면 false입니다.

*bActivate*<br/>
【인】 TRUE 탭을 활성 탭으로 만듭니다. 그렇지 않으면 false입니다.

### <a name="return-value"></a>Return Value

TRUE 탭이 표시되었거나 성공적으로 숨겨져 있는 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하면 *bShow* 매개 변수의 값에 따라 창이 표시되거나 숨김됩니다. 탭을 숨기고 기본 탭 창에서 마지막으로 표시되는 탭인 경우 탭창이 숨겨지게 됩니다. 이전에 탭이 표시되지 않았던 경우 탭창이 표시됩니다.

## <a name="cbasetabbedpanerecalclayout"></a><a name="recalclayout"></a>CBaseTabbedPane::RecalcLayout

창에 대한 레이아웃 정보를 다시 계산합니다.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>설명

창이 부동 하는 경우이 메서드는 프레임 에 대 한 창을 미니 프레임의 현재 크기로 크기를 조정 하는 것을 알수 있습니다.

창이 도킹된 경우 이 메서드는 아무 것도 수행하지 않습니다.

## <a name="cbasetabbedpanesetautohidemode"></a><a name="setautohidemode"></a>CBaseTabbedPane::SetAutoHideMode

탭된 창에서 분리 가능한 창에 대한 자동 숨기기 모드를 설정합니다.

```
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,
    DWORD dwAlignment,
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>매개 변수

*b 모드*<br/>
【인】 TRUE는 자동 숨기기 모드를 활성화합니다. FALSE는 일반 도킹 모드를 활성화합니다.

*dw정렬*<br/>
【인】 작성할 자동 숨기기 창의 정렬을 지정합니다. 가능한 값 목록은 [CPane::MoveBy정렬](../../mfc/reference/cpane-class.md#movebyalignment)을 참조하십시오.

*pCurr자동하이드바*<br/>
【인, 아웃】 현재 자동 숨기기 도구 모음에 대한 포인터입니다. NULL일 수 있습니다.

*bUse타이머*<br/>
【인】 사용자가 창을 자동 숨기기 모드로 전환할 때 자동 숨기기 효과를 사용할지 또는 창을 즉시 숨길지 지정합니다.

### <a name="return-value"></a>Return Value

자동 숨기기 모드로 전환할 때 생성되는 자동 숨기기 도구 모음에 대한 포인터 또는 도구 모음이 만들어지지 않은 경우 NULL입니다.

### <a name="remarks"></a>설명

사용자가 탭 된 창을 자동 숨기기 모드 또는 일반 도킹 모드로 전환 하기 위해 핀 단추를 선택할 때 프레임 워크는이 메서드를 호출 합니다.

탭된 창의 각 분리 가능 창에 대해 자동 숨기기 모드가 설정됩니다. 분리할 수 없는 창은 무시됩니다. 자세한 내용은 [CMFCBaseTabCtrl::EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach)을 참조하십시오.

이 메서드를 호출하여 탭된 창을 프로그래밍 방식으로 자동 숨기기 모드로 전환합니다. 창은 기본 프레임 창에 도킹되어야 [합니다(CDockablePane:GetDefaultPaneDivider는](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) [CPaneDivider에](../../mfc/reference/cpanedivider-class.md)유효한 포인터를 반환해야 합니다).

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)
