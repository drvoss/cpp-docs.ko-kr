---
title: CRecentDockSiteInfo 클래스
ms.date: 11/04/2016
f1_keywords:
- CRecentDockSiteInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::CleanUp
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDefaultPaneDivider
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDockedPercent
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDockedRect
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentListOfPanes
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentPaneContainer
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentTabContainer
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::Init
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::IsRecentLeftPane
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::SaveListOfRecentPanes
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::SetInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::StoreDockInfo
helpviewer_keywords:
- CRecentDockSiteInfo [MFC], CleanUp
- CRecentDockSiteInfo [MFC], GetRecentDefaultPaneDivider
- CRecentDockSiteInfo [MFC], GetRecentDockedPercent
- CRecentDockSiteInfo [MFC], GetRecentDockedRect
- CRecentDockSiteInfo [MFC], GetRecentListOfPanes
- CRecentDockSiteInfo [MFC], GetRecentPaneContainer
- CRecentDockSiteInfo [MFC], GetRecentTabContainer
- CRecentDockSiteInfo [MFC], Init
- CRecentDockSiteInfo [MFC], IsRecentLeftPane
- CRecentDockSiteInfo [MFC], SaveListOfRecentPanes
- CRecentDockSiteInfo [MFC], SetInfo
- CRecentDockSiteInfo [MFC], StoreDockInfo
ms.assetid: 2dd14f95-d5a2-4461-a7a5-2c6c36a3a165
ms.openlocfilehash: 9f23d5aff2bac65363086c077af45e35c3263f65
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750576"
---
# <a name="crecentdocksiteinfo-class"></a>CRecentDockSiteInfo 클래스

클래스는 `CRecentDockSiteInfo` [CPane](../../mfc/reference/cpane-class.md)클래스에 대한 최신 상태 정보를 저장하는 도우미 클래스입니다.

## <a name="syntax"></a>구문

```
class CRecentDockSiteInfo : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CRecentDockSiteInfo::CRecentDockSiteInfo`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRecentDockSiteInfo::CleanUp](#cleanup)||
|[CRecentDockSiteInfo::GetRecentDefaultPaneDivider](#getrecentdefaultpanedivider)||
|[CRecentDockSiteInfo::GetRecentDockedPercent](#getrecentdockedpercent)||
|[CRecentDockSiteInfo::GetRecentDockedRect](#getrecentdockedrect)||
|[CRecentDockSiteInfo::GetRecentListOfPanes](#getrecentlistofpanes)||
|[CRecentDockSiteInfo::GetRecentPaneContainer](#getrecentpanecontainer)||
|[CRecentDockSiteInfo::GetRecentTabContainer](#getrecenttabcontainer)||
|[CRecentDockSiteInfo::Init](#init)||
|[CRecentDockSiteInfo::IsRecentLeftPane](#isrecentleftpane)||
|[CRecentDockSiteInfo::연산자 =](#operator_eq)||
|[CRecentDockSiteInfo::SaveListOfRecentPanes](#savelistofrecentpanes)||
|[CRecentDockSiteInfo::SetInfo](#setinfo)||
|[CRecentDockSiteInfo::StoreDockInfo](#storedockinfo)||

## <a name="remarks"></a>설명

`CRecentDockSiteInfo` 클래스는 데이터 관리 클래스입니다. 이 클래스는 도킹과 부동 간에 전환될 때 `CPane`의 마지막 상태를 추적합니다. 사용자가 도킹 가능한 부동 창을 두 번 클릭하면 도킹됩니다. 도킹된 창을 두 번 클릭하면 이전 위치, 크기 및 상태로 돌아갑니다. 마찬가지로 창이 다시 도킹되면 이전 도킹 위치로 돌아갑니다. 이 데이터 클래스를 통해 이 작업을 수행할 수 있습니다. 이 클래스의 멤버는 도킹된 창에 대한 상태 정보를 저장하므로 애플리케이션에서 직접 수정할 수 없습니다.

`CRecentDockSiteInfo` 개체는 창을 만들 때마다 생성됩니다. 각 `CPane` 개체에는 이 정보를 저장할 멤버 변수 [CPane:.m_recentDockInfo](../../mfc/reference/cpane-class.md#m_recentdockinfo)있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrecentDockSiteInfo.h

## <a name="crecentdocksiteinfocleanup"></a><a name="cleanup"></a>CRecentDockSiteInfo::정리

```cpp
void CleanUp();
```

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfocrecentdocksiteinfo"></a><a name="crecentdocksiteinfo"></a>CRecentDockSiteInfo::CRecentDockSiteInfo

```
CRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>매개 변수

【인】 *pBar*<br/>

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfogetrecentdefaultpanedivider"></a><a name="getrecentdefaultpanedivider"></a>CRecentDockSiteInfo::GetRecentDefaultPane 분배기

```
CPaneDivider* GetRecentDefaultPaneDivider();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfogetrecentdockedpercent"></a><a name="getrecentdockedpercent"></a>CRecentDockSiteInfo::GetRecentDockedPercent

```
int GetRecentDockedPercent(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

【인】 *b포슬라이더*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfogetrecentdockedrect"></a><a name="getrecentdockedrect"></a>CRecentDockSiteInfo::GetRecentDockedRect

```
CRect& GetRecentDockedRect(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

【인】 *b포슬라이더*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfogetrecentlistofpanes"></a><a name="getrecentlistofpanes"></a>CRecentDockSiteInfo::GetRecentListOfpanes

```
CList<HWND, HWND>& GetRecentListOfPanes(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

【인】 *b포슬라이더*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfogetrecentpanecontainer"></a><a name="getrecentpanecontainer"></a>CRecentDockSiteInfo::GetRecentPaneContainer

```
CPaneContainer* GetRecentPaneContainer(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

【인】 *b포슬라이더*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfogetrecenttabcontainer"></a><a name="getrecenttabcontainer"></a>CRecentDockSiteInfo::GetRecentTabContainer

```
CPaneContainer* GetRecentTabContainer(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

【인】 *b포슬라이더*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfoinit"></a><a name="init"></a>CRecentDockSiteInfo::이니트

```cpp
void Init();
```

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfoisrecentleftpane"></a><a name="isrecentleftpane"></a>CRecentDockSiteInfo::최근레프트파인

```
BOOL IsRecentLeftPane(BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

【인】 *b포슬라이더*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfooperator-"></a><a name="operator_eq"></a>CRecentDockSiteInfo::연산자 =

```
CRecentDockSiteInfo& operator=(CRecentDockSiteInfo& src);
```

### <a name="parameters"></a>매개 변수

【인】 *src*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfosavelistofrecentpanes"></a><a name="savelistofrecentpanes"></a>CRecentDockSiteInfo::SaveListofRecentpanes

```cpp
void SaveListOfRecentPanes(CList<HWND,
    HWND>& lstOrg,
    BOOL bForSlider);
```

### <a name="parameters"></a>매개 변수

【인】 *CList<HWND*<br/>
【인】 *lstOrg*<br/>
【인】 *b포슬라이더*<br/>

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfosetinfo"></a><a name="setinfo"></a>CRecentDockSiteInfo::SetInfo

```
virtual void SetInfo(
    BOOL bForSlider,
    CRecentDockSiteInfo& srcInfo);
```

### <a name="parameters"></a>매개 변수

【인】 *b포슬라이더*<br/>
【인】 *srcInfo*<br/>

### <a name="remarks"></a>설명

## <a name="crecentdocksiteinfostoredockinfo"></a><a name="storedockinfo"></a>CRecentDockSiteInfo::스토어독정보

```
virtual void StoreDockInfo(
    CPaneContainer* pRecentContainer,
    CDockablePane* pTabbedBar = NULL);
```

### <a name="parameters"></a>매개 변수

【인】 *p최근 컨테이너*<br/>
【인】 *pTabbedBar*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite Class](../../mfc/reference/cdocksite-class.md)
