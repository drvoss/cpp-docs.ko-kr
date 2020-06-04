---
title: CMFC쉘리스트Ctrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayParentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::EnableShellContextMenu
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolderName
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentItemIdList
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentShellFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemPath
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemTypes
- AFXSHELLLISTCTRL/CMFCShellListCtrl::IsDesktop
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnCompareItems
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileDate
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileSize
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemIcon
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemText
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnSetColumns
- AFXSHELLLISTCTRL/CMFCShellListCtrl::Refresh
- AFXSHELLLISTCTRL/CMFCShellListCtrl::SetItemTypes
helpviewer_keywords:
- CMFCShellListCtrl [MFC], DisplayFolder
- CMFCShellListCtrl [MFC], DisplayParentFolder
- CMFCShellListCtrl [MFC], EnableShellContextMenu
- CMFCShellListCtrl [MFC], GetCurrentFolder
- CMFCShellListCtrl [MFC], GetCurrentFolderName
- CMFCShellListCtrl [MFC], GetCurrentItemIdList
- CMFCShellListCtrl [MFC], GetCurrentShellFolder
- CMFCShellListCtrl [MFC], GetItemPath
- CMFCShellListCtrl [MFC], GetItemTypes
- CMFCShellListCtrl [MFC], IsDesktop
- CMFCShellListCtrl [MFC], OnCompareItems
- CMFCShellListCtrl [MFC], OnFormatFileDate
- CMFCShellListCtrl [MFC], OnFormatFileSize
- CMFCShellListCtrl [MFC], OnGetItemIcon
- CMFCShellListCtrl [MFC], OnGetItemText
- CMFCShellListCtrl [MFC], OnSetColumns
- CMFCShellListCtrl [MFC], Refresh
- CMFCShellListCtrl [MFC], SetItemTypes
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
ms.openlocfilehash: 445556535217b0887a02227a0773c287911922a2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753481"
---
# <a name="cmfcshelllistctrl-class"></a>CMFC쉘리스트Ctrl 클래스

클래스는 `CMFCShellListCtrl` Windows 목록 제어 기능을 제공 하 고 셸 항목 목록을 표시 하는 기능을 포함 하 여 확장 합니다.

## <a name="syntax"></a>구문

```
class CMFCShellListCtrl : public CMFCListCtrl
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC쉘리스트Ctrl::DisplayFolder](#displayfolder)|제공된 폴더에 포함된 항목 목록을 표시합니다.|
|[CMFC쉘리스트Ctrl::DisplayParentFolder](#displayparentfolder)|현재 표시된 폴더의 상위 폴더인 폴더에 포함된 항목 목록을 표시합니다.|
|[CMFC쉘리스트Ctrl::인에이블쉘컨텍스트메뉴](#enableshellcontextmenu)|바로 가기 메뉴를 사용하거나 사용하지 않도록 설정합니다.|
|[CMFC쉘리스트Ctrl::GetCurrentFolder](#getcurrentfolder)|현재 폴더의 경로를 검색합니다.|
|[CMFC쉘리스트Ctrl::GetCurrentFolderName](#getcurrentfoldername)|현재 폴더의 이름을 검색합니다.|
|[CMFC쉘리스트Ctrl::GetCurrent항목ID리스트](#getcurrentitemidlist)|현재 목록 컨트롤 항목의 PIDL을 반환합니다.|
|[CMFC쉘리스트Ctrl::GetCurrentShell폴더](#getcurrentshellfolder)|현재 Shell 폴더에 대한 포인터를 반환합니다.|
|[CMFC쉘리스트Ctrl:::겟아이템패스](#getitempath)|항목의 텍스트 경로를 반환합니다.|
|[CMFC쉘리스트Ctrl::GetItemtype](#getitemtypes)|목록 컨트롤에 의해 표시되는 Shell 항목 유형을 반환합니다.|
|[CMFC쉘리스트Ctrl::IsDesktop](#isdesktop)|현재 선택된 폴더가 데스크톱 폴더인지 확인합니다.|
|[CMFC쉘리스트Ctrl::온비교항목](#oncompareitems)|프레임워크는 두 항목을 비교할 때 이 메서드를 호출합니다. [(CMFCListCtrl 재정의::OnCompareItems.)](../../mfc/reference/cmfclistctrl-class.md#oncompareitems)|
|[CMFC쉘리스트Ctrl::온포맷파일데이트](#onformatfiledate)|프레임워크가 목록 컨트롤에 의해 표시되는 파일 날짜를 검색할 때 호출됩니다.|
|[CMFC쉘리스트Ctrl::온포맷파일크기](#onformatfilesize)|프레임워크가 목록 컨트롤의 파일 크기를 변환할 때 호출됩니다.|
|[CMFC쉘리스트Ctrl:::온겟항목아이콘](#ongetitemicon)|프레임워크가 목록 제어 항목의 아이콘을 검색할 때 호출됩니다.|
|[CMFC쉘리스트Ctrl:::온겟항목텍스트](#ongetitemtext)|프레임워크가 목록 제어 항목의 텍스트를 변환할 때 호출됩니다.|
|[CMFC쉘리스트Ctrl::온셋컬럼](#onsetcolumns)|열의 이름을 설정할 때 프레임워크에서 호출합니다.|
|[CMFC쉘리스트Ctrl::새로 고침](#refresh)|목록 컨트롤을 새로 고치고 다시 그립니다.|
|[CMFC쉘리스트Ctrl::세트항목 유형](#setitemtypes)|목록 컨트롤에 의해 표시되는 항목의 유형을 설정합니다.|

## <a name="remarks"></a>설명

클래스는 `CMFCShellListCtrl` 프로그램에서 Windows 셸 항목을 나열할 수 있도록 설정 하여 [CMFCListCtrl 클래스의](../../mfc/reference/cmfclistctrl-class.md) 기능을 확장 합니다. 사용되는 표시 형식은 탐색기 창의 목록 보기와 같습니다.

[CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) 개체는 `CMFCShellListCtrl` 개체와 연결하여 전체 탐색기 창을 만들 수 있습니다. 그런 다음 에서 `CMFCShellTreeCtrl` 항목을 선택하면 `CMFCShellListCtrl` 개체가 선택한 항목의 내용을 나열합니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCShellListCtrl` 클래스의 개체를 만드는 방법과 현재 표시된 폴더의 상위 폴더를 표시하는 방법을 보여 줍니다. 이 코드 조각은 [탐색기 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

`CMFCShellListCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afx셸리스트Ctrl.h

## <a name="cmfcshelllistctrldisplayfolder"></a><a name="displayfolder"></a>CMFC쉘리스트Ctrl::DisplayFolder

제공된 폴더에 포함된 항목 목록을 표시합니다.

```
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```

### <a name="parameters"></a>매개 변수

*lpszPath*<br/>
【인】 폴더의 경로를 포함하는 문자열입니다.

*lpItemInfo*<br/>
【인】 표시할 폴더를 `LPAFX_SHELLITEMINFO` 설명하는 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 E_FAIL.

## <a name="cmfcshelllistctrldisplayparentfolder"></a><a name="displayparentfolder"></a>CMFC쉘리스트Ctrl::DisplayParentFolder

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체를 업데이트하여 현재 표시된 폴더의 상위 폴더를 표시합니다.

```
virtual HRESULT DisplayParentFolder();
```

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 E_FAIL.

## <a name="cmfcshelllistctrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a>CMFC쉘리스트Ctrl::인에이블쉘컨텍스트메뉴

바로 가기 메뉴를 활성화합니다.

```cpp
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 프레임워크에서 바로 가기 메뉴를 사용할 수 있는지 여부를 지정하는 부울입니다.

## <a name="cmfcshelllistctrlgetcurrentfolder"></a><a name="getcurrentfolder"></a>CMFC쉘리스트Ctrl::GetCurrentFolder

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체에서 현재 선택한 폴더의 경로를 검색합니다.

```
BOOL GetCurrentFolder(CString& strPath) const;
```

### <a name="parameters"></a>매개 변수

*스트라스 (strpath)*<br/>
【아웃】 메서드가 경로를 작성하는 문자열 매개 변수에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아닌 값입니다. 그렇지 않은 경우 0입니다.

### <a name="remarks"></a>설명

에서 선택한 폴더가 없는 경우 `CMFCShellListCtrl`이 메서드가 실패합니다.

## <a name="cmfcshelllistctrlgetcurrentfoldername"></a><a name="getcurrentfoldername"></a>CMFC쉘리스트Ctrl::GetCurrentFolderName

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체에서 현재 선택한 폴더의 이름을 검색합니다.

```
BOOL GetCurrentFolderName(CString& strName) const;
```

### <a name="parameters"></a>매개 변수

*strName*<br/>
【아웃】 메서드가 이름을 쓰는 문자열 매개 변수에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아닌 값입니다. 그렇지 않은 경우 0입니다.

### <a name="remarks"></a>설명

에서 선택한 폴더가 없는 경우 `CMFCShellListCtrl`이 메서드가 실패합니다.

## <a name="cmfcshelllistctrlgetcurrentitemidlist"></a><a name="getcurrentitemidlist"></a>CMFC쉘리스트Ctrl::GetCurrent항목ID리스트

현재 선택한 항목의 PIDL을 반환합니다.

```
LPITEMIDLIST GetCurrentItemIdList() const;
```

### <a name="return-value"></a>Return Value

현재 항목의 PIDL입니다.

## <a name="cmfcshelllistctrlgetcurrentshellfolder"></a><a name="getcurrentshellfolder"></a>CMFC쉘리스트Ctrl::GetCurrentShell폴더

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체에서 현재 선택한 항목에 대한 포인터를 가져옵니다.

```
const IShellFolder* GetCurrentShellFolder() const;
```

### <a name="return-value"></a>Return Value

선택한 개체에 대한 [IShellFolder 인터페이스에](/windows/win32/api/shobjidl_core/nn-shobjidl_core-ishellfolder) 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 현재 선택 된 개체가 없는 경우 NULL을 반환 합니다.

## <a name="cmfcshelllistctrlgetitempath"></a><a name="getitempath"></a>CMFC쉘리스트Ctrl:::겟아이템패스

항목의 경로를 검색합니다.

```
BOOL GetItemPath(
    CString& strPath,
    int iItem) const;
```

### <a name="parameters"></a>매개 변수

*스트라스 (strpath)*<br/>
【아웃】 경로를 받는 문자열에 대한 참조입니다.

*iItem*<br/>
【인】 목록 항목의 인덱스입니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

*iItem에서* 제공하는 인덱스는 [CMFCShellListCtrl 클래스](../../mfc/reference/cmfcshelllistctrl-class.md) 개체에서 현재 표시되는 항목을 기반으로 합니다.

## <a name="cmfcshelllistctrlgetitemtypes"></a><a name="getitemtypes"></a>CMFC쉘리스트Ctrl::GetItemtype

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체에 의해 표시되는 항목의 유형을 반환합니다.

```
SHCONTF GetItemTypes() const;
```

### <a name="return-value"></a>Return Value

에 나열된 항목의 형식을 포함하는 [SHCONTF](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf) 값입니다. `CMFCShellListCtrl`

### <a name="remarks"></a>설명

`CMFCShellListCtrl`에 나열된 항목의 형식을 설정하려면 [CMFCShellListCtrl::SetItemtypes](#setitemtypes)을 호출합니다.

## <a name="cmfcshelllistctrlisdesktop"></a><a name="isdesktop"></a>CMFC쉘리스트Ctrl::IsDesktop

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체에 표시되는 폴더가 데스크톱 폴더인지 확인합니다.

```
BOOL IsDesktop() const;
```

### <a name="return-value"></a>Return Value

표시된 폴더가 데스크톱 폴더인 경우 TRUE; 그렇지 않으면 거짓.

## <a name="cmfcshelllistctrloncompareitems"></a><a name="oncompareitems"></a>CMFC쉘리스트Ctrl::온비교항목

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>매개 변수

【인】 *l파라름1*<br/>
【인】 *l파라름2*<br/>
【인】 *아이 칼럼*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcshelllistctrlonformatfiledate"></a><a name="onformatfiledate"></a>CMFC쉘리스트Ctrl::온포맷파일데이트

프레임워크는 개체와 연결된 날짜를 문자열로 변환해야 하는 경우 이 메서드를 호출합니다.

```
virtual void OnFormatFileDate(
    const CTime& tmFile,
    CString& str);
```

### <a name="parameters"></a>매개 변수

*tmFile*<br/>
【인】 파일과 연결된 날짜입니다.

*Str*<br/>
【아웃】 형식이 지정된 파일 날짜가 포함된 문자열입니다.

### <a name="remarks"></a>설명

[CMFCShellListCtrl 클래스](../../mfc/reference/cmfcshelllistctrl-class.md) 개체가 파일과 연결된 날짜를 표시하는 경우 해당 날짜를 문자열 형식으로 변환해야 합니다. 는 `CMFCShellListCtrl` 이 메서드를 사용하여 변환합니다. 기본적으로 이 메서드는 현재 로캘을 사용하여 날짜를 문자열로 포맷합니다.

## <a name="cmfcshelllistctrlonformatfilesize"></a><a name="onformatfilesize"></a>CMFC쉘리스트Ctrl::온포맷파일크기

프레임워크는 개체의 크기를 문자열로 변환할 때 이 메서드를 호출합니다.

```
virtual void OnFormatFileSize(
    long lFileSize,
    CString& str);
```

### <a name="parameters"></a>매개 변수

*l파일크기*<br/>
【인】 프레임워크가 표시할 파일의 크기입니다.

*Str*<br/>
【아웃】 형식이 지정된 파일 크기를 포함하는 문자열입니다.

### <a name="remarks"></a>설명

[CMFCShellListCtrl 클래스](../../mfc/reference/cmfcshelllistctrl-class.md) 개체가 파일 크기를 표시해야 하는 경우 파일 크기를 문자열 형식으로 변환해야 합니다. 는 `CMFCShellListCtrl` 이 메서드를 사용하여 변환합니다. 기본적으로 이 메서드는 파일 크기를 바이트에서 킬로바이트로 변환한 다음 현재 로캘을 사용하여 크기를 문자열로 포맷합니다.

## <a name="cmfcshelllistctrlongetitemicon"></a><a name="ongetitemicon"></a>CMFC쉘리스트Ctrl:::온겟항목아이콘

프레임워크는 이 메서드를 호출하여 셸 목록 항목과 연결된 아이콘을 검색합니다.

```
virtual int OnGetItemIcon(
    int iItem,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>매개 변수

*iItem*<br/>
【인】 항목 인덱스입니다.

*pItem*<br/>
【인】 항목을 설명하는 LPAFX_SHELLITEMINFO 매개 변수입니다.

### <a name="return-value"></a>Return Value

성공하면 아이콘 이미지의 인덱스; -1 함수가 실패하면

### <a name="remarks"></a>설명

아이콘 이미지 인덱스는 시스템 이미지 목록을 기반으로 합니다.

기본적으로 이 메서드는 *pItem* 매개 변수를 사용합니다. *iItem* 값은 기본 구현에서 사용되지 않습니다. *iItem을* 사용하여 사용자 지정 동작을 구현할 수 있습니다.

## <a name="cmfcshelllistctrlongetitemtext"></a><a name="ongetitemtext"></a>CMFC쉘리스트Ctrl:::온겟항목텍스트

프레임워크는 셸 항목의 텍스트를 검색해야 하는 경우 이 메서드를 호출합니다.

```
virtual CString OnGetItemText(
    int iItem,
    int iColumn,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>매개 변수

*iItem*<br/>
【인】 항목 인덱스입니다.

*iColumn*<br/>
【인】 관심 있는 열입니다.

*pItem*<br/>
【인】 항목을 설명하는 LPAFX_SHELLITEMINFO 매개 변수입니다.

### <a name="return-value"></a>Return Value

항목과 연결된 텍스트를 포함하는 A입니다. `CString`

### <a name="remarks"></a>설명

개체의 `CMFCShellListCtrl` 각 항목에는 하나 이상의 열에 텍스트가 있을 수 있습니다. 프레임워크에서 이 메서드를 호출하면 관심 있는 열을 지정합니다. 이 함수를 수동으로 호출하는 경우 관심 있는 열도 지정해야 합니다.

기본적으로 이 메서드는 *pItem* 매개 변수를 사용하여 처리할 항목을 결정합니다. *iItem* 값은 기본 구현에서 사용되지 않습니다.

## <a name="cmfcshelllistctrlonsetcolumns"></a><a name="onsetcolumns"></a>CMFC쉘리스트Ctrl::온셋컬럼

프레임워크는 열의 이름을 설정할 때 이 메서드를 호출합니다.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>설명

기본적으로 프레임워크는 `CMFCShellListCtrl` 개체에 4개의 열을 만듭니다. 이러한 열의 이름은 **이름,** **크기,** **유형**및 **수정된**입니다. 이 메서드를 재정의하여 열 수와 해당 이름을 사용자 지정할 수 있습니다.

## <a name="cmfcshelllistctrlrefresh"></a><a name="refresh"></a>CMFC쉘리스트Ctrl::새로 고침

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체를 새로 고치고 다시 그립니다.

```
virtual HRESULT Refresh();
```

### <a name="return-value"></a>Return Value

`S_OK`성공하는 경우; 그렇지 않으면 오류 값입니다.

### <a name="remarks"></a>설명

`CMFCShellListCtrl` 이 메서드를 호출하여 개체에 의해 표시되는 항목 목록을 새로 고칩니다.

## <a name="cmfcshelllistctrlsetitemtypes"></a><a name="setitemtypes"></a>CMFC쉘리스트Ctrl::세트항목 유형

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) 개체에 나열된 항목의 형식을 설정 합니다.

```cpp
void SetItemTypes(SHCONTF nTypes);
```

### <a name="parameters"></a>매개 변수

*n유형*<br/>
【인】 개체가 지원하는 항목 `CMFCShellListCtrl` 유형의 목록입니다.

### <a name="remarks"></a>설명

항목 유형 목록에 대한 자세한 내용은 [SHCONTF](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf)를 참조하십시오.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리스트Ctrl 클래스](../../mfc/reference/cmfclistctrl-class.md)<br/>
[CMFC쉘트리트럴 클래스](../../mfc/reference/cmfcshelltreectrl-class.md)
