---
title: 리치에이트닥 클래스
ms.date: 11/04/2016
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
ms.openlocfilehash: 587cf65543e24e586fb8b2336481d6e841473134
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368268"
---
# <a name="cricheditdoc-class"></a>리치에이트닥 클래스

[CRichEditView](../../mfc/reference/cricheditview-class.md) 및 [CRichEditCntrItem을](../../mfc/reference/cricheditcntritem-class.md)사용하면 MFC의 문서 보기 아키텍처의 컨텍스트 내에서 풍부한 편집 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRichEditDoc::Create클라이언트항목](#createclientitem)|문서 정리를 수행하도록 호출됩니다.|
|[CRichEditDoc::GetStream 형식](#getstreamformat)|스트림 입력 및 출력에 서식 정보가 포함되어야 하는지 여부를 나타냅니다.|
|[CrichEditDoc::GetView](#getview)|연관된 [CRichEditView](../../mfc/reference/cricheditview-class.md) 개체를 검색합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CRichEditDoc::m_bRTF](#m_brtf)|스트림 I/O에 서식을 포함해야 하는지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

"풍부한 편집 컨트롤"은 사용자가 텍스트를 입력하고 편집할 수 있는 창입니다. 텍스트에 문자 및 단락 서식을 할당할 수 있으며 포함된 OLE 개체를 포함할 수 있습니다. 풍부한 편집 컨트롤은 텍스트 서식을 지정하기 위한 프로그래밍 인터페이스를 제공합니다. 그러나 응용 프로그램은 사용자가 서식 지정 작업을 사용할 수 있도록 하는 데 필요한 모든 사용자 인터페이스 구성 요소를 구현 해야 합니다.

`CRichEditView`은 텍스트의 텍스트 및 서식 특성을 유지합니다. `CRichEditDoc`은 뷰에 있는 클라이언트 항목 목록을 유지 관리합니다. `CRichEditCntrItem`은 OLE 클라이언트 항목에 대한 컨테이너 측 액세스를 제공합니다.

이 Windows 공통 제어(따라서 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스)는 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

MFC 응용 프로그램에서 리치 편집 문서를 사용하는 예는 [WORDPAD](../../overview/visual-cpp-samples.md) 샘플 응용 프로그램을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>요구 사항

**헤더:** afxrich.h

## <a name="cricheditdoccreateclientitem"></a><a name="createclientitem"></a>CRichEditDoc::Create클라이언트항목

이 함수를 호출하여 개체를 `CRichEditCntrItem` 만들고 이 문서에 추가합니다.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>매개 변수

*프레오*<br/>
OLE 항목을 설명하는 [REOBJECT](/windows/win32/api/richole/ns-richole-reobject) 구조에 대한 포인터입니다. 새 `CRichEditCntrItem` 개체는 이 OLE 항목 주위에 생성됩니다. *preo가* NULL이면 새 클라이언트 항목이 비어 있습니다.

### <a name="return-value"></a>Return Value

이 문서에 추가된 새 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 OLE 초기화를 수행하지 않습니다.

자세한 내용은 Windows SDK의 [REOBJECT](/windows/win32/api/richole/ns-richole-reobject) 구조를 참조하십시오.

## <a name="cricheditdocgetstreamformat"></a><a name="getstreamformat"></a>CRichEditDoc::GetStream 형식

이 함수를 호출하여 리치 편집의 내용을 스트리밍하기 위한 텍스트 형식을 결정합니다.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>Return Value

다음 플래그 중 하나:

- SF_TEXT 풍부한 편집 컨트롤이 서식 정보를 유지 관리하지 않음을 나타냅니다.

- SF_RTF 풍부한 편집 컨트롤이 서식 정보를 유지 관리한다는 것을 나타냅니다.

### <a name="remarks"></a>설명

반환 값은 [m_bRTF](#m_brtf) 데이터 멤버를 기반으로 합니다. 이 함수는 `m_bRTF` true인 경우 SF_RTF 반환합니다. 그렇지 않으면, SF_TEXT.

## <a name="cricheditdocgetview"></a><a name="getview"></a>CrichEditDoc::GetView

이 함수를 호출하여 이 `CRichEditDoc` 개체와 연결된 [CRichEditView](../../mfc/reference/cricheditview-class.md) 개체에 액세스합니다.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>Return Value

문서와 `CRichEditView` 연결된 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

텍스트 및 서식 정보는 `CRichEditView` 개체 내에 포함됩니다. 개체는 `CRichEditDoc` 직렬화를 위해 OLE 항목을 유지 관리합니다. 각 `CRichEditDoc`에 대해 `CRichEditView` 하나만 있어야 합니다.

## <a name="cricheditdocm_brtf"></a><a name="m_brtf"></a>CRichEditDoc::m_bRTF

TRUE이면 [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) 및 [CRichEditCtrl:StreamOut은](../../mfc/reference/cricheditctrl-class.md#streamout) 단락 및 문자 서식 특성을 저장해야 한다는 것을 나타냅니다.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>참고 항목

[MFC 샘플 워드패드](../../overview/visual-cpp-samples.md)<br/>
[콜레서버독 클래스](../../mfc/reference/coleserverdoc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[리치에이트뷰 클래스](../../mfc/reference/cricheditview-class.md)<br/>
[리치에이트Cntr항목 클래스](../../mfc/reference/cricheditcntritem-class.md)<br/>
[콜레문서 클래스](../../mfc/reference/coledocument-class.md)<br/>
[리치에이트Ctrl 클래스](../../mfc/reference/cricheditctrl-class.md)
