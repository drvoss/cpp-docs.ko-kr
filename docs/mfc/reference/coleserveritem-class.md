---
title: 콜레서버아이템 클래스
ms.date: 11/04/2016
f1_keywords:
- COleServerItem
- AFXOLE/COleServerItem
- AFXOLE/COleServerItem::COleServerItem
- AFXOLE/COleServerItem::AddOtherClipboardData
- AFXOLE/COleServerItem::CopyToClipboard
- AFXOLE/COleServerItem::DoDragDrop
- AFXOLE/COleServerItem::GetClipboardData
- AFXOLE/COleServerItem::GetDocument
- AFXOLE/COleServerItem::GetEmbedSourceData
- AFXOLE/COleServerItem::GetItemName
- AFXOLE/COleServerItem::GetLinkSourceData
- AFXOLE/COleServerItem::GetObjectDescriptorData
- AFXOLE/COleServerItem::IsConnected
- AFXOLE/COleServerItem::IsLinkedItem
- AFXOLE/COleServerItem::NotifyChanged
- AFXOLE/COleServerItem::OnDoVerb
- AFXOLE/COleServerItem::OnDraw
- AFXOLE/COleServerItem::OnDrawEx
- AFXOLE/COleServerItem::OnGetClipboardData
- AFXOLE/COleServerItem::OnGetExtent
- AFXOLE/COleServerItem::OnInitFromData
- AFXOLE/COleServerItem::OnQueryUpdateItems
- AFXOLE/COleServerItem::OnRenderData
- AFXOLE/COleServerItem::OnRenderFileData
- AFXOLE/COleServerItem::OnRenderGlobalData
- AFXOLE/COleServerItem::OnSetColorScheme
- AFXOLE/COleServerItem::OnSetData
- AFXOLE/COleServerItem::OnSetExtent
- AFXOLE/COleServerItem::OnUpdate
- AFXOLE/COleServerItem::OnUpdateItems
- AFXOLE/COleServerItem::SetItemName
- AFXOLE/COleServerItem::GetDataSource
- AFXOLE/COleServerItem::OnHide
- AFXOLE/COleServerItem::OnOpen
- AFXOLE/COleServerItem::OnShow
- AFXOLE/COleServerItem::m_sizeExtent
helpviewer_keywords:
- COleServerItem [MFC], COleServerItem
- COleServerItem [MFC], AddOtherClipboardData
- COleServerItem [MFC], CopyToClipboard
- COleServerItem [MFC], DoDragDrop
- COleServerItem [MFC], GetClipboardData
- COleServerItem [MFC], GetDocument
- COleServerItem [MFC], GetEmbedSourceData
- COleServerItem [MFC], GetItemName
- COleServerItem [MFC], GetLinkSourceData
- COleServerItem [MFC], GetObjectDescriptorData
- COleServerItem [MFC], IsConnected
- COleServerItem [MFC], IsLinkedItem
- COleServerItem [MFC], NotifyChanged
- COleServerItem [MFC], OnDoVerb
- COleServerItem [MFC], OnDraw
- COleServerItem [MFC], OnDrawEx
- COleServerItem [MFC], OnGetClipboardData
- COleServerItem [MFC], OnGetExtent
- COleServerItem [MFC], OnInitFromData
- COleServerItem [MFC], OnQueryUpdateItems
- COleServerItem [MFC], OnRenderData
- COleServerItem [MFC], OnRenderFileData
- COleServerItem [MFC], OnRenderGlobalData
- COleServerItem [MFC], OnSetColorScheme
- COleServerItem [MFC], OnSetData
- COleServerItem [MFC], OnSetExtent
- COleServerItem [MFC], OnUpdate
- COleServerItem [MFC], OnUpdateItems
- COleServerItem [MFC], SetItemName
- COleServerItem [MFC], GetDataSource
- COleServerItem [MFC], OnHide
- COleServerItem [MFC], OnOpen
- COleServerItem [MFC], OnShow
- COleServerItem [MFC], m_sizeExtent
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
ms.openlocfilehash: bdb91168a7c0ae718ca7d7514448b55965186aa8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753746"
---
# <a name="coleserveritem-class"></a>콜레서버아이템 클래스

OLE 항목에 대한 서버 인터페이스를 제공합니다.

## <a name="syntax"></a>구문

```
class COleServerItem : public CDocItem
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[COleServerItem::COleServerItem](#coleserveritem)|`COleServerItem` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|개체에 프레젠테이션 및 변환 `COleDataSource` 형식을 배치합니다.|
|[COleServerItem::CopyToClipboard](#copytoclipboard)|항목을 클립보드에 복사합니다.|
|[COleServerItem::DoDragDrop](#dodragdrop)|끌어서 놓기 작업을 수행합니다.|
|[COleServerItem::GetClipboardData](#getclipboarddata)|데이터 전송(드래그 앤 드롭 또는 클립보드)에 사용할 데이터 원본을 가져옵니다.|
|[COleServerItem::GetDocument](#getdocument)|항목이 포함된 서버 문서를 반환합니다.|
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|OLE 항목에 대한 CF_EMBEDSOURCE 데이터를 가져옵니다.|
|[COleServerItem::GetItemName](#getitemname)|항목의 이름을 반환합니다. 연결된 항목에만 사용됩니다.|
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|OLE 항목에 대한 CF_LINKSOURCE 데이터를 가져옵니다.|
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|OLE 항목에 대한 CF_OBJECTDESCRIPTOR 데이터를 가져옵니다.|
|[COleServerItem::IsConnected](#isconnected)|항목이 현재 활성 컨테이너에 연결되어 있는지 여부를 나타냅니다.|
|[COleServerItem::IsLinkedItem](#islinkeditem)|항목이 연결된 OLE 항목을 나타내는지 여부를 나타냅니다.|
|[COleServerItem::NotifyChanged](#notifychanged)|자동 링크 업데이트로 모든 컨테이너를 업데이트합니다.|
|[COleServerItem::OnDoVerb](#ondoverb)|동사를 실행 하기 위해 호출 됩니다.|
|[COleServerItem::OnDraw](#ondraw)|컨테이너가 항목을 그릴 것을 요청할 때 호출됩니다. 구현이 필요합니다.|
|[COleServerItem::OnDrawEx](#ondrawex)|특수 항목 그리기를 요청했습니다.|
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|클립보드에 복사될 데이터를 얻기 위해 프레임워크에서 호출됩니다.|
|[COleServerItem::OnGetExtent](#ongetextent)|프레임워크에서 호출하여 OLE 항목의 크기를 검색합니다.|
|[COleServer항목::OnInitFromData](#oninitfromdata)|지정된 데이터 전송 개체의 내용을 사용하여 OLE 항목을 초기화하기 위해 프레임워크에서 호출합니다.|
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|연결된 항목에 업데이트가 필요한지 여부를 확인하기 위해 호출됩니다.|
|[COleServerItem::OnRenderData](#onrenderdata)|지연된 렌더링의 일부로 데이터를 검색합니다.|
|[COleServer항목::온렌더파일데이터](#onrenderfiledata)|지연된 렌더링의 `CFile` 일부로 데이터를 개체로 검색합니다.|
|[콜레서버항목:온렌더글로벌데이터](#onrenderglobaldata)|지연된 렌더링의 일부로 HGLOBAL에 데이터를 검색합니다.|
|[콜레 서버 항목::온셋컬러스킴](#onsetcolorscheme)|항목의 색 구성표를 설정하기 위해 호출됩니다.|
|[콜레서버항목::온셋데이터](#onsetdata)|항목의 데이터를 설정하기 위해 호출됩니다.|
|[COleServerItem::OnSetExtent](#onsetextent)|프레임워크에서 호출하여 OLE 항목의 크기를 설정합니다.|
|[COleServerItem::OnUpdate](#onupdate)|항목이 속한 문서의 일부가 변경될 때 호출됩니다.|
|[COleServerItem::OnUpdateItems](#onupdateitems)|서버 문서의 모든 항목의 프레젠테이션 캐시를 업데이트하기 위해 호출됩니다.|
|[콜레서버항목::세트항목이름](#setitemname)|항목의 이름을 설정합니다. 연결된 항목에만 사용됩니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[COleServerItem::GetDataSource](#getdatasource)|변환 형식을 저장하는 데 사용되는 개체를 가져옵니다.|
|[콜서버아이템::온하이드](#onhide)|올레 항목을 숨기려면 프레임워크에서 호출합니다.|
|[COleServerItem::OnOpen](#onopen)|프레임워크에서 호출하여 OLE 항목을 자체 최상위 창에 표시합니다.|
|[콜서버항목::온쇼](#onshow)|컨테이너가 항목을 표시하도록 요청할 때 호출됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[COleServerItem::m_sizeExtent](#m_sizeextent)|OLE 항목의 표시 정도를 서버에 알립니다.|

## <a name="remarks"></a>설명

연결된 항목은 서버 문서의 일부 또는 전부를 나타낼 수 있습니다. 포함된 항목은 항상 전체 서버 문서를 나타냅니다.

클래스는 `COleServerItem` 일반적으로 컨테이너 응용 프로그램의 요청에 응답하여 OLE 시스템 동적 링크 라이브러리(DLL)에서 호출되는 여러 재정의 가능한 멤버 함수를 정의합니다. 이러한 멤버 함수를 사용하면 컨테이너 응용 프로그램이 항목을 표시하거나 동사를 실행하거나 다양한 형식으로 데이터를 검색하는 등 다양한 방법으로 항목을 간접적으로 조작할 수 있습니다.

이를 `COleServerItem`사용하려면 클래스를 파생시키고 [OnDraw](#ondraw) 및 [Serialize](../../mfc/reference/cobject-class.md#serialize) 멤버 함수를 구현합니다. 이 `OnDraw` 함수는 항목의 메타파일 표현을 제공하므로 컨테이너 응용 프로그램이 복합 문서를 열 때 표시할 수 있습니다. 함수는 `Serialize` `CObject` 항목의 기본 표현을 제공하므로 포함된 항목을 서버와 컨테이너 응용 프로그램 간에 전송할 수 있습니다. [OnGetExtent는](#ongetextent) 컨테이너에 항목의 자연스러운 크기를 제공하여 컨테이너가 항목의 크기를 조정할 수 있도록 합니다.

서버 및 관련 항목에 대한 자세한 내용은 [문서 서버: 서버 구현](../../mfc/servers-implementing-a-server.md) 및 "컨테이너/서버 응용 프로그램 만들기" 문서 [컨테이너: 고급 기능을](../../mfc/containers-advanced-features.md)참조하세요.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

`COleServerItem`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="coleserveritemaddotherclipboarddata"></a><a name="addotherclipboarddata"></a>COleServer항목::추가클립보드데이터

이 함수를 호출하여 OLE 항목의 프레젠테이션 및 변환 `COleDataSource` 형식을 지정된 개체에 배치합니다.

```cpp
void AddOtherClipboardData(COleDataSource* pDataSource);
```

### <a name="parameters"></a>매개 변수

*pDataSource*<br/>
데이터를 배치해야 하는 `COleDataSource` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

항목에 대한 프레젠테이션 형식(메타파일 그림)을 제공하기 위해 [OnDraw](#ondraw) 멤버 함수를 구현해야 합니다. 다른 변환 형식을 지원하려면 [GetDataSource에서](#getdatasource) 반환하는 [COleDataSource](../../mfc/reference/coledatasource-class.md) 개체를 사용하여 등록하고 [OnRenderData](#onrenderdata) 멤버 함수를 재정의하여 지원하려는 형식으로 데이터를 제공합니다.

## <a name="coleserveritemcoleserveritem"></a><a name="coleserveritem"></a>콜레 서버 항목::콜서버항목

개체를 `COleServerItem` 생성하고 서버 문서의 문서 항목 컬렉션에 추가합니다.

```
COleServerItem(
    COleServerDoc* pServerDoc,
    BOOL bAutoDelete);
```

### <a name="parameters"></a>매개 변수

*pServerDoc*<br/>
새 항목을 포함 하는 문서에 대 한 포인터입니다.

*bAutoDelete*<br/>
개체에 대한 링크가 해제될 때 개체를 삭제할 수 있는지 여부를 나타내는 플래그입니다. 개체가 `COleServerItem` 삭제해야 하는 문서 데이터의 필수적인 일부인 경우 FALSE로 설정합니다. 개체가 프레임워크에서 삭제할 수 있는 문서 데이터의 범위를 식별하는 데 사용되는 보조 구조인 경우 TRUE로 설정합니다.

## <a name="coleserveritemcopytoclipboard"></a><a name="copytoclipboard"></a>콜레서버아이템::카피토클립보드

이 함수를 호출하여 OLE 항목을 클립보드에 복사합니다.

```cpp
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```

### <a name="parameters"></a>매개 변수

*bIncludeLink*<br/>
링크 데이터를 클립보드에 복사해야 하는 경우 TRUE로 설정합니다. 서버 응용 프로그램이 링크를 지원하지 않는 경우 FALSE로 설정합니다.

### <a name="remarks"></a>설명

이 함수는 [OnGetClipboardData](#ongetclipboarddata) 멤버 함수를 사용하여 지원되는 형식으로 OLE 항목의 데이터를 포함하는 [COleDataSource](../../mfc/reference/coledatasource-class.md) 개체를 만듭니다. 그런 다음 `COleDataSource` [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) 함수를 사용하여 개체를 클립보드에 배치합니다. 개체에는 `COleDataSource` 항목의 기본 데이터와 CF_METAFILEPICT 형식의 표현, 지원하도록 선택한 변환 형식의 데이터가 포함됩니다. 이 멤버 함수가 작동하려면 [직렬화](../../mfc/reference/cobject-class.md#serialize) 및 [OnDraw를](#ondraw) 구현해야 합니다.

## <a name="coleserveritemdodragdrop"></a><a name="dodragdrop"></a>콜서버아이템::D오드래그드롭

멤버 `DoDragDrop` 함수를 호출하여 끌어서 놓기 작업을 수행합니다.

```
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,
    CPoint ptOffset,
    BOOL bIncludeLink = FALSE,
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,
    LPCRECT lpRectStartDrag = NULL);
```

### <a name="parameters"></a>매개 변수

*lpRectItem*<br/>
클라이언트 영역을 기준으로 화면에서 항목의 사각형(픽셀)입니다.

*ptOffset*<br/>
마우스 위치가 끌 때 있던 *lpItemRect의* 오프셋입니다.

*bIncludeLink*<br/>
링크 데이터를 클립보드에 복사해야 하는 경우 TRUE로 설정합니다. 응용 프로그램에서 링크를 지원하지 않는 경우 FALSE로 설정합니다.

*dwEffects*<br/>
끌기 소스가 끌기 작업에서 허용할 효과(복사, 이동 및 링크의 조합)를 결정합니다.

*lpRectStartDrag*<br/>
드래그가 실제로 시작되는 위치를 정의하는 사각형에 대한 포인터입니다. 자세한 내용은 아래 설명 부분을 참조하십시오.

### <a name="return-value"></a>Return Value

DROPEFFECT 열거형의 값입니다. DROPEFFECT_MOVE 경우 원본 데이터를 제거해야 합니다.

### <a name="remarks"></a>설명

끌어서 놓기 작업이 즉시 시작되지 는 않습니다. 마우스 커서가 *lpRectStartDrag에서* 지정한 사각형을 떠날 때까지 또는 지정된 밀리초가 경과할 때까지 기다립니다. *lpRectStartDrag가* NULL인 경우 마우스 커서가 한 픽셀을 이동할 때 드래그가 시작되도록 기본 사각형이 사용됩니다.

지연 시간은 레지스트리 키 설정에 의해 지정됩니다. [CWinApp:::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) 또는 [CWinApp::WriteProfileInt를](../../mfc/reference/cwinapp-class.md#writeprofileint)호출하여 지연 시간을 변경할 수 있습니다. 지연 시간을 지정하지 않으면 기본값 200밀리초가 사용됩니다. 드래그 지연 시간은 다음과 같이 저장됩니다.

- 윈도우 NT 드래그 지연 시간은 HKEY_LOCAL_MACHINE 저장됩니다 \SOFTWARE\마이크로 소프트 \윈도우 \NT \현재버전\IniFileMapping\win.ini\Windows\DragDelay.

- 윈도우 3.x 드래그 지연 시간은 WIN에 저장됩니다. [Windows} 섹션 아래의 INI 파일입니다.

- 윈도우 95/98 드래그 지연 시간은 WIN의 캐시 된 버전에 저장됩니다. Ini.

드래그 지연 정보가 레지스트리 또는 에 저장되는 방법에 대한 자세한 내용은 INI 파일은 Windows SDK의 [WriteProfileString을](/windows/win32/api/winbase/nf-winbase-writeprofilestringw) 참조하십시오.

## <a name="coleserveritemgetclipboarddata"></a><a name="getclipboarddata"></a>COleServer항목::겟클립보드데이터

이 함수를 호출하여 지정된 [COleDataSource](../../mfc/reference/coledatasource-class.md) 개체를 [CopyToClipboard라고](#copytoclipboard) 하는 경우 클립보드에 복사할 모든 데이터를 채웁니다(DoDragDrop이라고 하는 경우 동일한 데이터도 전송됨). [DoDragDrop](#dodragdrop)

```cpp
void GetClipboardData(
    COleDataSource* pDataSource,
    BOOL bIncludeLink = FALSE,
    LPPOINT lpOffset = NULL,
    LPSIZE lpSize = NULL);
```

### <a name="parameters"></a>매개 변수

*pDataSource*<br/>
지원되는 `COleDataSource` 모든 형식으로 OLE 항목의 데이터를 수신할 개체에 대한 포인터입니다.

*bIncludeLink*<br/>
링크 데이터를 클립보드에 복사해야 하는 경우 TRUE입니다. 서버 응용 프로그램이 링크를 지원하지 않는 경우 FALSE입니다.

*lpOffset*<br/>
개체의 원점에서 마우스 커서의 오프셋(픽셀 단위)입니다.

*lpSize*<br/>
개체의 크기(픽셀)입니다.

### <a name="remarks"></a>설명

이 함수는 [GetEmbedSourceData](#getembedsourcedata) 멤버 함수를 호출하여 OLE 항목에 대한 기본 데이터를 얻고 [AddOtherClipboardData](#addotherclipboarddata) 멤버 함수를 호출하여 프레젠테이션 형식 및 지원되는 변환 형식을 가져옵니다. *bIncludeLink가* TRUE이면 함수는 [GetLinkSourceData를](#getlinksourcedata) 호출하여 항목에 대한 링크 데이터를 가져옵니다.

에서 제공하는 형식 의 앞이나 이후에 `COleDataSource` 개체에 형식을 배치하려면 이 함수를 재정의합니다. `CopyToClipboard`

## <a name="coleserveritemgetdatasource"></a><a name="getdatasource"></a>COleServer항목::겟데이터소스

서버 응용 프로그램이 지원하는 변환 형식을 저장하는 데 사용되는 [COleDataSource](../../mfc/reference/coledatasource-class.md) 개체를 얻으려면 이 함수를 호출합니다.

```
COleDataSource* GetDataSource();
```

### <a name="return-value"></a>Return Value

변환 형식을 `COleDataSource` 저장하는 데 사용되는 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

데이터 전송 작업 중에 서버 응용 프로그램이 다양한 형식으로 데이터를 제공하려면 이 함수에서 반환되는 `COleDataSource` 개체로 해당 형식을 등록합니다. 예를 들어 클립보드 또는 끌어서 놓기 작업에 대한 OLE 항목의 CF_TEXT 표현을 제공하려는 경우 `COleDataSource` 이 함수가 반환하는 개체에 `OnRenderXxxData` 형식을 등록한 다음 멤버 함수를 재정의하여 데이터를 제공합니다.

## <a name="coleserveritemgetdocument"></a><a name="getdocument"></a>COleServer항목::GetDocument

이 함수를 호출하여 항목이 포함된 문서에 대한 포인터를 가져옵니다.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Return Value

항목이 포함된 문서에 대한 포인터입니다. 항목이 문서의 일부가 아닌 경우 NULL입니다.

### <a name="remarks"></a>설명

이렇게 하면 `COleServerItem` 생성자에 대한 인수로 전달한 서버 문서에 액세스할 수 있습니다.

## <a name="coleserveritemgetembedsourcedata"></a><a name="getembedsourcedata"></a>COleServer항목::GetEmbedSourceData

이 함수를 호출하여 OLE 항목에 대한 CF_EMBEDSOURCE 데이터를 가져옵니다.

```cpp
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>매개 변수

*lpStgMedium*<br/>
OLE 항목에 대한 CF_EMBEDSOURCE 데이터를 수신하는 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 형식에는 항목의 기본 데이터가 포함됩니다. 이 함수가 `Serialize` 제대로 작동하려면 멤버 함수를 구현해야 합니다.

그런 다음 [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata)를 사용하여 결과를 데이터 원본에 추가할 수 있습니다. 이 함수는 [COleServerItem::OnGetClipboardData](#ongetclipboarddata).

자세한 내용은 Windows SDK의 [STGMEDIUM를](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 참조하십시오.

## <a name="coleserveritemgetitemname"></a><a name="getitemname"></a>콜레 서버항목::GetItemName

이 함수를 호출하여 항목 이름을 가져옵니다.

```
const CString& GetItemName() const;
```

### <a name="return-value"></a>Return Value

항목의 이름입니다.

### <a name="remarks"></a>설명

일반적으로 연결된 항목에 대해서만 이 함수를 호출합니다.

## <a name="coleserveritemgetlinksourcedata"></a><a name="getlinksourcedata"></a>COleServer항목::겟링크소스데이터

이 함수를 호출하여 OLE 항목에 대한 CF_LINKSOURCE 데이터를 가져옵니다.

```
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>매개 변수

*lpStgMedium*<br/>
OLE 항목에 대한 CF_LINKSOURCE 데이터를 수신하는 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 형식에는 OLE 항목의 형식과 OLE 항목이 포함된 문서를 찾는 데 필요한 정보를 설명하는 CLSID가 포함됩니다.

그런 다음 [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata)를 사용하여 데이터 원본에 결과를 추가할 수 있습니다. 이 함수는 [OnGetClipboardData에](#ongetclipboarddata)의해 자동으로 호출됩니다.

자세한 내용은 Windows SDK의 [STGMEDIUM를](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 참조하십시오.

## <a name="coleserveritemgetobjectdescriptordata"></a><a name="getobjectdescriptordata"></a>COleServer항목::겟오브젝트 설명자데이터

이 함수를 호출하여 OLE 항목에 대한 CF_OBJECTDESCRIPTOR 데이터를 가져옵니다.

```cpp
void GetObjectDescriptorData(
    LPPOINT lpOffset,
    LPSIZE lpSize,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>매개 변수

*lpOffset*<br/>
OLE 항목의 왼쪽 위 모서리에서 마우스 를 클릭합니다. NULL일 수 있습니다.

*lpSize*<br/>
OLE 항목의 크기입니다. NULL일 수 있습니다.

*lpStgMedium*<br/>
OLE 항목에 대한 CF_OBJECTDESCRIPTOR 데이터를 수신하는 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

정보는 `STGMEDIUM` *lpStgMedium에*의해 가리키는 구조로 복사됩니다. 이 형식에는 특수 붙여넣기 대화에 필요한 정보가 포함됩니다.

자세한 내용은 Windows SDK의 [STGMEDIUM를](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 참조하십시오.

## <a name="coleserveritemisconnected"></a><a name="isconnected"></a>콜레서버항목::연결됨

이 함수를 호출하여 OLE 항목이 연결되어 있는지 확인합니다.

```
BOOL IsConnected() const;
```

### <a name="return-value"></a>Return Value

항목이 연결된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

하나 이상의 컨테이너에 항목에 대한 참조가 있는 경우 OLE 항목은 연결된 것으로 간주됩니다. 참조 수가 0보다 크거나 포함된 항목인 경우 항목이 연결됩니다.

## <a name="coleserveritemislinkeditem"></a><a name="islinkeditem"></a>콜레서버항목::연결된 항목

이 함수를 호출하여 OLE 항목이 연결된 항목인지 확인합니다.

```
BOOL IsLinkedItem() const;
```

### <a name="return-value"></a>Return Value

항목이 연결된 항목인 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

항목이 유효하고 문서의 포함된 항목 목록에 반환되지 않은 경우 항목이 연결됩니다. 연결된 항목은 컨테이너에 연결될 수도 또는 연결되지 않을 수 있습니다.

연결된 항목과 포함된 항목 모두에 동일한 클래스를 사용하는 것이 일반적입니다. `IsLinkedItem`연결된 항목을 포함된 항목과 다르게 다르게 행동하도록 만들 수 있지만 코드는 여러 번 일반적입니다.

## <a name="coleserveritemm_sizeextent"></a><a name="m_sizeextent"></a>콜레서버아이템::m_sizeExtent

이 멤버는 컨테이너 문서에 표시되는 개체의 양을 서버에 알려줍니다.

```
CSize m_sizeExtent;
```

### <a name="remarks"></a>설명

[OnSetExtent의](#onsetextent) 기본 구현은 이 멤버를 설정합니다.

## <a name="coleserveritemnotifychanged"></a><a name="notifychanged"></a>COleServer항목::알림 변경

연결된 항목이 변경된 후 이 함수를 호출합니다.

```cpp
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>매개 변수

*nDrawAspect*<br/>
OLE 항목의 어떤 측면이 변경되었는지 나타내는 DVASPECT 열거형의 값입니다. 이 매개 변수는 다음 값 중 일부를 가질 수 있습니다.

- DVASPECT_CONTENT 항목은 컨테이너 내부에 포함된 개체로 표시될 수 있는 방식으로 표시됩니다.

- DVASPECT_THUMBNAIL 항목은 검색 도구에 표시될 수 있도록 "썸네일" 표현으로 렌더링됩니다.

- DVASPECT_ICON 항목은 아이콘으로 표시됩니다.

- DVASPECT_DOCPRINT 항목은 파일 메뉴에서 인쇄 명령을 사용하여 인쇄된 것처럼 표시됩니다.

### <a name="remarks"></a>설명

컨테이너 항목이 자동 링크로 문서에 연결되어 있으면 변경 내용을 반영하도록 항목이 업데이트됩니다. Microsoft 파운데이션 클래스 라이브러리를 사용하여 작성된 컨테이너 응용 프로그램에서 [COleClientItem::OnChange가](../../mfc/reference/coleclientitem-class.md#onchange) 응답으로 호출됩니다.

## <a name="coleserveritemondoverb"></a><a name="ondoverb"></a>콜서버항목::온도버브

지정된 동사를 실행 하기 위해 프레임 워크에 의해 호출 됩니다.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
실행할 동사를 지정합니다. 다음 중 하나일 수 있습니다.

|값|의미|기호|
|-----------|-------------|------------|
|0|기본 동사|OLEIVERB_PRIMARY|
|1|보조 동사|(없음)|
|- 1|편집할 항목 표시|OLEIVERB_SHOW|
|- 2|별도의 창에서 항목 편집|OLEIVERB_OPEN|
|- 3|항목 숨기기|OLEIVERB_HIDE|

-1 값은 일반적으로 다른 동사의 별칭입니다. 열린 편집이 지원되지 않으면 -2는 -1과 동일한 효과를 가짐을 가합니다. 추가 값은 Windows SDK에서 [IOleObject::Doverb를](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) 참조하십시오.

### <a name="remarks"></a>설명

컨테이너 응용 프로그램이 Microsoft Foundation 클래스 라이브러리로 작성된 경우 해당 `COleClientItem` 개체의 [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate) 멤버 함수가 호출될 때 이 함수가 호출됩니다. 기본 구현은 기본 동사 또는 OLEIVERB_SHOW 지정된 경우 [OnShow](#onshow) 멤버 함수 OLEIVERB_HIDE [OLEIVERB_OPEN를](#onopen) 호출합니다. [OnHide](#onhide) `OnShow` *iVerb가* 위에 나열된 동사 중 하나가 아닌 경우 기본 구현 호출합니다.

기본 동사에 항목이 표시되지 않는 경우 이 함수를 재정의합니다. 예를 들어 항목이 사운드 녹음이고 기본 동사가 재생인 경우 항목을 재생하기 위해 서버 응용 프로그램을 표시할 필요가 없습니다.

자세한 내용은 Windows SDK의 [IOleObject::Doverb를](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) 참조하십시오.

## <a name="coleserveritemondraw"></a><a name="ondraw"></a>콜서버항목::온드로우

프레임워크에서 호출하여 OLE 항목을 메타파일로 렌더링합니다.

```
virtual BOOL OnDraw(
    CDC* pDC,
    CSize& rSize) = 0;
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
항목을 그릴 [CDC](../../mfc/reference/cdc-class.md) 개체에 대한 포인터입니다. 표시 컨텍스트는 특성 표시 컨텍스트에 자동으로 연결되므로 특성 함수를 호출할 수 있지만 이렇게 하면 메타파일 장치가 특정하게 됩니다.

*rSize*<br/>
메타파일을 그릴 HIMETRIC 단위의 크기입니다.

### <a name="return-value"></a>Return Value

항목이 성공적으로 그려진 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

OLE 항목의 메타파일 표현은 컨테이너 응용 프로그램에 항목을 표시하는 데 사용됩니다. 컨테이너 응용 프로그램이 Microsoft Foundation 클래스 라이브러리로 작성된 경우 메타파일은 해당 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 개체의 [Draw](../../mfc/reference/coleclientitem-class.md#draw) 멤버 함수에서 사용됩니다. 기본 구현은 없습니다. 지정된 장치 컨텍스트에 항목을 그리려면 이 함수를 재정의해야 합니다.

## <a name="coleserveritemondrawex"></a><a name="ondrawex"></a>콜레 서버 항목::온드로우엑스

모든 도면에 대한 프레임워크에서 호출됩니다.

```
virtual BOOL OnDrawEx(
    CDC* pDC,
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
항목을 그릴 [CDC](../../mfc/reference/cdc-class.md) 개체에 대한 포인터입니다. DC는 특성 DC에 자동으로 연결되므로 특성 함수를 호출할 수 있지만 이렇게 하면 메타파일 장치가 특정하게 됩니다.

*nDrawAspect*<br/>
DVASPECT 열거형의 값입니다. 이 매개 변수는 다음 값 중 일부를 가질 수 있습니다.

- DVASPECT_CONTENT 항목은 컨테이너 내부에 포함된 개체로 표시될 수 있는 방식으로 표시됩니다.

- DVASPECT_THUMBNAIL 항목은 검색 도구에 표시될 수 있도록 "썸네일" 표현으로 렌더링됩니다.

- DVASPECT_ICON 항목은 아이콘으로 표시됩니다.

- DVASPECT_DOCPRINT 항목은 파일 메뉴에서 인쇄 명령을 사용하여 인쇄된 것처럼 표시됩니다.

*rSize*<br/>
HIMETRIC 단위의 항목 크기입니다.

### <a name="return-value"></a>Return Value

항목이 성공적으로 그려진 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

DVASPECT가 `OnDraw` DVASPECT_CONTENT 같을 때 기본 구현이 호출됩니다. 그렇지 않으면 실패합니다.

이 함수를 재정의하여 DVASPECT_ICON 또는 DVASPECT_THUMBNAIL 같은 DVASPECT_CONTENT 이외의 측면에 대한 프레젠테이션 데이터를 제공합니다.

## <a name="coleserveritemongetclipboarddata"></a><a name="ongetclipboarddata"></a>콜레서버아이템::온겟클립보드데이터

[CopyToClipboard](#copytoclipboard) 멤버 함수를 호출하여 클립보드에 배치 되는 모든 데이터를 포함하는 `COleDataSource` 개체를 가져오기 위해 프레임 워크에서 호출됩니다.

```
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,
    LPPOINT lpOffset,
    LPSIZE lpSize);
```

### <a name="parameters"></a>매개 변수

*bIncludeLink*<br/>
링크 데이터를 클립보드에 복사해야 하는 경우 TRUE로 설정합니다. 서버 응용 프로그램이 링크를 지원하지 않는 경우 FALSE로 설정합니다.

*lpOffset*<br/>
개체의 원점에서 픽셀 단위로 마우스 커서의 간격띄우기입니다.

*lpSize*<br/>
개체의 크기(픽셀)입니다.

### <a name="return-value"></a>Return Value

클립보드 데이터가 포함된 [COleDataSource](../../mfc/reference/coledatasource-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 [GetClipboardData](#getclipboarddata)를 호출합니다.

## <a name="coleserveritemongetextent"></a><a name="ongetextent"></a>콜서버항목::온겟익

올레 항목의 HIMETRIC 단위로 크기를 검색하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>매개 변수

*nDrawAspect*<br/>
경계를 검색할 OLE 항목의 측면을 지정합니다. 이 매개 변수는 다음 값 중 일부를 가질 수 있습니다.

- DVASPECT_CONTENT 항목은 컨테이너 내부에 포함된 개체로 표시될 수 있는 방식으로 표시됩니다.

- DVASPECT_THUMBNAIL 항목은 검색 도구에 표시될 수 있도록 "썸네일" 표현으로 렌더링됩니다.

- DVASPECT_ICON 항목은 아이콘으로 표시됩니다.

- DVASPECT_DOCPRINT 항목은 파일 메뉴에서 인쇄 명령을 사용하여 인쇄된 것처럼 표시됩니다.

*rSize*<br/>
OLE 항목의 크기를 수신하는 `CSize` 개체를 참조합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

컨테이너 응용 프로그램이 Microsoft Foundation 클래스 라이브러리를 사용 하 여 작성 된 경우 `COleClientItem` 이 함수는 해당 개체의 [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) 멤버 함수를 호출할 때 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다. 직접 구현해야 합니다. OLE 항목의 크기에 대한 요청을 처리할 때 특수 처리를 수행하려는 경우 이 함수를 재정의합니다.

## <a name="coleserveritemonhide"></a><a name="onhide"></a>콜서버아이템::온하이드

올레 항목을 숨기려면 프레임워크에서 호출합니다.

```
virtual void OnHide();
```

### <a name="remarks"></a>설명

기본 호출은 을 호출합니다. `COleServerDoc::OnShowDocument( FALSE )` 또한 이 함수는 OLE 항목이 숨겨져 있음을 컨테이너에 통보합니다. OLE 항목을 숨길 때 특수 처리를 수행하려는 경우 이 함수를 재정의합니다.

## <a name="coleserveritemoninitfromdata"></a><a name="oninitfromdata"></a>COleServer항목::OnInitFromData

*pDataObject의*내용을 사용 하 여 OLE 항목을 초기화 하는 프레임 워크에서 호출 합니다.

```
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,
    BOOL bCreation);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
OLE 항목을 초기화하기 위한 다양한 형식의 데이터를 포함하는 OLE 데이터 개체에 대한 포인터입니다.

*bCreation*<br/>
TRUE 함수가 컨테이너 응용 프로그램에서 새로 생성되는 OLE 항목을 초기화하는 데 호출되는 경우 FALSE 함수가 이미 기존 OLE 항목의 내용을 대체하기 위해 호출되는 경우.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

*bCreation이* TRUE이면 컨테이너가 현재 선택을 기반으로 새 개체 삽입을 구현하는 경우 이 함수가 호출됩니다. 선택한 데이터는 새 OLE 항목을 만들 때 사용됩니다. 예를 들어 스프레드시트 프로그램에서 셀 범위를 선택한 다음 새 개체 삽입을 사용하여 선택한 범위의 값을 기반으로 차트를 만들 수 있습니다. 기본 구현은 아무 작업도 수행하지 않습니다. 이 함수를 재정의하여 *pDataObject에서* 제공하는 형식에서 허용 가능한 형식을 선택하고 제공된 데이터를 기반으로 OLE 항목을 초기화합니다. 이 고급 재정의 할 수 있습니다.

자세한 내용은 [IOleObject::InitFromData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) Windows SDK를 참조하십시오.

## <a name="coleserveritemonopen"></a><a name="onopen"></a>콜서버항목::온오픈

프레임워크에서 호출하여 OLE 항목을 서버 응용 프로그램의 별도의 인스턴스에 표시하지 않고 배치합니다.

```
virtual void OnOpen();
```

### <a name="remarks"></a>설명

기본 구현은 OLE 항목을 포함하는 문서를 표시하는 첫 번째 프레임 창을 활성화합니다. 응용 프로그램이 미니 서버인 경우 기본 구현에 기본 창이 표시됩니다. 또한 이 함수는 OLE 항목이 열려 있음을 컨테이너에 통보합니다.

OLE 항목을 열 때 특수 처리를 수행하려는 경우 이 함수를 재정의합니다. 이 항목은 열 때 선택 영역을 링크로 설정하려는 링크된 항목에서 특히 일반적입니다.

자세한 내용은 [IOleClientSite::OnShowWindow](/windows/win32/api/oleidl/nf-oleidl-ioleclientsite-onshowwindow) Windows SDK를 참조하십시오.

## <a name="coleserveritemonqueryupdateitems"></a><a name="onqueryupdateitems"></a>COleServer항목::온쿼리 업데이트항목

현재 서버 문서의 연결된 항목이 최신 상태인지 여부를 확인하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnQueryUpdateItems();
```

### <a name="return-value"></a>Return Value

문서에 업데이트가 필요한 항목이 있는 경우 0이 아닙니다. 모든 항목이 최신 상태인 경우 0입니다.

### <a name="remarks"></a>설명

원본 문서가 변경되었지만 문서의 변경 내용을 반영하도록 연결된 항목이 업데이트되지 않은 경우 항목이 최신 상태로 지정되지 않았습니다.

## <a name="coleserveritemonrenderdata"></a><a name="onrenderdata"></a>콜레서버항목::온렌더데이터

지정된 형식으로 데이터를 검색하는 프레임워크에서 호출됩니다.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
정보가 요청되는 형식을 지정하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다.

*lpStgMedium*<br/>
데이터를 반환할 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정된 형식은 지연 렌더링을 `COleDataSource` 위해 [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) 또는 [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) 멤버 함수를 사용하여 이전에 개체에 배치된 형식입니다. 이 함수의 기본 구현은 제공된 저장소 매체가 파일 또는 메모리인 경우 [OnRenderFileData](#onrenderfiledata) 또는 [OnRenderGlobalData를](#onrenderglobaldata)각각 호출합니다. 이러한 형식이 제공되지 않으면 기본 구현은 0을 반환하고 아무 것도 수행하지 않습니다.

*lpStgMedium*-> *타이메드가* TYMED_NULL 경우 STGMEDIUM는 *lpFormatEtc->로*지정된 대로 할당되고 채워야 합니다. TYMED_NULL 않으면 STGMEDIUM가 데이터로 채워져야 합니다.

이 고급 재정의 할 수 있습니다. 이 함수를 재정의하여 요청된 형식 및 매체로 데이터를 제공합니다. 데이터에 따라 이 함수의 다른 버전 중 하나를 대신 재정의할 수 있습니다. 데이터가 작고 크기가 고정된 경우 `OnRenderGlobalData`재정의합니다. 데이터가 파일에 있거나 크기가 가변인 경우 재정의합니다. `OnRenderFileData`

자세한 내용은 [IDataObject:GetData,](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)및 Windows SDK에서 [TYMED를](/windows/win32/api/objidl/ne-objidl-tymed) 참조하십시오.

## <a name="coleserveritemonrenderfiledata"></a><a name="onrenderfiledata"></a>COleServer항목::온렌더파일데이터

저장소 매체가 파일일 때 지정된 형식으로 데이터를 검색하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
정보가 요청되는 형식을 지정하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다.

*pFile*<br/>
데이터를 렌더링할 `CFile` 오브젝트를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정된 형식은 지연된 렌더링을 `COleDataSource` 위해 [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) 멤버 함수를 사용하여 개체에 이전에 배치된 형식입니다. 이 함수의 기본 구현은 단순히 FALSE를 반환합니다.

이 고급 재정의 할 수 있습니다. 이 함수를 재정의하여 요청된 형식 및 매체로 데이터를 제공합니다. 데이터에 따라 이 함수의 다른 버전 중 하나를 대신 재정의할 수 있습니다. 여러 저장소 매체를 처리하려면 [OnRenderData](#onrenderdata)를 재정의합니다. 데이터가 파일에 있거나 가변 크기인 경우 [OnRenderFileData](#onrenderfiledata)를 재정의합니다.

자세한 내용은 Windows SDK에서 [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) 및 [FORMATETC를](/windows/win32/api/objidl/ns-objidl-formatetc) 참조하십시오.

## <a name="coleserveritemonrenderglobaldata"></a><a name="onrenderglobaldata"></a>콜레서버항목:온렌더글로벌데이터

지정된 저장소 매체가 전역 메모리인 경우 지정된 형식으로 데이터를 검색하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
정보가 요청되는 형식을 지정하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다.

*phGlobal*<br/>
데이터를 반환할 전역 메모리에 대한 핸들을 가리킵니다. 메모리가 할당되지 않은 경우 이 매개 변수는 NULL이 될 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정된 형식은 지연된 렌더링을 `COleDataSource` 위해 [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) 멤버 함수를 사용하여 개체에 이전에 배치된 형식입니다. 이 함수의 기본 구현은 단순히 FALSE를 반환합니다.

*phGlobal이* NULL이면 새 HGLOBAL을 할당하고 *phGlobal로*반환해야 합니다. 그렇지 않으면 phGlobal에서 지정한 *HGLOBAL은* 데이터로 채워야 합니다. HGLOBAL에 배치된 데이터 양은 메모리 블록의 현재 크기를 초과해서는 안 됩니다. 또한 블록을 더 큰 크기로 다시 할당할 수 없습니다.

이 고급 재정의 할 수 있습니다. 이 함수를 재정의하여 요청된 형식 및 매체로 데이터를 제공합니다. 데이터에 따라 이 함수의 다른 버전 중 하나를 대신 재정의할 수 있습니다. 여러 저장소 매체를 처리하려면 [OnRenderData](#onrenderdata)를 재정의합니다. 데이터가 파일에 있거나 가변 크기인 경우 [OnRenderFileData](#onrenderfiledata)를 재정의합니다.

자세한 내용은 Windows SDK에서 [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) 및 [FORMATETC를](/windows/win32/api/objidl/ns-objidl-formatetc) 참조하십시오.

## <a name="coleserveritemonsetcolorscheme"></a><a name="onsetcolorscheme"></a>콜레 서버 항목::온셋컬러스킴

프레임워크에서 호출하여 OLE 항목을 편집할 때 사용할 색상 팔레트를 지정합니다.

```
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```

### <a name="parameters"></a>매개 변수

*lpLogPalette*<br/>
Windows [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

색상 팔레트를 사용하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

Microsoft Foundation 클래스 라이브러리를 사용하여 컨테이너 응용 프로그램을 작성한 경우 해당 `COleClientItem` 개체의 [IOleObject:SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) 함수가 호출될 때 이 함수가 호출됩니다. 기본 구현은 FALSE를 반환합니다. 권장 팔레트를 사용하려는 경우 이 함수를 재정의합니다. 제안된 팔레트를 사용할 필요는 없습니다.

자세한 내용은 [IOleObject::SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) Windows SDK를 참조하십시오.

## <a name="coleserveritemonsetdata"></a><a name="onsetdata"></a>콜레서버항목::온셋데이터

OLE 항목의 데이터를 지정된 데이터로 바꾸기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
데이터의 형식을 지정하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조에 대한 포인터입니다.

*lpStgMedium*<br/>
데이터가 상주하는 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조에 대한 포인터입니다.

*bRelease*<br/>
함수 호출을 완료한 후 저장소 매체의 소유권이 있는 사람을 나타냅니다. 호출자는 저장소 매체를 대신하여 할당된 리소스를 해제할 책임이 있는 사람을 결정합니다. 호출자는 *bRelease*를 설정하여 이 작업을 수행합니다. *bRelease가* 0이 아닌 경우 서버 항목은 소유권을 가지며, 서버 항목은 사용이 완료되면 미디어를 해제합니다. *bRelease가* 0이면 호출자는 소유권을 유지하고 서버 항목은 호출 기간 동안에만 저장소 매체를 사용할 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

서버 항목은 데이터의 소유권을 성공적으로 얻을 때까지 가져오지 않습니다. 즉, 0을 반환하는 경우 소유권을 받지 않습니다. 데이터 원본이 소유권을 가지면 [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) 함수를 호출하여 저장소 매체를 해제합니다.

기본 구현은 아무 작업도 수행하지 않습니다. 이 함수를 재정의하여 OLE 항목의 데이터를 지정된 데이터로 바꿉습니다. 이 고급 재정의 할 수 있습니다.

자세한 내용은 Windows SDK의 [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)및 [ReleaseStgMedium를](/windows/win32/api/ole2/nf-ole2-releasestgmedium) 참조하십시오.

## <a name="coleserveritemonsetextent"></a><a name="onsetextent"></a>콜서버항목::온셋익

프레임워크에서 호출하여 컨테이너 문서에서 사용할 수 있는 공간의 양을 OLE 항목에 알려줍니다.

```
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,
    const CSize& size);
```

### <a name="parameters"></a>매개 변수

*nDrawAspect*<br/>
경계가 지정된 OLE 항목의 측면을 지정합니다. 이 매개 변수는 다음 값 중 일부를 가질 수 있습니다.

- DVASPECT_CONTENT 항목은 컨테이너 내부에 포함된 개체로 표시될 수 있는 방식으로 표시됩니다.

- DVASPECT_THUMBNAIL 항목은 검색 도구에 표시될 수 있도록 "썸네일" 표현으로 렌더링됩니다.

- DVASPECT_ICON 항목은 아이콘으로 표시됩니다.

- DVASPECT_DOCPRINT 항목은 파일 메뉴에서 인쇄 명령을 사용하여 인쇄된 것처럼 표시됩니다.

*size*<br/>
OLE 항목의 새 크기를 지정하는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 구조입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

컨테이너 응용 프로그램이 Microsoft Foundation 클래스 라이브러리로 작성된 경우 해당 `COleClientItem` 개체의 [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) 멤버 함수가 호출될 때 이 함수가 호출됩니다. 기본 구현은 *nDrawAspect가* DVASPECT_CONTENT 경우 [m_sizeExtent](#m_sizeextent) 멤버를 지정된 크기로 설정합니다. 그렇지 않으면 0을 반환합니다. 항목 크기를 변경할 때 특수 처리를 수행하려면 이 함수를 재정의합니다.

## <a name="coleserveritemonshow"></a><a name="onshow"></a>콜서버항목::온쇼

서버 응용 프로그램에 OLE 항목을 표시하도록 지시하기 위해 프레임워크에서 호출됩니다.

```
virtual void OnShow();
```

### <a name="remarks"></a>설명

이 함수는 일반적으로 컨테이너 응용 프로그램의 사용자가 항목을 만들거나 항목을 표시해야 하는 편집과 같은 동사를 실행할 때 호출됩니다. 기본 구현은 내부 활성화를 시도합니다. 이 작업이 실패하면 함수는 멤버 함수를 `OnOpen` 호출하여 OLE 항목을 별도의 창에 표시합니다.

OLE 항목이 표시될 때 특수 처리를 수행하려는 경우 이 함수를 재정의합니다.

## <a name="coleserveritemonupdate"></a><a name="onupdate"></a>콜레 서버 항목::에 업데이트

항목이 수정되었을 때 프레임워크에서 호출합니다.

```
virtual void OnUpdate(
    COleServerItem* pSender,
    LPARAM lHint,
    CObject* pHint,
    DVASPECT nDrawAspect);
```

### <a name="parameters"></a>매개 변수

*pSender*<br/>
문서를 수정한 항목에 대한 포인터입니다. NULL일 수 있습니다.

*lHint*<br/>
수정에 대한 정보가 들어 있습니다.

*pHint*<br/>
수정에 대한 정보를 저장하는 개체에 대한 포인터입니다.

*nDrawAspect*<br/>
DVASPECT 열거형의 값입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.

- DVASPECT_CONTENT 항목은 컨테이너 내부에 포함된 개체로 표시될 수 있는 방식으로 표시됩니다.

- DVASPECT_THUMBNAIL 항목은 검색 도구에 표시될 수 있도록 "썸네일" 표현으로 렌더링됩니다.

- DVASPECT_ICON 항목은 아이콘으로 표시됩니다.

- DVASPECT_DOCPRINT 항목은 파일 메뉴에서 인쇄 명령을 사용하여 인쇄된 것처럼 표시됩니다.

### <a name="remarks"></a>설명

기본 구현호출 [NotifyChanged](#notifychanged), 힌트 또는 보낸 사람의 여부에 관계 없이.

## <a name="coleserveritemonupdateitems"></a><a name="onupdateitems"></a>COleServer항목::업데이트 항목

서버 문서의 모든 항목을 업데이트하려면 프레임워크에서 호출합니다.

```
virtual void OnUpdateItems();
```

### <a name="remarks"></a>설명

기본 구현에서는 문서의 `COleClientItem` 모든 개체에 대해 [UpdateLink를](../../mfc/reference/coleclientitem-class.md#updatelink) 호출합니다.

## <a name="coleserveritemsetitemname"></a><a name="setitemname"></a>콜레서버항목::세트항목이름

연결된 항목을 만들 때 이 함수를 호출하여 이름을 설정합니다.

```cpp
void SetItemName(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>매개 변수

*lpszItemName*<br/>
항목의 새 이름에 대한 포인터입니다.

### <a name="remarks"></a>설명

이름은 문서 내에서 고유해야 합니다. 연결된 항목을 편집하기 위해 서버 응용 프로그램이 호출되면 응용 프로그램은 이 이름을 사용하여 항목을 찾습니다. 포함된 항목에 대해 이 함수를 호출할 필요가 없습니다.

## <a name="see-also"></a>참조

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CDocItem 클래스](../../mfc/reference/cdocitem-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COle클라이언트항목 클래스](../../mfc/reference/coleclientitem-class.md)<br/>
[콜레서버독 클래스](../../mfc/reference/coleserverdoc-class.md)<br/>
[COle템플릿서버 클래스](../../mfc/reference/coletemplateserver-class.md)
