---
title: CDocObjectServer 클래스
ms.date: 09/12/2018
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
helpviewer_keywords:
- CDocObjectServer [MFC], CDocObjectServer
- CDocObjectServer [MFC], ActivateDocObject
- CDocObjectServer [MFC], OnActivateView
- CDocObjectServer [MFC], OnApplyViewState
- CDocObjectServer [MFC], OnSaveViewState
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
ms.openlocfilehash: f415df35b13e50eee092f87eca0627e5cf143720
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753288"
---
# <a name="cdocobjectserver-class"></a>CDocObjectServer 클래스

일반 `COleDocument` 서버를 전체 DocObject 서버로 만드는 데 필요한 추가 OLE 인터페이스( `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`, 및 `IPrint`)를 구현합니다.

## <a name="syntax"></a>구문

```
class CDocObjectServer : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|`CDocObjectServer` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDocObjectServer::활성화DocObject](#activatedocobject)|문서 개체 서버를 활성화하지만 표시되지는 않습니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CDocObjectServer::온인스로이스뷰](#onactivateview)|DocObject 보기를 표시합니다.|
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|DocObject 보기의 상태를 복원합니다.|
|[CDocObjectServer::온세이브뷰스테이트](#onsaveviewstate)|DocObject 보기의 상태를 저장합니다.|

## <a name="remarks"></a>설명

`CDocObjectServer`에서 파생 `CCmdTarget` 되고 `COleServerDoc` 인터페이스를 노출 하기 위해 밀접 하 게 작동 합니다.

DocObject 서버 문서에는 DocObject 항목에 대한 서버 인터페이스를 나타내는 [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) 개체가 포함될 수 있습니다.

DocObject 서버를 사용자 지정하려면 뷰 `CDocObjectServer` 설정 기능, [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate)및 [OnSaveViewState](#onsaveviewstate)에서 고유한 클래스를 파생하고 재정의합니다. 프레임워크 호출에 대한 응답으로 클래스의 새 인스턴스를 제공해야 합니다.

DocObjects에 대한 자세한 내용은 *MFC 참조의* [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) 및 [COleCmdUI를](../../mfc/reference/colecmdui-class.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocObjectServer`

## <a name="requirements"></a>요구 사항

**헤더:** afxdocob.h

## <a name="cdocobjectserveractivatedocobject"></a><a name="activatedocobject"></a>CDocObjectServer::활성화DocObject

이 함수를 호출하여 문서 개체 서버를 활성화(표시되지는 않음)합니다.

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>설명

`ActivateDocObject`의 `IOleDocumentSite` `ActivateMe` 메서드를 호출하지만 [CDocObjectServer::OnActivateView에](#onactivateview)대한 호출에서 제공된 뷰를 설정하고 표시하는 방법에 대한 특정 지침을 기다리기 때문에 뷰가 표시되지 않습니다.

함께 `ActivateDocObject` 활성화하고 `OnActivateView` DocObject 보기를 표시합니다. DocObject 활성화는 다른 종류의 OLE 내부 활성화와 다릅니다. DocObject 활성화는 내부 해치 테두리 및 개체 장식(예: 크기 조정 핸들)을 표시하고, 개체 범위 함수를 무시하고, 뷰 사각형 내에서 스크롤 막대를 그리는 것을 우회합니다(일반 내부 활성화와 같이).

## <a name="cdocobjectservercdocobjectserver"></a><a name="cdocobjectserver"></a>CDocObjectServer::CDocObjectServer

`CDocObjectServer` 개체를 생성하고 초기화합니다.

```
explicit CDocObjectServer(
    COleServerDoc* pOwner,
    LPOLEDOCUMENTSITE pDocSite = NULL);
```

### <a name="parameters"></a>매개 변수

*p 소유자*<br/>
DocObject 서버의 클라이언트인 클라이언트 사이트 문서에 대한 포인터입니다.

*pDocSite*<br/>
컨테이너에 의해 `IOleDocumentSite` 구현된 인터페이스에 대한 포인터입니다.

### <a name="remarks"></a>설명

DocObject가 활성화되어 있는 경우 클라이언트 `IOleDocumentSite`사이트 OLE 인터페이스()는 DocObject 서버가 해당 클라이언트(컨테이너)와 통신할 수 있도록 하는 것입니다. DocObject 서버가 활성화되면 먼저 컨테이너가 인터페이스를 `IOleDocumentSite` 구현하는지 확인합니다. 이 경우 [COleServerDoc::GetDocObjectServer는](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) 컨테이너가 DocObjects를 지원하는지 확인하기 위해 호출됩니다. 기본적으로 NULL을 `GetDocObjectServer` 반환합니다. 컨테이너에 대한 `COleServerDoc::GetDocObjectServer` 포인터와 `CDocObjectServer` 해당 `IOleDocumentSite` 인터페이스를 생성자의 인수로 사용하여 새 개체 또는 파생 된 개체를 생성하려면 재정의해야 합니다. `COleServerDoc`

## <a name="cdocobjectserveronactivateview"></a><a name="onactivateview"></a>CDocObjectServer::온인스로이스뷰

이 함수를 호출하여 DocObject 보기를 표시합니다.

```
virtual HRESULT OnActivateView();
```

### <a name="return-value"></a>Return Value

오류 또는 경고 값을 반환합니다. 기본적으로 성공하면 NOERROR를 반환합니다. 그렇지 않으면, E_FAIL.

### <a name="remarks"></a>설명

이 함수는 내부 프레임 창을 만들고, 뷰 내에서 스크롤 막대를 그리고, 서버가 컨테이너와 공유하는 메뉴를 설정하고, 프레임 컨트롤을 추가하고, 활성 개체를 설정한 다음, 마지막으로 내부 프레임 창을 표시하고 포커스를 설정합니다.

## <a name="cdocobjectserveronapplyviewstate"></a><a name="onapplyviewstate"></a>CDocObjectServer::OnApplyViewState

이 함수를 재정의하여 DocObject 뷰의 상태를 복원합니다.

```
virtual void OnApplyViewState(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
뷰 `CArchive` 상태를 직렬화할 개체입니다.

### <a name="remarks"></a>설명

이 함수는 뷰가 인스턴스화 후 처음으로 표시될 때 호출됩니다. `OnApplyViewState`View에서 이전에 `CArchive` [OnSaveViewState](#onsaveviewstate)로 저장된 개체의 데이터에 따라 자체 초기화하도록 지시합니다. 컨테이너가 `CArchive` 뷰 상태 데이터를 어떤 식으로든 해석하려고 시도하지 않기 때문에 뷰는 개체의 데이터의 유효성을 검사해야 합니다.

뷰의 `OnSaveViewState` 상태와 관련된 영구 정보를 저장하는 데 사용할 수 있습니다. 정보를 저장하기 `OnSaveViewState` 위해 재정의하는 경우 해당 `OnApplyViewState` 정보를 읽고 새로 활성화될 때 뷰에 적용하도록 재정의할 수 있습니다.

## <a name="cdocobjectserveronsaveviewstate"></a><a name="onsaveviewstate"></a>CDocObjectServer::온세이브뷰스테이트

이 함수를 재정의하여 DocObject 보기에 대한 추가 상태 정보를 저장합니다.

```
virtual void OnSaveViewState(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
뷰 `CArchive` 상태가 직렬화되는 개체입니다.

### <a name="remarks"></a>설명

상태에는 뷰 유형, 확대/축소 비율, 삽입 및 선택 점 등과 같은 속성이 포함될 수 있습니다. 컨테이너는 일반적으로 뷰를 비활성화하기 전에 이 함수를 호출합니다. 저장된 상태는 나중에 [OnApplyViewState](#onapplyviewstate)를 통해 복원할 수 있습니다.

뷰의 `OnSaveViewState` 상태와 관련된 영구 정보를 저장하는 데 사용할 수 있습니다. 정보를 저장하기 `OnSaveViewState` 위해 재정의하는 경우 해당 `OnApplyViewState` 정보를 읽고 새로 활성화될 때 뷰에 적용하도록 재정의할 수 있습니다.

## <a name="see-also"></a>참조

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServer항목 클래스](../../mfc/reference/cdocobjectserveritem-class.md)
