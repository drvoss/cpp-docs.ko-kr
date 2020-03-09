---
title: CCmdTarget 클래스
ms.date: 11/04/2016
f1_keywords:
- CCmdTarget
- AFXWIN/CCmdTarget
- AFXWIN/CCmdTarget::CCmdTarget
- AFXWIN/CCmdTarget::BeginWaitCursor
- AFXWIN/CCmdTarget::DoOleVerb
- AFXWIN/CCmdTarget::EnableAutomation
- AFXWIN/CCmdTarget::EnableConnections
- AFXWIN/CCmdTarget::EnableTypeLib
- AFXWIN/CCmdTarget::EndWaitCursor
- AFXWIN/CCmdTarget::EnumOleVerbs
- AFXWIN/CCmdTarget::FromIDispatch
- AFXWIN/CCmdTarget::GetDispatchIID
- AFXWIN/CCmdTarget::GetIDispatch
- AFXWIN/CCmdTarget::GetTypeInfoCount
- AFXWIN/CCmdTarget::GetTypeInfoOfGuid
- AFXWIN/CCmdTarget::GetTypeLib
- AFXWIN/CCmdTarget::GetTypeLibCache
- AFXWIN/CCmdTarget::IsInvokeAllowed
- AFXWIN/CCmdTarget::IsResultExpected
- AFXWIN/CCmdTarget::OnCmdMsg
- AFXWIN/CCmdTarget::OnFinalRelease
- AFXWIN/CCmdTarget::RestoreWaitCursor
helpviewer_keywords:
- CCmdTarget [MFC], CCmdTarget
- CCmdTarget [MFC], BeginWaitCursor
- CCmdTarget [MFC], DoOleVerb
- CCmdTarget [MFC], EnableAutomation
- CCmdTarget [MFC], EnableConnections
- CCmdTarget [MFC], EnableTypeLib
- CCmdTarget [MFC], EndWaitCursor
- CCmdTarget [MFC], EnumOleVerbs
- CCmdTarget [MFC], FromIDispatch
- CCmdTarget [MFC], GetDispatchIID
- CCmdTarget [MFC], GetIDispatch
- CCmdTarget [MFC], GetTypeInfoCount
- CCmdTarget [MFC], GetTypeInfoOfGuid
- CCmdTarget [MFC], GetTypeLib
- CCmdTarget [MFC], GetTypeLibCache
- CCmdTarget [MFC], IsInvokeAllowed
- CCmdTarget [MFC], IsResultExpected
- CCmdTarget [MFC], OnCmdMsg
- CCmdTarget [MFC], OnFinalRelease
- CCmdTarget [MFC], RestoreWaitCursor
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
ms.openlocfilehash: 583b685295bf77910ef134776c1c4fa39baf93ad
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78867038"
---
# <a name="ccmdtarget-class"></a>CCmdTarget 클래스

MFC 라이브러리 메시지 맵 아키텍처의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CCmdTarget : public CObject
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CCmdTarget::CCmdTarget](#ccmdtarget)|`CCmdTarget` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|커서를 모래 시계 커서로 표시 합니다.|
|[CCmdTarget::DoOleVerb](#dooleverb)|OLE 동사로 지정 된 작업을 수행 합니다.|
|[CCmdTarget::EnableAutomation](#enableautomation)|`CCmdTarget` 개체에 대 한 OLE 자동화를 허용 합니다.|
|[CCmdTarget::EnableConnections](#enableconnections)|연결 지점의 이벤트 발생을 사용 하도록 설정 합니다.|
|[CCmdTarget::EnableTypeLib](#enabletypelib)|개체의 형식 라이브러리를 사용 하도록 설정 합니다.|
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|이전 커서로 돌아갑니다.|
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|개체의 OLE 동사를 열거 합니다.|
|[CCmdTarget::FromIDispatch](#fromidispatch)|`IDispatch` 포인터와 연결 된 `CCmdTarget` 개체에 대 한 포인터를 반환 합니다.|
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|기본 디스패치 인터페이스 ID를 가져옵니다.|
|[CCmdTarget::GetIDispatch](#getidispatch)|`CCmdTarget` 개체와 연결 된 `IDispatch` 개체에 대 한 포인터를 반환 합니다.|
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|개체에서 제공 하는 형식 정보 인터페이스의 수를 검색 합니다.|
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|지정된 된 GUID에 해당 하는 형식 설명을 검색 합니다.|
|[CCmdTarget::GetTypeLib](#gettypelib)|형식 라이브러리에 대 한 포인터를 가져옵니다.|
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|형식 라이브러리 캐시를 가져옵니다.|
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|자동화 메서드 호출을 사용 합니다.|
|[CCmdTarget::IsResultExpected](#isresultexpected)|자동화 함수에서 값을 반환 해야 하는 경우 0이 아닌 값을 반환 합니다.|
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|명령 메시지를 라우팅하고 디스패치합니다.|
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|마지막 OLE 참조가 해제 된 후 정리 합니다.|
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|모래 시계 커서를 복원 합니다.|

## <a name="remarks"></a>설명

메시지 맵은 명령 또는 메시지를 처리 하기 위해 작성 하는 멤버 함수로 라우팅합니다. 명령은 메뉴 항목, 명령 단추 또는 액셀러레이터 키의 메시지입니다.

`CCmdTarget`에서 파생 된 키 프레임 워크 클래스에는 [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md)및 [CFrameWnd](../../mfc/reference/cframewnd-class.md)가 포함 됩니다. 새 클래스에서 메시지를 처리 하려는 경우 이러한 `CCmdTarget`파생 클래스 중 하나에서 클래스를 파생 시킵니다. `CCmdTarget`에서 직접 클래스를 파생 시키는 경우는 거의 없습니다.

명령 대상 및 `OnCmdMsg` 라우팅에 대 한 개요는 [명령 대상](../../mfc/command-targets.md), [명령 라우팅](../../mfc/command-routing.md)및 [메시지 매핑](../../mfc/mapping-messages.md)을 참조 하세요.

`CCmdTarget`에는 모래 시계 커서의 표시를 처리 하는 멤버 함수가 포함 되어 있습니다. 명령을 실행 하는 데 눈에 띄는 시간 간격을 사용 하는 경우 모래 시계 커서를 표시 합니다.

메시지 맵과 유사한 디스패치 맵은 OLE automation `IDispatch` 기능을 노출 하는 데 사용 됩니다. 이 인터페이스를 노출 하면 다른 응용 프로그램 (예: Visual Basic)이 응용 프로그램을 호출할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="beginwaitcursor"></a>  CCmdTarget::BeginWaitCursor

명령을 실행 하는 데 눈에 띄는 시간 간격을 사용 하는 경우 커서를 모래 시계 모양으로 표시 하려면이 함수를 호출 합니다.

```
void BeginWaitCursor();
```

### <a name="remarks"></a>설명

프레임 워크는이 함수를 호출 하 여 `CDocument` 개체가 파일에 로드 하거나 저장 하는 경우와 같이 사용 중인 사용자를 표시 합니다.

`BeginWaitCursor` 작업은 `OnSetCursor` 처리와 같은 다른 동작이 커서를 변경할 수 있으므로 단일 메시지 처리기 외부에서 항상 유효 하지는 않습니다.

`EndWaitCursor`를 호출 하 여 이전 커서를 복원 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="ccmdtarget"></a>  CCmdTarget::CCmdTarget

`CCmdTarget` 개체를 생성합니다.

```
CCmdTarget();
```

##  <a name="dooleverb"></a>  CCmdTarget::DoOleVerb

OLE 동사로 지정 된 작업을 수행 합니다.

```
BOOL DoOleVerb(
    LONG iVerb,
    LPMSG lpMsg,
    HWND hWndParent,
    LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
동사의 숫자 식별자입니다.

*lpMsg*<br/>
동사를 호출한 이벤트를 설명 하는 [메시지](/windows/win32/api/winuser/ns-winuser-msg) 구조 (예: 두 번 클릭)에 대 한 포인터입니다.

*hWndParent*<br/>
개체가 포함된 문서 창의 핸들입니다.

*lpRect*<br/>
*HwndParent*에서 개체의 경계 사각형을 정의 하는 좌표 (픽셀)를 포함 하는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 하면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 [:D IOleObject](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb)의 구현입니다. 가능한 동작은 [Ccmdtarget:: EnumOleVerbs](#enumoleverbs)에 의해 열거 됩니다.

##  <a name="enableautomation"></a>  CCmdTarget::EnableAutomation

개체에 대해 OLE 자동화를 사용 하도록 설정 하려면이 함수를 호출 합니다.

```
void EnableAutomation();
```

### <a name="remarks"></a>설명

이 함수는 일반적으로 개체의 생성자에서 호출 되며 디스패치 맵이 클래스에 대해 선언 된 경우에만 호출 해야 합니다. 자동화에 대 한 자세한 내용은 [자동화 클라이언트](../../mfc/automation-clients.md) 및 [자동화 서버](../../mfc/automation-servers.md)문서를 참조 하세요.

##  <a name="enableconnections"></a>  CCmdTarget::EnableConnections

연결 지점의 이벤트 발생을 사용 하도록 설정 합니다.

```
void EnableConnections();
```

### <a name="remarks"></a>설명

연결 요소를 사용 하도록 설정 하려면 파생 클래스의 생성자에서이 멤버 함수를 호출 합니다.

##  <a name="enabletypelib"></a>  CCmdTarget::EnableTypeLib

개체의 형식 라이브러리를 사용 하도록 설정 합니다.

```
void EnableTypeLib();
```

### <a name="remarks"></a>설명

형식 정보를 제공 하는 경우 `CCmdTarget`파생 개체의 생성자에서이 멤버 함수를 호출 합니다.

##  <a name="endwaitcursor"></a>  CCmdTarget::EndWaitCursor

`BeginWaitCursor` 멤버 함수를 호출 하 여 모래 시계 커서에서 이전 커서로 돌아간 후이 함수를 호출 합니다.

```
void EndWaitCursor();
```

### <a name="remarks"></a>설명

프레임 워크는 모래 시계 커서를 호출한 후에도이 멤버 함수를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="enumoleverbs"></a>  CCmdTarget::EnumOleVerbs

개체의 OLE 동사를 열거 합니다.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>매개 변수

*ppenumOleVerb*<br/>
[IEnumOLEVERB](/windows/win32/api/oleidl/nn-oleidl-ienumoleverb) 인터페이스에 대 한 포인터에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

개체가 하나 이상의 OLE 동사를 지원 하면 TRUE이 고,이 경우 \* *ppenumOleVerb* 는 `IEnumOLEVERB` 열거자 인터페이스를 가리키고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 [IOleObject:: EnumVerbs](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs)의 구현입니다.

##  <a name="fromidispatch"></a>  CCmdTarget::FromIDispatch

클래스의 자동화 멤버 함수에서 받은 `IDispatch` 포인터를 `IDispatch` 개체의 인터페이스를 구현 하는 `CCmdTarget` 개체로 매핑하려면이 함수를 호출 합니다.

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>매개 변수

*lpDispatch*<br/>
`IDispatch` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

*Lpdispatch*와 연결 된 `CCmdTarget` 개체에 대 한 포인터입니다. 이 함수는 `IDispatch` 개체가 Microsoft Foundation Class `IDispatch` 개체로 인식 되지 않는 경우 NULL을 반환 합니다.

### <a name="remarks"></a>설명

이 함수의 결과는 `GetIDispatch`멤버 함수 호출의 역함수입니다.

##  <a name="getdispatchiid"></a>  CCmdTarget::GetDispatchIID

기본 디스패치 인터페이스 ID를 가져옵니다.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>매개 변수

*pIID*<br/>
인터페이스 ID ( [GUID](/previous-versions/cc317743(v%3dmsdn.10)))에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 하면 TRUE이 고, 그렇지 않으면 FALSE입니다. 성공 하면 \* *Piid* 가 기본 디스패치 인터페이스 ID로 설정 됩니다.

### <a name="remarks"></a>설명

파생 클래스는이 멤버 함수를 재정의 해야 합니다. 재정의 되지 않으면 FALSE를 반환 하는 `GetDispatchIID`. [COleControl](../../mfc/reference/colecontrol-class.md)을 참조 하세요.

##  <a name="getidispatch"></a>  CCmdTarget::GetIDispatch

`IDispatch` 포인터를 반환 하거나 참조로 `IDispatch` 포인터를 사용 하는 자동화 메서드에서 `IDispatch` 포인터를 검색 하려면이 멤버 함수를 호출 합니다.

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>매개 변수

*bAddRef*<br/>
개체의 참조 횟수를 증가 시킬 것인지 여부를 지정 합니다.

### <a name="return-value"></a>Return Value

개체와 연결 된 `IDispatch` 포인터입니다.

### <a name="remarks"></a>설명

생성자에서 `EnableAutomation`를 호출 하는 개체의 경우 자동화를 사용 하도록 설정 하면이 함수는 `IDispatch` 인터페이스를 통해 통신 하는 클라이언트에서 사용 하는 `IDispatch`의 Foundation 클래스 구현에 대 한 포인터를 반환 합니다. 이 함수를 호출 하면 포인터에 대 한 참조가 자동으로 추가 되므로 [IUnknown:: AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)에 대 한 호출을 만들 필요가 없습니다.

##  <a name="gettypeinfocount"></a>  CCmdTarget::GetTypeInfoCount

개체에서 제공 하는 형식 정보 인터페이스의 수를 검색 합니다.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Return Value

형식 정보 인터페이스의 수입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 [IDispatch:: GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount)을 구현 합니다.

파생 클래스는 제공 된 형식 정보 인터페이스의 수 (0 또는 1)를 반환 하도록이 함수를 재정의 해야 합니다. 재정의 되지 않은 경우 `GetTypeInfoCount`는 0을 반환 합니다. 재정의 하려면 [ 및 ](../../mfc/reference/type-library-access.md#implement_oletypelib)도 구현 하는 `GetTypeLib`IMPLEMENT_OLETYPELIB`GetTypeLibCache` 매크로를 사용 합니다.

##  <a name="gettypeinfoofguid"></a>  CCmdTarget::GetTypeInfoOfGuid

지정된 된 GUID에 해당 하는 형식 설명을 검색 합니다.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>매개 변수

*lcid*<br/>
로캘 식별자 (`LCID`)입니다.

*guid*<br/>
유형 설명의 [GUID](/previous-versions/cc317743(v%3dmsdn.10)) 입니다.

*ppTypeInfo*<br/>
`ITypeInfo` 인터페이스에 대 한 포인터에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

호출의 성공 또는 실패를 나타내는 HRESULT입니다. 성공 하면 \* *Pptypeinfo* 가 유형 정보 인터페이스를 가리킵니다.

##  <a name="gettypelib"></a>  CCmdTarget::GetTypeLib

형식 라이브러리에 대 한 포인터를 가져옵니다.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>매개 변수

*lcid*<br/>
LCID(로캘 식별자)입니다.

*ppTypeLib*<br/>
`ITypeLib` 인터페이스에 대 한 포인터에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

호출의 성공 또는 실패를 나타내는 HRESULT입니다. 성공 하면 \* *Pptypelib* 가 형식 라이브러리 인터페이스를 가리킵니다.

### <a name="remarks"></a>설명

파생 된 클래스는이 멤버 함수를 재정의 해야 합니다. 재정의 되지 않으면 TYPE_E_CANTLOADLIBRARY `GetTypeLib` 반환 됩니다. [ 및 ](../../mfc/reference/type-library-access.md#implement_oletypelib)도 구현하는 `GetTypeInfoCount`IMPLEMENT_OLETYPELIB`GetTypeLibCache` 매크로를 사용합니다.

##  <a name="gettypelibcache"></a>  CCmdTarget::GetTypeLibCache

형식 라이브러리 캐시를 가져옵니다.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Return Value

`CTypeLibCache` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

파생 된 클래스는이 멤버 함수를 재정의 해야 합니다. 재정의 되지 않으면 NULL을 반환 `GetTypeLibCache` 반환 됩니다. [ 및 ](../../mfc/reference/type-library-access.md#implement_oletypelib)도 구현하는 `GetTypeInfoCount`IMPLEMENT_OLETYPELIB`GetTypeLib` 매크로를 사용합니다.

##  <a name="isinvokeallowed"></a>  CCmdTarget::IsInvokeAllowed

이 함수는 지정 된 자동화 메서드 ( *dispid*로 식별)를 호출할 수 있는지 여부를 확인 하기 위해 `IDispatch::Invoke`의 MFC 구현에 의해 호출 됩니다.

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>매개 변수

*dispid*<br/>
디스패치 ID입니다.

### <a name="return-value"></a>Return Value

메서드를 호출할 수 있으면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

`IsInvokeAllowed`에서 TRUE를 반환 하는 경우 `Invoke`는 메서드를 호출 합니다. 그렇지 않으면 `Invoke`에 오류가 발생 하 여 E_UNEXPECTED 반환 됩니다.

파생 클래스는이 함수를 재정의 하 여 적절 한 값을 반환할 수 있습니다 .이 값을 재정의 하지 않으면 TRUE를 반환 `IsInvokeAllowed`. 자세한 내용은 특정 [COleControl:: IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed)를 참조 하세요.

##  <a name="isresultexpected"></a>  CCmdTarget::IsResultExpected

`IsResultExpected`를 사용 하 여 클라이언트에서 자동화 함수 호출의 반환 값을 예상 하는지 여부를 확인 합니다.

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Return Value

자동화 함수에서 값을 반환 해야 하는 경우 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

OLE 인터페이스는 클라이언트에서 함수 호출 결과를 사용 하거나 무시 하는지 여부에 대 한 정보를 MFC에 제공 하 고, MFC는이 정보를 사용 하 여 `IsResultExpected`에 대 한 호출의 결과를 확인 합니다. 반환 값의 프로덕션이 시간 또는 리소스를 많이 사용 하는 경우 반환 값을 계산 하기 전에이 함수를 호출 하 여 효율성을 높일 수 있습니다.

이 함수는 클라이언트에서 호출한 자동화 함수에서 호출 하는 경우 다른 자동화 함수에서 유효한 반환 값을 얻을 수 있도록 0을 한 번만 반환 합니다.

`IsResultExpected`는 자동화 함수 호출이 진행 되 고 있지 않을 때 호출 되는 경우 0이 아닌 값을 반환 합니다.

##  <a name="oncmdmsg"></a>  CCmdTarget::OnCmdMsg

명령 메시지를 라우팅하고 발송 하 고 명령 사용자 인터페이스 개체의 업데이트를 처리 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
명령 ID를 포함 합니다.

*nCode*<br/>
명령 알림 코드를 식별 합니다. *Ncode*의 값에 대 한 자세한 내용은 **설명 부분** 을 참조 하십시오.

*pExtra*<br/>
*Ncode*의 값에 따라 사용 됩니다. *Pextra*에 대 한 자세한 내용은 **설명** 을 참조 하세요.

*pHandlerInfo*<br/>
NULL이 아닌 경우 `OnCmdMsg`는 명령을 발송 하는 대신 *Phandlerinfo* 구조의 *ptarget* 및 *pmf* 멤버를 채웁니다. 일반적으로이 매개 변수는 NULL 이어야 합니다.

### <a name="return-value"></a>Return Value

메시지가 처리 되 면 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이는 프레임 워크 명령 아키텍처의 기본 구현 루틴입니다.

런타임에는 `OnCmdMsg` 다른 개체에 명령을 발송 하거나 실제 메시지 매핑 조회를 수행 하는 루트 클래스 `CCmdTarget::OnCmdMsg`를 호출 하 여 명령 자체를 처리 합니다. 기본 명령 라우팅에 대 한 자세한 내용은 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)을 참조 하세요.

드문 경우 지만이 멤버 함수를 재정의 하 여 프레임 워크의 표준 명령 라우팅을 확장할 수 있습니다. 명령 라우팅 아키텍처에 대 한 자세한 내용은 [기술 정보 21](../../mfc/tn021-command-and-message-routing.md) 을 참조 하세요.

`OnCmdMsg`를 재정의 하는 *경우 ncode*의 값에 따라 *ncode*, 명령 알림 코드 및 *pextra*에 적절 한 값을 제공 해야 합니다. 다음 표에서는 해당 값을 보여 줍니다.

|*Ncode* 값|*Pextra* 값|
|-------------------|--------------------|
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|CN_UPDATE_COMMAND_UI|CCmdUI\*|
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

##  <a name="onfinalrelease"></a>  CCmdTarget::OnFinalRelease

개체에 대 한 마지막 OLE 참조가 해제 될 때 프레임 워크에서 호출 됩니다.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>설명

이 상황에 대 한 특별 한 처리를 제공 하려면이 함수를 재정의 합니다. 기본 구현에서는 개체를 삭제 합니다.

##  <a name="restorewaitcursor"></a>  CCmdTarget::RestoreWaitCursor

시스템 커서가 변경 된 후에 적절 한 모래 시계 커서를 복원 하려면이 함수를 호출 합니다 (예: 긴 작업 중에 메시지 상자를 연 후 닫은 후).

```
void RestoreWaitCursor();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>참고 항목

[MFC 샘플 ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)<br/>
[CDocument 클래스](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[CWinApp 클래스](../../mfc/reference/cwinapp-class.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[COleDispatchDriver 클래스](../../mfc/reference/coledispatchdriver-class.md)
