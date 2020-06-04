---
title: 리치에이트Cntr항목 클래스
ms.date: 11/04/2016
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
ms.openlocfilehash: 7b566fe7f1c0667dbcdb4976f79cd2e1597f48f6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752763"
---
# <a name="cricheditcntritem-class"></a>리치에이트Cntr항목 클래스

[CRichEditView](../../mfc/reference/cricheditview-class.md) 및 [CRichEditDoc에서는](../../mfc/reference/cricheditdoc-class.md)MFC의 문서 보기 아키텍처의 컨텍스트 내에서 풍부한 편집 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CRichEditCntr항목::CRichEditCntr항목](#cricheditcntritem)|`CRichEditCntrItem` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CrichEditCntr항목::동기화토리치편집개체](#synctoricheditobject)|항목을 다른 유형으로 활성화합니다.|

## <a name="remarks"></a>설명

"풍부한 편집 컨트롤"은 사용자가 텍스트를 입력하고 편집할 수 있는 창입니다. 텍스트에 문자 및 단락 서식을 할당할 수 있으며 포함된 OLE 개체를 포함할 수 있습니다. 풍부한 편집 컨트롤은 텍스트 서식을 지정하기 위한 프로그래밍 인터페이스를 제공합니다. 그러나 응용 프로그램은 사용자가 서식 지정 작업을 사용할 수 있도록 하는 데 필요한 모든 사용자 인터페이스 구성 요소를 구현 해야 합니다.

`CRichEditView`은 텍스트의 텍스트 및 서식 특성을 유지합니다. `CRichEditDoc`은 보기에 있는 OLE 클라이언트 항목 의 목록을 유지 관리합니다. `CRichEditCntrItem`은 OLE 클라이언트 항목에 대한 컨테이너 측 액세스를 제공합니다.

이 Windows 공통 제어(따라서 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스)는 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

MFC 응용 프로그램에서 리치 편집 컨테이너 항목을 사용하는 예는 [WORDPAD](../../overview/visual-cpp-samples.md) 샘플 응용 프로그램을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>요구 사항

**헤더:** afxrich.h

## <a name="cricheditcntritemcricheditcntritem"></a><a name="cricheditcntritem"></a>CRichEditCntr항목::CRichEditCntr항목

이 함수를 호출하여 개체를 `CRichEditCntrItem` 만들고 컨테이너 문서에 추가합니다.

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>매개 변수

*프레오*<br/>
OLE 항목을 설명하는 [REOBJECT](/windows/win32/api/richole/ns-richole-reobject) 구조에 대한 포인터입니다. 새 `CRichEditCntrItem` 개체는 이 OLE 항목 주위에 생성됩니다. *preo가* NULL이면 클라이언트 항목이 비어 있습니다.

*pContainer*<br/>
이 항목을 포함 할 컨테이너 문서에 대한 포인터입니다. *pContainer가* NULL인 경우 [COleDocument::AddItem을](../../mfc/reference/coledocument-class.md#additem) 명시적으로 호출하여 이 클라이언트 항목을 문서에 추가해야 합니다.

### <a name="remarks"></a>설명

이 함수는 OLE 초기화를 수행하지 않습니다.

자세한 내용은 Windows SDK의 [REOBJECT](/windows/win32/api/richole/ns-richole-reobject) 구조를 참조하십시오.

## <a name="cricheditcntritemsynctoricheditobject"></a><a name="synctoricheditobject"></a>CrichEditCntr항목::동기화토리치편집개체

이 함수를 호출하여 장치 측면 인 [DVASPECT를](/windows/win32/api/wtypes/ne-wtypes-dvaspect) `CRichEditCntrltem` *reo가*지정한 것과 동기화합니다.

```cpp
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>매개 변수

*Reo*<br/>
OLE 항목을 설명하는 [REOBJECT](/windows/win32/api/richole/ns-richole-reobject) 구조를 참조합니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [DVASPECT를](/windows/win32/api/wtypes/ne-wtypes-dvaspect) 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 워드패드](../../overview/visual-cpp-samples.md)<br/>
[COle클라이언트항목 클래스](../../mfc/reference/coleclientitem-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[리치에이트닥 클래스](../../mfc/reference/cricheditdoc-class.md)<br/>
[리치에이트뷰 클래스](../../mfc/reference/cricheditview-class.md)
