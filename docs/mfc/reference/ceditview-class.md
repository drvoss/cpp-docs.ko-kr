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
ms.openlocfilehash: e9b7dea980e607c776e2d50c679042c765080fdb
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424424"
---
# <a name="ceditview-class"></a>CEditView 클래스

Windows 편집 컨트롤의 기능을 제공하고 간단한 텍스트 편집기 기능을 구현하는 데 사용할 수 있는 뷰 클래스의 유형입니다.

## <a name="syntax"></a>구문

```
class CEditView : public CCtrlView
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CEditView:: CEditView](#ceditview)|`CEditView` 형식의 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CEditView:: FindText](#findtext)|텍스트 내에서 문자열을 검색 합니다.|
|[CEditView:: GetBufferLength](#getbufferlength)|문자 버퍼의 길이를 가져옵니다.|
|[CEditView:: GetEditCtrl](#geteditctrl)|`CEditView` 개체의 `CEdit` 부분 (Windows 편집 컨트롤)에 대 한 액세스를 제공 합니다.|
|[CEditView:: Get프린터 글꼴](#getprinterfont)|현재 프린터 글꼴을 검색 합니다.|
|[CEditView:: GetSelectedText](#getselectedtext)|현재 텍스트 선택 영역을 검색 합니다.|
|[CEditView:: LockBuffer](#lockbuffer)|버퍼를 잠급니다.|
|[CEditView::P rintInsideRect](#printinsiderect)|지정 된 사각형 안에 텍스트를 렌더링 합니다.|
|[CEditView:: SerializeRaw](#serializeraw)|`CEditView` 개체를 디스크에 원시 텍스트로 serialize 합니다.|
|[CEditView:: Set프린터 글꼴](#setprinterfont)|새 프린터 글꼴을 설정 합니다.|
|[CEditView:: SetTabStops](#settabstops)|화면 표시와 인쇄 모두에 대해 탭 정지를 설정 합니다.|
|[CEditView:: UnlockBuffer](#unlockbuffer)|버퍼의 잠금을 해제 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CEditView:: OnFindNext](#onfindnext)|텍스트 문자열의 다음 항목을 찾습니다.|
|[CEditView:: OnReplaceAll](#onreplaceall)|지정 된 문자열의 모든 항목을 새 문자열로 바꿉니다.|
|[CEditView:: OnReplaceSel](#onreplacesel)|현재 선택 영역을 바꿉니다.|
|[CEditView:: OnTextNotFound](#ontextnotfound)|찾기 작업이 더 이상 텍스트와 일치 하지 않는 경우 호출 됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CEditView::d wStyleDefault](#dwstyledefault)|`CEditView`형식의 개체에 대 한 기본 스타일입니다.|

## <a name="remarks"></a>설명

`CEditView` 클래스는 다음과 같은 추가 함수를 제공 합니다.

- 인쇄.

- 찾기 및 바꾸기.

클래스 `CEditView`는 클래스 `CView`의 파생 이므로 문서와 문서 템플릿에 `CEditView` 클래스의 개체를 사용할 수 있습니다.

각 `CEditView` 컨트롤의 텍스트는 해당 하는 전역 메모리 개체에 유지 됩니다. 응용 프로그램에는 원하는 수의 `CEditView` 개체가 있을 수 있습니다.

위에 나열 된 기능이 추가 된 편집 창이 필요 하거나 간단한 텍스트 편집기 기능을 원하는 경우 `CEditView` 형식의 개체를 만듭니다. `CEditView` 개체는 창의 전체 클라이언트 영역을 차지할 수 있습니다. `CEditView`에서 고유한 클래스를 파생 하 여 기본 기능을 추가 또는 수정 하거나 문서 템플릿에 추가할 수 있는 클래스를 선언 합니다.

클래스 `CEditView`의 기본 구현에서는 ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT 및 ID_FILE_PRINT 명령을 처리 합니다.

`CEditView`에 대 한 기본 문자 제한은 (1024 \* 1024-1 = 1048575)입니다. 이는 기본 편집 컨트롤의 EM_LIMITTEXT 함수를 호출 하 여 변경할 수 있습니다. 그러나 한도는 운영 체제와 편집 컨트롤의 형식 (단일 또는 여러 줄)에 따라 달라 집니다. 이러한 제한에 대 한 자세한 내용은 [EM_LIMITTEXT](/windows/win32/Controls/em-limittext)를 참조 하세요.

컨트롤에서이 한도를 변경 하려면 `CEditView` 클래스의 `OnCreate()` 함수를 재정의 하 고 다음 코드 줄을 삽입 합니다.

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

`CEditView` 형식 (또는 `CEditView`에서 파생 된 형식)의 개체에는 다음과 같은 제한 사항이 있습니다.

- `CEditView`은 사용자가 WYSIWYG (WYSIWYG) 편집 기능을 구현 하지 않습니다. 화면에서 가독성을 선택 하 고 인쇄 된 출력을 일치 opts 화면 가독성을 위해 `CEditView`을 선택 합니다.

- `CEditView` 텍스트를 단일 글꼴로만 표시할 수 있습니다. 특수 문자 서식 지정은 지원 되지 않습니다. 더 많은 기능을 보려면 클래스 [CRichEditView](../../mfc/reference/cricheditview-class.md) 를 참조 하세요.

- `CEditView` 포함할 수 있는 텍스트의 양은 제한 됩니다. 한도는 `CEdit` 컨트롤과 동일 합니다.

`CEditView`에 대 한 자세한 내용은 [MFC에서 사용할 수 있는 파생 뷰 클래스](../../mfc/derived-view-classes-available-in-mfc.md)를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[에서 파생되지 않은](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="ceditview"></a>CEditView:: CEditView

`CEditView` 형식의 개체를 생성합니다.

```
CEditView();
```

### <a name="remarks"></a>설명

개체를 생성 한 후에는 edit 컨트롤을 사용 하기 전에 [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) 함수를 호출 해야 합니다. `CEditView`에서 클래스를 파생 시키고 `CWinApp::AddDocTemplate`를 사용 하 여 템플릿에 추가 하는 경우 프레임 워크는이 생성자와 `Create` 함수를 모두 호출 합니다.

##  <a name="dwstyledefault"></a>CEditView::d wStyleDefault

`CEditView` 개체의 기본 스타일을 포함 합니다.

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>설명

이 정적 멤버를 `Create` 함수의 *Dwstyle* 매개 변수로 전달 하 여 `CEditView` 개체에 대 한 기본 스타일을 가져옵니다.

##  <a name="findtext"></a>CEditView:: FindText

`FindText` 함수를 호출 하 여 `CEditView` 개체의 텍스트 버퍼를 검색 합니다.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 텍스트입니다.

*bNext*<br/>
검색 방향을 지정 합니다. TRUE 이면 검색 방향이 버퍼의 끝 부분에 있습니다. FALSE 이면 검색 방향이 버퍼의 시작 부분을 향해 있습니다.

*bCase*<br/>
검색에서 대/소문자를 구분 하는지 여부를 지정 합니다. TRUE 이면 검색에서 대/소문자를 구분 합니다. FALSE 이면 검색에서 대/소문자를 구분 하지 않습니다.

### <a name="return-value"></a>Return Value

검색 텍스트가 있는 경우 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 현재 선택 영역에서 시작 하 여 *lpszFind*에 지정 된 텍스트에 대 한 버퍼의 텍스트를 *bnext*에서 지정한 방향으로 검색 하 고, 대 */소문자 구분*을 사용 하 여 검색 합니다. 텍스트를 찾은 경우 선택 항목을 찾은 텍스트로 설정 하 고 0이 아닌 값을 반환 합니다. 텍스트를 찾을 수 없는 경우이 함수는 0을 반환 합니다.

일반적으로 `FindText`를 호출 하는 `OnFindNext`를 재정의 하지 않으면 `FindText` 함수를 호출할 필요가 없습니다.

##  <a name="getbufferlength"></a>CEditView:: GetBufferLength

이 멤버 함수를 호출 하 여 null 종결자를 포함 하지 않고 편집 컨트롤의 버퍼에 현재 있는 문자 수를 가져옵니다.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>Return Value

버퍼에 있는 문자열의 길이입니다.

##  <a name="geteditctrl"></a>CEditView:: GetEditCtrl

`GetEditCtrl`를 호출 하 여 편집 보기에서 사용 하는 편집 컨트롤에 대 한 참조를 가져옵니다.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>Return Value

`CEdit` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 컨트롤은 [CEdit](../../mfc/reference/cedit-class.md)형식 이므로 `CEdit` 멤버 함수를 사용 하 여 Windows 편집 컨트롤을 직접 조작할 수 있습니다.

> [!CAUTION]
>  `CEdit` 개체를 사용 하 여 기본 Windows 편집 컨트롤의 상태를 변경할 수 있습니다. 예를 들어, `CEditView`는 편집 컨트롤 및 인쇄에 모두 사용 하기 위해 이러한 설정을 캐시 하기 때문에 [CEdit:: SetTabStops](../../mfc/reference/cedit-class.md#settabstops) 함수를 사용 하 여 탭 설정을 변경할 수 없습니다. 대신 [Ceditview:: SetTabStops](#settabstops)을 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

##  <a name="getprinterfont"></a>CEditView:: Get프린터 글꼴

`GetPrinterFont`를 호출 하 여 현재 프린터 글꼴을 설명 하는 [Cfont](../../mfc/reference/cfont-class.md) 개체에 대 한 포인터를 가져옵니다.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>Return Value

현재 프린터 글꼴을 지정 하는 `CFont` 개체에 대 한 포인터입니다. 프린터 글꼴이 설정 되지 않은 경우 NULL입니다. 해당 포인터는 임시적이며, 나중에 사용하려고 저장하면 안됩니다.

### <a name="remarks"></a>설명

프린터 글꼴이 설정 되지 않은 경우 `CEditView` 클래스의 기본 인쇄 동작은 표시에 사용 되는 것과 동일한 글꼴을 사용 하 여 인쇄 하는 것입니다.

현재 프린터 글꼴을 확인 하려면이 함수를 사용 합니다. 원하는 프린터 글꼴이 아니면 [Ceditview:: Set프린터 글꼴](#setprinterfont) 을 사용 하 여 변경 합니다.

##  <a name="getselectedtext"></a>CEditView:: GetSelectedText

`GetSelectedText`를 호출 하 여 선택한 텍스트를 선택 영역의 끝 또는 선택의 첫 번째 캐리지 리턴 문자 앞에 있는 `CString` 개체에 복사 합니다.

```
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>매개 변수

*strResult*<br/>
선택한 텍스트를 받을 `CString` 개체에 대 한 참조입니다.

##  <a name="lockbuffer"></a>CEditView:: LockBuffer

이 멤버 함수를 호출 하 여 버퍼에 대 한 포인터를 가져옵니다. 버퍼를 수정 하면 안 됩니다.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>Return Value

편집 컨트롤의 버퍼에 대 한 포인터입니다.

##  <a name="onfindnext"></a>CEditView:: OnFindNext

Bnext에 지정 된 방향으로 *lpszFind*에 지정 된 텍스트에 대 한 버퍼의 텍스트를 검색 하 고, 대 */소문자 구분*여부를 검색 합니다.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 텍스트입니다.

*bNext*<br/>
검색 방향을 지정 합니다. TRUE 이면 검색 방향이 버퍼의 끝 부분에 있습니다. FALSE 이면 검색 방향이 버퍼의 시작 부분을 향해 있습니다.

*bCase*<br/>
검색에서 대/소문자를 구분 하는지 여부를 지정 합니다. TRUE 이면 검색에서 대/소문자를 구분 합니다. FALSE 이면 검색에서 대/소문자를 구분 하지 않습니다.

### <a name="remarks"></a>설명

검색은 현재 선택의 시작 부분에서 시작 되며 [FindText](#findtext)를 호출 하 여 수행 됩니다. 기본 구현에서 텍스트를 찾을 수 없는 경우 `OnFindNext`는 [Ontextnotfound](#ontextnotfound) 를 호출 합니다.

`CEditView`파생 개체에서 텍스트를 검색 하는 방법을 변경 하려면 `OnFindNext`를 재정의 합니다. 사용자가 표준 찾기 대화 상자에서 다음 찾기 단추를 선택 하면 `CEditView` 호출 `OnFindNext`.

##  <a name="onreplaceall"></a>CEditView:: OnReplaceAll

사용자가 표준 바꾸기 대화 상자의 모두 바꾸기 단추를 선택 하면 `CEditView` 호출 `OnReplaceAll`.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 텍스트입니다.

*lpszReplace*<br/>
검색 텍스트를 바꿀 텍스트입니다.

*bCase*<br/>
검색에서 대/소문자를 구분 하는지 여부를 지정 합니다. TRUE 이면 검색에서 대/소문자를 구분 합니다. FALSE 이면 검색에서 대/소문자를 구분 하지 않습니다.

### <a name="remarks"></a>설명

`OnReplaceAll`는 *b case*로 지정 된 대/소문자 구분을 사용 하 여 버퍼에서 *lpszFind*에 지정 된 텍스트를 검색 합니다. 현재 선택 영역의 시작 부분에서 검색이 시작 됩니다. 검색 텍스트가 발견 될 때마다이 함수는 해당 텍스트의 발생 항목을 *lpszReplace*에 지정 된 텍스트로 바꿉니다. 검색은 [FindText](#findtext)에 대 한 호출을 통해 수행 됩니다. 기본 구현에서 텍스트를 찾을 수 없는 경우에는 [Ontextnotfound](#ontextnotfound) 가 호출 됩니다.

현재 선택 영역이 *lpszFind*일치 하지 않는 경우 선택 항목은 *lpszFind* 에 의해 지정 된 첫 번째 텍스트로 업데이트 되며 바꾸기는 수행 되지 않습니다. 이를 통해 사용자는 선택 영역이 교체할 텍스트와 일치 하지 않을 때 수행할 작업을 확인할 수 있습니다.

`CEditView`파생 개체가 텍스트를 바꾸는 방법을 변경 하려면 `OnReplaceAll`를 재정의 합니다.

##  <a name="onreplacesel"></a>CEditView:: OnReplaceSel

`CEditView` 사용자가 표준 바꾸기 대화 상자에서 바꾸기 단추를 선택 하면 `OnReplaceSel`를 호출 합니다.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 텍스트입니다.

*bNext*<br/>
검색 방향을 지정 합니다. TRUE 이면 검색 방향이 버퍼의 끝 부분에 있습니다. FALSE 이면 검색 방향이 버퍼의 시작 부분을 향해 있습니다.

*bCase*<br/>
검색에서 대/소문자를 구분 하는지 여부를 지정 합니다. TRUE 이면 검색에서 대/소문자를 구분 합니다. FALSE 이면 검색에서 대/소문자를 구분 하지 않습니다.

*lpszReplace*<br/>
찾은 텍스트를 바꿀 텍스트입니다.

### <a name="remarks"></a>설명

선택 내용을 바꾼 후이 함수 *는 b에*지정 된 방향으로 *lpszFind*에 의해 지정 된 텍스트가 *b case*로 지정 된 방향으로 버퍼의 텍스트를 검색 합니다. 검색은 [FindText](#findtext)에 대 한 호출을 통해 수행 됩니다. 텍스트를 찾을 수 없는 경우에는 [Ontextnotfound](#ontextnotfound) 가 호출 됩니다.

`CEditView`파생 개체가 선택한 텍스트를 대체 하는 방법을 변경 하려면 `OnReplaceSel`를 재정의 합니다.

##  <a name="ontextnotfound"></a>CEditView:: OnTextNotFound

Windows 함수 `MessageBeep`를 호출 하는 기본 구현을 변경 하려면이 함수를 재정의 합니다.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 텍스트입니다.

##  <a name="printinsiderect"></a>CEditView::P rintInsideRect

`PrintInsideRect`를 호출 하 여 *rectLayout*에 지정 된 사각형의 텍스트를 인쇄 합니다.

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 장치 컨텍스트에 대 한 포인터입니다.

*rectLayout*<br/>
텍스트를 렌더링할 사각형을 지정 하는 [Crect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT 구조](/windows/win32/api/windef/ns-windef-rect) 에 대 한 참조입니다.

*nIndexStart*<br/>
렌더링할 첫 번째 문자의 버퍼 내의 인덱스입니다.

*nIndexStop*<br/>
렌더링할 마지막 문자 다음에 나오는 문자 버퍼 내의 인덱스입니다.

### <a name="return-value"></a>Return Value

인쇄할 다음 문자의 인덱스입니다 (마지막으로 렌더링 된 문자 다음에 나오는 문자).

### <a name="remarks"></a>설명

`CEditView` 컨트롤에 스타일이 ES_AUTOHSCROLL 없는 경우 텍스트는 렌더링 사각형 안에 래핑됩니다. 컨트롤에 ES_AUTOHSCROLL 스타일이 있으면 사각형의 오른쪽 가장자리에 텍스트가 잘립니다.

*RectLayout* 개체의 `rect.bottom` 요소가 변경 되어 사각형의 차원이 텍스트가 차지 하는 원본 사각형의 일부를 정의 합니다.

##  <a name="serializeraw"></a>CEditView:: SerializeRaw

`SerializeRaw`를 호출 하 여 `CArchive` 개체가 `CEditView` 개체의 텍스트를 읽고 텍스트 파일에 씁니다.

```
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
Serialize 된 텍스트를 저장 하는 `CArchive` 개체에 대 한 참조입니다.

### <a name="remarks"></a>설명

`SerializeRaw`은 (는) 개체 설명 데이터를 사용 하지 않고 텍스트만 읽고 쓸 `CEditView`의 `Serialize`에 대 한 내부 구현과 다릅니다.

##  <a name="setprinterfont"></a>CEditView:: Set프린터 글꼴

`SetPrinterFont`를 호출 하 여 프린터 글꼴을 *Pfont*로 지정 된 글꼴로 설정 합니다.

```
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
`CFont`형식의 개체에 대 한 포인터입니다. NULL 인 경우 인쇄에 사용 되는 글꼴은 표시 글꼴을 기반으로 합니다.

### <a name="remarks"></a>설명

보기에서 항상 특정 글꼴을 사용 하 여 인쇄 하려면 클래스의 `OnPreparePrinting` 함수에서 `SetPrinterFont`에 대 한 호출을 포함 합니다. 이 가상 함수는 인쇄를 수행 하기 전에 호출 되므로 보기의 내용이 인쇄 되기 전에 글꼴 변경이 발생 합니다.

##  <a name="settabstops"></a>CEditView:: SetTabStops

표시 및 인쇄에 사용 되는 탭 정지를 설정 하려면이 함수를 호출 합니다.

```
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>매개 변수

*nTabStops*<br/>
각 탭 정지의 너비 (대화 상자 단위)입니다.

### <a name="remarks"></a>설명

탭 정지 너비가 하나만 지원 됩니다. `CEdit` 개체는 여러 개의 탭 너비를 지원 합니다. 너비는 인쇄 하거나 표시할 때 사용 되는 글꼴의 평균 문자 너비 (대문자 및 소문자만 기반)의 네 번째 1/4과 같은 대화 단위에 있습니다. `CEditView` 탭 정지 값을 캐시 해야 하므로 `CEdit::SetTabStops`를 사용 하면 안 됩니다.

이 함수는 호출 되는 개체의 탭만 수정 합니다. 응용 프로그램의 각 `CEditView` 개체에 대 한 탭 정지를 변경 하려면 각 개체의 `SetTabStops` 함수를 호출 합니다.

### <a name="example"></a>예제

이 코드 조각은 컨트롤에서 사용 하는 글꼴을 신중 하 게 측정 하 여 컨트롤의 탭 정지를 4 번째 문자로 설정 합니다.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

##  <a name="unlockbuffer"></a>CEditView:: UnlockBuffer

이 멤버 함수를 호출 하 여 버퍼 잠금을 해제 합니다.

```
void UnlockBuffer() const;
```

### <a name="remarks"></a>설명

[Lockbuffer](#lockbuffer)에서 반환 된 포인터 사용을 완료 한 후 `UnlockBuffer`를 호출 합니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CDocument 클래스](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView 클래스](../../mfc/reference/cricheditview-class.md)
