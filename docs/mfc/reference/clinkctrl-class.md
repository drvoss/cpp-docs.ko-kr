---
title: 클링Ctrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
ms.openlocfilehash: aa1f630b448c60a0eeb6a905ed6eef6f84a2ff8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372251"
---
# <a name="clinkctrl-class"></a>클링Ctrl 클래스

Windows의 공용 SysLink 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CLinkCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[클링Ctrl:::클링Ctrl](#clinkctrl)|`CLinkCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CLinkCtrl::만들기](#create)|링크 컨트롤을 만들고 개체에 `CLinkCtrl` 연결합니다.|
|[CLinkCtrl::만들기](#createex)|확장 된 스타일을 가진 링크 컨트롤을 `CLinkCtrl` 만들고 개체에 연결 합니다.|
|[클링Ctrl::GetIdeal높이](#getidealheight)|링크 컨트롤의 이상적인 높이를 검색합니다.|
|[클링크터링::겟아이노어사이즈](#getidealsize)|링크의 지정된 너비에 따라 현재 링크 컨트롤에 대한 링크 텍스트의 기본 높이를 계산합니다.|
|[CLinkCtrl::GetItem](#getitem)|링크 컨트롤 항목의 상태 및 특성을 검색합니다.|
|[클링Ctrl:::GetItemID](#getitemid)|링크 컨트롤 항목의 ID를 검색합니다.|
|[CLinkCtrl::겟아이템 상태](#getitemstate)|링크 제어 항목의 상태를 검색합니다.|
|[CLinkCtrl:::GetItemUrl](#getitemurl)|링크 컨트롤 항목으로 표시되는 URL을 검색합니다.|
|[클링Ctrl::히트 테스트](#hittest)|사용자가 지정된 링크를 클릭했는지 여부를 확인합니다.|
|[CLinkCtrl::세트항목](#setitem)|링크 컨트롤 항목의 상태와 특성을 설정합니다.|
|[CLinkCtrl::세트항목ID](#setitemid)|링크 컨트롤 항목의 ID를 설정합니다.|
|[CLinkCtrl::세트항목 상태](#setitemstate)|링크 제어 항목의 상태를 설정합니다.|
|[CLinkCtrl:::세트항목Url](#setitemurl)|링크 컨트롤 항목으로 표시되는 URL을 설정합니다.|

## <a name="remarks"></a>설명

"링크 컨트롤"은 창에 하이퍼텍스트 링크를 포함할 수 있는 편리한 방법을 제공합니다. 실제 컨트롤은 표시가 표시된 텍스트를 렌더링하고 사용자가 포함된 링크를 클릭할 때 적절한 응용 프로그램을 실행하는 창입니다. 하나의 컨트롤 내에서 여러 링크가 지원되며 0기반 인덱스로 액세스할 수 있습니다.

이 컨트롤(및 `CLinkCtrl` 따라서 클래스)은 Windows XP 및 이후 에서 실행되는 프로그램에서만 사용할 수 있습니다.

자세한 내용은 Windows SDK의 [SysLink 제어를](/windows/win32/Controls/syslink-overview) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CLinkCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="clinkctrlclinkctrl"></a><a name="clinkctrl"></a>클링Ctrl:::클링Ctrl

`CLinkCtrl` 개체를 생성합니다.

```
CLinkCtrl();
```

## <a name="clinkctrlcreate"></a><a name="create"></a>CLinkCtrl::만들기

링크 컨트롤을 만들고 개체에 `CLinkCtrl` 연결합니다.

```
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*lpszLinkMarkup*<br/>
표시할 표시된 텍스트를 포함하는 0-종료된 문자열에 대한 포인터입니다. 자세한 내용은 [SysLink 컨트롤의 개요](/windows/win32/Controls/syslink-overview)항목에서 "마크업 및 링크 액세스" 섹션을 참조하십시오.

*dwStyle*<br/>
링크 컨트롤의 스타일을 지정합니다. 컨트롤 스타일의 조합을 적용합니다. 자세한 내용은 [에서](/windows/win32/Controls/common-control-styles) `Windows SDK` 일반 제어 스타일을 참조하십시오.

*rect*<br/>
링크 컨트롤의 크기와 위치를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다.

*pParentWnd*<br/>
링크 컨트롤의 상위 창을 지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
링크 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

초기화가 성공한 경우 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

두 단계로 `CLinkCtrl` 객체를 생성합니다. 먼저 생성자 호출 한 `Create`다음 호출 합니다 . `CLinkCtrl` 컨트롤에서 확장 된 창 스타일을 사용 하려면 [CLinkCtrl::CreateEx](#createex) 대신 호출 `Create`합니다.

`Create` 메서드의 두 번째 형식은 더 이상 사용되지 않습니다. *lpszLinkMarkup* 매개 변수를 지정하는 첫 번째 양식을 사용합니다.

### <a name="example"></a>예제

다음 코드 예제에서는 두 개의 `m_Link1` 링크 `m_Link2`컨트롤에 액세스하는 데 사용되는 명명된 변수와 의 두 변수를 정의합니다.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제는 다른 링크 컨트롤의 위치에 따라 하나의 링크 컨트롤을 만듭니다. 리소스 로더는 응용 프로그램이 시작될 때 첫 번째 링크 컨트롤을 만듭니다. 응용 프로그램이 OnInitDialog 메서드를 입력하면 첫 번째 링크 컨트롤의 위치를 기준으로 두 번째 링크 컨트롤을 만듭니다. 그런 다음 두 번째 링크 컨트롤의 크기를 조정하여 표시되는 텍스트에 맞춥습니다.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]

## <a name="clinkctrlcreateex"></a><a name="createex"></a>CLinkCtrl::만들기

확장 된 스타일을 가진 링크 컨트롤을 `CLinkCtrl` 만들고 개체에 연결 합니다.

```
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```

### <a name="parameters"></a>매개 변수

*lpszLinkMarkup*<br/>
표시할 표시된 텍스트를 포함하는 0-종료된 문자열에 대한 포인터입니다. 자세한 내용은 [SysLink 컨트롤의 개요](/windows/win32/Controls/syslink-overview)항목에서 "마크업 및 링크 액세스" 섹션을 참조하십시오.

*dwExStyle*<br/>
링크 컨트롤의 확장 스타일을 지정합니다. 확장 된 Windows 스타일 목록은 Windows SDK에서 [CreateWindowEx에](/windows/win32/api/winuser/nf-winuser-createwindowexw) 대한 *dwExStyle* 매개 변수를 참조하십시오.

*dwStyle*<br/>
링크 컨트롤의 스타일을 지정합니다. 컨트롤 스타일의 조합을 적용합니다. 자세한 내용은 Windows SDK의 [일반 제어 스타일을](/windows/win32/Controls/common-control-styles) 참조하십시오.

*rect*<br/>
링크 컨트롤의 크기와 위치를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다.

*pParentWnd*<br/>
링크 컨트롤의 상위 창을 지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
링크 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

초기화가 성공한 경우 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

만들기 `CreateEx` 대신 [확장된](#create) Windows 스타일 상수를 적용합니다.

`CreateEx` 메서드의 두 번째 형식은 더 이상 사용되지 않습니다. *lpszLinkMarkup* 매개 변수를 지정하는 첫 번째 양식을 사용합니다.

## <a name="clinkctrlgetidealheight"></a><a name="getidealheight"></a>클링Ctrl::GetIdeal높이

링크 컨트롤의 이상적인 높이를 검색합니다.

```
int GetIdealHeight() const;
```

### <a name="return-value"></a>Return Value

컨트롤의 이상적인 높이(픽셀 단위)입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [LM_GETIDEALHEIGHT](/windows/win32/Controls/lm-getidealheight)Win32 메시지의 동작을 구현합니다.

## <a name="clinkctrlgetidealsize"></a><a name="getidealsize"></a>클링크터링::겟아이노어사이즈

링크의 지정된 너비에 따라 현재 링크 컨트롤에 대한 링크 텍스트의 기본 높이를 계산합니다.

```
int GetIdealSize(
    int cxMaxWidth,
    SIZE* pSize) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*cx맥스폭*|【인】 링크의 최대 너비(픽셀)입니다.|
|【아웃】 \* *p사이즈*|Windows [SIZE](/windows/win32/api/windef/ns-windef-size) 구조에 대한 포인터입니다. 이 메서드가 반환하면 `SIZE` 구조체의 *cy* 멤버에는 *cxMaxWidth로*지정된 링크 텍스트 너비에 대한 이상적인 링크 텍스트 높이가 포함되어 있습니다. 구조체의 *cx* 멤버에는 실제로 필요한 링크 텍스트 너비가 포함되어 있습니다.|

### <a name="return-value"></a>Return Value

링크 텍스트의 기본 높이(픽셀)입니다. 반환 값은 구조의 *cy* 멤버 값과 `SIZE` 동일합니다.

### <a name="remarks"></a>설명

`GetIdealSize` 메서드의 예는 [CLinkCtrl:만들기](#create)의 예제를 참조하십시오.

이 메서드는 Windows SDK에 설명 된 [LM_GETIDEALSIZE](/windows/win32/Controls/lm-getidealsize) 메시지를 보냅니다.

## <a name="clinkctrlgetitem"></a><a name="getitem"></a>CLinkCtrl::GetItem

링크 컨트롤 항목의 상태 및 특성을 검색합니다.

```
BOOL GetItem(PLITEM pItem) const;
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
항목 정보를 수신하는 [LITEM](/windows/win32/api/commctrl/ns-commctrl-litem) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 LM_GETITEM Win32 [메시지의](/windows/win32/Controls/lm-getitem)동작을 구현합니다.

## <a name="clinkctrlgetitemid"></a><a name="getitemid"></a>클링Ctrl:::GetItemID

링크 컨트롤 항목의 ID를 검색합니다.

```
BOOL GetItemID(
    int iLink,
    CString& strID) const;

BOOL GetItemID(
    int iLink,
    LPWSTR szID,
    UINT cchID) const;
```

### <a name="parameters"></a>매개 변수

*아이 링크*<br/>
링크 제어 항목의 인덱스입니다.

*스트리드 (것)들*<br/>
지정된 항목의 ID를 포함하는 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

*szID*<br/>
지정된 항목의 ID를 포함하는 null-종료된 문자열입니다.

*cchID*<br/>
*szID* 버퍼의 문자 크기입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

> [!NOTE]
> 또한 이 함수는 *szID 또는 strID의* 버퍼가 MAX_LINKID_TEXT 보다 작은 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

특정 링크 컨트롤 항목의 ID를 검색합니다. 자세한 내용은 Windows SDK에서 [LM_GETITEM](/windows/win32/Controls/lm-getitem) Win32 메시지를 참조하십시오.

## <a name="clinkctrlgetitemstate"></a><a name="getitemstate"></a>CLinkCtrl::겟아이템 상태

링크 제어 항목의 상태를 검색합니다.

```
BOOL GetItemState(
    int iLink,
    UINT* pnState,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;
```

### <a name="parameters"></a>매개 변수

*아이 링크*<br/>
링크 제어 항목의 인덱스입니다.

*pnState*<br/>
지정된 상태 항목의 값입니다.

*상태 마스크*<br/>
얻을 상태 항목을 설명하는 플래그의 조합입니다. 값 목록은 `state` [LITEM](/windows/win32/api/commctrl/ns-commctrl-litem) 구조의 멤버 설명을 참조하십시오. 허용 가능한 항목은 에서 `state`허용되는 항목과 동일합니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

특정 링크 컨트롤 항목의 지정된 상태 항목의 값을 검색합니다. 자세한 내용은 Windows SDK에서 [LM_GETITEM](/windows/win32/Controls/lm-getitem) Win32 메시지를 참조하십시오.

## <a name="clinkctrlgetitemurl"></a><a name="getitemurl"></a>CLinkCtrl:::GetItemUrl

링크 컨트롤 항목으로 표시되는 URL을 검색합니다.

```
BOOL GetItemUrl(
    int iLink,
    CString& strUrl) const;

BOOL GetItemUrl(
    int iLink,
    LPWSTR szUrl,
    UINT cchUrl) const;
```

### <a name="parameters"></a>매개 변수

*아이 링크*<br/>
링크 제어 항목의 인덱스입니다.

*스트렐*<br/>
지정된 항목으로 표시되는 URL을 포함하는 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 개체

*szUrl*<br/>
지정된 항목으로 표시되는 URL을 포함하는 null-종료된 문자열

*cchUrl*<br/>
*szURL* 버퍼의 문자 크기입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

> [!NOTE]
> *또한 szUrl 또는 strUrl의* 버퍼가 MAX_LINKID_TEXT 보다 작은 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

지정된 링크 컨트롤 항목으로 표시되는 URL을 검색합니다. 자세한 내용은 Windows SDK에서 [LM_GETITEM](/windows/win32/Controls/lm-getitem) Win32 메시지를 참조하십시오.

## <a name="clinkctrlhittest"></a><a name="hittest"></a>클링Ctrl::히트 테스트

사용자가 지정된 링크를 클릭했는지 여부를 확인합니다.

```
BOOL HitTest(PLHITTESTINFO phti) const;
```

### <a name="parameters"></a>매개 변수

*phti*<br/>
사용자가 클릭한 `LHITTESTINFO` 링크에 대한 정보가 포함된 구조체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [LM_HITTEST](/windows/win32/Controls/lm-hittest)Win32 메시지의 동작을 구현합니다.

## <a name="clinkctrlsetitem"></a><a name="setitem"></a>CLinkCtrl::세트항목

링크 컨트롤 항목의 상태와 특성을 설정합니다.

```
BOOL SetItem(PLITEM pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
설정할 정보가 포함된 [LITEM](/windows/win32/api/commctrl/ns-commctrl-litem) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [LM_SETITEM](/windows/win32/Controls/lm-setitem)Win32 메시지의 동작을 구현합니다.

## <a name="clinkctrlsetitemid"></a><a name="setitemid"></a>CLinkCtrl::세트항목ID

링크 컨트롤 항목의 ID를 검색합니다.

```
BOOL SetItemID(
    int iLink,
    LPCWSTR szID);
```

### <a name="parameters"></a>매개 변수

*아이 링크*<br/>
링크 제어 항목의 인덱스입니다.

*szID*<br/>
지정된 항목의 ID를 포함하는 null-종료된 문자열입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

특정 링크 컨트롤 항목의 ID를 설정합니다. 자세한 내용은 Windows SDK에서 [LM_SETITEM](/windows/win32/Controls/lm-setitem) Win32 메시지를 참조하십시오.

## <a name="clinkctrlsetitemstate"></a><a name="setitemstate"></a>CLinkCtrl::세트항목 상태

링크 제어 항목의 상태를 검색합니다.

```
BOOL SetItemState(
    int iLink,
    UINT state,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```

### <a name="parameters"></a>매개 변수

*아이 링크*<br/>
링크 제어 항목의 인덱스입니다.

*pnState*<br/>
설정 중인 지정된 상태 항목의 값입니다.

*상태 마스크*<br/>
설정 중인 상태 항목을 설명하는 플래그의 조합입니다. 값 목록은 `state` [LITEM](/windows/win32/api/commctrl/ns-commctrl-litem) 구조의 멤버 설명을 참조하십시오. 허용 가능한 항목은 에서 `state`허용되는 항목과 동일합니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

특정 링크 컨트롤 항목의 지정된 상태 항목의 값을 설정합니다. 자세한 내용은 Windows SDK에서 [LM_SETITEM](/windows/win32/Controls/lm-setitem) Win32 메시지를 참조하십시오.

## <a name="clinkctrlsetitemurl"></a><a name="setitemurl"></a>CLinkCtrl:::세트항목Url

링크 컨트롤 항목으로 표시되는 URL을 설정합니다.

```
BOOL SetItemUrl(
    int iLink,
    LPCWSTR szUrl);
```

### <a name="parameters"></a>매개 변수

*아이 링크*<br/>
링크 제어 항목의 인덱스입니다.

*szUrl*<br/>
지정된 항목으로 표시되는 URL을 포함하는 null-종료된 문자열

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

지정된 링크 컨트롤 항목으로 표시되는 URL을 설정합니다. 자세한 내용은 Windows SDK에서 [LM_SETITEM](/windows/win32/Controls/lm-setitem) Win32 메시지를 참조하십시오.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)
