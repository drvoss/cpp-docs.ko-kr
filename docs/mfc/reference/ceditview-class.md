---
title: CEditView 클래스
ms.date: 11/04/2016
f1_keywords:
- CEditView
- AFXEXT/CEditView
- AFXEXT/CEditView::CEditView
- AFXEXT/CEditView::FindText
- AFXEXT/CEditView::GetBufferLength
- AFXEXT/CEditView::GetEditCtrl
- AFXEXT/CEditView::GetPrinterFont
- AFXEXT/CEditView::GetSelectedText
- AFXEXT/CEditView::LockBuffer
- AFXEXT/CEditView::PrintInsideRect
- AFXEXT/CEditView::SerializeRaw
- AFXEXT/CEditView::SetPrinterFont
- AFXEXT/CEditView::SetTabStops
- AFXEXT/CEditView::UnlockBuffer
- AFXEXT/CEditView::OnFindNext
- AFXEXT/CEditView::OnReplaceAll
- AFXEXT/CEditView::OnReplaceSel
- AFXEXT/CEditView::OnTextNotFound
- AFXEXT/CEditView::dwStyleDefault
helpviewer_keywords:
- CEditView [MFC], CEditView
- CEditView [MFC], FindText
- CEditView [MFC], GetBufferLength
- CEditView [MFC], GetEditCtrl
- CEditView [MFC], GetPrinterFont
- CEditView [MFC], GetSelectedText
- CEditView [MFC], LockBuffer
- CEditView [MFC], PrintInsideRect
- CEditView [MFC], SerializeRaw
- CEditView [MFC], SetPrinterFont
- CEditView [MFC], SetTabStops
- CEditView [MFC], UnlockBuffer
- CEditView [MFC], OnFindNext
- CEditView [MFC], OnReplaceAll
- CEditView [MFC], OnReplaceSel
- CEditView [MFC], OnTextNotFound
- CEditView [MFC], dwStyleDefault
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
ms.openlocfilehash: 33b5975eea534eeaf308f73b5ca7fca2cd76787f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753192"
---
# <a name="ceditview-class"></a>CEditView 클래스

Windows 편집 컨트롤의 기능을 제공하고 간단한 텍스트 편집기 기능을 구현하는 데 사용할 수 있는 뷰 클래스의 유형입니다.

## <a name="syntax"></a>구문

```
class CEditView : public CCtrlView
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CEditView::CEditView](#ceditview)|`CEditView` 형식의 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CEditView::찾기 텍스트](#findtext)|텍스트 내에서 문자열을 검색합니다.|
|[CEditView::Get버퍼길이](#getbufferlength)|문자 버퍼의 길이를 가져옵니다.|
|[CEditView::GetEditCtrl](#geteditctrl)|`CEditView` 개체 부분(Windows `CEdit` 편집 컨트롤)에 대한 액세스를 제공합니다.|
|[CEditView::겟프린터폰트](#getprinterfont)|현재 프린터 글꼴을 검색합니다.|
|[CEditView::선택 텍스트 받기](#getselectedtext)|현재 텍스트 선택을 검색합니다.|
|[CEditView::잠금 버퍼](#lockbuffer)|버퍼를 잠그습니다.|
|[CEditView::P린트인사이드렉트](#printinsiderect)|지정된 사각형 내에서 텍스트를 렌더링합니다.|
|[CEditView::직렬화](#serializeraw)|개체를 `CEditView` 디스크에 원시 텍스트로 직렬화합니다.|
|[CEditView::세트프린터폰트](#setprinterfont)|새 프린터 글꼴을 설정합니다.|
|[CEditView::SetTabstops](#settabstops)|화면 표시 및 인쇄 모두에 대한 탭 중지를 설정합니다.|
|[CEditView::잠금 해제 버퍼](#unlockbuffer)|버퍼의 잠금을 해제합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CEditView::다음 찾기](#onfindnext)|텍스트 문자열의 다음 발생을 찾습니다.|
|[CEditView::에대체 모두](#onreplaceall)|지정된 문자열의 모든 발생을 새 문자열로 바꿉습니다.|
|[CEditView::에대체셀](#onreplacesel)|현재 선택 영역을 바꿉습니다.|
|[CEditView::OnTextNot](#ontextnotfound)|찾기 작업이 추가 텍스트와 일치하지 않을 때 호출됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CEditView::dw스타일기본](#dwstyledefault)|형식의 `CEditView`개체에 대한 기본 스타일 .|

## <a name="remarks"></a>설명

클래스는 `CEditView` 다음과 같은 추가 기능을 제공합니다.

- 인쇄.

- 찾기 및 교체.

클래스는 `CEditView` 클래스의 `CView`파생이기 때문에 `CEditView` 클래스의 개체를 문서 및 문서 템플릿과 함께 사용할 수 있습니다.

각 `CEditView` 컨트롤의 텍스트는 자체 전역 메모리 개체에 보관됩니다. 응용 프로그램에는 개체 `CEditView` 수가 많을 수 있습니다.

위에 나열된 `CEditView` 추가 기능이 있는 편집 창을 만들거나 간단한 텍스트 편집기 기능을 원하는 경우 형식의 개체를 만듭니다. 개체는 `CEditView` 창의 전체 클라이언트 영역을 차지할 수 있습니다. 기본 기능을 추가 `CEditView` 하거나 수정하거나 문서 템플릿에 추가할 수 있는 클래스를 선언하기 위해 고유한 클래스를 파생합니다.

클래스의 `CEditView` 기본 구현은 ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT 및 ID_FILE_PRINT 명령을 처리합니다.

기본 문자 `CEditView` 제한은 (1024 \* 1024 - 1 = 1048575)입니다. 기본 편집 컨트롤의 EM_LIMITTEXT 함수를 호출하 여 변경할 수 있습니다. 그러나 제한은 운영 체제 및 편집 컨트롤(단일 또는 다중 줄)의 유형에 따라 다릅니다. 이러한 제한에 대한 자세한 내용은 [EM_LIMITTEXT](/windows/win32/Controls/em-limittext)을 참조하십시오.

컨트롤에서 이 제한을 변경하려면 클래스의 함수를 `OnCreate()` 재정의하고 다음 코드 줄을 삽입합니다. `CEditView`

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

형식(또는 `CEditView` 파생된 `CEditView`형식)의 개체에는 다음과 같은 제한 사항이 있습니다.

- `CEditView`당신이 보는 것을 사실 구현하지 않습니다 당신이 얻을 것입니다 (WYSIWYG) 편집. 화면의 가독성과 인쇄된 출력 일치 중에서 `CEditView` 선택할 수 있는 경우 화면 가독성을 선택합니다.

- `CEditView`텍스트를 단일 글꼴로만 표시할 수 있습니다. 특수 문자 서식이 지원되지 않습니다. 더 큰 기능을 보려면 [클래스 CRichEditView를](../../mfc/reference/cricheditview-class.md) 참조하십시오.

- 포함할 수 `CEditView` 있는 텍스트의 양은 제한되어 있습니다. 제한은 컨트롤과 동일합니다. `CEdit`

자세한 `CEditView`내용은 [MFC에서 사용할 수 있는 파생 보기 클래스를](../../mfc/derived-view-classes-available-in-mfc.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="ceditviewceditview"></a><a name="ceditview"></a>CEditView::CEditView

`CEditView` 형식의 개체를 생성합니다.

```
CEditView();
```

### <a name="remarks"></a>설명

개체를 생성한 후 편집 컨트롤을 사용하기 전에 [CWnd::Create](../../mfc/reference/cwnd-class.md#create) 함수를 호출해야 합니다. 에서 `CEditView` 클래스를 파생 하 고 사용 `CWinApp::AddDocTemplate`하 여 템플릿에 추가 하는 `Create` 경우 프레임 워크는이 생성자와 함수를 모두 호출 합니다.

## <a name="ceditviewdwstyledefault"></a><a name="dwstyledefault"></a>CEditView::dw스타일기본

개체의 기본 스타일을 `CEditView` 포함합니다.

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>설명

이 정적 멤버를 `Create` 함수의 *dwStyle* 매개 변수로 전달하여 `CEditView` 개체의 기본 스타일을 가져옵니다.

## <a name="ceditviewfindtext"></a><a name="findtext"></a>CEditView::찾기 텍스트

함수를 `FindText` 호출하여 `CEditView` 개체의 텍스트 버퍼를 검색합니다.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 수 있는 텍스트입니다.

*b다음*<br/>
검색 방향을 지정합니다. TRUE이면 검색 방향이 버퍼의 끝을 향합니다. FALSE인 경우 검색 방향이 버퍼의 시작 부분을 향합니다.

*b 케이스*<br/>
검색이 대/소문자를 구분하는지 여부를 지정합니다. TRUE인 경우 검색이 대/소문자를 구분합니다. FALSE인 경우 검색은 대/소문자를 구분하지 않습니다.

### <a name="return-value"></a>Return Value

검색 텍스트가 발견되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 버퍼의 텍스트를 *lpszFind에서*지정한 텍스트에 대해 검색하고 현재 선택 항목에서 시작하여 *bNext에서*지정한 방향으로 시작하고 *bCase에서*지정한 대/소문자 구분을 검색합니다. 텍스트가 발견되면 선택 영역을 찾은 텍스트로 설정하고 영하지 않은 값을 반환합니다. 텍스트를 찾을 수 없는 경우 함수는 0을 반환합니다.

일반적으로 을 재정의하지 `FindText` `OnFindNext`않는 한 함수를 호출할 `FindText`필요가 없습니다.

## <a name="ceditviewgetbufferlength"></a><a name="getbufferlength"></a>CEditView::Get버퍼길이

null 종단자를 포함하지 않고 편집 컨트롤의 버퍼에 현재 있는 문자 수를 가져오려면 이 멤버 함수를 호출합니다.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>Return Value

버퍼의 문자열 길이입니다.

## <a name="ceditviewgeteditctrl"></a><a name="geteditctrl"></a>CEditView::GetEditCtrl

호출을 `GetEditCtrl` 통해 편집 뷰에서 사용하는 편집 컨트롤에 대한 참조를 가져옵니다.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>Return Value

`CEdit` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 컨트롤은 [CEdit](../../mfc/reference/cedit-class.md)형식이므로 멤버 함수를 사용하여 Windows 편집 `CEdit` 컨트롤을 직접 조작할 수 있습니다.

> [!CAUTION]
> 개체를 `CEdit` 사용하면 기본 Windows 편집 컨트롤의 상태가 변경될 수 있습니다. 예를 들어 편집 컨트롤과 인쇄에서 모두 사용할 수 있는 `CEditView` 이러한 설정을 캐시하므로 [CEdit:SetTabStops](../../mfc/reference/cedit-class.md#settabstops) 기능을 사용하여 탭 설정을 변경하면 안 됩니다. 대신 [CEditView::SetTabStops](#settabstops)를 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

## <a name="ceditviewgetprinterfont"></a><a name="getprinterfont"></a>CEditView::겟프린터폰트

현재 `GetPrinterFont` 프린터 글꼴을 설명하는 [CFont](../../mfc/reference/cfont-class.md) 개체에 대한 포인터를 얻으려면 호출합니다.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>Return Value

현재 프린터 `CFont` 글꼴을 지정하는 개체에 대한 포인터입니다. 프린터 글꼴이 설정되지 않은 경우 NULL입니다. 해당 포인터는 임시적이며, 나중에 사용하려고 저장하면 안됩니다.

### <a name="remarks"></a>설명

프린터 글꼴이 설정되지 않은 경우 `CEditView` 클래스의 기본 인쇄 동작은 표시에 사용된 것과 동일한 글꼴을 사용하여 인쇄하는 것입니다.

이 함수를 사용하여 현재 프린터 글꼴을 확인합니다. 원하는 프린터 글꼴이 아닌 경우 [CEditView::SetPrinterFont를](#setprinterfont) 사용하여 변경합니다.

## <a name="ceditviewgetselectedtext"></a><a name="getselectedtext"></a>CEditView::선택 텍스트 받기

선택 `GetSelectedText` 영역의 끝또는 `CString` 선택 영역의 첫 번째 캐리지 반환 문자 앞에 있는 문자까지 선택한 텍스트를 개체에 복사하는 호출입니다.

```cpp
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>매개 변수

*strResult*<br/>
선택한 텍스트를 `CString` 수신할 개체에 대한 참조입니다.

## <a name="ceditviewlockbuffer"></a><a name="lockbuffer"></a>CEditView::잠금 버퍼

이 멤버 함수를 호출하여 버퍼에 대한 포인터를 가져옵니다. 버퍼를 수정하면 안 됩니다.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>Return Value

편집 컨트롤의 버퍼에 대한 포인터입니다.

## <a name="ceditviewonfindnext"></a><a name="onfindnext"></a>CEditView::다음 찾기

버퍼의 텍스트를 *검색하여 lpszFind*에서 지정한 텍스트를 *bNext에*의해 지정된 방향으로 검색하고 대/소문자 구분은 *bCase*로 지정됩니다.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 수 있는 텍스트입니다.

*b다음*<br/>
검색 방향을 지정합니다. TRUE이면 검색 방향이 버퍼의 끝을 향합니다. FALSE인 경우 검색 방향이 버퍼의 시작 부분을 향합니다.

*b 케이스*<br/>
검색이 대/소문자를 구분하는지 여부를 지정합니다. TRUE인 경우 검색이 대/소문자를 구분합니다. FALSE인 경우 검색은 대/소문자를 구분하지 않습니다.

### <a name="remarks"></a>설명

검색은 현재 선택의 시작 부분에서 시작되며 [FindText](#findtext)에 대한 호출을 통해 수행됩니다. 기본 구현에서 `OnFindNext` 텍스트가 없는 경우 [OnTextNotFound를](#ontextnotfound) 호출합니다.

-derive된 개체가 텍스트를 검색하는 방법을 변경하려면 재정의합니다. `OnFindNext` `CEditView` `CEditView`사용자가 `OnFindNext` 표준 대화 상자에서 다음 찾기 단추를 선택하면 호출됩니다.

## <a name="ceditviewonreplaceall"></a><a name="onreplaceall"></a>CEditView::에대체 모두

`CEditView`사용자가 `OnReplaceAll` 표준 대화 상자에서 모두 바꾸기 단추를 선택하면 호출됩니다.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 수 있는 텍스트입니다.

*lpszReplace*<br/>
검색 텍스트를 대체할 텍스트입니다.

*b 케이스*<br/>
검색이 대/소문자를 구분하는지 여부를 지정합니다. TRUE인 경우 검색이 대/소문자를 구분합니다. FALSE인 경우 검색은 대/소문자를 구분하지 않습니다.

### <a name="remarks"></a>설명

`OnReplaceAll`버퍼의 텍스트를 *검색하여 lpszFind에서*지정한 텍스트에 대해 *bCase*로 지정된 대/소문자 구분을 검색합니다. 검색은 현재 선택 항목의 시작 부분에서 시작됩니다. 검색 텍스트를 찾을 때마다 이 함수는 텍스트의 발생을 *lpszReplace*에서 지정한 텍스트로 바꿉습니다. 검색은 [FindText](#findtext)에 대한 호출을 통해 수행됩니다. 기본 구현에서 [OnTextNot텍스트가](#ontextnotfound) 없는 경우 호출됩니다.

현재 선택 영역이 *lpszFind와*일치하지 않으면 *lpszFind에서* 지정한 텍스트의 첫 번째 발생으로 선택이 업데이트되고 바꾸기가 수행되지 않습니다. 이렇게 하면 선택 영역이 대체할 텍스트와 일치하지 않을 때 수행하려는 작업을 확인할 수 있습니다.

-derive된 개체가 텍스트를 대체하는 방법을 변경하려면 재정의합니다. `OnReplaceAll` `CEditView`

## <a name="ceditviewonreplacesel"></a><a name="onreplacesel"></a>CEditView::에대체셀

`CEditView`사용자가 `OnReplaceSel` 표준 대화 상자에서 바꾸기 단추를 선택하면 호출됩니다.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 수 있는 텍스트입니다.

*b다음*<br/>
검색 방향을 지정합니다. TRUE이면 검색 방향이 버퍼의 끝을 향합니다. FALSE인 경우 검색 방향이 버퍼의 시작 부분을 향합니다.

*b 케이스*<br/>
검색이 대/소문자를 구분하는지 여부를 지정합니다. TRUE인 경우 검색이 대/소문자를 구분합니다. FALSE인 경우 검색은 대/소문자를 구분하지 않습니다.

*lpszReplace*<br/>
찾은 텍스트를 대체할 텍스트입니다.

### <a name="remarks"></a>설명

선택 영역을 대체한 후 이 함수는 버퍼의 텍스트를 *검색하여 lpszFind에서*지정한 텍스트의 다음 발생을 *bNext에*의해 지정된 방향으로 검색하고 대/소문자 구분은 *bCase*에 의해 지정됩니다. 검색은 [FindText](#findtext)에 대한 호출을 통해 수행됩니다. 텍스트를 찾을 수 없는 경우 [OnTextNot이](#ontextnotfound) 호출됩니다.

-derive된 개체가 선택한 텍스트를 대체하는 방법을 변경하려면 재정의합니다. `OnReplaceSel` `CEditView`

## <a name="ceditviewontextnotfound"></a><a name="ontextnotfound"></a>CEditView::OnTextNot

이 함수를 재정의하여 Windows 함수를 `MessageBeep`호출하는 기본 구현을 변경합니다.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 수 있는 텍스트입니다.

## <a name="ceditviewprintinsiderect"></a><a name="printinsiderect"></a>CEditView::P린트인사이드렉트

호출을 호출하여 `PrintInsideRect` 사각형레이아웃으로 지정된 사각형의 텍스트를 *인쇄합니다.*

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 장치 컨텍스트에 대한 포인터입니다.

*정류 레이아웃*<br/>
텍스트를 렌더링할 사각형을 지정하는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT 구조에](/windows/win32/api/windef/ns-windef-rect) 대한 참조입니다.

*nIndexStart*<br/>
렌더링할 첫 번째 문자의 버퍼 내에 인덱싱합니다.

*n인덱스 스탑*<br/>
렌더링할 마지막 문자 다음에 있는 문자 버퍼 내에서 인덱싱합니다.

### <a name="return-value"></a>Return Value

인쇄할 다음 문자의 인덱스(즉, 렌더링된 마지막 문자 다음에 있는 문자)입니다.

### <a name="remarks"></a>설명

컨트롤에 `CEditView` 스타일 ES_AUTOHSCROLL 없는 경우 텍스트는 렌더링 사각형 내에서 래핑됩니다. 컨트롤에 스타일 ES_AUTOHSCROLL 경우 텍스트가 사각형의 오른쪽 가장자리에 잘립니다.

사각형의 치수가 텍스트가 차지하는 원래 사각형의 일부를 정의할 수 있도록 `rect.bottom` *사각형레이아웃* 개체의 요소가 변경됩니다.

## <a name="ceditviewserializeraw"></a><a name="serializeraw"></a>CEditView::직렬화

개체를 `SerializeRaw` `CArchive` 읽거나 `CEditView` 개체의 텍스트를 텍스트 파일에 쓰도록 호출합니다.

```cpp
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
직렬화된 `CArchive` 텍스트를 저장하는 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

`SerializeRaw`개체 `CEditView`설명 데이터 앞에 `Serialize` 두지 않고 텍스트만 읽고 쓴다는 점에서 내부 구현과 다릅니다.

## <a name="ceditviewsetprinterfont"></a><a name="setprinterfont"></a>CEditView::세트프린터폰트

프린터 `SetPrinterFont` 글꼴을 pFont에서 지정한 글꼴로 설정하려면 *호출합니다.*

```cpp
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
형식의 `CFont`개체에 대한 포인터입니다. NULL인 경우 인쇄에 사용되는 글꼴은 표시 글꼴을 기반으로 합니다.

### <a name="remarks"></a>설명

뷰에서 항상 특정 글꼴을 인쇄에 사용하려면 클래스 `SetPrinterFont` `OnPreparePrinting` 함수에 호출을 포함합니다. 이 가상 함수는 인쇄가 발생하기 전에 호출되므로 뷰의 내용을 인쇄하기 전에 글꼴 이 변경됩니다.

## <a name="ceditviewsettabstops"></a><a name="settabstops"></a>CEditView::SetTabstops

이 함수를 호출하여 표시 및 인쇄에 사용되는 탭 정지를 설정합니다.

```cpp
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>매개 변수

*nTabStops*<br/>
각 탭의 너비는 대화 상자 단위로 중지됩니다.

### <a name="remarks"></a>설명

단일 탭 중지 너비만 지원됩니다. (개체는 `CEdit` 여러 탭 너비를 지원합니다.) 너비는 인쇄 또는 표시 시 사용된 글꼴의 평균 문자 너비(대문자 및 소문자 알파벳 문자만 기준)의 4분의 1에 해당하는 대화 상자 단위로 표시됩니다. 탭 중지 `CEdit::SetTabStops` 값을 `CEditView` 캐시해야 하므로 사용하지 않아야 합니다.

이 함수는 호출되는 개체의 탭만 수정합니다. 응용 프로그램의 각 `CEditView` 개체에 대한 탭 중지를 변경하려면 각 개체의 함수를 `SetTabStops` 호출합니다.

### <a name="example"></a>예제

이 코드 조각은 컨트롤에서 사용하는 글꼴을 신중하게 측정하여 컨트롤의 탭 중지를 모든 네 번째 문자로 설정합니다.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

## <a name="ceditviewunlockbuffer"></a><a name="unlockbuffer"></a>CEditView::잠금 해제 버퍼

이 멤버 함수를 호출하여 버퍼의 잠금을 해제합니다.

```cpp
void UnlockBuffer() const;
```

### <a name="remarks"></a>설명

LockBuffer에서 반환된 포인터 사용을 완료한 후 `UnlockBuffer` [호출합니다.](#lockbuffer)

## <a name="see-also"></a>참조

[MFC 샘플 슈퍼패드](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CEdit 클래스](../../mfc/reference/cedit-class.md)<br/>
[C문서 클래스](../../mfc/reference/cdocument-class.md)<br/>
[CDoc템플릿 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[리치에이트뷰 클래스](../../mfc/reference/cricheditview-class.md)
