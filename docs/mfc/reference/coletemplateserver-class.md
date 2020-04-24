---
title: COle템플릿서버 클래스
ms.date: 11/04/2016
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
helpviewer_keywords:
- COleTemplateServer [MFC], COleTemplateServer
- COleTemplateServer [MFC], ConnectTemplate
- COleTemplateServer [MFC], Unregister
- COleTemplateServer [MFC], UpdateRegistry
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
ms.openlocfilehash: 561da5060aae3c938dc3e55d0310718a881c1a3b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753731"
---
# <a name="coletemplateserver-class"></a>COle템플릿서버 클래스

OLE 비주얼 편집 서버, 자동화 서버 및 링크 컨테이너(포함에 대한 링크를 지원하는 애플리케이션)에 사용합니다.

## <a name="syntax"></a>구문

```
class COleTemplateServer : public COleObjectFactory
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COle템플릿 서버::COle템플릿서버](#coletemplateserver)|`COleTemplateServer` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COle템플릿 서버::연결 템플릿](#connecttemplate)|문서 템플릿을 기본 `COleObjectFactory` 개체에 연결합니다.|
|[COle템플릿 서버::등록 취소](#unregister)|연결된 문서 템플릿을 등록 취소합니다.|
|[COle템플릿 서버::업데이트 레지스트리](#updateregistry)|OLE 시스템 레지스트리에 문서 유형을 등록합니다.|

## <a name="remarks"></a>설명

이 클래스는 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)클래스에서 파생됩니다. 일반적으로 자신의 클래스를 파생하는 대신 직접 사용할 `COleTemplateServer` 수 있습니다. `COleTemplateServer`는 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체를 사용하여 서버 문서를 관리합니다. 전체 `COleTemplateServer` 서버, 즉 독립 실행형 응용 프로그램으로 실행할 수 있는 서버를 구현할 때 사용합니다. 전체 서버는 일반적으로 여러 문서 인터페이스(MDI) 응용 프로그램이지만 단일 문서 인터페이스(SDI) 응용 프로그램이 지원됩니다. 응용 `COleTemplateServer` 프로그램이 지원하는 각 서버 문서 유형에 대해 하나의 개체가 필요합니다. 즉, 서버 응용 프로그램이 워크시트와 차트를 모두 `COleTemplateServer` 지원하는 경우 두 개의 개체가 있어야 합니다.

`COleTemplateServer`에서 정의된 `OnCreateInstance` 멤버 함수를 재정의합니다. `COleObjectFactory` 이 멤버 함수는 올바른 형식의 C++ 개체를 만들기 위해 프레임워크에서 호출됩니다.

서버에 대한 자세한 내용은 [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="coletemplateservercoletemplateserver"></a><a name="coletemplateserver"></a>COle템플릿 서버::COle템플릿서버

`COleTemplateServer` 개체를 생성합니다.

```
COleTemplateServer();
```

### <a name="remarks"></a>설명

`COleTemplateServer` 클래스 사용에 대한 자세한 설명은 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) 클래스 개요를 참조하십시오.

## <a name="coletemplateserverconnecttemplate"></a><a name="connecttemplate"></a>COle템플릿 서버::연결 템플릿

*pDocTemplate에서* 가리키는 문서 템플릿을 기본 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) 개체에 연결합니다.

```cpp
void ConnectTemplate(
    REFCLSID clsid,
    CDocTemplate* pDocTemplate,
    BOOL bMultiInstance);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
템플릿이 요청하는 OLE 클래스 ID를 참조합니다.

*pDoc 템플릿*<br/>
문서 템플릿에 대한 포인터입니다.

*bMulti인스턴스*<br/>
응용 프로그램의 단일 인스턴스가 여러 인스턴스를 지원할 수 있는지 여부를 나타냅니다. TRUE인 경우 개체를 만들기 위해 각 요청에 대해 응용 프로그램의 여러 인스턴스가 시작됩니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [CLSID 키를](/windows/win32/com/clsid-key-hklm) 참조하십시오.

## <a name="coletemplateserverunregister"></a><a name="unregister"></a>COle템플릿 서버::등록 취소

연결된 문서 템플릿을 등록 취소합니다.

```
BOOL Unregister();
```

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

입력비고스

## <a name="coletemplateserverupdateregistry"></a><a name="updateregistry"></a>COle템플릿 서버::업데이트 레지스트리

문서 템플릿 문자열에서 파일 형식 정보를 로드하고 해당 정보를 OLE 시스템 레지스트리에 배치합니다.

```cpp
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>매개 변수

*nAppType*<br/>
AFXDISP에 정의된 OLE_APPTYPE 열거형의 값입니다. H. 다음 값 중 하나를 가질 수 있습니다.

- OAT_INPLACE_SERVER 서버에는 전체 서버 사용자 인터페이스가 있습니다.

- OAT_SERVER 서버는 포함만 지원합니다.

- OAT_CONTAINER 컨테이너는 포함된 개체에 대한 링크를 지원합니다.

- OAT_DISPATCH_OBJECT 개체는 `IDispatch`-수 있습니다.

- OAT_DOC_OBJECT_SERVER 서버는 포함 및 문서 개체 구성 요소 모델을 모두 지원합니다.

*rglpsz레지스터*<br/>
항목이 없는 경우에만 레지스트리에 기록된 항목 목록입니다.

*rglpsz오버쓰기*<br/>
이전 항목이 있는지 여부에 관계없이 레지스트리에 기록된 항목 목록입니다.

*bRegister*<br/>
클래스를 등록할지 여부를 결정합니다. *bRegister가* TRUE이면 클래스가 시스템 레지스트리에 등록됩니다. 그렇지 않으면 클래스를 등록 취소합니다.

### <a name="remarks"></a>설명

등록 정보는 [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)에 대한 호출을 통해 로드됩니다. 검색된 하위 문자열은 참조 페이지에 설명된 `regFileTypeName`대로 `fileNewName`인덱스 `regFileTypeId`및 `GetDocString` 및 에 의해 식별된 문자열입니다.

하위 `regFileTypeId` 문자열이 비어 있거나 다른 `GetDocString` 이유로 호출이 실패하면 이 함수가 실패하고 파일 정보가 레지스트리에 입력되지 않습니다.

인수의 정보는 *rglpszRegister* 및 *rglpszOverwrite* [AfxOleRegisterServerClass에](application-control.md#afxoleregisterserverclass)대한 호출을 통해 레지스트리에 기록됩니다. 두 인수가 NULL일 때 등록되는 기본 정보는 대부분의 응용 프로그램에 적합합니다. 이러한 인수의 정보 구조에 대한 자세한 `AfxOleRegisterServerClass`내용은 을 참조하십시오.

자세한 내용은 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)을 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[콜레오브젝트팩토리 클래스](../../mfc/reference/coleobjectfactory-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레서버독 클래스](../../mfc/reference/coleserverdoc-class.md)<br/>
[콜레서버아이템 클래스](../../mfc/reference/coleserveritem-class.md)
