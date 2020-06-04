---
title: CDocObjectServer항목 클래스
ms.date: 03/27/2019
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnDoVerb
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnDoVerb
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
ms.openlocfilehash: 1f0f5cf93aab35a17f7174b2beee0d1398564a3d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375535"
---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServer항목 클래스

DocObject 서버 전용 OLE 서버 동사를 구현합니다.

## <a name="syntax"></a>구문

```
class CDocObjectServerItem : public COleServerItem
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CDocObjectServer항목::CDocObjectServer항목](#cdocobjectserveritem)|`CDocObjectServerItem` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDocObject서버항목::GetDocument](#getdocument)|항목이 포함된 문서에 대한 포인터를 검색합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CDocObject서버항목::온도버브](#ondoverb)|동사를 실행 하기 위해 호출 됩니다.|
|[CDocObject서버항목::온하이드](#onhide)|프레임워크에서 DocObject 항목을 숨기려고 하면 예외를 throw합니다.|
|[CDocObject서버항목::온쇼](#onshow)|DocObject 항목을 현재 활성화하도록 프레임워크에서 호출합니다. 항목이 DocObject가 아닌 경우 [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)를 호출합니다.|

## <a name="remarks"></a>설명

`CDocObjectServerItem`재정의 가능한 멤버 함수를 정의합니다: [OnHide,](#onhide) [OnDoVerb](#ondoverb)및 [OnShow](#onshow).

을 `CDocObjectServerItem`사용하려면 `COleServerDoc`-derive된 클래스에서 [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) 재정의가 새 `CDocObjectServerItem` 개체를 반환합니다. 항목의 기능을 변경해야 하는 경우 사용자 고유의 `CDocObjectServerItem`파생 클래스의 새 인스턴스를 만들 수 있습니다.

DocObjects에 대한 자세한 내용은 *MFC 참조의* [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) 및 [COleCmdUI를](../../mfc/reference/colecmdui-class.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleServerItem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>요구 사항

**헤더:** afxdocob.h

## <a name="cdocobjectserveritemcdocobjectserveritem"></a><a name="cdocobjectserveritem"></a>CDocObjectServer항목::CDocObjectServer항목

`CDocObjectServerItem` 개체를 생성합니다.

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>매개 변수

*pServerDoc*<br/>
새 DocObject 항목을 포함 하는 문서에 대 한 포인터입니다.

*bAutoDelete*<br/>
개체에 대한 링크가 해제될 때 개체를 삭제할 수 있는지 여부를 나타냅니다. `CDocObjectServerItem` 개체가 문서 데이터의 필수적인 일부인 경우 인수를 FALSE로 설정합니다. 개체가 프레임워크에서 삭제할 수 있는 문서 데이터의 범위를 식별하는 데 사용되는 보조 구조인 경우 TRUE로 설정합니다.

## <a name="cdocobjectserveritemgetdocument"></a><a name="getdocument"></a>CDocObject서버항목::GetDocument

항목이 포함된 문서에 대한 포인터를 검색합니다.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Return Value

항목이 포함된 문서에 대한 포인터입니다. 항목이 문서의 일부가 아닌 경우 NULL입니다.

### <a name="remarks"></a>설명

이렇게 하면 [CDocObjectServerItem](#cdocobjectserveritem) 생성자에 인수로 전달한 서버 문서에 액세스할 수 있습니다.

## <a name="cdocobjectserveritemondoverb"></a><a name="ondoverb"></a>CDocObject서버항목::온도버브

지정된 동사를 실행 하기 위해 프레임 워크에 의해 호출 됩니다.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
실행할 동사를 지정합니다. 가능한 값은 Windows SDK에서 [IOleObject::Doverb를](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) 참조하십시오.

### <a name="remarks"></a>설명

기본 구현은 항목이 DocObject이고 OLEIVERB_INPLACEACTIVATE 또는 OLEIVERB_SHOW 지정된 경우 [OnShow](#onshow) 멤버 함수를 호출합니다. 항목이 DocObject가 아니거나 다른 동사가 지정되면 기본 구현에서 [COleServerItem::OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb)를 호출합니다.

## <a name="cdocobjectserveritemonhide"></a><a name="onhide"></a>CDocObject서버항목::온하이드

항목을 숨기기 위해 프레임워크에서 호출합니다.

```
virtual void OnHide();
```

### <a name="remarks"></a>설명

항목이 DocObject인 경우 기본 구현에서 예외를 throw합니다. 전체 보기를 사용하므로 활성 DocObject 항목을 숨길 수 없습니다. DocObject 항목을 비활성화하여 사라지게 해야 합니다. 항목이 DocObject가 아닌 경우 기본 구현에서 [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide)를 호출합니다.

## <a name="cdocobjectserveritemonshow"></a><a name="onshow"></a>CDocObject서버항목::온쇼

서버 응용 프로그램에 DocObject 항목을 활성화하도록 지시하기 위해 프레임워크에서 호출됩니다.

```
virtual void OnShow();
```

### <a name="remarks"></a>설명

항목이 DocObject가 아닌 경우 기본 구현에서 [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen)를 호출합니다. DocObject 항목을 열 때 특수 처리를 수행하려는 경우 이 함수를 재정의합니다.

## <a name="see-also"></a>참고 항목

[콜레서버아이템 클래스](../../mfc/reference/coleserveritem-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServer 클래스](../../mfc/reference/cdocobjectserver-class.md)<br/>
[콜레독오브젝트아이템 클래스](../../mfc/reference/coledocobjectitem-class.md)
