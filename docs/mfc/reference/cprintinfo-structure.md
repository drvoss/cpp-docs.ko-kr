---
title: C프린트정보 구조
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 3b081b0728514c0fca2eb31462e1bcd9e91a47aa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753018"
---
# <a name="cprintinfo-structure"></a>C프린트정보 구조

인쇄 또는 인쇄 미리 보기 작업에 대한 정보를 저장합니다.

## <a name="syntax"></a>구문

```
struct CPrintInfo
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C프린트정보::GetFromPage](#getfrompage)|인쇄할 첫 번째 페이지의 번호를 반환합니다.|
|[C프린트정보::겟맥스페이지](#getmaxpage)|문서의 마지막 페이지 수를 반환합니다.|
|[C프린트 정보::겟민페이지](#getminpage)|문서의 첫 페이지 수를 반환합니다.|
|[C프린트정보::오프셋 페이지](#getoffsetpage)|DocObject 항목의 첫 페이지 앞에 있는 페이지 수를 결합된 DocObject 인쇄 작업에서 인쇄합니다.|
|[C프린트정보::겟토페이지](#gettopage)|인쇄할 마지막 페이지 수를 반환합니다.|
|[C프린트정보::셋맥스페이지](#setmaxpage)|문서의 마지막 페이지 수를 설정합니다.|
|[C프린트정보::셋민페이지](#setminpage)|문서의 첫 번째 페이지 수를 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C프린트정보::m_bContinuePrinting](#m_bcontinueprinting)|프레임워크가 인쇄 루프를 계속해야 하는지 여부를 나타내는 플래그가 포함되어 있습니다.|
|[C프린트정보:m_bDirect](#m_bdirect)|인쇄 대화 상자를 표시하지 않고 문서가 직접 인쇄되고 있는지 여부를 나타내는 플래그가 포함되어 있습니다.|
|[C프린트정보::m_bDocObject](#m_bdocobject)|인쇄중인 문서가 DocObject인지 여부를 나타내는 플래그가 포함되어 있습니다.|
|[C프린트정보:m_bPreview](#m_bpreview)|문서를 미리 보기 여부를 나타내는 플래그가 포함되어 있습니다.|
|[C프린트정보:m_dwFlags](#m_dwflags)|DocObject 인쇄 작업을 지정합니다.|
|[C프린트정보:m_lpUserData](#m_lpuserdata)|사용자가 만든 구조에 대한 포인터를 포함합니다.|
|[C프린트정보:m_nCurPage](#m_ncurpage)|현재 인쇄 중인 페이지 수를 식별합니다.|
|[C프린트정보::m_nJobNumber](#m_njobnumber)|현재 인쇄 작업에 대해 운영 체제에서 할당한 작업 번호를 지정합니다.|
|[C프린트정보:m_nNumPreviewPages](#m_nnumpreviewpages)|미리 보기 창에 표시되는 페이지 수를 식별합니다. 1 또는 2.|
|[C프린트정보:m_nOffsetPage](#m_noffsetpage)|결합된 DocObject 인쇄 작업에서 특정 DocObject의 첫 번째 페이지의 오프셋을 지정합니다.|
|[C프린트정보:m_pPD](#m_ppd)|[인쇄 대화 `CPrintDialog` 상자]에 사용되는 개체에 대한 포인터를 포함합니다.|
|[C프린트정보::m_rectDraw](#m_rectdraw)|현재 사용 가능한 페이지 영역을 정의하는 사각형을 지정합니다.|
|[C프린트정보::m_strPageDesc](#m_strpagedesc)|페이지 번호 표시를 위한 형식 문자열을 포함합니다.|

## <a name="remarks"></a>설명

`CPrintInfo`는 구조이며 기본 클래스가 없습니다.

프레임워크는 미리 보기 `CPrintInfo` 인쇄 또는 인쇄 명령을 선택할 때마다 개체를 만들고 명령이 완료될 때 삭제합니다.

`CPrintInfo`에는 인쇄할 페이지 범위 및 현재 인쇄 중인 페이지와 같은 인쇄 작업의 현재 상태와 같은 인쇄 작업에 대한 정보가 모두 포함됩니다. 일부 정보는 연결된 [CPrintDialog](../../mfc/reference/cprintdialog-class.md) 개체에 저장됩니다. 이 개체에는 인쇄 대화 상자에서 사용자가 입력한 값이 포함됩니다.

`CPrintInfo` 개체는 인쇄 프로세스 중에 프레임워크와 뷰 클래스 간에 전달되며 둘 사이의 정보를 교환하는 데 사용됩니다. 예를 들어, 프레임워크는 다음의 `m_nCurPage` 멤버에 `CPrintInfo`값을 할당하여 인쇄할 문서의 페이지 뷰 클래스에 알려줍니다. 뷰 클래스는 값을 검색하고 지정된 페이지의 실제 인쇄를 수행합니다.

또 다른 예로, 문서의 길이가 인쇄될 때까지 알 수 없는 경우를 들 수 있습니다. 이 경우 페이지가 인쇄될 때마다 뷰 클래스가 문서 끝에 대해 테스트합니다. 끝에 도달하면 뷰 클래스는 FALSE의 `m_bContinuePrinting` `CPrintInfo` 멤버를 설정합니다. 이렇게 하면 프레임워크에 인쇄 루프가 중지됩니다.

`CPrintInfo`"참조"에 `CView` 나열된 멤버 함수에서 사용됩니다. Microsoft Foundation 클래스 라이브러리에서 제공하는 인쇄 아키텍처에 대한 자세한 내용은 [프레임 창](../../mfc/frame-windows.md) 및 [문서/보기 아키텍처](../../mfc/document-view-architecture.md) 및 문서 [인쇄](../../mfc/printing.md) 및 [인쇄 문서: 다중 페이지 문서를](../../mfc/multipage-documents.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CPrintInfo`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="cprintinfogetfrompage"></a><a name="getfrompage"></a>C프린트정보::GetFromPage

인쇄할 첫 번째 페이지의 번호를 검색하려면 이 함수를 호출합니다.

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>Return Value

인쇄할 첫 번째 페이지의 수입니다.

### <a name="remarks"></a>설명

이 값은 인쇄 대화 상자에서 사용자가 지정한 값이며 `CPrintDialog` `m_pPD` 멤버가 참조하는 개체에 저장됩니다. 사용자가 값을 지정하지 않은 경우 기본값은 문서의 첫 페이지입니다.

## <a name="cprintinfogetmaxpage"></a><a name="getmaxpage"></a>C프린트정보::겟맥스페이지

이 함수를 호출하여 문서의 마지막 페이지 수를 검색합니다.

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>Return Value

문서의 마지막 페이지 수입니다.

### <a name="remarks"></a>설명

이 값은 멤버가 `CPrintDialog` 참조하는 `m_pPD` 개체에 저장됩니다.

## <a name="cprintinfogetminpage"></a><a name="getminpage"></a>C프린트 정보::겟민페이지

이 함수를 호출하여 문서의 첫 번째 페이지 수를 검색합니다.

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>Return Value

문서의 첫 페이지 수입니다.

### <a name="remarks"></a>설명

이 값은 멤버가 `CPrintDialog` 참조하는 `m_pPD` 개체에 저장됩니다.

## <a name="cprintinfogetoffsetpage"></a><a name="getoffsetpage"></a>C프린트정보::오프셋 페이지

DocObject 클라이언트에서 여러 DocObject 항목을 인쇄할 때 오프셋을 검색하려면 이 함수를 호출합니다.

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>Return Value

DocObject 항목의 첫 페이지 앞에 있는 페이지 수로, 결합된 DocObject 인쇄 작업에서 인쇄됩니다.

### <a name="remarks"></a>설명

이 값은 멤버가 `m_nOffsetPage` 참조합니다. 문서의 첫 페이지에는 다른 활성 `m_nOffsetPage` 문서와 함께 DocObject로 인쇄할 때 값 + 1로 번호가 매겨집니다. 멤버는 `m_nOffsetPage` 값이 TRUE인 `m_bDocObject` 경우에만 유효합니다.

## <a name="cprintinfogettopage"></a><a name="gettopage"></a>C프린트정보::겟토페이지

이 함수를 호출하여 인쇄할 마지막 페이지의 수를 검색합니다.

```
UINT GetToPage() const;
```

### <a name="return-value"></a>Return Value

인쇄할 마지막 페이지의 수입니다.

### <a name="remarks"></a>설명

이 값은 인쇄 대화 상자에서 사용자가 지정한 값이며 `CPrintDialog` `m_pPD` 멤버가 참조하는 개체에 저장됩니다. 사용자가 값을 지정하지 않은 경우 기본값은 문서의 마지막 페이지입니다.

## <a name="cprintinfom_bcontinueprinting"></a><a name="m_bcontinueprinting"></a>C프린트정보::m_bContinuePrinting

프레임워크가 인쇄 루프를 계속해야 하는지 여부를 나타내는 플래그가 포함되어 있습니다.

### <a name="remarks"></a>설명

인쇄 시간 페이지 지정을 수행하는 경우 문서 끝에 도달하면 재정의시 `CView::OnPrepareDC` 이 멤버를 FALSE로 설정할 수 있습니다. 멤버 함수를 사용하여 인쇄 작업의 시작 부분에 문서 길이를 지정한 경우 이 `SetMaxPage` 변수를 수정할 필요가 없습니다. 멤버는 `m_bContinuePrinting` BOOL 형식의 공용 변수입니다.

## <a name="cprintinfom_bdirect"></a><a name="m_bdirect"></a>C프린트정보:m_bDirect

직접 인쇄를 위해 인쇄 대화 상자를 우회할 경우 프레임워크는 이 멤버를 TRUE로 설정합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

인쇄 대화 상자는 일반적으로 셸에서 인쇄하거나 명령 ID ID_FILE_PRINT_DIRECT 사용하여 인쇄를 수행할 때 우회됩니다.

일반적으로 이 멤버를 변경하지는 않지만 변경한 경우 [CView::DoPreparePrinting를](../../mfc/reference/cview-class.md#doprepareprinting) 호출하기 전에 [변경합니다.](../../mfc/reference/cview-class.md#onprepareprinting)

## <a name="cprintinfom_bdocobject"></a><a name="m_bdocobject"></a>C프린트정보::m_bDocObject

인쇄중인 문서가 DocObject인지 여부를 나타내는 플래그가 포함되어 있습니다.

### <a name="remarks"></a>설명

이 `m_dwFlags` 플래그가 TRUE가 아니면 데이터 멤버가 `m_nOffsetPage` 유효하지 않습니다.

## <a name="cprintinfom_bpreview"></a><a name="m_bpreview"></a>C프린트정보:m_bPreview

문서를 미리 보기 여부를 나타내는 플래그가 포함되어 있습니다.

### <a name="remarks"></a>설명

이는 사용자가 실행한 명령에 따라 프레임워크에 의해 설정됩니다. 인쇄 미리 보기 작업에 대해 인쇄 대화 상자가 표시되지 않습니다. 멤버는 `m_bPreview` BOOL 형식의 공용 변수입니다.

## <a name="cprintinfom_dwflags"></a><a name="m_dwflags"></a>C프린트정보:m_dwFlags

DocObject 인쇄 작업을 지정 하는 플래그의 조합을 포함 합니다.

### <a name="remarks"></a>설명

데이터 멤버가 `m_bDocObject` TRUE인 경우에만 유효합니다.

플래그는 다음 값 중 하나 이상일 수 있습니다.

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

## <a name="cprintinfom_lpuserdata"></a><a name="m_lpuserdata"></a>C프린트정보:m_lpUserData

사용자가 만든 구조에 대한 포인터를 포함합니다.

### <a name="remarks"></a>설명

뷰 클래스에 저장하지 않으려는 인쇄 관련 데이터를 저장하는 데 사용할 수 있습니다. 멤버는 `m_lpUserData` LPVOID 형식의 공용 변수입니다.

## <a name="cprintinfom_ncurpage"></a><a name="m_ncurpage"></a>C프린트정보:m_nCurPage

현재 페이지의 수를 포함합니다.

### <a name="remarks"></a>설명

프레임워크는 `CView::OnPrepareDC` 문서의 각 페이지에 대해 호출하고 `CView::OnPrint` 한 번씩 이 멤버에 대해 매번 다른 값을 지정합니다. 해당 값의 범위는 `GetFromPage` `GetToPage`에서 반환된 값까지입니다. 재의 복리에서 이 `CView::OnPrepareDC` `CView::OnPrint` 멤버를 사용하고 문서의 지정된 페이지를 인쇄합니다.

미리 보기 모드가 처음 호출되면 프레임워크는 이 멤버의 값을 읽고 문서의 어떤 페이지를 처음에 미리 볼지 결정합니다. 재정의에서 이 멤버의 `CView::OnPreparePrinting` 값을 설정하여 미리 보기 모드로 들어갈 때 문서에서 사용자의 현재 위치를 유지할 수 있습니다. 멤버는 `m_nCurPage` UINT 형식의 공용 변수입니다.

## <a name="cprintinfom_njobnumber"></a><a name="m_njobnumber"></a>C프린트정보::m_nJobNumber

현재 인쇄 작업에 대한 운영 체제에서 할당한 작업 번호를 나타냅니다.

### <a name="remarks"></a>설명

이 값은 작업이 아직 인쇄되지 `CPrintInfo` 않았거나(즉, 개체가 새로 생성되어 아직 인쇄에 사용되지 않은 경우) 작업을 시작하는 데 오류가 있는 경우 SP_ERROR 수 있습니다.

## <a name="cprintinfom_nnumpreviewpages"></a><a name="m_nnumpreviewpages"></a>C프린트정보:m_nNumPreviewPages

미리 보기 모드에 표시되는 페이지 수를 포함합니다. 1 또는 2일 수 있습니다.

### <a name="remarks"></a>설명

멤버는 `m_nNumPreviewPages` UINT 형식의 공용 변수입니다.

## <a name="cprintinfom_noffsetpage"></a><a name="m_noffsetpage"></a>C프린트정보:m_nOffsetPage

결합된 DocObject 인쇄 작업에서 특정 DocObject의 첫 페이지 앞에 있는 페이지 수를 포함합니다.

## <a name="cprintinfom_ppd"></a><a name="m_ppd"></a>C프린트정보:m_pPD

인쇄 작업에 대한 `CPrintDialog` 인쇄 대화 상자를 표시하는 데 사용되는 개체에 대한 포인터를 포함합니다.

### <a name="remarks"></a>설명

`m_pPD` 멤버는 `CPrintDialog`에 대한 포인터로 선언된 공용 변수입니다.

## <a name="cprintinfom_rectdraw"></a><a name="m_rectdraw"></a>C프린트정보::m_rectDraw

논리적 좌표에서 페이지의 사용 가능한 드로잉 영역을 지정합니다.

### <a name="remarks"></a>설명

재정의에서 `CView::OnPrint`이 것을 참조할 수 있습니다. 이 멤버를 사용하여 헤더, 바닥글 등을 인쇄한 후 사용할 수 있는 영역을 추적할 수 있습니다. `m_rectDraw` 멤버는 형식의 `CRect`공용 변수입니다.

## <a name="cprintinfom_strpagedesc"></a><a name="m_strpagedesc"></a>C프린트정보::m_strPageDesc

인쇄 미리 보기 중에 페이지 번호를 표시하는 데 사용되는 형식 문자열을 포함합니다. 이 문자열은 두 개의 하위 문자열로 구성되며, 하나는 단일 페이지 표시용이고 다른 하나는 이중 페이지 표시용으로 구성되며 각 문자열은 '\n' 문자로 종료됩니다.

### <a name="remarks"></a>설명

프레임워크는 "페이지 %u\nPages %u-%u\n"을 기본값으로 사용합니다. 페이지 번호에 대해 다른 형식을 원하는 경우 재정의에서 형식 `CView::OnPreparePrinting`문자열을 지정합니다. `m_strPageDesc` 멤버는 형식의 `CString`공용 변수입니다.

## <a name="cprintinfosetmaxpage"></a><a name="setmaxpage"></a>C프린트정보::셋맥스페이지

이 함수를 호출하여 문서의 마지막 페이지 수를 지정합니다.

```cpp
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>매개 변수

*n맥스페이지*<br/>
문서의 마지막 페이지 수입니다.

### <a name="remarks"></a>설명

이 값은 멤버가 `CPrintDialog` 참조하는 `m_pPD` 개체에 저장됩니다. 문서의 길이가 인쇄되기 전에 알려진 경우 재정의에서 이 `CView::OnPreparePrinting`함수를 호출합니다. 문서 길이가 인쇄 대화 상자에서 사용자가 지정한 설정에 따라 달라지면 재정의에서 `CView::OnBeginPrinting`이 함수를 호출합니다. 문서의 길이가 인쇄될 때까지 알 수 없는 `m_bContinuePrinting` 경우 멤버를 사용하여 인쇄 루프를 제어합니다.

### <a name="example"></a>예제

  [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)에 대한 예제를 참조하십시오.

## <a name="cprintinfosetminpage"></a><a name="setminpage"></a>C프린트정보::셋민페이지

이 함수를 호출하여 문서의 첫 번째 페이지 수를 지정합니다.

```cpp
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>매개 변수

*nMinPage*<br/>
문서의 첫 페이지 수입니다.

### <a name="remarks"></a>설명

페이지 번호는 일반적으로 1부터 시작합니다. 이 값은 멤버가 `CPrintDialog` 참조하는 `m_pPD` 개체에 저장됩니다.

## <a name="see-also"></a>참조

[MFC 샘플 디브룩](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[C보기::온엔드 프린팅](../../mfc/reference/cview-class.md#onendprinting)<br/>
[C보기::온엔드프린트프리뷰](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[C보기::온준비DC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[C보기::온준비 인쇄](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[C보기::온프린트](../../mfc/reference/cview-class.md#onprint)
