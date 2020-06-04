---
title: 콜레독오브젝트아이템 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
helpviewer_keywords:
- COleDocObjectItem [MFC], COleDocObjectItem
- COleDocObjectItem [MFC], DoDefaultPrinting
- COleDocObjectItem [MFC], ExecCommand
- COleDocObjectItem [MFC], GetActiveView
- COleDocObjectItem [MFC], GetPageCount
- COleDocObjectItem [MFC], OnPreparePrinting
- COleDocObjectItem [MFC], OnPrint
- COleDocObjectItem [MFC], QueryCommand
- COleDocObjectItem [MFC], Release
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
ms.openlocfilehash: a696226185dd99b9e277e74d92cbe15c95cc900a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375047"
---
# <a name="coledocobjectitem-class"></a>콜레독오브젝트아이템 클래스

액티브 문서 포함을 구현합니다.

## <a name="syntax"></a>구문

```
class COleDocObjectItem : public COleClientItem
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레닥오브젝트아이템::콜레닥오브젝트아이템](#coledocobjectitem)|항목을 생성합니다. `COleDocObject`|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleDocObject항목::Do기본 인쇄](#dodefaultprinting)|기본 프린터 설정을 사용하여 컨테이너 응용 프로그램의 문서를 인쇄합니다.|
|[콜레독오브젝트아이템::엑세커맨드](#execcommand)|사용자가 지정한 명령을 실행합니다.|
|[콜레독오브젝트항목::겟액티브뷰](#getactiveview)|문서의 활성 보기를 검색합니다.|
|[콜레독오브젝트아이템::겟페이지카운트](#getpagecount)|컨테이너 응용 프로그램의 문서에서 페이지 수를 검색합니다.|
|[콜레독오브젝트아이템::온준비인쇄](#onprepareprinting)|인쇄할 컨테이너 응용 프로그램의 문서를 준비합니다.|
|[콜레독 오브젝트아이템::온프린트](#onprint)|컨테이너 응용 프로그램의 문서를 인쇄합니다.|
|[COleDocObject항목::쿼리 명령](#querycommand)|사용자 인터페이스 이벤트에 의해 생성되는 하나 이상 명령의 상태를 쿼리합니다.|
|[콜레독오브젝트아이템::릴리즈](#release)|OLE 연결 항목에 대한 연결을 해제하고 열려 있는 경우 닫습니다. 클라이언트 항목을 삭제하지 않습니다.|

## <a name="remarks"></a>설명

MFC에서 활성 문서는 다음과 같은 차이점을 가진 일반 내부 편집 가능한 포함과 유사하게 처리됩니다.

- -derived 클래스는 `COleDocument`여전히 현재 포함된 항목의 목록을 유지 관리합니다. 그러나 이러한 항목은 `COleDocObjectItem`-파생 항목일 수 있습니다.

- 활성 문서가 활성 상태일 때 뷰의 전체 클라이언트 영역을 차지합니다.

- 활성 문서 컨테이너는 **도움말** 메뉴를 완전히 제어할 수 있습니다.

- **도움말** 메뉴에는 활성 문서 컨테이너와 서버 모두에 대한 메뉴 항목이 포함되어 있습니다.

활성 문서 컨테이너는 **도움말** 메뉴를 소유하므로 컨테이너는 서버 **도움말** 메뉴 메시지를 서버로 전달합니다. 이 통합은 `COleDocObjectItem`에서 처리됩니다.

메뉴 병합 및 활성 문서 활성화에 대한 자세한 내용은 [활성 문서 포함](../../mfc/active-document-containment.md)의 개요를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="coledocobjectitemcoledocobjectitem"></a><a name="coledocobjectitem"></a>콜레닥오브젝트아이템::콜레닥오브젝트아이템

이 멤버 함수를 호출하여 개체를 초기화합니다. `COleDocObjectItem`

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>매개 변수

*pContainerDoc*<br/>
활성 문서 `COleDocument` 컨테이너 역할을 하는 개체에 대한 포인터입니다. 이 매개 변수는 IMPLEMENT_SERIALIZE 활성화하려면 NULL이어야 합니다. 일반적으로 OLE 항목은 NULL이 아닌 문서 포인터로 구성됩니다.

## <a name="coledocobjectitemdodefaultprinting"></a><a name="dodefaultprinting"></a>COleDocObject항목::Do기본 인쇄

기본 설정을 사용하여 문서에 프레임워크에서 호출합니다.

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pCaller*<br/>
인쇄 명령을 보내는 [CView](../../mfc/reference/cview-class.md) 개체에 대한 포인터입니다.

*pInfo*<br/>
인쇄할 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 개체에 대한 포인터입니다.

## <a name="coledocobjectitemexeccommand"></a><a name="execcommand"></a>콜레독오브젝트아이템::엑세커맨드

사용자가 지정한 명령을 실행하려면 이 멤버 함수를 호출합니다.

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>매개 변수

*nCmdID*<br/>
실행할 명령의 식별자입니다. *pguidCmdGroup으로*식별된 그룹에 있어야 합니다.

*nCmdExecOpt*<br/>
명령 실행 옵션을 지정합니다. 기본적으로 사용자에게 메시지를 표시하지 않고 명령을 실행하도록 설정합니다. 값 목록은 [OLECMDEXECOPT를](/windows/win32/api/docobj/ne-docobj-olecmdexecopt) 참조하십시오.

*pguidCmdGroup*<br/>
명령 그룹의 고유 식별자입니다. 기본적으로 표준 그룹을 지정하는 NULL입니다. *nCmdID로* 전달된 명령은 그룹에 속해야 합니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK 반환합니다. 그렇지 않으면 다음 오류 코드 중 하나를 반환합니다.

|값|설명|
|-----------|-----------------|
|E_UNEXPECTED|예기치 않은 오류가 발생했습니다.|
|E_FAIL|오류가 발생했습니다.|
|E_NOTIMPL|MFC 자체가 명령을 번역하고 디스패치하려고 시도해야 한다는 것을 나타냅니다.|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup은* NULL이 아닌 경우이지만 인식된 명령 그룹을 지정하지 는 않습니다.|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID그룹* pGroup에서 유효한 명령으로 인식되지 않습니다.|
|OLECMDERR_DISABLED|*nCmdID로* 식별된 명령은 비활성화되어 실행할 수 없습니다.|
|OLECMDERR_NOHELP|발신자는 *nCmdID로* 식별 된 명령에 대한 도움을 요청했지만 도움을 받을 수 없습니다.|
|OLECMDERR_CANCELLED|사용자가 실행을 취소했습니다.|

### <a name="remarks"></a>설명

*pguidCmdGroup* 및 *nCmdID* 매개 변수는 함께 호출할 명령을 고유하게 식별합니다. *nCmdExecOpt* 매개 변수는 취할 정확한 작업을 지정합니다.

## <a name="coledocobjectitemgetactiveview"></a><a name="getactiveview"></a>콜레독오브젝트항목::겟액티브뷰

이 멤버 함수를 호출하여 `IOleDocumentView` 현재 활성 뷰의 인터페이스에 대한 포인터를 가져옵니다.

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>Return Value

현재 활성 뷰의 [IOleDocumentView](/windows/win32/api/docobj/nn-docobj-ioledocumentview) 인터페이스에 대한 포인터입니다. 현재 보기가 없는 경우 NULL을 반환합니다.

### <a name="remarks"></a>설명

반환된 `IOleDocumentView` 포인터의 참조 수는 이 함수에서 반환되기 전에 증분되지 않습니다.

## <a name="coledocobjectitemgetpagecount"></a><a name="getpagecount"></a>콜레독오브젝트아이템::겟페이지카운트

이 멤버 함수를 호출하여 문서의 페이지 수를 검색합니다.

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>매개 변수

*pnFirstPage*<br/>
문서의 첫 페이지 수에 대한 포인터입니다. NULL일 수 있으며, 이는 호출자에게 이 번호가 필요하지 않다는 것을 나타냅니다.

*pcPages*<br/>
문서의 총 페이지 수에 대한 포인터입니다. NULL일 수 있으며, 이는 호출자에게 이 번호가 필요하지 않다는 것을 나타냅니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="coledocobjectitemonprepareprinting"></a><a name="onprepareprinting"></a>콜레독오브젝트아이템::온준비인쇄

이 멤버 함수는 인쇄할 문서를 준비하기 위해 프레임워크에서 호출됩니다.

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>매개 변수

*pCaller*<br/>
인쇄 명령을 보내는 [CView](../../mfc/reference/cview-class.md) 개체에 대한 포인터입니다.

*pInfo*<br/>
인쇄할 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 개체에 대한 포인터입니다.

*b프린트모두*<br/>
전체 문서를 인쇄할지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="coledocobjectitemonprint"></a><a name="onprint"></a>콜레독 오브젝트아이템::온프린트

이 멤버 함수는 문서를 인쇄하기 위해 프레임워크에서 호출됩니다.

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>매개 변수

*pCaller*<br/>
인쇄 명령을 보내는 CView 개체에 대한 포인터입니다.

*pInfo*<br/>
인쇄할 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 개체에 대한 포인터입니다.

*b프린트모두*<br/>
전체 문서를 인쇄할지 여부를 지정합니다.

## <a name="coledocobjectitemquerycommand"></a><a name="querycommand"></a>COleDocObject항목::쿼리 명령

사용자 인터페이스 이벤트에 의해 생성되는 하나 이상 명령의 상태를 쿼리합니다.

```
HRESULT QueryCommand(
    ULONG nCmdID,
    DWORD* pdwStatus,
    OLECMDTEXT* pCmdText =NULL,
    const GUID* pguidCmdGroup =NULL);
```

### <a name="parameters"></a>매개 변수

*nCmdID*<br/>
쿼리중인 명령의 식별자입니다.

*pdw 상태*<br/>
쿼리의 결과로 반환된 플래그에 대한 포인터입니다. 가능한 값 목록은 [OLECMDF](/windows/win32/api/docobj/ne-docobj-olecmdf)를 참조하십시오.

*pCmd텍스트*<br/>
단일 명령에 대한 이름 및 상태 정보를 반환하는 [OLECMDTEXT](/windows/win32/api/docobj/ns-docobj-olecmdtext) 구조에 대한 포인터입니다. NULL이 호출자에게 이 정보가 필요하지 않음을 나타낼 수 있습니다.

*pguidCmdGroup*<br/>
명령 그룹의 고유 식별자; NULL로 사용하여 표준 그룹을 지정할 수 있습니다.

### <a name="return-value"></a>Return Value

반환 값의 전체 목록은 Windows SDK의 [IOleCommandTarget::QueryStatus를](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) 참조하십시오.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [IOleCommandTarget::QueryStatus](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) 메서드의 기능을 에뮬레이트합니다.

## <a name="coledocobjectitemrelease"></a><a name="release"></a>콜레독오브젝트아이템::릴리즈

OLE 연결 항목에 대한 연결을 해제하고 열려 있는 경우 닫습니다. 클라이언트 항목을 삭제하지 않습니다.

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>매개 변수

*dwCloseOption*<br/>
OLE 항목이 로드된 상태로 돌아갈 때 저장되는 상황을 지정하는 플래그입니다. 가능한 값 목록은 [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close)를 참조하십시오.

### <a name="remarks"></a>설명

클라이언트 항목을 삭제하지 않습니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[COle클라이언트항목 클래스](../../mfc/reference/coleclientitem-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COle클라이언트항목 클래스](../../mfc/reference/coleclientitem-class.md)<br/>
[CDocObjectServer항목 클래스](../../mfc/reference/cdocobjectserveritem-class.md)
