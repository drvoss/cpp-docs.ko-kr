---
title: 콜레서버독 클래스
ms.date: 11/04/2016
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
ms.openlocfilehash: 8e75ec5c00c614a225a059a2b3cf97a7a307c61c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753781"
---
# <a name="coleserverdoc-class"></a>콜레서버독 클래스

OLE 서버 문서의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레서버독::콜레서버독](#coleserverdoc)|`COleServerDoc` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[콜레서버독::활성화닥오브젝트](#activatedocobject)|연결된 DocObject 문서를 활성화합니다.|
|[콜레서버독::활성화인플레이스](#activateinplace)|문서를 활성화하여 현재 편집합니다.|
|[콜레서버독::D](#deactivateandundo)|서버의 사용자 인터페이스를 비활성화합니다.|
|[콜레서버독::D카드운도스테이트](#discardundostate)|취소 상태 정보를 삭제합니다.|
|[COleServerDoc::GetClientSite](#getclientsite)|기본 `IOleClientSite` 인터페이스에 대한 포인터를 검색합니다.|
|[COleServerDoc::GetEmbedded항목](#getembeddeditem)|전체 문서를 나타내는 항목에 대한 포인터를 반환합니다.|
|[콜레서버독::겟아이템클립렉트](#getitemcliprect)|현재 클리핑 사각형을 반환하여 현재 편집을 합니다.|
|[COleServerDoc::GetItem 포지션](#getitemposition)|현재 위치 사각형을 반환(컨테이너 응용 프로그램의 클라이언트 영역을 기준으로) 현재 위치 편집을 위해 반환합니다.|
|[콜레서버독::겟줌팩터](#getzoomfactor)|확대/축소 계수를 픽셀 단위로 반환합니다.|
|[콜레서버독::이스닥오브젝트](#isdocobject)|문서가 DocObject인지 확인합니다.|
|[콜레서버독::임베디드](#isembedded)|문서가 컨테이너 문서에 포함되는지 아니면 독립 실행형으로 실행중인지를 나타냅니다.|
|[콜레서버독::이스인플레이스액티브](#isinplaceactive)|항목이 현재 활성화된 경우 TRUE를 반환합니다.|
|[COleServerDoc::알림 변경](#notifychanged)|사용자가 문서를 변경했다는 것을 컨테이너에 지정합니다.|
|[COleServerDoc::알림 폐쇄](#notifyclosed)|사용자가 문서를 닫았다는 것을 컨테이너에 지정합니다.|
|[COleServerDoc::알림다시이름](#notifyrename)|사용자가 문서이름을 변경했다는 것을 컨테이너에 지정합니다.|
|[COleServerDoc::알림저장](#notifysaved)|사용자가 문서를 저장한 컨테이너에 대해 사용자에게 지정합니다.|
|[콜레서버독::온비활성화](#ondeactivate)|사용자가 활성화된 항목을 비활성화할 때 프레임워크에서 호출됩니다.|
|[콜레서버독::온데솔루UI](#ondeactivateui)|내부 활성화를 위해 만든 컨트롤 및 기타 사용자 인터페이스 요소를 삭제하기 위해 프레임워크에서 호출합니다.|
|[콜레서버독::온닥윈도우활성화](#ondocwindowactivate)|컨테이너의 문서 프레임 창이 활성화되거나 비활성화될 때 프레임워크에서 호출됩니다.|
|[콜레서버독::온리사이즈보더](#onresizeborder)|컨테이너 응용 프로그램의 프레임 창 또는 문서 창의 크기가 조정될 때 프레임워크에서 호출합니다.|
|[콜레서버독::온쇼컨트롤바](#onshowcontrolbars)|프레임워크에서 호출하여 작업장 편집을 위해 컨트롤 막대를 표시하거나 숨깁니다.|
|[COleServerDoc::업데이트 문서](#onupdatedocument)|포함된 항목인 서버 문서가 저장될 때 프레임워크에서 호출하여 컨테이너의 항목 복사본을 업데이트합니다.|
|[COleServerDoc::요청 위치 변경](#requestpositionchange)|현재 편집 프레임의 위치를 변경합니다.|
|[콜레서버독::세이브엠베딩](#saveembedding)|컨테이너 응용 프로그램에 문서를 저장하도록 지시합니다.|
|[COleServerDoc::스크롤 컨테이너](#scrollcontainerby)|컨테이너 문서를 스크롤합니다.|
|[COleServerDoc::업데이트모든 항목](#updateallitems)|사용자가 문서를 변경했다는 것을 컨테이너에 지정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[콜레서버독::인플레이스프레임 만들기](#createinplaceframe)|프레임워크에서 호출하여 현재 편집을 위한 프레임 창을 만듭니다.|
|[콜레서버독::D에스트로이인플레이스프레임](#destroyinplaceframe)|프레임워크에서 호출하여 현재 편집을 위한 프레임 창을 삭제합니다.|
|[콜레서버독::겟닥오브젝트서버](#getdocobjectserver)|이 함수를 재정의하여 `CDocObjectServer` 새 개체를 만들고 이 문서가 DocObject 컨테이너임을 나타냅니다.|
|[콜레서버독::온클로즈](#onclose)|컨테이너가 문서를 닫도록 요청할 때 프레임워크에서 호출됩니다.|
|[콜레서버독::오넥세올레Cmd](#onexecolecmd)|지정된 명령을 실행하거나 명령에 대한 도움말을 표시합니다.|
|[COleServerDoc::온프레임 윈도우활성화](#onframewindowactivate)|컨테이너의 프레임 창이 활성화되거나 비활성화될 때 프레임워크에서 호출됩니다.|
|[콜레서버독::온겟데베디드아이템](#ongetembeddeditem)|전체 문서를 `COleServerItem` 나타내는 을 얻으려면 호출됩니다. 포함된 항목을 얻는 데 사용됩니다. 구현이 필요합니다.|
|[콜레서버독::온리활성화안던도](#onreactivateandundo)|프레임워크에서 호출하여 현재 편집 중에 변경한 내용을 실행 취소합니다.|
|[COleServerDoc::OnSetHostNames](#onsethostnames)|컨테이너가 포함된 개체에 대한 창 제목을 설정하는 경우 프레임워크에서 호출됩니다.|
|[콜레서버독::온셋아이템렉트](#onsetitemrects)|프레임워크에서 호출하여 컨테이너 응용 프로그램의 창 내에 내부 편집 프레임 창을 배치합니다.|
|[콜레서버독::온쇼문서](#onshowdocument)|문서를 표시하거나 숨기기 위해 프레임워크에서 호출합니다.|

## <a name="remarks"></a>설명

서버 문서에는 포함된 항목또는 연결된 항목에 대한 서버 인터페이스를 나타내는 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 개체가 포함될 수 있습니다. 포함된 항목을 편집하기 위해 컨테이너에서 서버 응용 프로그램을 시작하면 해당 항목이 자체 서버 문서로 로드됩니다. `COleServerDoc` 개체에는 전체 `COleServerItem` 문서로 구성된 개체가 하나만 포함됩니다. 연결된 항목을 편집하기 위해 컨테이너에서 서버 응용 프로그램을 시작하면 기존 문서가 디스크에서 로드됩니다. 연결된 항목을 나타내기 위해 문서 내용의 일부가 강조 표시됩니다.

`COleServerDoc`개체에는 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 클래스의 항목도 포함될 수 있습니다. 이렇게 하면 컨테이너 서버 응용 프로그램을 만들 수 있습니다. 프레임워크는 `COleServerItem` 개체를 서비스하는 `COleClientItem` 동안 항목을 올바르게 저장하는 기능을 제공합니다.

서버 응용 프로그램이 링크를 지원하지 않는 경우 서버 문서에는 항상 포함된 전체 개체를 문서로 나타내는 하나의 서버 항목만 포함됩니다. 서버 응용 프로그램이 링크를 지원하는 경우 선택 영역을 Clipboard에 복사할 때마다 서버 항목을 만들어야 합니다.

을 `COleServerDoc`사용하려면 클래스를 파생하고 서버가 임베디드 항목을 지원할 수 있는 [OnGetEmbeddedItem](#ongetembeddeditem) 멤버 함수를 구현합니다. 에서 `COleServerItem` 클래스를 파생하여 문서에서 항목을 구현하고 `OnGetEmbeddedItem`에서 해당 클래스의 개체를 반환합니다.

연결된 항목을 지원하려면 `COleServerDoc` [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) 멤버 함수를 제공합니다. 문서 항목을 관리하는 고유한 방법이 있는 경우 기본 구현을 사용하거나 재정의할 수 있습니다.

응용 프로그램에서 `COleServerDoc`지원하는 각 서버 문서 유형에 대해 파생 클래스가 하나 필요합니다. 예를 들어 서버 응용 프로그램이 워크시트와 차트를 `COleServerDoc`지원하는 경우 두 개의 파생 클래스가 필요합니다.

서버에 대한 자세한 내용은 [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

`COleServerDoc`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="coleserverdocactivatedocobject"></a><a name="activatedocobject"></a>콜레서버독::활성화닥오브젝트

연결된 DocObject 문서를 활성화합니다.

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>설명

기본적으로 활성 `COleServerDoc` 문서(DocObjects라고도 함)는 지원하지 않습니다. 이 지원을 활성화하려면 [GetDocObjectServer](#getdocobjectserver) 및 클래스 [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)를 참조하십시오.

## <a name="coleserverdocactivateinplace"></a><a name="activateinplace"></a>콜레서버독::활성화인플레이스

항목을 활성화하여 현재 편집합니다.

```
BOOL ActivateInPlace();
```

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; 그렇지 않으면 0이며, 이는 항목이 완전히 열려 있음을 나타냅니다.

### <a name="remarks"></a>설명

이 함수는 내부 활성화에 필요한 모든 작업을 수행합니다. 내부 프레임 창을 만들고, 활성화하고, 항목에 크기를 조정하고, 공유 메뉴 및 기타 컨트롤을 설정하고, 항목을 보기로 스크롤하고, 내부 프레임 창으로 포커스를 설정합니다.

이 함수는 [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)의 기본 구현에서 호출됩니다. 응용 프로그램이 내부 활성화를 위해 다른 동사를 지원하는 경우 이 함수를 호출합니다(예: Play).

## <a name="coleserverdoccoleserverdoc"></a><a name="coleserverdoc"></a>콜레서버독::콜레서버독

OLE 시스템 `COleServerDoc` DLL에 연결하지 않고 개체를 생성합니다.

```
COleServerDoc();
```

### <a name="remarks"></a>설명

[OLELinkingDoc::등록을](../../mfc/reference/colelinkingdoc-class.md#register) 호출하여 OLE와의 통신을 열어야 합니다. 응용 프로그램에서 [COleTemplateServer를](../../mfc/reference/coletemplateserver-class.md) 사용하는 `COleLinkingDoc::Register` 경우 `COleLinkingDoc` `OnNewDocument`의 구현에 의해 `OnOpenDocument`호출됩니다. `OnSaveDocument`

## <a name="coleserverdoccreateinplaceframe"></a><a name="createinplaceframe"></a>콜레서버독::인플레이스프레임 만들기

프레임워크는 이 함수를 호출하여 현재 편집을 위한 프레임 창을 만듭니다.

```
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
컨테이너 응용 프로그램의 상위 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

인플레이스 프레임 창에 대한 포인터 또는 실패할 경우 NULL입니다.

### <a name="remarks"></a>설명

기본 구현은 문서 템플릿에 지정된 정보를 사용하여 프레임을 만듭니다. 사용된 뷰는 문서에 대해 생성된 첫 번째 뷰입니다. 이 뷰는 원래 프레임에서 일시적으로 분리되고 새로 생성된 프레임에 연결됩니다.

이 고급 재정의 할 수 있습니다.

## <a name="coleserverdocdeactivateandundo"></a><a name="deactivateandundo"></a>콜레서버독::D

응용 프로그램이 수행 취소를 지원하고 사용자가 항목을 활성화한 후 편집하기 전에 수행 취소를 선택하는 경우 이 함수를 호출합니다.

```
BOOL DeactivateAndUndo();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

컨테이너 응용 프로그램이 Microsoft Foundation 클래스 라이브러리를 사용하여 작성된 경우 이 함수를 호출하면 [COleClientItem::OnDeactivateAndUndo가](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) 호출되어 서버의 사용자 인터페이스가 비활성화됩니다.

## <a name="coleserverdocdestroyinplaceframe"></a><a name="destroyinplaceframe"></a>콜레서버독::D에스트로이인플레이스프레임

프레임워크는 이 함수를 호출하여 내부 프레임 창을 삭제하고 서버 응용 프로그램의 문서 창을 내부 활성화 전에 해당 상태로 반환합니다.

```
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>매개 변수

*pFrameWnd*<br/>
소멸할 인플레이스 프레임 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 고급 재정의 할 수 있습니다.

## <a name="coleserverdocdiscardundostate"></a><a name="discardundostate"></a>콜레서버독::D카드운도스테이트

사용자가 취소할 수 없는 편집 작업을 수행하는 경우 이 함수를 호출하여 컨테이너 응용 프로그램이 취소 상태 정보를 강제로 삭제하도록 합니다.

```
BOOL DiscardUndoState();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

이 함수는 Undo를 지원하는 서버가 사용할 수 없는 상태 취소 정보에서 사용할 수 있는 리소스를 해제할 수 있도록 제공됩니다.

## <a name="coleserverdocgetclientsite"></a><a name="getclientsite"></a>COleServerDoc::GetClientSite

기본 `IOleClientSite` 인터페이스에 대한 포인터를 검색합니다.

```
LPOLECLIENTSITE GetClientSite() const;
```

### <a name="return-value"></a>Return Value

기본 [IOleClientSite](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite) 인터페이스에 대한 포인터를 검색합니다.

## <a name="coleserverdocgetdocobjectserver"></a><a name="getdocobjectserver"></a>콜레서버독::겟닥오브젝트서버

이 함수를 재정의하여 `CDocObjectServer` 새 항목을 만들고 포인터를 반환합니다.

```
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```

### <a name="parameters"></a>매개 변수

*pDocSite*<br/>
이 문서를 `IOleDocumentSite` 서버에 연결하는 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

에 `CDocObjectServer`대한 포인터입니다. 작업이 실패한 경우 NULL입니다.

### <a name="remarks"></a>설명

DocObject 서버가 활성화되면 NULL이 아닌 포인터를 반환하면 클라이언트가 DocObjects를 지원할 수 있음을 알 수 있습니다. 기본 구현은 NULL을 반환합니다.

DocObjects를 지원하는 문서에 대한 일반적인 구현은 새 `CDocObjectServer` 개체를 할당하고 호출자에게 반환합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]

## <a name="coleserverdocgetembeddeditem"></a><a name="getembeddeditem"></a>COleServerDoc::GetEmbedded항목

전체 문서를 나타내는 항목에 대한 포인터를 얻으려면 이 함수를 호출합니다.

```
COleServerItem* GetEmbeddedItem();
```

### <a name="return-value"></a>Return Value

전체 문서를 나타내는 항목에 대한 포인터입니다. 작업이 실패한 경우 NULL입니다.

### <a name="remarks"></a>설명

그것은 [COleServerDoc를 호출::OnGetEmbeddedItem,](#ongetembeddeditem)기본 구현 없이 가상 함수.

## <a name="coleserverdocgetitemcliprect"></a><a name="getitemcliprect"></a>콜레서버독::겟아이템클립렉트

멤버 `GetItemClipRect` 함수를 호출하여 편집 중인 항목의 클리핑-사각형 좌표를 가져옵니다.

```cpp
void GetItemClipRect(LPRECT lpClipRect) const;
```

### <a name="parameters"></a>매개 변수

*lpClipRect*<br/>
항목의 `RECT` 클리핑-사각형 좌표를 받을 구조체 또는 `CRect` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

좌표는 컨테이너 응용 프로그램 창의 클라이언트 영역을 기준으로 픽셀입니다.

클리핑 사각형 외부에서 드로잉이 발생하지 않아야 합니다. 일반적으로 드로잉은 자동으로 제한됩니다. 이 함수를 사용하여 사용자가 문서의 표시되는 부분 외부로 스크롤했는지 여부를 확인합니다. 그렇다면 필요에 따라 컨테이너 문서를 [스크롤하여 ScrollContainerBy](#scrollcontainerby)에 대한 호출을 합니다.

## <a name="coleserverdocgetitemposition"></a><a name="getitemposition"></a>COleServerDoc::GetItem 포지션

멤버 `GetItemPosition` 함수를 호출하여 편집 중인 항목의 좌표를 가져옵니다.

```cpp
void GetItemPosition(LPRECT lpPosRect) const;
```

### <a name="parameters"></a>매개 변수

*lpPosRect*<br/>
항목의 `RECT` 좌표를 `CRect` 수신할 구조체 또는 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

좌표는 컨테이너 응용 프로그램 창의 클라이언트 영역을 기준으로 픽셀입니다.

항목의 위치를 현재 클리핑 사각형과 비교하여 항목이 화면에 표시되거나 표시되지 않는 정도를 결정할 수 있습니다.

## <a name="coleserverdocgetzoomfactor"></a><a name="getzoomfactor"></a>콜레서버독::겟줌팩터

멤버 `GetZoomFactor` 함수는 내부 편집을 위해 활성화된 항목의 "확대/축소 계수"를 결정합니다.

```
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,
    LPSIZE lpSizeDenom = NULL,
    LPCRECT lpPosRect = NULL) const;
```

### <a name="parameters"></a>매개 변수

*lpSizeNum*<br/>
확대/축소 계수의 분자를 보유하는 클래스 `CSize` 객체에 대한 포인터입니다. NULL일 수 있습니다.

*lpSizeDenom*<br/>
확대/축소 요소의 `CSize` 분모를 보유하는 클래스 오브젝트에 대한 포인터입니다. NULL일 수 있습니다.

*lpPosRect*<br/>
항목의 새 위치를 `CRect` 설명하는 클래스 개체에 대한 포인터입니다. 이 인수가 NULL이면 함수는 항목의 현재 위치를 사용합니다.

### <a name="return-value"></a>Return Value

항목이 현재 편집을 위해 활성화되고 확대/축소 계수가 100%(1:1)를 초과하는 경우 그렇지 않으면 0.

### <a name="remarks"></a>설명

확대/축소 계수는 항목 크기의 현재 범위 비율입니다. 컨테이너 응용 프로그램이 항목의 범위를 설정하지 않은 경우 자연 [범위(COleServerItem:OnGetExtent)가](../../mfc/reference/coleserveritem-class.md#ongetextent)결정합니다.

이 함수는 처음 두 인수를 항목의 "확대/축소 계수"의 분자 및 분모로 설정합니다. 항목이 편집되지 않으면 함수는 이러한 인수를 기본값 100%(또는 1:1)로 설정하고 0을 반환합니다. 자세한 내용은 기술 참고 40, [MFC/OLE 내 크기 조정 및 확대/축소를](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)참조하십시오.

## <a name="coleserverdocisdocobject"></a><a name="isdocobject"></a>콜레서버독::이스닥오브젝트

문서가 DocObject인지 확인합니다.

```
BOOL IsDocObject() const;
```

### <a name="return-value"></a>Return Value

TRUE 문서가 DocObject인 경우; 그렇지 않으면 거짓.

## <a name="coleserverdocisembedded"></a><a name="isembedded"></a>콜레서버독::임베디드

멤버 `IsEmbedded` 함수를 호출하여 문서가 컨테이너에 포함된 개체를 나타내는지 여부를 확인합니다.

```
BOOL IsEmbedded() const;
```

### <a name="return-value"></a>Return Value

개체가 컨테이너에 `COleServerDoc` 포함된 개체를 나타내는 문서인 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

컨테이너 응용 프로그램에서 링크로 조작할 수 있지만 파일에서 로드된 문서는 포함되지 않습니다. 컨테이너 문서에 포함된 문서는 포함된 것으로 간주됩니다.

## <a name="coleserverdocisinplaceactive"></a><a name="isinplaceactive"></a>콜레서버독::이스인플레이스액티브

Call the `IsInPlaceActive` member function to determine whether the item is currently in the in-place active state.

```
BOOL IsInPlaceActive() const;
```

### <a name="return-value"></a>Return Value

개체가 활성 `COleServerDoc` 상태인 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="coleserverdocnotifychanged"></a><a name="notifychanged"></a>COleServerDoc::알림 변경

이 함수를 호출하여 문서에 연결된 모든 연결된 항목에 문서가 변경되었음을 알립니다.

```cpp
void NotifyChanged();
```

### <a name="remarks"></a>설명

일반적으로 사용자가 서버 문서의 크기와 같은 일부 전역 특성을 변경한 후 이 함수를 호출합니다. OLE 항목이 자동 링크가 있는 문서에 연결되어 있으면 변경 내용을 반영하도록 항목이 업데이트됩니다. Microsoft Foundation 클래스 라이브러리로 작성된 컨테이너 응용 [프로그램에서OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 멤버 `COleClientItem` 함수를 호출합니다.

> [!NOTE]
> 이 기능은 OLE 1과의 호환성을 위해 포함되어 있습니다. 새 응용 프로그램은 [UpdateAllItems](#updateallitems).

## <a name="coleserverdocnotifyclosed"></a><a name="notifyclosed"></a>COleServerDoc::알림 폐쇄

이 함수를 호출하여 컨테이너에 문서가 닫혔다는 것을 알립니다.

```cpp
void NotifyClosed();
```

### <a name="remarks"></a>설명

사용자가 파일 메뉴에서 닫기 명령을 선택하면 `NotifyClosed` `COleServerDoc` [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) 멤버 함수의 구현에 의해 호출됩니다. Microsoft Foundation 클래스 라이브러리로 작성된 컨테이너 응용 [프로그램에서OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 멤버 `COleClientItem` 함수를 호출합니다.

## <a name="coleserverdocnotifyrename"></a><a name="notifyrename"></a>COleServerDoc::알림다시이름

사용자가 서버 문서의 이름을 바꾼 후 이 함수를 호출합니다.

```cpp
void NotifyRename(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>매개 변수

*lpszNewName*<br/>
서버 문서의 새 이름을 지정하는 문자열에 대한 포인터입니다. 일반적으로 정규화된 경로입니다.

### <a name="remarks"></a>설명

사용자가 파일 메뉴에서 As로 저장 명령을 `NotifyRename` 선택하면 `COleServerDoc` [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) 멤버 함수의 구현에 의해 호출됩니다. 이 함수는 OLE 시스템 DLL을 알리고 컨테이너에 알립니다. Microsoft Foundation 클래스 라이브러리로 작성된 컨테이너 응용 [프로그램에서OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 멤버 `COleClientItem` 함수를 호출합니다.

## <a name="coleserverdocnotifysaved"></a><a name="notifysaved"></a>COleServerDoc::알림저장

사용자가 서버 문서를 저장한 후 이 함수를 호출합니다.

```cpp
void NotifySaved();
```

### <a name="remarks"></a>설명

사용자가 파일 메뉴에서 저장 명령을 선택하면 `NotifySaved` [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument)의 `COleServerDoc`구현에 의해 호출됩니다. 이 함수는 OLE 시스템 DLL을 알리고 컨테이너에 알립니다. Microsoft Foundation 클래스 라이브러리로 작성된 컨테이너 응용 [프로그램에서OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 멤버 `COleClientItem` 함수를 호출합니다.

## <a name="coleserverdoconclose"></a><a name="onclose"></a>콜레서버독::온클로즈

컨테이너가 서버 문서를 닫아달라고 요청할 때 프레임워크에서 호출됩니다.

```
virtual void OnClose(OLECLOSE dwCloseOption);
```

### <a name="parameters"></a>매개 변수

*dwCloseOption*<br/>
열거형 OLECLOSE의 값입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.

- OLECLOSE_SAVEIFDIRTY 파일이 수정된 경우 저장됩니다.

- OLECLOSE_NOSAVE 파일을 저장하지 않고 닫힙입니다.

- OLECLOSE_PROMPTSAVE 파일이 수정된 경우 사용자에게 파일을 저장하라는 메시지가 표시됩니다.

### <a name="remarks"></a>설명

기본 구현은 `CDocument::OnCloseDocument`을 호출합니다.

자세한 정보 및 추가 값은 Windows SDK의 [OLECLOSE를](/windows/win32/api/oleidl/ne-oleidl-oleclose) 참조하십시오.

## <a name="coleserverdocondeactivate"></a><a name="ondeactivate"></a>콜레서버독::온비활성화

사용자가 현재 현재 활성 상태인 임베디드 또는 링크된 항목을 비활성화할 때 프레임워크에서 호출됩니다.

```
virtual void OnDeactivate();
```

### <a name="remarks"></a>설명

이 함수는 컨테이너 응용 프로그램의 사용자 인터페이스를 원래 상태로 복원하고 내부 활성화를 위해 만든 메뉴 및 기타 컨트롤을 삭제합니다.

취소 상태 정보는 이 시점에서 무조건 해제되어야 합니다.

자세한 내용은 [활성화](../../mfc/activation-cpp.md)문서를 참조하십시오.

## <a name="coleserverdocondeactivateui"></a><a name="ondeactivateui"></a>콜레서버독::온데솔루UI

사용자가 활성화된 항목을 비활성화할 때 호출됩니다.

```
virtual void OnDeactivateUI(BOOL bUndoable);
```

### <a name="parameters"></a>매개 변수

*bUndoable*<br/>
편집 변경 내용을 취소할 수 있는지 여부를 지정합니다.

### <a name="remarks"></a>설명

이 함수는 컨테이너 응용 프로그램의 사용자 인터페이스를 원래 상태로 복원하여 내부 활성화를 위해 만든 메뉴 및 기타 컨트롤을 숨김으로 합니다.

프레임워크는 항상 *bundoable을* FALSE로 설정합니다. 서버가 실행 취소를 지원하고 실행 취소할 수 있는 작업이 있는 경우 *bUndoable* 을 TRUE로 설정한 기본 클래스 구현을 호출합니다.

## <a name="coleserverdocondocwindowactivate"></a><a name="ondocwindowactivate"></a>콜레서버독::온닥윈도우활성화

프레임워크는 이 함수를 호출하여 문서 창을 활성화하거나 비활성화하여 현재 편집합니다.

```
virtual void OnDocWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*bActivate*<br/>
문서 창을 활성화 또는 비활성화할지 여부를 지정합니다.

### <a name="remarks"></a>설명

기본 구현은 프레임 수준 사용자 인터페이스 요소를 적절히 제거하거나 추가합니다. 항목이 포함된 문서가 활성화되거나 비활성화될 때 추가 작업을 수행하려는 경우 이 기능을 재정의합니다.

자세한 내용은 [활성화](../../mfc/activation-cpp.md)문서를 참조하십시오.

## <a name="coleserverdoconexecolecmd"></a><a name="onexecolecmd"></a>콜레서버독::오넥세올레Cmd

프레임워크는 이 함수를 호출하여 지정된 명령을 실행하거나 명령에 대한 도움말을 표시합니다.

```
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,
    DWORD nCmdID,
    DWORD nCmdExecOpt,
    VARIANTARG* pvarargIn,
    VARIANTARG* pvarargOut);
```

### <a name="parameters"></a>매개 변수

*pguidCmdGroup*<br/>
명령 집합을 식별하는 GUID에 대한 포인터입니다. 기본 명령 그룹을 나타내기 위해 NULL일 수 있습니다.

*nCmdID*<br/>
실행할 명령입니다. *pguidCmdGroup으로*식별된 그룹에 있어야 합니다.

*nCmdExecOut*<br/>
개체가 OLECMDEXECOPT 열거형에서 다음 값 중 하나 이상을 명령실행하는 방법:

OLECMDEXECOPT_DODEFAULT

OLECMDEXECOPT_PROMPTUSER

OLECMDEXECOPT_DONTPROMPTUSER

OLECMDEXECOPT_SHOWHELP

*프바라르긴*<br/>
명령에 대한 입력 인수를 포함하는 VARIANTARG에 대한 포인터입니다. NULL일 수 있습니다.

*프바라그아웃*<br/>
VARIANTARG에 대한 포인터를 사용하여 명령에서 출력 반환 값을 수신합니다. NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK 반환합니다. 그렇지 않으면 다음 오류 코드 중 하나입니다.

|값|Description|
|-----------|-----------------|
|E_UNEXPECTED|예기치 않은 오류가 발생했습니다.|
|E_FAIL|오류가 발생했습니다.|
|E_NOTIMPL|MFC 자체가 명령을 번역하고 디스패치하려고 시도해야 함|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup은* NULL이 아닌 비이지만 인식된 명령 그룹을 지정하지 않습니다.|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID그룹* *pguidCmdGroup에서* 유효한 명령으로 인식되지 않음|
|OLECMDERR_DISABLED|*nCmdID로* 식별된 명령이 비활성화되어 실행할 수 없습니다.|
|OLECMDERR_NOHELP|발신자가 *nCmdID로* 식별된 명령에 대한 도움을 요청했지만 도움을 받을 수 없습니다.|
|OLECMDERR_CANCELED|사용자가 실행을 취소했습니다.|

### <a name="remarks"></a>설명

`COleCmdUI`DocObject 사용자 인터페이스 명령의 다른 속성을 활성화, 업데이트 및 설정하는 데 사용할 수 있습니다. 명령이 초기화되면 을 실행하여 `OnExecOleCmd`실행할 수 있습니다.

프레임워크는 OLE 문서 명령을 번역하고 디스패치하기 전에 함수를 호출합니다. 표준 OLE 문서 명령을 처리하기 위해 이 함수를 재정의할 필요는 없지만 사용자 지정 명령을 처리하거나 매개 변수를 허용하거나 결과를 반환하는 명령을 처리하려면 이 함수에 재정의를 제공해야 합니다.

대부분의 명령은 인수를 수행하거나 값을 반환하지 않습니다. 명령의 대부분에 대 한 호출자는 *pvarargIn* 및 *pvarargOut에*대 한 NUL를 전달할 수 있습니다. 입력 값을 기대하는 명령의 경우 호출자는 VARIANTARG 변수를 선언하고 초기화하고 *pvarargIn의*변수에 포인터를 전달할 수 있습니다. 단일 값이 필요한 명령의 경우 인수를 VARIANTARG에 직접 저장하고 함수에 전달할 수 있습니다. 지원되는 형식(예: `IDispatch` SAFEARRAY) 중 하나를 사용하여 VARIANTARG 내에서 여러 인수를 패키징해야 합니다.

마찬가지로 명령이 인수를 반환하는 경우 호출자는 VARIANTARG를 선언하고 VT_EMPTY 초기화하고 *pvarargOut에서*주소를 전달합니다. 명령이 단일 값을 반환하는 경우 개체는 해당 값을 *pvarargOut에*직접 저장할 수 있습니다. VARIANTARG에 적합한 방식으로 여러 출력 값을 패키징해야 합니다.

이 함수의 기본 클래스 구현은 명령 대상과 연결된 OLE_COMMAND_MAP 구조를 안내하고 명령을 적절한 처리기로 디스패치하려고 시도합니다. 기본 클래스 구현은 인수를 수락하거나 값을 반환하지 않는 명령에서만 작동합니다. 인수를 수락하거나 값을 반환하는 명령을 처리해야 하는 경우 이 함수를 재정의하고 *pvarargIn* 및 *pvarargOut* 매개 변수를 직접 사용해야 합니다.

## <a name="coleserverdoconframewindowactivate"></a><a name="onframewindowactivate"></a>COleServerDoc::온프레임 윈도우활성화

프레임워크는 컨테이너 응용 프로그램의 프레임 창이 활성화되거나 비활성화될 때 이 함수를 호출합니다.

```
virtual void OnFrameWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*bActivate*<br/>
프레임 창을 활성화 또는 비활성화할지 여부를 지정합니다.

### <a name="remarks"></a>설명

기본 구현은 프레임 창에 있을 수 있는 도움말 모드를 취소합니다. 프레임 창이 활성화되거나 비활성화될 때 특수 처리를 수행하려는 경우 이 기능을 재정의합니다.

자세한 내용은 [활성화](../../mfc/activation-cpp.md)문서를 참조하십시오.

## <a name="coleserverdocongetembeddeditem"></a><a name="ongetembeddeditem"></a>콜레서버독::온겟데베디드아이템

컨테이너 응용 프로그램이 서버 응용 프로그램을 호출하여 포함된 항목을 만들거나 편집할 때 프레임워크에서 호출합니다.

```
virtual COleServerItem* OnGetEmbeddedItem() = 0;
```

### <a name="return-value"></a>Return Value

전체 문서를 나타내는 항목에 대한 포인터입니다. 작업이 실패한 경우 NULL입니다.

### <a name="remarks"></a>설명

기본 구현은 없습니다. 전체 문서를 나타내는 항목을 반환하려면 이 함수를 재정의해야 합니다. 이 반환 값은 `COleServerItem`-derived 클래스의 개체여야 합니다.

## <a name="coleserverdoconreactivateandundo"></a><a name="onreactivateandundo"></a>콜레서버독::온리활성화안던도

프레임워크는 사용자가 해당 위치에 활성화되고 변경된 항목이 변경된 항목의 변경 내용을 실행 취소하도록 선택할 때 이 함수를 호출합니다.

```
virtual BOOL OnReactivateAndUndo();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 구현은 실패를 나타내기 위해 FALSE를 반환하는 것 외에는 아무 것도 수행하지 않습니다.

응용 프로그램이 취소를 지원하는 경우 이 함수를 재정의합니다. 일반적으로 수행 취소 작업을 수행한 다음 을 호출하여 `ActivateInPlace`항목을 활성화합니다. 컨테이너 응용 프로그램이 Microsoft Foundation 클래스 라이브러리를 `COleClientItem::ReactivateAndUndo` 사용하여 작성된 경우 호출하면 이 함수가 호출됩니다.

## <a name="coleserverdoconresizeborder"></a><a name="onresizeborder"></a>콜레서버독::온리사이즈보더

프레임워크는 컨테이너 응용 프로그램의 프레임 창 크기가 변경될 때 이 함수를 호출합니다.

```
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,
    LPOLEINPLACEUIWINDOW lpUIWindow,
    BOOL bFrame);
```

### <a name="parameters"></a>매개 변수

*lpRectBorder*<br/>
테두리의 `RECT` 좌표를 `CRect` 지정하는 구조체 또는 개체에 대한 포인터입니다.

*lpui창*<br/>
현재 내부 편집 `IOleInPlaceUIWindow` 세션을 소유하는 클래스의 개체에 대한 포인터입니다.

*b프레임*<br/>
true *lpUIWindow* 컨테이너 응용 프로그램의 최상위 프레임 창을 가리키는 경우, 또는 *false lpUIWindow* 컨테이너 응용 프로그램의 문서 수준 프레임 창을 가리키는 경우.

### <a name="remarks"></a>설명

이 함수는 새 창 크기에 따라 도구 모음 및 기타 사용자 인터페이스 요소의 크기를 조정하고 조정합니다.

자세한 내용은 Windows SDK의 [IOleInPlaceUIWindow를](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceuiwindow) 참조하십시오.

이 고급 재정의 할 수 있습니다.

## <a name="coleserverdoconsethostnames"></a><a name="onsethostnames"></a>COleServerDoc::OnSetHostNames

컨테이너가 이 문서의 호스트 이름을 설정하거나 변경할 때 프레임워크에서 호출됩니다.

```
virtual void OnSetHostNames(
    LPCTSTR lpszHost,
    LPCTSTR lpszHostObj);
```

### <a name="parameters"></a>매개 변수

*lpszHost*<br/>
컨테이너 응용 프로그램의 이름을 지정하는 문자열에 대한 포인터입니다.

*lpszHostObj*<br/>
문서에 대 한 컨테이너의 이름을 지정 하는 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

기본 구현은 이 문서를 참조하는 모든 뷰에 대한 문서 제목을 변경합니다.

응용 프로그램이 다른 메커니즘을 통해 제목을 설정하는 경우 이 함수를 재정의합니다.

## <a name="coleserverdoconsetitemrects"></a><a name="onsetitemrects"></a>콜레서버독::온셋아이템렉트

프레임워크는 이 함수를 호출하여 컨테이너 응용 프로그램의 프레임 창 내에 내부 편집 프레임 창을 배치합니다.

```
virtual void OnSetItemRects(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>매개 변수

*lpPosRect*<br/>
컨테이너 응용 `RECT` 프로그램의 `CRect` 클라이언트 영역을 기준으로 현재 프레임 창의 위치를 지정하는 구조체 또는 개체에 대한 포인터입니다.

*lpClipRect*<br/>
컨테이너 응용 `RECT` 프로그램의 `CRect` 클라이언트 영역을 기준으로 현재 프레임 창의 클리핑 사각형을 지정하는 구조또는 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

필요한 경우 이 함수를 재정의하여 뷰의 확대/축소 비율을 업데이트합니다.

이 함수는 일반적으로 `RequestPositionChange` 호출에 대 한 응답으로 호출 되지만 컨테이너에 의해 언제든지 호출할 수 있습니다 내부 항목에 대 한 위치 변경을 요청 합니다.

## <a name="coleserverdoconshowcontrolbars"></a><a name="onshowcontrolbars"></a>콜레서버독::온쇼컨트롤바

프레임워크는 이 함수를 호출하여 *pFrameWnd로*식별된 프레임 창과 연결된 서버 응용 프로그램의 컨트롤 막대를 표시하거나 숨깁니다.

```
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*pFrameWnd*<br/>
컨트롤 막대를 숨기거나 표시해야 하는 프레임 창에 대한 포인터입니다.

*bShow*<br/>
컨트롤 막대가 표시되거나 숨김 여부를 결정합니다.

### <a name="remarks"></a>설명

기본 구현은 해당 프레임 창이 소유한 모든 컨트롤 막대를 개명하고 숨기거나 표시합니다.

## <a name="coleserverdoconshowdocument"></a><a name="onshowdocument"></a>콜레서버독::온쇼문서

프레임워크는 서버 `OnShowDocument` 문서를 숨겨거나 표시해야 하는 경우 함수를 호출합니다.

```
virtual void OnShowDocument(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
문서에 대한 사용자 인터페이스를 표시할지 숨길지 여부를 지정합니다.

### <a name="remarks"></a>설명

*bShow가* TRUE이면 기본 구현은 필요한 경우 서버 응용 프로그램을 활성화하고 컨테이너 응용 프로그램이 해당 창을 스크롤하여 항목이 표시되도록 합니다. *bShow가* FALSE이면 기본 구현은 `OnDeactivate`에 대한 호출을 통해 항목을 비활성화한 다음 첫 번째 를 제외하고 문서에 대해 만들어진 모든 프레임 창을 삭제하거나 숨깁니다. 표시 문서가 남아 있지 않으면 기본 구현에서 서버 응용 프로그램을 숨깁니다.

## <a name="coleserverdoconupdatedocument"></a><a name="onupdatedocument"></a>COleServerDoc::업데이트 문서

복합 문서에 포함된 항목인 문서를 저장할 때 프레임워크에서 호출합니다.

```
virtual BOOL OnUpdateDocument();
```

### <a name="return-value"></a>Return Value

문서가 성공적으로 업데이트된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

기본 구현은 [COleServerDoc::NotifySave](#notifysaved) 및 [COleServerDoc::SaveEmbedding](#saveembedding) 멤버 함수를 호출한 다음 문서를 정리됨으로 표시합니다. 포함된 항목을 업데이트할 때 특수 처리를 수행하려는 경우 이 함수를 재정의합니다.

## <a name="coleserverdocrequestpositionchange"></a><a name="requestpositionchange"></a>COleServerDoc::요청 위치 변경

컨테이너 응용 프로그램이 항목의 위치를 변경하도록 하려면 이 멤버 함수를 호출합니다.

```cpp
void RequestPositionChange(LPCRECT lpPosRect);
```

### <a name="parameters"></a>매개 변수

*lpPosRect*<br/>
항목의 `RECT` 새 위치를 `CRect` 포함하는 구조또는 객체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 내부 `UpdateAllItems`활성 항목의 데이터가 변경될 때(와 함께) 호출됩니다. 이 호출 이 후 컨테이너는 를 호출하여 `OnSetItemRects`변경을 수행하거나 수행하지 않을 수 있습니다. 결과 위치는 요청한 위치와 다를 수 있습니다.

## <a name="coleserverdocsaveembedding"></a><a name="saveembedding"></a>콜레서버독::세이브엠베딩

이 함수를 호출하여 컨테이너 응용 프로그램에 포함된 개체를 저장하도록 지시합니다.

```cpp
void SaveEmbedding();
```

### <a name="remarks"></a>설명

이 함수는 에서 `OnUpdateDocument`자동으로 호출됩니다. 이 함수는 항목을 디스크에서 업데이트하도록 하므로 일반적으로 특정 사용자 작업의 결과로만 호출됩니다.

## <a name="coleserverdocscrollcontainerby"></a><a name="scrollcontainerby"></a>COleServerDoc::스크롤 컨테이너

구성원 `ScrollContainerBy` 함수를 호출하여 컨테이너 문서를 에 표시된 픽셀 단위로 `sizeScroll`스크롤합니다.

```
BOOL ScrollContainerBy(CSize sizeScroll);
```

### <a name="parameters"></a>매개 변수

*크기스크롤*<br/>
컨테이너 문서가 스크롤할 정도를 나타냅니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

양수 값은 아래와 오른쪽으로 스크롤함을 나타냅니다. 음수 값은 위와 왼쪽으로 스크롤함을 나타냅니다.

## <a name="coleserverdocupdateallitems"></a><a name="updateallitems"></a>COleServerDoc::업데이트모든 항목

이 함수를 호출하여 문서에 연결된 모든 연결된 항목에 문서가 변경되었음을 알립니다.

```cpp
void UpdateAllItems(
    COleServerItem* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL,
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>매개 변수

*pSender*<br/>
문서를 수정한 항목에 대한 포인터 또는 모든 항목을 업데이트할 경우 NULL을 지정합니다.

*lHint*<br/>
수정에 대한 정보가 들어 있습니다.

*pHint*<br/>
수정에 대한 정보를 저장하는 개체에 대한 포인터입니다.

*nDrawAspect*<br/>
항목을 그리는 방법을 결정합니다. DVASPECT 열거형의 값입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.

- DVASPECT_CONTENT 항목은 컨테이너 내부에 포함된 개체로 표시될 수 있는 방식으로 표시됩니다.

- DVASPECT_THUMBNAIL 항목은 검색 도구에 표시될 수 있도록 "썸네일" 표현으로 렌더링됩니다.

- DVASPECT_ICON 항목은 아이콘으로 표시됩니다.

- DVASPECT_DOCPRINT 항목은 파일 메뉴에서 인쇄 명령을 사용하여 인쇄된 것처럼 표시됩니다.

### <a name="remarks"></a>설명

일반적으로 사용자가 서버 문서를 변경한 후 이 함수를 호출합니다. OLE 항목이 자동 링크가 있는 문서에 연결되어 있으면 변경 내용을 반영하도록 항목이 업데이트됩니다. Microsoft Foundation 클래스 라이브러리로 작성된 컨테이너 응용 [프로그램에서OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 멤버 `COleClientItem` 함수를 호출합니다.

이 함수는 `OnUpdate` 송신 항목, *전달 pHint, lHint*및 *nDrawAspect를*제외한 각 문서 항목에 대한 멤버 *함수를*호출합니다. 이러한 매개 변수를 사용하여 문서에 대한 수정 사항에 대한 정보를 항목에 전달합니다. *lHint를* 사용하여 정보를 인코딩하거나 -derived 클래스를 `CObject`정의하여 수정 사항에 대한 정보를 저장하고 *pHint를*사용하여 해당 클래스의 개체를 전달할 수 있습니다. -derived `OnUpdate` 클래스의 멤버 함수를 재정의하여 프레젠테이션이 변경되었는지 여부에 따라 각 항목의 업데이트를 최적화합니다. `COleServerItem`

## <a name="see-also"></a>참조

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[코올링싱독 클래스](../../mfc/reference/colelinkingdoc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레문서 클래스](../../mfc/reference/coledocument-class.md)<br/>
[코올링싱독 클래스](../../mfc/reference/colelinkingdoc-class.md)<br/>
[COle템플릿서버 클래스](../../mfc/reference/coletemplateserver-class.md)
