---
title: 코올링싱독 클래스
ms.date: 11/04/2016
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
ms.openlocfilehash: 1fad986b7e7304075cacb0b5ced9feeb8af4664f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753845"
---
# <a name="colelinkingdoc-class"></a>코올링싱독 클래스

포함된 항목에 대한 연결을 지원하는 OLE 컨테이너 문서의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class COleLinkingDoc : public COleDocument
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[코올링독:::코올링독](#colelinkingdoc)|`COleLinkingDoc` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COle링독::등록](#register)|OLE 시스템 DLL로 문서를 등록합니다.|
|[코올링독::취소](#revoke)|문서 등록을 취소합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[코올링독::온파인데임베디드아이템](#onfindembeddeditem)|지정된 포함된 항목을 찾습니다.|
|[코올링독::온겟링크드아이템](#ongetlinkeditem)|지정된 연결된 항목을 찾습니다.|

## <a name="remarks"></a>설명

포함된 항목에 대한 연결을 지원하는 컨테이너 응용 프로그램을 "링크 컨테이너"라고 합니다. [OCLIENT](../../overview/visual-cpp-samples.md) 샘플 응용 프로그램은 링크 컨테이너의 예입니다.

링크된 항목의 원본이 다른 문서에 포함된 항목인 경우 포함된 항목을 편집하려면 문서가 포함된 항목을 로드해야 합니다. 따라서 사용자가 연결된 항목의 소스를 편집하려는 경우 다른 컨테이너 응용 프로그램에서 링크 컨테이너를 시작할 수 있어야 합니다. 응용 프로그램은 프로그래밍 방식으로 시작할 때 문서를 만들 수 있도록 [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) 클래스를 사용해야 합니다.

컨테이너를 링크 컨테이너로 만들려면 `COleLinkingDoc` [COleDocument](../../mfc/reference/coledocument-class.md)대신 문서 클래스를 파생합니다. 다른 OLE 컨테이너와 마찬가지로 응용 프로그램의 기본 데이터와 포함된 항목 또는 연결된 항목을 저장하기 위해 클래스를 디자인해야 합니다. 또한 네이티브 데이터를 저장하기 위한 데이터 구조를 디자인해야 합니다. 응용 프로그램의 `CDocItem`기본 데이터에 대해 -derived 클래스를 정의하는 경우 기본 `COleDocument` 데이터와 OLE 데이터를 저장하기 위해 정의된 인터페이스를 사용할 수 있습니다.

다른 컨테이너에서 프로그래밍 방식으로 응용 프로그램을 시작할 수 `COleTemplateServer` 있도록 하려면 개체를 응용 `CWinApp`프로그램의 -derived 클래스의 멤버로 선언합니다.

[!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]

-derived 클래스의 `InitInstance` 멤버 함수에서 문서 템플릿을 만들고 -derived 클래스를 문서 클래스로 지정합니다. `COleLinkingDoc` `CWinApp`

[!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]

`COleTemplateServer` 개체의 `ConnectTemplate` 멤버 함수를 호출하여 개체를 문서 템플릿에 연결하고 다음을 호출하여 `COleTemplateServer::RegisterAll`OLE 시스템에 모든 클래스 개체를 등록합니다.

[!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]

샘플 `CWinApp`-파생 클래스 정의 `InitInstance` 및 함수는 OCLIENT를 참조하십시오. H 및 OCLIENT. MFC 샘플 [OCLIENT의](../../overview/visual-cpp-samples.md)CPP.

사용에 `COleLinkingDoc`대한 자세한 내용은 [컨테이너: 컨테이너](../../mfc/containers-implementing-a-container.md) 및 [컨테이너 구현: 고급 기능](../../mfc/containers-advanced-features.md)입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

`COleLinkingDoc`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="colelinkingdoccolelinkingdoc"></a><a name="colelinkingdoc"></a>코올링독:::코올링독

OLE 시스템 `COleLinkingDoc` DLL과의 통신을 시작하지 않고 개체를 생성합니다.

```
COleLinkingDoc();
```

### <a name="remarks"></a>설명

문서가 열려 `Register` 있음을 OLE에 알리려면 멤버 함수를 호출해야 합니다.

## <a name="colelinkingdoconfindembeddeditem"></a><a name="onfindembeddeditem"></a>코올링독::온파인데임베디드아이템

프레임워크에서 호출하여 문서에 지정된 이름이 포함된 포함된 OLE 항목이 포함되어 있는지 여부를 확인합니다.

```
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>매개 변수

*lpszItemName*<br/>
요청된 포함된 OLE 항목의 이름에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

지정된 항목에 대한 포인터; 항목을 찾을 수 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

기본 구현은 지정된 이름의 항목에 대해 포함된 항목 목록을 검색합니다(이름 비교는 대/소문자를 구분함). 포함된 OLE 항목을 저장하거나 이름을 지정하는 고유한 방법이 있는 경우 이 함수를 재정의합니다.

## <a name="colelinkingdocongetlinkeditem"></a><a name="ongetlinkeditem"></a>코올링독::온겟링크드아이템

프레임워크에서 호출하여 문서에 지정된 이름이 있는 연결된 서버 항목이 포함되어 있는지 확인합니다.

```
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>매개 변수

*lpszItemName*<br/>
요청된 연결된 OLE 항목의 이름에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

지정된 항목에 대한 포인터; 항목을 찾을 수 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

기본 `COleLinkingDoc` 구현은 항상 NULL을 반환합니다. 이 함수는 지정된 이름으로 연결된 `COleServerDoc` 항목에 대한 OLE 서버 항목 목록을 검색하기 위해 파생 클래스에서 재정의됩니다(이름 비교는 대/소문자 구분). 연결된 서버 항목을 저장하거나 검색하는 고유한 방법을 구현한 경우 이 함수를 재정의합니다.

## <a name="colelinkingdocregister"></a><a name="register"></a>COle링독::등록

OLE 시스템 DLL에 문서가 열려 있음을 알립니다.

```
BOOL Register(
    COleObjectFactory* pFactory,
    LPCTSTR lpszPathName);
```

### <a name="parameters"></a>매개 변수

*pFactory*<br/>
OLE 팩터리 개체에 대한 포인터(NULL일 수 있음).

*lpszPathName*<br/>
컨테이너 문서의 정규화된 경로에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

문서가 성공적으로 등록된 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

명명된 파일을 만들거나 열 때 이 함수를 호출하여 OLE 시스템 DLL에 문서를 등록합니다. 문서가 포함된 항목을 나타내는 경우 이 함수를 호출할 필요가 없습니다.

응용 프로그램에서 `COleTemplateServer` 사용하는 경우 `Register` `COleLinkingDoc` `OnNewDocument`의 구현에 의해 호출됩니다. `OnOpenDocument` `OnSaveDocument`

## <a name="colelinkingdocrevoke"></a><a name="revoke"></a>코올링독::취소

OLE 시스템 DLL에 문서가 더 이상 열려 있지 않다는 것을 알립니다.

```cpp
void Revoke();
```

### <a name="remarks"></a>설명

이 함수를 호출하여 OLE 시스템 DLL에 대한 문서 등록을 취소합니다.

명명된 파일을 닫을 때이 함수를 호출해야하지만 일반적으로 직접 호출 할 필요는 없습니다. `Revoke`의 구현에 `COleLinkingDoc`의해 당신을 `OnCloseDocument`위해 `OnNewDocument` `OnOpenDocument`호출됩니다 `OnSaveDocument`.

## <a name="see-also"></a>참조

[MFC 샘플 클라이언트](../../overview/visual-cpp-samples.md)<br/>
[콜레문서 클래스](../../mfc/reference/coledocument-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDoc템플릿 클래스](../../mfc/reference/cdoctemplate-class.md)
