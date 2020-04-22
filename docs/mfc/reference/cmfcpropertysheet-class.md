---
title: CMFC프로퍼티시트 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPage
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPageToTree
- AFXPROPERTYSHEET/CMFCPropertySheet::AddTreeCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::EnablePageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::GetHeaderHeight
- AFXPROPERTYSHEET/CMFCPropertySheet::GetLook
- AFXPROPERTYSHEET/CMFCPropertySheet::GetNavBarWidth
- AFXPROPERTYSHEET/CMFCPropertySheet::GetTab
- AFXPROPERTYSHEET/CMFCPropertySheet::InitNavigationControl
- AFXPROPERTYSHEET/CMFCPropertySheet::OnActivatePage
- AFXPROPERTYSHEET/CMFCPropertySheet::OnDrawPageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::OnRemoveTreePage
- AFXPROPERTYSHEET/CMFCPropertySheet::RemoveCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::RemovePage
- AFXPROPERTYSHEET/CMFCPropertySheet::SetIconsList
- AFXPROPERTYSHEET/CMFCPropertySheet::SetLook
helpviewer_keywords:
- CMFCPropertySheet [MFC], CMFCPropertySheet
- CMFCPropertySheet [MFC], AddPage
- CMFCPropertySheet [MFC], AddPageToTree
- CMFCPropertySheet [MFC], AddTreeCategory
- CMFCPropertySheet [MFC], EnablePageHeader
- CMFCPropertySheet [MFC], GetHeaderHeight
- CMFCPropertySheet [MFC], GetLook
- CMFCPropertySheet [MFC], GetNavBarWidth
- CMFCPropertySheet [MFC], GetTab
- CMFCPropertySheet [MFC], InitNavigationControl
- CMFCPropertySheet [MFC], OnActivatePage
- CMFCPropertySheet [MFC], OnDrawPageHeader
- CMFCPropertySheet [MFC], OnRemoveTreePage
- CMFCPropertySheet [MFC], RemoveCategory
- CMFCPropertySheet [MFC], RemovePage
- CMFCPropertySheet [MFC], SetIconsList
- CMFCPropertySheet [MFC], SetLook
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
ms.openlocfilehash: 9b1bb2ce9a957b9cd9f7add983b4da7a228d7a1d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750069"
---
# <a name="cmfcpropertysheet-class"></a>CMFC프로퍼티시트 클래스

`CMFCPropertySheet` 클래스는 각 속성 페이지가 페이지 탭, 도구 모음 단추, 트리 컨트롤 노드 또는 목록 항목으로 표시되는 속성 시트를 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCPropertySheet : public CPropertySheet
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|`CMFCPropertySheet` 개체를 생성합니다.|
|`CMFCPropertySheet::~CMFCPropertySheet`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCPropertySheet::AddPage](#addpage)|속성 시트에 페이지를 추가합니다.|
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|트리 컨트롤에 새 속성 페이지를 추가합니다.|
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|트리 컨트롤에 새 노드를 추가합니다.|
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|각 페이지 위쪽에서 사용자 지정 머리글을 그릴 공간을 예약합니다.|
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|현재 머리글의 높이를 검색합니다.|
|[CMFCPropertySheet::GetLook](#getlook)|현재 속성 시트의 모양을 지정하는 열거형 값을 검색합니다.|
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|탐색 모음의 너비(픽셀)를 검색합니다.|
|[CMFCPropertySheet::GetTab](#gettab)|현재 속성 시트 컨트롤을 지원하는 내부 탭 컨트롤 개체를 검색합니다.|
|`CMFCPropertySheet::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|현재 속성 시트 컨트롤의 모양을 초기화합니다.|
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|속성 페이지를 사용하도록 설정한 경우 프레임워크에서 호출됩니다.|
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|사용자 지정 속성 페이지 머리글을 그리기 위해 프레임워크에서 호출됩니다.|
|`CMFCPropertySheet::OnInitDialog`|[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) 메시지를 처리합니다. [(재정의 시트 재정의::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|트리 컨트롤에서 속성 페이지를 제거하기 위해 프레임워크에서 호출됩니다.|
|`CMFCPropertySheet::PreTranslateMessage`|창 메시지가 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 함수로 전달되기 전에 변환합니다. ( `CPropertySheet::PreTranslateMessage`을 재정의합니다.)|
|[CMFCPropertySheet::RemoveCategory](#removecategory)|트리 컨트롤에서 노드를 제거합니다.|
|[CMFCPropertySheet::RemovePage](#removepage)|속성 시트에서 속성 페이지를 제거합니다.|
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Outlook 창의 탐색 컨트롤에서 사용되는 이미지 목록을 지정합니다.|
|[CMFCPropertySheet::SetLook](#setlook)|속성 시트의 모양을 지정합니다.|

## <a name="remarks"></a>설명

`CMFCPropertySheet` 클래스는 속성 시트(탭 대화 상자라고도 함)를 나타냅니다. `CMFCPropertySheet` 클래스는 다양한 방식으로 속성 페이지를 표시할 수 있습니다.

애플리케이션에서 `CMFCPropertySheet` 클래스를 사용하려면 다음 단계를 수행합니다.

1. `CMFCPropertySheet` 클래스에서 클래스를 파생시키고 클래스 이름(예: CMyPropertySheet)을 지정합니다.

1. 각 속성 페이지에 대한 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) 개체를 생성합니다.

1. CMyPropertySheet 생성자에서 [CMFCPropertySheet::SetLook](#setlook) 메서드를 호출합니다. 이 메서드의 매개 변수는 속성 페이지가 속성 시트의 위쪽이나 왼쪽에 있는 탭, Microsoft OneNote 속성 시트 스타일의 탭, Microsoft Outlook 도구 모음 컨트롤의 단추, 트리 컨트롤의 노드 또는 속성 시트의 왼쪽에 있는 항목 목록으로 표시되도록 지정합니다.

1. Microsoft Outlook 도구 모음 스타일로 속성 시트를 만드는 경우 [CMFCPropertySheet::SetIconsList](#seticonslist) 메서드를 호출하여 이미지 목록을 속성 페이지와 함께 연결합니다.

1. 각 속성 페이지에 대해 [CMFCPropertySheet::AddPage](#addpage) 메서드를 호출합니다.

1. `CMFCPropertySheet` 컨트롤을 만들고 해당 `DoModal` 메서드를 호출합니다.

## <a name="illustrations"></a>그림

다음 그림에서는 포함된 Microsoft Outlook 도구 모음 스타일의 속성 시트를 보여 줍니다. Outlook 도구 모음은 속성 시트의 왼쪽에 나타납니다.

![CMFCPropertySheet 색 컨트롤](../../mfc/reference/media/cmfcpropertysheet_color.png "CMFCPropertySheet 색 컨트롤")

다음 그림에서는 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md) 개체를 포함하는 속성 시트를 설명합니다. 해당 개체는 표준 공용 컨트롤 속성 시트 스타일의 속성 시트입니다.

![CMFCPropertySheet 목록 및 속성 컨트롤](../../mfc/reference/media/cmfcpropertysheet_list.png "CMFCPropertySheet 목록 및 속성 컨트롤")

다음 그림에서는 트리 컨트롤 스타일의 속성 시트를 보여 줍니다.

![속성 트리](../../mfc/reference/media/proptree.png "속성 트리")

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpropertysheet.h

## <a name="cmfcpropertysheetaddpage"></a><a name="addpage"></a>CMFC속성 시트::추가 페이지

속성 시트에 페이지를 추가합니다.

```cpp
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*p페이지*<br/>
【인】 페이지 개체에 대한 포인터입니다. 이 매개 변수는 NULL일 수 없습니다.

### <a name="remarks"></a>설명

이 메서드는 지정 된 속성 페이지를 속성 시트에서 가장 오른쪽 탭으로 추가 합니다. 따라서 이 메서드를 사용 하 여 페이지를 왼쪽에서 오른쪽 순서로 추가 합니다.

속성 시트가 Microsoft Outlook 스타일인 경우 프레임워크는 속성 시트왼쪽에 탐색 단추 목록을 표시합니다. 이 메서드는 속성 페이지를 추가 한 후 목록에 해당 단추를 추가 합니다. 속성 페이지를 표시하려면 해당 단추를 클릭합니다. 속성 시트의 스타일에 대한 자세한 내용은 [CMFCPropertySheet::SetLook](#setlook)을 참조하십시오.

## <a name="cmfcpropertysheetaddpagetotree"></a><a name="addpagetotree"></a>CMFC속성 시트::추가 페이지토트리

트리 컨트롤에 새 속성 페이지를 추가합니다.

```cpp
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,
    CMFCPropertyPage* pPage,
    int nIconNum=-1,
    int nSelIconNum=-1);
```

### <a name="parameters"></a>매개 변수

*p카테고리*<br/>
【인】 지정된 페이지를 최상위 노드와 연결하는 상위 트리 노드 또는 NULL에 대한 포인터입니다. 이 포인터를 얻으려면 [CMFCPropertySheet::AddTreeCategory](#addtreecategory) 메서드를 호출합니다.

*p페이지*<br/>
【인】 속성 페이지 개체에 대한 포인터입니다.

*니콘넘*<br/>
【인】 아이콘의 0기반 인덱스 또는 아이콘이 사용되지 않는 경우 -1입니다. 페이지를 선택하지 않을 때 트리 제어 속성 페이지 옆에 아이콘이 표시됩니다. 기본값은 -1입니다.

*n셀리콘넘*<br/>
【인】 아이콘의 0기반 인덱스 또는 아이콘이 사용되지 않는 경우 -1입니다. 페이지를 선택하면 트리 제어 속성 페이지 옆에 아이콘이 표시됩니다. 기본값은 -1입니다.

### <a name="remarks"></a>설명

이 메서드는 트리 컨트롤의 리프로 속성 페이지를 추가 합니다. 속성 페이지를 추가하려면 개체를 `CMFCPropertySheet` 만들고 *LOOK* 매개 변수가 로 설정된 [CMFCPropertySheet::SetLook](#setlook) 메서드를 `CMFCPropertySheet::PropSheetLook_Tree`호출한 다음 이 메서드를 사용하여 속성 페이지를 추가합니다.

## <a name="cmfcpropertysheetaddtreecategory"></a><a name="addtreecategory"></a>CMFC속성 시트::애드트리카테고리

트리 컨트롤에 새 노드를 추가합니다.

```
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,
    int nIconNum=-1,
    int nSelectedIconNum=-1,
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 노드의 이름입니다.

*니콘넘*<br/>
【인】 아이콘의 0기반 인덱스 또는 아이콘이 사용되지 않는 경우 -1입니다. 페이지를 선택하지 않을 때 트리 제어 속성 페이지 옆에 아이콘이 표시됩니다. 기본값은 -1입니다.

*n선택된 아이콘넘*<br/>
【인】 아이콘의 0기반 인덱스 또는 아이콘이 사용되지 않는 경우 -1입니다. 페이지를 선택하면 트리 제어 속성 페이지 옆에 아이콘이 표시됩니다. 기본값은 -1입니다.

*p부모 범주*<br/>
【인】 지정된 페이지를 최상위 노드와 연결하는 상위 트리 노드 또는 NULL에 대한 포인터입니다. [CMFCPropertySheet::AddTreeCategory](#addtreecategory) 메서드를 사용하여 이 매개 변수를 설정합니다.

### <a name="return-value"></a>Return Value

트리 컨트롤의 새 노드에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 트리 컨트롤에 범주라고도 하는 새 노드를 추가 합니다. 노드를 추가하려면 개체를 `CMFCPropertySheet` 만들고 *LOOK* 매개 변수가 로 설정된 [CMFCPropertySheet::SetLook](#setlook) 메서드를 `CMFCPropertySheet::PropSheetLook_Tree`호출한 다음 이 메서드를 사용하여 노드를 추가합니다.

[CMFCPropertySheet::AddPageToTree](#addpagetotree) 및 [CMFCPropertySheet::AddTree범주에](#addtreecategory)대한 후속 호출에서 이 메서드의 반환 값을 사용합니다.

## <a name="cmfcpropertysheetcmfcpropertysheet"></a><a name="cmfcpropertysheet"></a>CMFC프로퍼티시트::CMFC프로퍼티시트

`CMFCPropertySheet` 개체를 생성합니다.

```
CMFCPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);
```

### <a name="parameters"></a>매개 변수

*pszCaption*<br/>
【인】 속성 시트 캡션을 포함하는 문자열입니다. NULL이 될 수 없습니다.

*nIDCaption*<br/>
【인】 속성 시트 캡션을 포함하는 리소스 ID입니다.

*pParentWnd*<br/>
【인】 속성 시트의 상위 창에 대한 포인터 또는 부모 창이 응용 프로그램의 기본 창인 경우 NULL입니다. 기본값은 NULL입니다.

*아이 셀렉토리페이지*<br/>
【인】 최상위 속성 페이지의 0기반 인덱스입니다. 기본값은 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) 생성자의 매개 변수를 참조하십시오.

## <a name="cmfcpropertysheetenablepageheader"></a><a name="enablepageheader"></a>CMFCPropertySheet::인에이블페이지헤더

각 페이지 위쪽에서 사용자 지정 머리글을 그릴 공간을 예약합니다.

```cpp
void EnablePageHeader(int nHeaderHeight);
```

### <a name="parameters"></a>매개 변수

*n헤더높이*<br/>
【인】 헤더의 높이(픽셀)입니다.

### <a name="remarks"></a>설명

*nHeaderHeight* 매개 변수의 값을 사용하여 사용자 지정 헤더를 그리려면 [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) 메서드를 재정의합니다.

## <a name="cmfcpropertysheetgetheaderheight"></a><a name="getheaderheight"></a>CMFCPropertySheet::Get헤더높이

현재 머리글의 높이를 검색합니다.

```
int GetHeaderHeight() const;
```

### <a name="return-value"></a>Return Value

헤더의 높이(픽셀)입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하기 전에 [CMFCPropertySheet::EnablePageHeader](#enablepageheader) 메서드를 호출합니다.

## <a name="cmfcpropertysheetgetlook"></a><a name="getlook"></a>CMFC속성 시트 :: GetLook

현재 속성 시트의 모양을 지정하는 열거형 값을 검색합니다.

```
PropSheetLook GetLook() const;
```

### <a name="return-value"></a>Return Value

속성 시트의 모양을 지정하는 열거형 값 중 하나입니다. 가능한 값 목록은 [CMFCPropertySheet::SetLook](#setlook)의 비고 섹션에서 열거 테이블을 참조하십시오.

## <a name="cmfcpropertysheetgetnavbarwidth"></a><a name="getnavbarwidth"></a>CMFC속성 시트::겟나브바폭

탐색 모음의 너비를 가져옵니다.

```
int GetNavBarWidth() const;
```

### <a name="return-value"></a>Return Value

탐색 모음의 너비(픽셀)입니다.

## <a name="cmfcpropertysheetgettab"></a><a name="gettab"></a>CMFC속성 시트 :: GetTab

현재 속성 시트 컨트롤을 지원하는 내부 탭 컨트롤 개체를 검색합니다.

```
CMFCTabCtrl& GetTab() const;
```

### <a name="return-value"></a>Return Value

내부 탭 제어 개체입니다.

### <a name="remarks"></a>설명

트리 컨트롤, 탐색 단추 목록 또는 탭된 페이지 집합과 같은 다른 스타일로 표시되도록 속성 시트를 설정할 수 있습니다.

이 메서드를 호출 하기 전에 [CMFCPropertySheet::SetLook](#setlook) 메서드를 호출 하여 속성 시트 컨트롤의 모양을 설정 합니다. 그런 다음 [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) 메서드를 호출하여 내부 탭 제어 개체를 초기화합니다. 이 메서드를 사용 하 여 탭 컨트롤 개체를 검색 하 고 속성 시트에 탭으로 작동 하도록 해당 개체를 사용 합니다.

이 메서드는 속성 시트 컨트롤이 Microsoft OneNote 스타일로 표시되도록 설정되지 않은 경우 디버그 모드에서 어설션합니다.

## <a name="cmfcpropertysheetinitnavigationcontrol"></a><a name="initnavigationcontrol"></a>CMFCPropertySheet::Init내비게이션제어

현재 속성 시트 컨트롤의 모양을 초기화합니다.

```
virtual CWnd* InitNavigationControl();
```

### <a name="return-value"></a>Return Value

속성 시트 컨트롤의 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

속성 시트 컨트롤은 탭된 페이지 집합, 트리 컨트롤 또는 탐색 단추 목록과 같은 여러 가지 형태로 나타날 수 있습니다. [CMFCPropertySheet::SetLook](#setlook) 메서드를 사용하여 속성 시트 컨트롤의 모양을 지정합니다.

## <a name="cmfcpropertysheetonactivatepage"></a><a name="onactivatepage"></a>CMFC속성 시트::온활성화 페이지

속성 페이지를 사용하도록 설정한 경우 프레임워크에서 호출됩니다.

```
virtual void OnActivatePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*p페이지*<br/>
【인】 활성화된 속성 페이지를 나타내는 속성 페이지 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 사용 가능한 속성 페이지가 보기로 스크롤되도록 합니다. 현재 속성 시트의 스타일에 Microsoft Outlook 창이 포함되어 있는 경우 이 메서드는 해당 Outlook 단추를 선택된 상태로 설정합니다.

## <a name="cmfcpropertysheetondrawpageheader"></a><a name="ondrawpageheader"></a>CMFC속성 시트::온드로우 페이지헤더

사용자 지정 속성 페이지에 대 한 헤더를 그리는 프레임 워크에 의해 호출 됩니다.

```
virtual void OnDrawPageHeader(
    CDC* pDC,
    int nPage,
    CRect rectHeader);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*n페이지*<br/>
【인】 0기반 속성 페이지 번호입니다.

*렉트헤더*<br/>
【인】 헤더를 그릴 위치를 지정하는 경계 사각형입니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 아무것도 수행하지 않습니다. 이 메서드를 재정의하는 경우 프레임워크에서 이 메서드를 호출하기 전에 [CMFCPropertySheet::EnablePageHeader](#enablepageheader) 메서드를 호출합니다.

## <a name="cmfcpropertysheetonremovetreepage"></a><a name="onremovetreepage"></a>CMFC속성 시트::에 제거트리 페이지

트리 컨트롤에서 속성 페이지를 제거하기 위해 프레임워크에서 호출됩니다.

```
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*p페이지*<br/>
【인】 제거할 속성 페이지를 나타내는 속성 페이지 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="cmfcpropertysheetremovecategory"></a><a name="removecategory"></a>CMFCProperty시트::제거범주

트리 컨트롤에서 노드를 제거합니다.

```cpp
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```

### <a name="parameters"></a>매개 변수

*p카테고리*<br/>
【인】 제거할 범주(노드)에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 트리 컨트롤에서 범주라고도 하는 노드를 제거 합니다. [CMFCPropertySheet::AddTreeCategory](#addtreecategory) 메서드를 사용하여 트리 컨트롤에 노드를 추가합니다.

## <a name="cmfcpropertysheetremovepage"></a><a name="removepage"></a>CMFCProperty시트::제거페이지

속성 시트에서 속성 페이지를 제거합니다.

```cpp
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>매개 변수

*p페이지*<br/>
【인】 제거할 속성 페이지를 나타내는 속성 페이지 개체에 대한 포인터입니다. NULL이 될 수 없습니다.

*n페이지*<br/>
【인】 제거할 페이지의 0기반 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 지정 된 속성 페이지를 제거 하 고 관련 된 창을 삭제 합니다. *pPage* 매개 변수가 지정하는 속성 페이지 개체는 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) 창이 닫혀야 소멸되지 않습니다.

## <a name="cmfcpropertysheetseticonslist"></a><a name="seticonslist"></a>CMFC속성 시트::설정 아이콘 목록

Outlook 창의 탐색 컨트롤에서 사용되는 이미지 목록을 지정합니다.

```
BOOL SetIconsList(
    UINT uiImageListResID,
    int cx,
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```

### <a name="parameters"></a>매개 변수

*uiImageListResID*<br/>
【인】 이미지 목록의 리소스 ID입니다.

*Cx*<br/>
【인】 이미지 목록의 아이콘 너비(픽셀 단위)입니다.

*clr투명*<br/>
【인】 투명 한 이미지 색상입니다. 이 색상인 이미지 부분은 투명합니다. 기본값은 색상 자홍색, RGB(255,0,255)입니다.

*아이콘*<br/>
【인】 기존 이미지 목록에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

첫 번째 메서드에서 이 메서드가 성공한 경우 TRUE와 오버로드구문입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

속성 시트가 Microsoft Outlook 스타일인 경우 프레임워크는 속성 시트 왼쪽에 Outlook 창 컨트롤이라는 탐색 단추 목록을 표시합니다. 이 메서드를 사용 하 여 Outlook 창 컨트롤에서 사용할 이미지 목록을 설정 합니다.

이 메서드를 지원하는 메서드에 대한 자세한 내용은 [CImageList::만들기](../../mfc/reference/cimagelist-class.md#create) 및 [CImageList::Add](../../mfc/reference/cimagelist-class.md#add)를 참조하십시오. 속성 시트의 스타일을 설정하는 방법에 대한 자세한 내용은 [CMFCPropertySheet::SetLook](#setlook)을 참조하십시오.

## <a name="cmfcpropertysheetsetlook"></a><a name="setlook"></a>CMFC속성 시트::세트룩

속성 시트의 모양을 지정합니다.

```cpp
void SetLook(
    PropSheetLook look,
    int nNavControlWidth=100);
```

### <a name="parameters"></a>매개 변수

*보기*<br/>
【인】 속성 시트의 모양을 지정하는 열거형 값 중 하나입니다. 속성 시트의 기본 스타일은 `CMFCPropertySheet::PropSheetLook_Tabs`입니다. 자세한 내용은 이 항목의 비고 섹션의 표를 참조하십시오.

*nNav컨트롤폭*<br/>
【인】 탐색 컨트롤의 너비(픽셀)입니다. 기본값은 100입니다.

### <a name="remarks"></a>설명

기본값이 아닌 다른 스타일로 속성 시트를 표시하려면 속성 시트 창을 만들기 전에 이 메서드를 호출합니다.

다음 표에는 *look* 매개 변수에 지정할 수 있는 열거형 값이 나열되어 있습니다.

|값|Description|
|-----------|-----------------|
|`CMFCPropertySheet::PropSheetLook_Tabs`|(기본값) 각 속성 페이지에 대한 탭을 표시합니다. 탭은 속성 시트의 맨 위에 표시되며 단일 행에 맞는 것보다 많은 탭이 있는 경우 누적됩니다.|
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|속성 시트의 왼쪽에 Microsoft Outlook 막대 스타일로 탐색 단추 목록을 표시합니다. 목록의 각 단추는 속성 페이지에 해당합니다. 목록의 가시 영역에 맞는 것보다 많은 단추가 있는 경우 프레임워크에 스크롤 화살표가 표시됩니다.|
|`CMFCPropertySheet::PropSheetLook_Tree`|속성 시트의 왼쪽에 트리 컨트롤을 표시합니다. 트리 컨트롤의 각 부모 또는 자식 노드는 속성 페이지에 해당합니다. 트리 컨트롤의 가시 영역에 맞는 노드보다 많은 노드가 있는 경우 프레임워크에 스크롤 화살표가 표시됩니다.|
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|각 속성 페이지에 대해 Microsoft OneNote 스타일로 탭을 표시합니다. 프레임워크는 속성 시트 의 맨 위에 탭을 표시하고 단일 행에 맞는 탭이 더 많은 경우 스크롤 화살표를 표시합니다.|
|`CMFCPropertySheet::PropSheetLook_List`|속성 시트의 왼쪽에 목록을 표시합니다. 각 목록 항목은 속성 페이지에 해당합니다. 목록의 가시 영역에 맞는 것보다 많은 목록 항목이 있는 경우 프레임워크에 스크롤 화살표가 표시됩니다.|

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC프로퍼티페이지 클래스](../../mfc/reference/cmfcpropertypage-class.md)<br/>
[CMFC아웃아웃바 클래스](../../mfc/reference/cmfcoutlookbar-class.md)
