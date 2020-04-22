---
title: CShellManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
helpviewer_keywords:
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
ms.openlocfilehash: 1c2f9ac1658f50f0ec5bd9e2f53d270c09bfcb6a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750328"
---
# <a name="cshellmanager-class"></a>CShellManager 클래스

PIDL(식별자 포인터 목록)에 대한 포인터를 사용하여 작업할 수 있는 몇 가지 메서드를 구현합니다.

## <a name="syntax"></a>구문

```
class CShellManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C셸 관리자:::C셸관리자](#cshellmanager)|`CShellManager` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CShellManager::찾아보기폴더](#browseforfolder)|사용자가 셸 폴더를 선택할 수 있도록 하는 대화 상자를 표시합니다.|
|[CShellManager:::연결 항목](#concatenateitem)|두 개의 PID를 연결합니다.|
|[CShellManager::복사 항목](#copyitem)|새 PIDL을 만들고 제공된 PIDL을 복사합니다.|
|[CShellManager::만들기항목](#createitem)|지정된 크기의 새 PIDL을 만듭니다.|
|[CShellManager:::무료 항목](#freeitem)|제공된 PIDL을 삭제합니다.|
|[CShellManager::GetItemCount](#getitemcount)|제공된 PIDL의 항목 수를 반환합니다.|
|[CShellManager::GetItemSize](#getitemsize)|제공된 PIDL 의 크기를 반환합니다.|
|[CShellManager::GetNext항목](#getnextitem)|PIDL에서 다음 항목을 반환합니다.|
|[CShellManager::GetParent항목](#getparentitem)|제공된 항목의 상위 항목을 검색합니다.|
|[CShellManager::항목FromPath](#itemfrompath)|제공된 경로로 식별된 항목에 대한 PIDL을 검색합니다.|

## <a name="remarks"></a>설명

`CShellManager` 클래스의 메서드는 모두 PIDL을 처리합니다. PIDL은 셸 개체에 대한 고유 식별자입니다.

개체를 `CShellManager` 수동으로 만들지 않아야 합니다. 응용 프로그램의 프레임워크에 의해 자동으로 만들어집니다. 그러나 응용 프로그램의 초기화 프로세스 중에 [CWinAppEx::InitShellManager를](../../mfc/reference/cwinappex-class.md#initshellmanager) 호출해야 합니다. 응용 프로그램에 대한 셸 관리자에 대한 포인터를 얻으려면 [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)로 전화하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CShellManager](../../mfc/reference/cshellmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxshellmanager.h

## <a name="cshellmanagerbrowseforfolder"></a><a name="browseforfolder"></a>CShellManager::찾아보기폴더

사용자가 셸 폴더를 선택할 수 있도록 하는 대화 상자를 표시합니다.

```
BOOL BrowseForFolder(
    CString& strOutFolder,
    CWnd* pWndParent = NULL,
    LPCTSTR lplszInitialFolder = NULL,
    LPCTSTR lpszTitle = NULL,
    UINT ulFlags = BIF_RETURNONLYFSDIRS,
    LPINT piFolderImage = NULL);
```

### <a name="parameters"></a>매개 변수

*스트라우트 폴더*<br/>
【아웃】 메서드에서 선택한 폴더의 경로를 저장하는 데 사용되는 문자열입니다.

*pWndParent*<br/>
【인】 상위 창에 대한 포인터입니다.

*lplsz초기폴더*<br/>
【인】 대화 상자가 표시될 때 기본적으로 선택된 폴더가 포함된 문자열입니다.

*lpszTitle*<br/>
【인】 대화 상자의 제목입니다.

*ulFlags*<br/>
【인】 대화 상자에 대한 옵션을 지정하는 플래그입니다. 자세한 설명은 [BROWSEINFO를](/windows/win32/api/shlobj_core/ns-shlobj_core-browseinfow) 참조하십시오.

*파이폴더이미지*<br/>
【아웃】 메서드가 선택한 폴더의 이미지 인덱스를 쓰는 정수 값에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

사용자가 대화 상자에서 폴더를 선택하면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드를 호출하면 응용 프로그램이 만들고 사용자가 폴더를 선택할 수 있는 대화 상자를 표시합니다. 메서드는 *strOutFolder* 매개 변수에 폴더의 경로를 작성합니다.

### <a name="example"></a>예제

다음 예제에서는 `CShellManager` `CWinAppEx::GetShellManager` 메서드를 사용 하 여 개체에 대 한 참조를 검색 하는 방법 및 메서드를 `BrowseForFolder` 사용 하는 방법을 보여 줍니다. 이 코드 조각은 [탐색기 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]

## <a name="cshellmanagerconcatenateitem"></a><a name="concatenateitem"></a>CShellManager:::연결 항목

두 개의 PID를 포함하는 새 목록을 만듭니다.

```
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,
    LPCITEMIDLIST pidl2);
```

### <a name="parameters"></a>매개 변수

*피들1*<br/>
【인】 첫 번째 항목입니다.

*pidl2*<br/>
【인】 두 번째 항목입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 새 항목 목록에 대한 포인터입니다( 그렇지 않으면 NULL).

### <a name="remarks"></a>설명

이 메서드는 *pidl1* 및 *pidl2를*모두 포함할 수 있을 만큼 큰 새 [ITEMIDLIST를](/windows/win32/api/shtypes/ns-shtypes-itemidlist) 만듭니다. 그런 다음 *pidl1* 및 *pidl2를* 새 목록에 복사합니다.

## <a name="cshellmanagercopyitem"></a><a name="copyitem"></a>CShellManager::복사 항목

항목 목록을 복사합니다.

```
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```

### <a name="parameters"></a>매개 변수

*피들 소스*<br/>
【인】 원래 항목 목록입니다.

### <a name="return-value"></a>Return Value

성공한 경우 새로 만든 항목 목록에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

새로 만든 항목 목록은 원본 항목 목록과 크기가 같습니다.

## <a name="cshellmanagercreateitem"></a><a name="createitem"></a>CShellManager::만들기항목

새 PIDL을 만듭니다.

```
LPITEMIDLIST CreateItem(UINT cbSize);
```

### <a name="parameters"></a>매개 변수

*cbSize*<br/>
【인】 항목 목록의 크기입니다.

### <a name="return-value"></a>Return Value

성공한 경우 생성된 항목 목록에 대한 포인터입니다. 그렇지 않으면 NULL.

## <a name="cshellmanagercshellmanager"></a><a name="cshellmanager"></a>C셸 관리자:::C셸관리자

`CShellManager` 개체를 생성합니다.

```
CShellManager();
```

### <a name="remarks"></a>설명

대부분의 경우 `CShellManager` 직접 만들 필요가 없습니다. 기본적으로 프레임 워크는 당신을 위해 하나를 만듭니다. 에 대한 포인터를 `CShellManager`얻으려면 [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)를 호출하십시오. `CShellManager` 수동으로 만드는 경우 [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).

## <a name="cshellmanagerfreeitem"></a><a name="freeitem"></a>CShellManager:::무료 항목

항목 목록을 삭제합니다.

```cpp
void FreeItem(LPITEMIDLIST pidl);
```

### <a name="parameters"></a>매개 변수

*Pidl*<br/>
【인】 삭제할 항목 목록입니다.

## <a name="cshellmanagergetitemcount"></a><a name="getitemcount"></a>CShellManager::GetItemCount

항목 목록의 항목 수를 반환합니다.

```
UINT GetItemCount(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>매개 변수

*Pidl*<br/>
【인】 항목 목록에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

항목 목록의 항목 수입니다.

## <a name="cshellmanagergetitemsize"></a><a name="getitemsize"></a>CShellManager::GetItemSize

항목 목록의 크기를 반환합니다.

```
UINT GetItemSize(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>매개 변수

*Pidl*<br/>
【인】 항목 목록에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

항목 목록의 크기입니다.

## <a name="cshellmanagergetnextitem"></a><a name="getnextitem"></a>CShellManager::GetNext항목

포인터에서 PIDL(항목 식별자 목록)에 대한 다음 항목을 검색합니다.

```
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>매개 변수

*Pidl*<br/>
【인】 반복할 항목 목록입니다.

### <a name="return-value"></a>Return Value

목록의 다음 항목에 대한 포인터입니다.

### <a name="remarks"></a>설명

목록에 항목이 더 이상 없는 경우 이 메서드는 NULL을 반환합니다.

## <a name="cshellmanagergetparentitem"></a><a name="getparentitem"></a>CShellManager::GetParent항목

PIDL(항목 식별자 목록)에 대한 포인터의 부모를 검색합니다.

```
int GetParentItem(
    LPCITEMIDLIST lpidl,
    LPITEMIDLIST& lpidlParent);
```

### <a name="parameters"></a>매개 변수

*lpidl*<br/>
【인】 부모가 검색되는 PIDL입니다.

*lpidlParent*<br/>
【아웃】 메서드가 결과를 저장할 PIDL에 대한 참조입니다.

### <a name="return-value"></a>Return Value

상위 PIDL의 수준입니다.

### <a name="remarks"></a>설명

PIDL 수준은 데스크톱을 기준으로 합니다. 데스크톱 PIDL의 수준은 0으로 간주됩니다.

## <a name="cshellmanageritemfrompath"></a><a name="itemfrompath"></a>CShellManager::항목FromPath

문자열 경로로 식별된 항목에서 PIDL(항목 식별자 목록)에 대한 포인터를 검색합니다.

```
HRESULT ItemFromPath(
    LPCTSTR lpszPath,
    LPITEMIDLIST& pidl);
```

### <a name="parameters"></a>매개 변수

*lpszPath*<br/>
【인】 항목의 경로를 지정하는 문자열입니다.

*Pidl*<br/>
【아웃】 PIDL에 대한 참조입니다. 메서드는 이 PIDL을 사용하여 포인터를 반환 값으로 저장합니다.

### <a name="return-value"></a>Return Value

성공하면 NOERROR를 반환합니다. OLE 정의 오류 값입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
