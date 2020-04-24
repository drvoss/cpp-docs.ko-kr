---
title: CMFC쉘트리트럴 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::EnableShellContextMenu
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetItemPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetRelatedList
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnChildNotify
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemIcon
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemText
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::Refresh
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SelectPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetRelatedList
helpviewer_keywords:
- CMFCShellTreeCtrl [MFC], EnableShellContextMenu
- CMFCShellTreeCtrl [MFC], GetFlags
- CMFCShellTreeCtrl [MFC], GetItemPath
- CMFCShellTreeCtrl [MFC], GetRelatedList
- CMFCShellTreeCtrl [MFC], OnChildNotify
- CMFCShellTreeCtrl [MFC], OnGetItemIcon
- CMFCShellTreeCtrl [MFC], OnGetItemText
- CMFCShellTreeCtrl [MFC], Refresh
- CMFCShellTreeCtrl [MFC], SelectPath
- CMFCShellTreeCtrl [MFC], SetFlags
- CMFCShellTreeCtrl [MFC], SetRelatedList
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
ms.openlocfilehash: c6f5856e92c2aca1d23ee6a37b99ea9700ea6db0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753438"
---
# <a name="cmfcshelltreectrl-class"></a>CMFC쉘트리트럴 클래스

클래스는 `CMFCShellTreeCtrl` 셸 항목의 계층 구조를 표시 하여 [CTreeCtrl 클래스](../../mfc/reference/ctreectrl-class.md) 기능을 확장 합니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC쉘트리Ctrl::인에이블쉘컨텍스트메뉴](#enableshellcontextmenu)|바로 가기 메뉴를 사용하거나 사용하지 않도록 설정합니다.|
|[CMFC쉘트리Ctrl::겟플래그](#getflags)|[IShellFolder::열거](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)객체에 전달되는 플래그의 조합을 반환합니다.|
|[CMFC쉘트리Ctrl::겟아이템패스](#getitempath)|항목에 대한 경로를 검색합니다.|
|[CMFC쉘트리Ctrl::관련 목록](#getrelatedlist)|이 `CMFCShellTreeCtrl` 개체와 함께 사용되는 [CMFCShellListCtrl 클래스 개체에](../../mfc/reference/cmfcshelllistctrl-class.md) 대한 포인터를 반환하여 탐색기와 같은 창을 만듭니다.|
|[CMFC쉘트리Ctrl::에차일드 알림](#onchildnotify)|이 멤버 함수는 이 창에 적용되는 알림 메시지를 받을 때 이 창의 부모 창에서 호출됩니다. [(CWnd 재정의::OnChildNotify.)](../../mfc/reference/cwnd-class.md#onchildnotify)|
|[CMFC쉘트리Ctrl::온겟아이템아이콘](#ongetitemicon)||
|[CMFC쉘트리Ctrl:::온겟항목텍스트](#ongetitemtext)||
|[CMFC쉘트리Ctrl::새로 고침](#refresh)|현재 `CMFCShellTreeCtrl` 개체를 새로 고치고 다시 그립니다.|
|[CMFC쉘트리Ctrl::셀렉트 패스](#selectpath)|제공된 PIDL 또는 문자열 경로를 기반으로 적절한 트리 제어 항목을 선택합니다.|
|[CMFC쉘트리Ctrl::세트 플래그](#setflags)|트리 컨텍스트를 필터링하는 플래그를 설정합니다(사용 되는 플래그와 `IShellFolder::EnumObjects`유사).|
|[CMFC쉘트리Ctrl:::세트 관련 목록](#setrelatedlist)|현재 `CMFCShellTreeCtrl` 개체와 개체 간의 `CMFCShellListCtrl` 관계를 설정합니다.|

## <a name="remarks"></a>설명

이 클래스는 `CTreeCtrl` 프로그램에서 트리에 Windows 셸 항목을 포함하도록 설정하여 클래스를 확장합니다. 이 클래스는 `CMFCShellListCtrl` 개체와 연결하여 전체 탐색기 창을 만들 수 있습니다. 그런 다음 트리에서 항목을 선택하면 연결된 목록에 Windows 셸 항목 목록이 표시됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxshelltreeCtrl.h

## <a name="example"></a>예제

다음 예제에서는 `CMFCShellTreeCtrl` 클래스의 개체를 만드는 방법을 보여 줍니다. 이 코드 조각은 [탐색기 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

## <a name="cmfcshelltreectrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a>CMFC쉘트리Ctrl::인에이블쉘컨텍스트메뉴

바로 가기 메뉴를 활성화합니다.

```cpp
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 바로 가기 메뉴를 사용하도록 설정할지 여부를 지정하는 부울입니다.

## <a name="cmfcshelltreectrlgetflags"></a><a name="getflags"></a>CMFC쉘트리Ctrl::겟플래그

[CMFCShellTreeCtrl 클래스](../../mfc/reference/cmfcshelltreectrl-class.md) 개체에 대해 설정된 플래그를 반환합니다.

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>Return Value

현재 설정된 플래그의 조합을 지정하는 DWORD 값입니다.

### <a name="remarks"></a>설명

에 설정된 `CMFCShellTreeCtrl` 플래그는 개체를 새로 고칠 때마다 [IShellFolder::EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) 메서드로 전송됩니다. [CMFCShellTreeCtrl:SetFlags](#setflags) 메서드를 사용하여 플래그를 변경할 수 있습니다.

## <a name="cmfcshelltreectrlgetitempath"></a><a name="getitempath"></a>CMFC쉘트리Ctrl::겟아이템패스

[CMFCShellTreeCtrl 클래스](../../mfc/reference/cmfcshelltreectrl-class.md) 개체에서 항목의 경로를 검색합니다.

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>매개 변수

*스트라스 (strpath)*<br/>
【아웃】 문자열 매개 변수에 대한 참조입니다. 메서드는 이 매개 변수에 항목의 경로를 기록합니다.

*htree항목*<br/>
【인】 메서드는 이 트리 컨트롤 항목에 대 한 경로를 검색합니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아닌 값입니다. 그렇지 않은 경우 0입니다.

### <a name="remarks"></a>설명

이 메서드가 실패하면 *strPath에는* 빈 문자열이 포함됩니다.

*hTreeItem을*지정하지 않으면 이 메서드는 현재 선택한 항목에 대한 문자열을 가져오려고 시도합니다. 항목을 선택하지 않고 *hTreeItem이* NULL인 경우 이 메서드가 실패합니다.

## <a name="cmfcshelltreectrlgetrelatedlist"></a><a name="getrelatedlist"></a>CMFC쉘트리Ctrl::관련 목록

이 [CMFCShellTreeCtrl 개체와 연결된 CMFCShellListCtrl 클래스 개체에](../../mfc/reference/cmfcshelllistctrl-class.md) 대한 [포인터를](../../mfc/reference/cmfcshelltreectrl-class.md) 반환합니다.

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>Return Value

이 트리 `CMFCShellListCtrl` 컨트롤 개체와 연결된 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

개체와 `CMFCShellListCtrl` 함께 `CMFCShellTreeCtrl` 개체를 사용 하 여 탐색기 같은 창을 만들 수 있습니다. [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) 메서드를 사용하여 두 클래스를 연결합니다. 연관된 후 프레임워크는 변경 중인 `CMFCShellListCtrl` if를 자동으로 `CMFCShellTreeCtrl` 업데이트합니다.

## <a name="cmfcshelltreectrlonchildnotify"></a><a name="onchildnotify"></a>CMFC쉘트리Ctrl::에차일드 알림

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>매개 변수

【인】 *메시지*<br/>
【인】 *wParam*<br/>
【인】 *l파라임*<br/>
【인】 *pL결과*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcshelltreectrlongetitemicon"></a><a name="ongetitemicon"></a>CMFC쉘트리Ctrl::온겟아이템아이콘

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>매개 변수

【인】 *p항목*<br/>
【인】 *b 선택됨*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcshelltreectrlongetitemtext"></a><a name="ongetitemtext"></a>CMFC쉘트리Ctrl:::온겟항목텍스트

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>매개 변수

【인】 *p항목*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcshelltreectrlrefresh"></a><a name="refresh"></a>CMFC쉘트리Ctrl::새로 고침

[CMFCShellTreeCtrl을](../../mfc/reference/cmfcshelltreectrl-class.md)새로 고치고 다시 칠합니다.

```cpp
void Refresh();
```

### <a name="remarks"></a>설명

이 메서드를 호출하여 에 표시된 항목의 계층 구조를 새로 고칩니다. `CMFCShellTreeCtrl`

## <a name="cmfcshelltreectrlselectpath"></a><a name="selectpath"></a>CMFC쉘트리Ctrl::셀렉트 패스

제공된 경로에 따라 [CMFCShellTreeCtrl 클래스에서](../../mfc/reference/cmfcshelltreectrl-class.md) 항목을 선택합니다.

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>매개 변수

*lpszPath*<br/>
【인】 항목의 경로를 지정하는 문자열입니다.

*lpidl*<br/>
【인】 항목을 지정하는 PIDL

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 E_FAIL.

## <a name="cmfcshelltreectrlsetflags"></a><a name="setflags"></a>CMFC쉘트리Ctrl::세트 플래그

트리 컨텍스트를 필터링하는 플래그를 설정합니다.

```cpp
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
【인】 설정할 플래그입니다.

*b 새로 고침*<br/>
【인】 즉시 새로 `CMFCShellTreeCtrl` 고쳐야 하는지 여부를 지정하는 부울입니다.

### <a name="remarks"></a>설명

모든 `CMFCShellTreeCtrl` 설정 플래그를 [IShellFolder::열거형](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)개체로 전달합니다. 다른 플래그의 값에 대한 자세한 내용은 [IShellFolder::열거형](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)개체 를 참조하십시오.

## <a name="cmfcshelltreectrlsetrelatedlist"></a><a name="setrelatedlist"></a>CMFC쉘트리Ctrl:::세트 관련 목록

[CMFC쉘리스트Ctrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체를 [CMFC쉘트리Ctrl](../../mfc/reference/cmfcshelltreectrl-class.md) 개체와 연결합니다.

```cpp
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>매개 변수

*p셸리스트*<br/>
【인】 개체에 대한 `CMFCShellListCtrl` 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 `CMFCShellListCtrl` a를 연결합니다. `CMFCShellTreeCtrl` 이러한 개체는 탐색기와 같은 창으로 `CMFCShellTreeCtrl` `CMFCShellListCtrl` 표시될 수 있습니다.

[CMFCShellTreeCtrl](#getrelatedlist) 메서드를 `CMFCShellTreeCtrl`사용하여:GetRelatedList를 `CMFCShellListCtrl` 사용하여 와 관련된 을 검색합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CTreeCtrl 클래스](../../mfc/reference/ctreectrl-class.md)<br/>
[CMFC쉘리스트Ctrl 클래스](../../mfc/reference/cmfcshelllistctrl-class.md)
