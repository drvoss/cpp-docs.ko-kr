---
title: CMFC리본상태 바 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
helpviewer_keywords:
- CMFCRibbonStatusBar [MFC], AddDynamicElement
- CMFCRibbonStatusBar [MFC], AddElement
- CMFCRibbonStatusBar [MFC], AddExtendedElement
- CMFCRibbonStatusBar [MFC], AddSeparator
- CMFCRibbonStatusBar [MFC], Create
- CMFCRibbonStatusBar [MFC], CreateEx
- CMFCRibbonStatusBar [MFC], FindByID
- CMFCRibbonStatusBar [MFC], FindElement
- CMFCRibbonStatusBar [MFC], GetCount
- CMFCRibbonStatusBar [MFC], GetElement
- CMFCRibbonStatusBar [MFC], GetExCount
- CMFCRibbonStatusBar [MFC], GetExElement
- CMFCRibbonStatusBar [MFC], GetExtendedArea
- CMFCRibbonStatusBar [MFC], GetSpace
- CMFCRibbonStatusBar [MFC], IsBottomFrame
- CMFCRibbonStatusBar [MFC], IsExtendedElement
- CMFCRibbonStatusBar [MFC], IsInformationMode
- CMFCRibbonStatusBar [MFC], RecalcLayout
- CMFCRibbonStatusBar [MFC], RemoveAll
- CMFCRibbonStatusBar [MFC], RemoveElement
- CMFCRibbonStatusBar [MFC], SetInformation
- CMFCRibbonStatusBar [MFC], OnDrawInformation
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
ms.openlocfilehash: 8d90e01db022c33edd654e83af05e9986799f2b9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754048"
---
# <a name="cmfcribbonstatusbar-class"></a>CMFC리본상태 바 클래스

클래스는 `CMFCRibbonStatusBar` 리본 요소를 표시할 수 있는 상태 표시줄 컨트롤을 구현 합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonStatusBar : public CMFCRibbonBar
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 리본 상태 표시줄::추가 동적 요소](#adddynamicelement)|리본 상태 표시줄에 동적 요소를 추가합니다.|
|[CMFC 리본 상태 표시줄::추가 요소](#addelement)|리본 상태 표시줄에 새 리본 요소를 추가합니다.|
|[CMFC 리본 상태 표시줄::확장 요소 추가](#addextendedelement)|리본 상태 표시줄의 확장 영역에 리본 요소를 추가합니다.|
|[CMFC리본 상태 표시줄::추가 분리기](#addseparator)|리본 상태 표시줄에 구분 기호를 추가합니다.|
|[CMFC 리본 상태 표시줄::만들기](#create)|리본 상태 표시줄을 만듭니다.|
|[CMFC 리본 상태 표시줄::만들기 Ex](#createex)|확장된 스타일로 리본 상태 표시줄을 만듭니다.|
|[CMFC 리본 상태 표시줄::찾기ByID](#findbyid)||
|[CMFC 리본 상태 표시줄::찾기 요소](#findelement)|지정된 명령 ID가 있는 요소에 대한 포인터를 반환합니다.|
|[CMFC 리본 상태 표시줄::GetCount](#getcount)|리본 상태 표시줄의 기본 영역에 있는 요소 수를 반환합니다.|
|[CMFC 리본 상태 표시줄::GetElement](#getelement)|지정된 인덱스에 있는 요소에 대한 포인터를 반환합니다.|
|[CMFC 리본 상태 표시줄::GetExCount](#getexcount)|리본 상태 표시줄의 확장 영역에 있는 요소 수를 반환합니다.|
|[CMFC 리본 상태 표시줄::GetExElement](#getexelement)|리본 메뉴 상태 표시줄에서 확장된 영역의 지정한 인덱스에 있는 요소에 대한 포인터를 반환합니다.|
|[CMFC 리본 상태 표시줄::GetExtendedArea](#getextendedarea)||
|[CMFC 리본 상태 표시줄::겟스페이스](#getspace)||
|[CMFC 리본 상태 표시줄::IsBottom프레임](#isbottomframe)||
|[CMFC 리본 상태 표시줄::확장 요소](#isextendedelement)||
|[CMFC 리본 상태 표시줄::IsInformationMode](#isinformationmode)|리본 상태 표시줄에 대해 정보 모드가 활성화되어 있는지 여부를 결정합니다.|
|[CMFC 리본 상태 표시줄::recalc레이아웃](#recalclayout)|[(CMFC 리본바 재정의::RecalcLayout.)](../../mfc/reference/cmfcribbonbar-class.md#recalclayout)|
|[CMFC 리본 상태 표시줄::모두 제거](#removeall)|리본 상태 표시줄에서 모든 요소를 제거합니다.|
|[CMFC 리본 상태 표시줄::제거요소](#removeelement)|리본 상태 표시줄에서 지정된 명령 ID가 있는 요소를 제거합니다.|
|[CMFC 리본 상태 표시줄::설정 정보](#setinformation)|리본 상태 표시줄의 정보 모드를 활성화하거나 사용하지 않도록 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 리본 상태 표시줄::에 그리기 정보](#ondrawinformation)|정보 모드가 활성화되면 리본 상태 표시줄에 표시되는 정보 문자열을 표시합니다.|

## <a name="remarks"></a>설명

사용자는 리본 상태 표시줄에 대한 기본 제공 컨텍스트 메뉴를 사용하여 리본 상태 표시줄에서 리본 요소의 가시성을 변경할 수 있습니다. 요소를 동적으로 추가하거나 제거할 수 있습니다.

리본 상태 표시줄에는 주 영역과 확장 영역의 두 영역이 있습니다. 확장 영역은 리본 상태 표시줄의 오른쪽에 표시되며 기본 영역과 다른 색상으로 나타납니다.

일반적으로 상태 표시줄의 기본 영역에는 상태 알림이 표시되고 확장 영역에는 보기 컨트롤이 표시됩니다. 확장된 영역은 사용자가 리본 상태 표시줄의 크기를 조정할 때 가능한 한 오랫동안 표시됩니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonStatusBar` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 리본 상태 표시줄에 새 리본 요소를 추가하고, 리본 상태 표시줄의 확장 영역에 리본 요소를 추가하고, 구분 기호를 추가하고, 리본 상태 표시줄에 대한 일반 모드를 사용하도록 설정하는 방법을 보여 주며, 리본 상태 표시줄에 대한 일반 모드를 사용하도록 설정하는 방법을 보여 주며, 리본 상태 표시줄에 대한 일반 모드를 활성화합니다.

[!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)

[CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribbonstatusbar.h

## <a name="cmfcribbonstatusbaradddynamicelement"></a><a name="adddynamicelement"></a>CMFC 리본 상태 표시줄::추가 동적 요소

리본 상태 표시줄에 동적 요소를 추가합니다.

```cpp
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```

### <a name="parameters"></a>매개 변수

*pElement*<br/>
【인】 동적 요소에 대한 포인터입니다.

### <a name="remarks"></a>설명

일반 요소와 달리 동적 요소는 사용자 지정할 수 없으며 상태 표시줄의 사용자 지정 메뉴에는 요소가 표시되지 않습니다.

## <a name="cmfcribbonstatusbaraddelement"></a><a name="addelement"></a>CMFC 리본 상태 표시줄::추가 요소

리본 상태 표시줄에 새 리본 요소를 추가합니다.

```cpp
void AddElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>매개 변수

*pElement*<br/>
【인】 추가된 요소에 대한 포인터입니다.

*lpszLabel*<br/>
【인】 요소의 텍스트 레이블입니다.

*bIsVisible*<br/>
【인】 TRUE 요소를 표시로 추가하려는 경우 FALSE를 숨김요소로 추가하려는 경우 TRUE입니다.

## <a name="cmfcribbonstatusbaraddextendedelement"></a><a name="addextendedelement"></a>CMFC 리본 상태 표시줄::확장 요소 추가

리본 상태 표시줄의 확장 영역에 리본 요소를 추가합니다.

```cpp
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>매개 변수

*pElement*<br/>
【인】 추가된 요소에 대한 포인터입니다.

*lpszLabel*<br/>
【인】 요소의 텍스트 레이블입니다.

*bIsVisible*<br/>
【인】 TRUE 요소를 표시로 추가하려는 경우 FALSE를 숨김요소로 추가하려는 경우 TRUE입니다.

### <a name="remarks"></a>설명

확장된 영역은 상태 표시줄 컨트롤의 오른쪽에 있습니다.

## <a name="cmfcribbonstatusbaraddseparator"></a><a name="addseparator"></a>CMFC리본 상태 표시줄::추가 분리기

리본 상태 표시줄에 구분 기호를 추가합니다.

```cpp
void AddSeparator();
```

### <a name="remarks"></a>설명

프레임워크는 [CMFCRibbonStatusBar::AddElement](#addelement)메서드 다음의 구분 기호를 추가합니다. 마지막 요소를 삽입합니다.

## <a name="cmfcribbonstatusbarcreate"></a><a name="create"></a>CMFC 리본 상태 표시줄::만들기

리본 상태 표시줄을 만듭니다.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
【인】 상위 창에 대한 포인터입니다.

*dwStyle*<br/>
【인】 컨트롤 스타일의 논리적 OR 조합입니다.

*nID*<br/>
【인】 상태 표시줄의 제어 ID입니다.

### <a name="return-value"></a>Return Value

TRUE 상태 표시줄이 성공적으로 생성되면 FALSE입니다.

## <a name="cmfcribbonstatusbarcreateex"></a><a name="createex"></a>CMFC 리본 상태 표시줄::만들기 Ex

확장 된 스타일을 가지고 리본 상태 표시줄을 만듭니다.

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle=0,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
상위 창에 대한 포인터입니다.

*dwCtrl스타일*<br/>
상태 표시줄 개체를 만들기 위한 추가 스타일의 논리적 OR 조합입니다.

*dwStyle*<br/>
상태 표시줄의 컨트롤 스타일입니다.

*nID*<br/>
상태 표시줄의 제어 ID입니다.

### <a name="return-value"></a>Return Value

TRUE 상태 표시줄이 성공적으로 생성되면 FALSE입니다.

## <a name="cmfcribbonstatusbarfindbyid"></a><a name="findbyid"></a>CMFC 리본 상태 표시줄::찾기ByID

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```

### <a name="parameters"></a>매개 변수

【인】 *uiCmdID*<br/>
【인】 *불 (것)이*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonstatusbarfindelement"></a><a name="findelement"></a>CMFC 리본 상태 표시줄::찾기 요소

지정된 명령 ID가 있는 요소에 대한 포인터를 반환합니다.

```
CMFCRibbonBaseElement* FindElement(UINT uiID);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
【인】 요소의 ID입니다.

### <a name="return-value"></a>Return Value

지정된 명령 ID가 있는 요소에 대한 포인터입니다. 이러한 요소가 없는 경우 NULL입니다.

## <a name="cmfcribbonstatusbargetcount"></a><a name="getcount"></a>CMFC 리본 상태 표시줄::GetCount

리본 상태 표시줄의 기본 영역에 있는 요소 수를 반환합니다.

```
int GetCount() const;
```

### <a name="return-value"></a>Return Value

리본 상태 표시줄의 기본 영역에 있는 요소 수입니다.

## <a name="cmfcribbonstatusbargetelement"></a><a name="getelement"></a>CMFC 리본 상태 표시줄::GetElement

지정된 인덱스에 있는 요소에 대한 포인터를 반환합니다.

```
CMFCRibbonBaseElement* GetElement(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 상태 표시줄 컨트롤의 기본 영역에 있는 요소의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

지정된 인덱스에 있는 요소에 대한 포인터입니다. 인덱스가 음수이거나 상태 표시줄의 요소 수를 초과하는 경우 NULL입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribbonstatusbargetexcount"></a><a name="getexcount"></a>CMFC 리본 상태 표시줄::GetExCount

리본 상태 표시줄의 확장 영역에 있는 요소 수를 반환합니다.

```
int GetExCount() const;
```

### <a name="return-value"></a>Return Value

리본 상태 표시줄의 확장 영역에 있는 요소 수입니다.

## <a name="cmfcribbonstatusbargetexelement"></a><a name="getexelement"></a>CMFC 리본 상태 표시줄::GetExElement

리본 메뉴 상태 표시줄에서 확장된 영역의 지정한 인덱스에 있는 요소에 대한 포인터를 반환합니다. 확장된 영역은 상태 표시줄 컨트롤의 오른쪽에 있습니다.

```
CMFCRibbonBaseElement* GetExElement(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
【인】 상태 표시줄 컨트롤의 확장 영역에 있는 요소의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

리본 메뉴 상태 표시줄에서 확장된 영역의 지정한 인덱스에 있는 요소에 대한 포인터입니다. null *nIndex가* 음수이거나 리본 상태 표시줄의 확장 영역의 요소 수를 초과하는 경우

### <a name="remarks"></a>설명

## <a name="cmfcribbonstatusbargetextendedarea"></a><a name="getextendedarea"></a>CMFC 리본 상태 표시줄::GetExtendedArea

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonstatusbargetspace"></a><a name="getspace"></a>CMFC 리본 상태 표시줄::겟스페이스

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
int GetSpace() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonstatusbarisbottomframe"></a><a name="isbottomframe"></a>CMFC 리본 상태 표시줄::IsBottom프레임

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
BOOL IsBottomFrame() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonstatusbarisextendedelement"></a><a name="isextendedelement"></a>CMFC 리본 상태 표시줄::확장 요소

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;
```

### <a name="parameters"></a>매개 변수

【인】 *p엘리아*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonstatusbarisinformationmode"></a><a name="isinformationmode"></a>CMFC 리본 상태 표시줄::IsInformationMode

리본 상태 표시줄에 대해 정보 모드가 활성화되어 있는지 여부를 결정합니다.

```
BOOL IsInformationMode() const;
```

### <a name="return-value"></a>Return Value

TRUE 상태 표시줄정보 모드에서 작동할 수 있는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

정보 모드에서 상태 표시줄은 모든 일반 창을 숨기고 메시지 문자열을 표시합니다.

## <a name="cmfcribbonstatusbarondrawinformation"></a><a name="ondrawinformation"></a>CMFC 리본 상태 표시줄::에 그리기 정보

정보 모드가 활성화되면 리본 상태 표시줄에 나타나는 문자열을 표시합니다.

```
virtual void OnDrawInformation(
    CDC* pDC,
    CString& strInfo,
    CRect rectInfo);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*strInfo*<br/>
【인】 정보 문자열입니다.

*정류정보*<br/>
【인】 경계 사각형입니다.

### <a name="remarks"></a>설명

상태 표시줄에서 정보 문자열의 모양을 사용자 지정하려는 경우 파생 클래스에서 이 메서드를 재정의합니다. [CMFC리본 상태 표시줄을](#setinformation) 사용 하 여:SetInformation 메서드 정보 모드에 상태 표시줄을 넣습니다. 이 모드에서 상태 표시줄은 모든 창을 숨기고 *strInfo*에 의해 지정된 정보 문자열을 표시합니다.

## <a name="cmfcribbonstatusbarrecalclayout"></a><a name="recalclayout"></a>CMFC 리본 상태 표시줄::recalc레이아웃

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>설명

## <a name="cmfcribbonstatusbarremoveall"></a><a name="removeall"></a>CMFC 리본 상태 표시줄::모두 제거

리본 상태 표시줄에서 모든 요소를 제거합니다.

```cpp
void RemoveAll();
```

## <a name="cmfcribbonstatusbarremoveelement"></a><a name="removeelement"></a>CMFC 리본 상태 표시줄::제거요소

리본 상태 표시줄에서 지정된 명령 ID가 있는 요소를 제거합니다.

```
BOOL RemoveElement(UINT uiID);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
【인】 상태 표시줄에서 제거할 요소의 ID입니다.

### <a name="return-value"></a>Return Value

TRUE 지정된 *uiID가* 있는 요소가 제거된 경우 그렇지 않으면 FALSE입니다.

## <a name="cmfcribbonstatusbarsetinformation"></a><a name="setinformation"></a>CMFC 리본 상태 표시줄::설정 정보

리본 상태 표시줄의 정보 모드를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void SetInformation(LPCTSTR lpszInfo);
```

### <a name="parameters"></a>매개 변수

*lpsz정보*<br/>
【인】 정보 문자열입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 상태 표시줄을 정보 모드에 넣습니다. 이 모드에서 상태 표시줄은 모든 창을 숨기고 *lpszInfo*에 의해 지정된 정보 문자열을 표시합니다.

lpszInfo가 NULL이면 상태 표시줄이 일반 모드로 되돌아갑니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본바 클래스](../../mfc/reference/cmfcribbonbar-class.md)<br/>
[CMFC리본베이스요소 클래스](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFC리본바 클래스](../../mfc/reference/cmfcribbonbar-class.md)
