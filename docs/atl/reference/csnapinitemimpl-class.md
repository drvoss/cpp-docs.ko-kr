---
title: CSnapInItemImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::AddMenuItems
- ATLSNAP/ATL::CSnapInItemImpl::Command
- ATLSNAP/ATL::CSnapInItemImpl::CreatePropertyPages
- ATLSNAP/ATL::CSnapInItemImpl::FillData
- ATLSNAP/ATL::CSnapInItemImpl::GetResultPaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::GetResultViewType
- ATLSNAP/ATL::CSnapInItemImpl::GetScopePaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::Notify
- ATLSNAP/ATL::CSnapInItemImpl::QueryPagesFor
- ATLSNAP/ATL::CSnapInItemImpl::SetMenuInsertionFlags
- ATLSNAP/ATL::CSnapInItemImpl::SetToolbarButtonInfo
- ATLSNAP/ATL::CSnapInItemImpl::UpdateMenuState
- ATLSNAP/ATL::CSnapInItemImpl::UpdateToolbarButton
- ATLSNAP/ATL::CSnapInItemImpl::m_bstrDisplayName
- ATLSNAP/ATL::CSnapInItemImpl::m_resultDataItem
- ATLSNAP/ATL::CSnapInItemImpl::m_scopeDataItem
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
ms.openlocfilehash: 04eeba0239789b9f3220b7bfece3eb41dc7f2826
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746421"
---
# <a name="csnapinitemimpl-class"></a>CSnapInItemImpl 클래스

이 클래스는 스냅인 노드 개체를 구현하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, BOOL bIsExtension = FALSE>
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `CSnapInItemImpl`

*비스익스텐션*<br/>
TRUE 개체가 스냅인 확장인 경우 그렇지 않으면 거짓.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSnapInItemImpl:::CSnapInItemImpl](#csnapinitemimpl)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSnapInItem임플::추가 메뉴항목](#addmenuitems)|메뉴 메뉴에 메뉴 항목을 추가합니다.|
|[CSnapInItem임플::명령](#command)|사용자 지정 메뉴 항목을 선택할 때 콘솔에서 호출됩니다.|
|[CSnapInItemImpl::만들기속성 페이지](#createpropertypages)|스냅인의 속성 시트에 페이지를 추가합니다.|
|[CSnapInItem임플::채우기 데이터](#filldata)|스냅인 개체에 대한 정보를 지정된 스트림으로 복사합니다.|
|[CSnapInItemImpl::GetresultPaneInfo](#getresultpaneinfo)|스냅인의 `RESULTDATAITEM` 구조를 검색합니다.|
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|결과 창에서 사용되는 뷰 유형을 결정합니다.|
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|스냅인의 `SCOPEDATAITEM` 구조를 검색합니다.|
|[CSnapInItemImpl::알림](#notify)|사용자가 수행한 작업의 스냅인을 알리기 위해 콘솔에서 호출합니다.|
|[CSnapInItemImpl::쿼리 페이지](#querypagesfor)|스냅 인 노드가 속성 페이지를 지원하는지 확인하기 위해 호출됩니다.|
|[CSnapInItemImpl::세트메뉴 삽입 플래그](#setmenuinsertionflags)|스냅인 개체에 대한 메뉴 삽입 플래그를 수정합니다.|
|[CSnapInItemImpl::setToolbar단추정보](#settoolbarbuttoninfo)|지정된 도구 모음 단추의 정보를 설정합니다.|
|[CSnapInItem임플::업데이트 메뉴 상태](#updatemenustate)|컨텍스트 메뉴 항목의 상태를 업데이트합니다.|
|[CSnapInItem임플::업데이트 도구 모음 단추](#updatetoolbarbutton)|지정된 도구 모음 단추의 상태를 업데이트합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|스냅인 개체의 이름입니다.|
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|개체에서 `RESULTDATAITEM` 사용하는 Windows `CSnapInItemImpl` 구조입니다.|
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|개체에서 `SCOPEDATAITEM` 사용하는 Windows `CSnapInItemImpl` 구조입니다.|

## <a name="remarks"></a>설명

`CSnapInItemImpl`는 메뉴 항목 및 도구 모음 추가 및 해당 처리기 함수에 스냅 인 노드에 대한 명령을 전달하는 등 스냅인 노드 개체에 대한 기본 구현을 제공합니다. 이러한 기능은 여러 가지 인터페이스와 맵 유형을 사용하여 구현됩니다. 기본 구현은 파생 된 클래스의 올바른 인스턴스를 확인 하 고 올바른 인스턴스에 메시지를 전달 하 여 노드 개체에 전송 된 알림을 처리 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlsnap.h

## <a name="csnapinitemimpladdmenuitems"></a><a name="addmenuitems"></a>CSnapInItem임플::추가 메뉴항목

이 메서드는 Win32 함수 [IExtendContextMenu::AddMenuItems](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-addmenuitems).

```
AddMenuItems(
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>매개 변수

*파이콜백*<br/>
【인】 컨텍스트 메뉴에 `IContextMenuCallback` 항목을 추가할 수 있는 포인터입니다.

*p삽입허용*<br/>
【인, 아웃】 사용할 수 있는 MMC(Microsoft 관리 콘솔)가 정의한 메뉴 항목 삽입 지점을 식별합니다. 다음 플래그의 조합일 수 있습니다.

- CCM_INSERTIONALLOWED_TOP 항목을 컨텍스트 메뉴의 맨 위에 삽입할 수 있습니다.

- CCM_INSERTIONALLOWED_NEW 항목을 새 하위 메뉴 만들기에 삽입할 수 있습니다.

- CCM_INSERTIONALLOWED_TASK 항목작업 하위 메뉴에 삽입할 수 있습니다.

- CCM_INSERTIONALLOWED_VIEW 항목을 도구 모음 보기 메뉴 또는 결과 창 컨텍스트 메뉴의 보기 하위 메뉴에 삽입할 수 있습니다.

*type*<br/>
【인】 개체 유형을 지정합니다. 다음 값 중 하나일 수 있습니다.

- 범위 창 컨텍스트에 대한 데이터 개체를 CCT_SCOPE.

- 결과 창 컨텍스트에 대한 데이터 개체를 CCT_RESULT.

- 스냅인 관리자 컨텍스트에 대한 데이터 개체를 CCT_SNAPIN_MANAGER.

- CCT_UNINITIALIZED 데이터 개체에 잘못된 형식이 있습니다.

## <a name="csnapinitemimplcommand"></a><a name="command"></a>CSnapInItem임플::명령

이 메서드는 Win32 함수 [IExtendContextMenu::Command를](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-command)구현합니다.

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>매개 변수

*lCommandID*<br/>
【인】 메뉴 항목의 명령 식별자를 지정합니다.

*type*<br/>
【인】 개체 유형을 지정합니다. 다음 값 중 하나일 수 있습니다.

- 범위 창 컨텍스트에 대한 데이터 개체를 CCT_SCOPE.

- 결과 창 컨텍스트에 대한 데이터 개체를 CCT_RESULT.

- 스냅인 관리자 컨텍스트에 대한 데이터 개체를 CCT_SNAPIN_MANAGER.

- CCT_UNINITIALIZED 데이터 개체에 잘못된 형식이 있습니다.

## <a name="csnapinitemimplcreatepropertypages"></a><a name="createpropertypages"></a>CSnapInItemImpl::만들기속성 페이지

이 메서드는 Win32 함수 [IExtendPropertySheet::CreatePropertyPages](/windows/win32/api/mmc/nn-mmc-iextendpropertysheet2).

```
CreatePropertyPages(
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>매개 변수

*lpProvider*<br/>
【인】 인터페이스에 `IPropertySheetCallback` 대한 포인터입니다.

*처리*<br/>
【인】 MMCN_PROPERTY_CHANGE 알림 메시지를 적절한 데이터 클래스로 라우팅하는 데 사용되는 핸들을 지정합니다.

*pUnk*<br/>
【인】 노드에 `IExtendPropertySheet` 대한 컨텍스트 정보를 포함하는 개체의 인터페이스에 대한 포인터입니다.

*type*<br/>
【인】 개체 유형을 지정합니다. 다음 값 중 하나일 수 있습니다.

- 범위 창 컨텍스트에 대한 데이터 개체를 CCT_SCOPE.

- 결과 창 컨텍스트에 대한 데이터 개체를 CCT_RESULT.

- 스냅인 관리자 컨텍스트에 대한 데이터 개체를 CCT_SNAPIN_MANAGER.

- CCT_UNINITIALIZED 데이터 개체에 잘못된 형식이 있습니다.

## <a name="csnapinitemimplcsnapinitemimpl"></a><a name="csnapinitemimpl"></a>CSnapInItemImpl:::CSnapInItemImpl

`CSnapInItemImpl` 개체를 생성합니다.

```
CSnapInItemImpl();
```

## <a name="csnapinitemimplfilldata"></a><a name="filldata"></a>CSnapInItem임플::채우기 데이터

이 함수는 항목에 대한 정보를 검색하기 위해 호출됩니다.

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>매개 변수

*Cf*<br/>
【인】 클립보드의 형식(텍스트, 진부한 텍스트 또는 OLE 항목이 있는 진부한 텍스트)입니다.

*pStream*<br/>
【인】 개체 데이터를 포함하는 스트림에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수를 제대로 구현하려면 *cf로*표시된 클립보드 형식에 따라 올바른 정보를*스트림(pStream)에*복사합니다.

## <a name="csnapinitemimplgetresultviewtype"></a><a name="getresultviewtype"></a>CSnapInItemImpl::GetResultViewType

이 함수를 호출하여 스냅인 개체의 결과 창에 대한 뷰 유형을 검색합니다.

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>매개 변수

*ppViewType*<br/>
【아웃】 반환된 뷰 유형의 주소에 대한 포인터입니다.

*pView옵션*<br/>
【아웃】 MMC_VIEW_OPTIONS 열거형에 대한 포인터로, 콘솔에 소유 스냅인에 의해 지정된 옵션을 제공합니다. 이 값은 다음 중 하나일 수 있습니다.

- MMC_VIEW_OPTIONS_NOLISTVIEWS = 0x00000001 **보기** 메뉴에서 표준 목록 보기 선택 사항을 표시하지 않도록 콘솔에 지시합니다. 스냅인이 결과 보기 창에만 고유한 사용자 지정 뷰를 표시할 수 있습니다. 이 플래그는 현재 정의된 유일한 옵션 플래그입니다.

- MMC_VIEW_OPTIONS_NONE = 0 기본 보기 옵션을 허용합니다.

## <a name="csnapinitemimplgetscopepaneinfo"></a><a name="getscopepaneinfo"></a>CSnapInItemImpl::GetScopePaneInfo

이 함수를 호출하여 스냅인의 `SCOPEDATAITEM` 구조를 검색합니다.

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>매개 변수

*pScope데이터항목*<br/>
【아웃】 개체의 구조에 `SCOPEDATAITEM` 대한 `CSnapInItemImpl` 포인터입니다.

## <a name="csnapinitemimplgetresultpaneinfo"></a><a name="getresultpaneinfo"></a>CSnapInItemImpl::GetresultPaneInfo

이 함수를 호출하여 스냅인의 `RESULTDATAITEM` 구조를 검색합니다.

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>매개 변수

*pResult데이터항목*<br/>
【아웃】 개체의 구조에 `RESULTDATAITEM` 대한 `CSnapInItemImpl` 포인터입니다.

## <a name="csnapinitemimplm_bstrdisplayname"></a><a name="m_bstrdisplayname"></a>CSnapInItemImpl::m_bstrDisplayName

노드 항목에 대해 표시되는 문자열을 포함합니다.

```
CComBSTR m_bstrDisplayName;
```

## <a name="csnapinitemimplm_scopedataitem"></a><a name="m_scopedataitem"></a>CSnapInItemImpl::m_scopeDataItem

스냅인 데이터 개체의 `SCOPEDATAITEM` 구조입니다.

```
SCOPEDATAITEM m_scopeDataItem;
```

## <a name="csnapinitemimplm_resultdataitem"></a><a name="m_resultdataitem"></a>CSnapInItemImpl::m_resultDataItem

스냅인 데이터 개체의 [RESULTDATAITEM](/windows/win32/api/mmc/ns-mmc-resultdataitem) 구조입니다.

```
RESULTDATAITEM m_resultDataItem;
```

## <a name="csnapinitemimplnotify"></a><a name="notify"></a>CSnapInItemImpl::알림

사용자가 스냅 인 개체를 작동할 때 호출됩니다.

```
STDMETHOD(Notify)(
    MMC_NOTIFY_TYPE event,
    long arg,
    long param,
    IComponentData* pComponentData,
    IComponent* pComponent,
    DATA_OBJECT_TYPES type) = 0;
```

### <a name="parameters"></a>매개 변수

*event*<br/>
【인】 사용자가 수행한 작업을 식별합니다. 다음과 같은 알림이 가능합니다.

- MMCN_ACTIVATE 창이 활성화되고 비활성화될 때 전송됩니다.

- MMCN_ADD_IMAGES 결과 창에 이미지를 추가하기 위해 전송되었습니다.

- 사용자가 도구 모음 단추 중 하나를 클릭하면 MMCN_BTN_CLICK 전송됩니다.

- MMCN_CLICK 사용자가 목록 보기 항목에서 마우스 단추를 클릭하면 전송됩니다.

- MMCN_DBLCLICK 사용자가 목록 보기 항목에서 마우스 단추를 두 번 클릭하면 전송됩니다.

- MMCN_DELETE 개체를 삭제해야 한다는 스냅인을 알리기 위해 전송되었습니다.

- MMCN_EXPAND 폴더를 확장하거나 축소해야 할 때 전송됩니다.

- MMCN_MINIMIZED 창이 최소화되거나 최대화될 때 전송됩니다.

- MMCN_PROPERTY_CHANGE 스냅인 개체의 보기가 변경될 것이라는 것을 스냅인 개체에 알리기 위해 전송되었습니다.

- MMCN_REMOVE_CHILDREN 스냅인이 지정된 노드 아래에 추가한 전체 하위 트리를 삭제해야 할 때 전송됩니다.

- MMCN_RENAME 이름을 쿼리하는 첫 번째 시간과 이름을 변경하기 위해 두 번째로 보냈습니다.

- MMCN_SELECT 범위 또는 결과 보기 창의 항목이 선택되면 전송됩니다.

- MMCN_SHOW 범위 항목을 처음 선택하거나 선택 취소할 때 전송됩니다.

- MMCN_VIEW_CHANGE 스냅인이 변경이 발생할 때 모든 보기를 업데이트할 수 있을 때 전송됩니다.

*Arg*<br/>
【인】 알림 유형에 따라 다릅니다.

*Param*<br/>
【인】 알림 유형에 따라 다릅니다.

*p컴포넌트 데이터*<br/>
【아웃】 을 구현하는 `IComponentData`개체에 대한 포인터입니다. 이 매개 변수는 에서 알림이 전달되지 않는 경우 `IComponentData::Notify`NULL입니다.

*p 컴포넌트*<br/>
【아웃】 을 구현하는 개체에 대한 `IComponent`포인터입니다. 이 매개 변수는 에서 알림이 전달되지 않는 경우 `IComponent::Notify`NULL입니다.

*type*<br/>
【인】 개체 유형을 지정합니다. 다음 값 중 하나일 수 있습니다.

- 범위 창 컨텍스트에 대한 데이터 개체를 CCT_SCOPE.

- 결과 창 컨텍스트에 대한 데이터 개체를 CCT_RESULT.

- 스냅인 관리자 컨텍스트에 대한 데이터 개체를 CCT_SNAPIN_MANAGER.

- CCT_UNINITIALIZED 데이터 개체에 잘못된 형식이 있습니다.

## <a name="csnapinitemimplquerypagesfor"></a><a name="querypagesfor"></a>CSnapInItemImpl::쿼리 페이지

스냅 인 노드가 속성 페이지를 지원하는지 확인하기 위해 호출됩니다.

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

## <a name="csnapinitemimplsetmenuinsertionflags"></a><a name="setmenuinsertionflags"></a>CSnapInItemImpl::세트메뉴 삽입 플래그

이 함수를 호출하여 스냅인 개체에 대해 *pInsertionAllowed로*지정된 메뉴 삽입 플래그를 수정합니다.

```cpp
void SetMenuInsertionFlags(
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>매개 변수

*b삽입 전*<br/>
【인】 항목이 컨텍스트 메뉴에 추가되기 전에 함수를 호출해야 하는 경우 0이 아닙니다. 그렇지 않으면 0.

*p삽입허용*<br/>
【인, 아웃】 사용할 수 있는 MMC(Microsoft 관리 콘솔)가 정의한 메뉴 항목 삽입 지점을 식별합니다. 다음 플래그의 조합일 수 있습니다.

- CCM_INSERTIONALLOWED_TOP 항목을 컨텍스트 메뉴의 맨 위에 삽입할 수 있습니다.

- CCM_INSERTIONALLOWED_NEW 항목을 새 하위 메뉴 만들기에 삽입할 수 있습니다.

- CCM_INSERTIONALLOWED_TASK 항목작업 하위 메뉴에 삽입할 수 있습니다.

- CCM_INSERTIONALLOWED_VIEW 항목을 도구 모음 보기 메뉴 또는 결과 창 컨텍스트 메뉴의 보기 하위 메뉴에 삽입할 수 있습니다.

### <a name="remarks"></a>설명

기본 스냅인을 개발하는 경우 타사 확장이 추가할 수 있는 메뉴 항목의 종류를 제한하는 방법으로 삽입 플래그를 재설정할 수 있습니다. 예를 들어 기본 스냅인은 CCM_INSERTIONALLOWED_NEW 플래그를 지우면 확장이 새 메뉴 만들기 항목을 추가하지 못하도록 할 수 있습니다.

원래 지워진 *pInsertion허용에서* 비트를 설정하려고 시도해서는 안됩니다. 이후 버전의 MMC는 현재 정의되지 않은 비트를 사용할 수 있으므로 현재 정의되지 않은 비트를 변경해서는 안 됩니다.

## <a name="csnapinitemimplsettoolbarbuttoninfo"></a><a name="settoolbarbuttoninfo"></a>CSnapInItemImpl::setToolbar단추정보

이 함수를 호출하여 도구 모음을 작성하기 전에 스냅인 오브젝트의 도구 모음 단추 스타일을 수정합니다.

```cpp
void SetToolbarButtonInfo(
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 설정할 도구 모음 단추의 ID입니다.

*fsState*<br/>
【인】 단추의 상태 플래그입니다. 다음 중 하나 이상이 될 수 있습니다.

- TBSTATE_CHECKED 버튼은 TBSTYLE_CHECKED 스타일을 가지며 누르고 있습니다.

- TBSTATE_ENABLED 버튼은 사용자 입력을 허용합니다. 이 상태가 없는 단추는 사용자 입력을 허용하지 않으며 회색으로 표시됩니다.

- TBSTATE_HIDDEN 버튼이 표시되지 않고 사용자 입력을 받을 수 없습니다.

- TBSTATE_INDETERMINATE 버튼이 회색으로 표시됩니다.

- TBSTATE_PRESSED 버튼을 누르고 있습니다.

- TBSTATE_WRAP 줄 바이탈은 단추를 따릅니다. 단추에는 TBSTATE_ENABLED 있어야 합니다.

*fsType*<br/>
【인】 단추의 상태 플래그입니다. 다음 중 하나 이상이 될 수 있습니다.

- TBSTYLE_BUTTON 표준 푸시 버튼을 만듭니다.

- TBSTYLE_CHECK 사용자가 누를 때마다 누른 상태와 누른 상태가 아닌 상태 사이를 전환하는 단추를 만듭니다. 단추를 누른 상태에서 다른 배경 색을 가있습니다.

- TBSTYLE_CHECKGROUP 그룹의 다른 단추를 누를 때까지 계속 누르는 검사 단추를 만듭니다.

- TBSTYLE_GROUP 그룹의 다른 단추를 누를 때까지 계속 누르는 단추를 만듭니다.

- TBSTYLE_SEP 구분 기호를 만들어 단추 그룹 간에 작은 간격을 제공합니다. 이 스타일을 가지고 있는 단추는 사용자 입력을 받지 않습니다.

## <a name="csnapinitemimplupdatemenustate"></a><a name="updatemenustate"></a>CSnapInItem임플::업데이트 메뉴 상태

스냅인 개체의 컨텍스트 메뉴에 삽입하기 전에 이 함수를 호출하여 메뉴 항목을 수정합니다.

```cpp
void UpdateMenuState(
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 설정할 메뉴 항목의 ID입니다.

*pBuf*<br/>
【인】 업데이트할 메뉴 항목에 대한 문자열에 대한 포인터입니다.

*플래그*<br/>
【인】 새 상태 플래그를 지정합니다. 다음 플래그의 조합일 수 있습니다.

- MF_POPUP 컨텍스트 메뉴 내의 하위 메뉴임을 지정합니다. 메뉴 항목, 삽입 점 및 추가 하위 메뉴를 `lCommandID` `IInsertionPointID`의 하위 메뉴로 사용하여 이 하위 메뉴에 추가할 수 있습니다.

- MF_BITMAP 및 MF_OWNERDRAW 이러한 플래그는 허용되지 않으며 E_INVALIDARG 반환 값이 됩니다.

- MF_SEPARATOR 수평 구분선을 그립니다. MF_SEPARATOR `IContextMenuProvider` 세트로 메뉴 항목을 추가할 수 있습니다.

- MF_CHECKED 메뉴 항목 옆에 확인 표시를 배치합니다.

- MF_DISABLED 메뉴 항목을 선택하지 않도록 설정하지만 플래그는 회색으로 표시되지 않습니다.

- MF_ENABLED 메뉴 항목을 선택하여 회색 상태에서 복원할 수 있도록 설정합니다.

- MF_GRAYED 메뉴 항목을 선택하지 못하도록 회색으로 표시합니다.

- MF_MENUBARBREAK 메뉴 모음의 MF_MENUBREAK 플래그와 동일하게 작동합니다. 드롭다운 메뉴, 하위 메뉴 또는 바로 가기 메뉴의 경우 새 열이 이전 열과 세로 줄로 구분됩니다.

- MF_MENUBREAK 열을 분리하지 않고 새 줄(메뉴 모음의 경우) 또는 새 열(드롭다운 메뉴, 하위 메뉴 또는 바로 가기 메뉴)에 항목을 배치합니다.

- MF_UNCHECKED 항목 옆에 확인 표시를 배치하지 않습니다(기본값).

다음 플래그 그룹을 함께 사용할 수 없습니다.

- MF_DISABLED, MF_ENABLED 및 MF_GRAYED.

- MF_MENUBARBREAK and MF_MENUBREAK.

- MF_CHECKED and MF_UNCHECKED.

## <a name="csnapinitemimplupdatetoolbarbutton"></a><a name="updatetoolbarbutton"></a>CSnapInItem임플::업데이트 도구 모음 단추

이 함수를 호출하여 스냅인 개체의 도구 모음 단추를 표시하기 전에 수정합니다.

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>매개 변수

*id*<br/>
업데이트할 도구 모음 단추의 단추 ID를 지정합니다.

*fsState*<br/>
도구 모음 단추 상태를 지정합니다. 이 상태를 설정하려면 TRUE를 반환합니다. 다음 플래그의 조합일 수 있습니다.

- ENABLED 버튼은 사용자 입력을 허용합니다. 이 상태가 없는 단추는 사용자 입력을 허용하지 않으며 회색으로 표시됩니다.

- 확인 버튼이 CHECKED 스타일을 가지고 있으며 누르고 있습니다.

- 숨겨진 버튼이 표시되지 않으며 사용자 입력을 받을 수 없습니다.

- 확정되지 않음 버튼이 회색으로 표시됩니다.

- 단추 를 누른 버튼을 누른 중입니다.

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)
