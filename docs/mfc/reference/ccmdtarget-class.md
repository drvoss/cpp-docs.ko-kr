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
ms.openlocfilehash: 1ef7040f3be1e4c30a6dc19e6093727299c9f1c3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752719"
---
# <a name="ccmdtarget-class"></a>CCmdTarget 클래스

Microsoft 재단 클래스 라이브러리 메시지 맵 아키텍처의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CCmdTarget : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CCmdTarget::CCmdTarget](#ccmdtarget)|`CCmdTarget` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|커서를 모래 시계 커서로 표시합니다.|
|[CCmdTarget::DoOleVerb](#dooleverb)|OLE 동사에 의해 지정된 작업을 수행합니다.|
|[CCmdTarget::EnableAutomation](#enableautomation)|개체에 대한 `CCmdTarget` OLE 자동화를 허용합니다.|
|[CCmdTarget::EnableConnections](#enableconnections)|연결 지점에서 이벤트를 발생시면 됩니다.|
|[CCmdTarget::EnableTypeLib](#enabletypelib)|개체의 형식 라이브러리를 활성화합니다.|
|[CCmdTarget::종료웨이트커서](#endwaitcursor)|이전 커서로 돌아갑니다.|
|[CCmdTarget::에누몰레베브](#enumoleverbs)|개체의 OLE 동사를 연수합니다.|
|[CCmdTarget::FromIDispatch](#fromidispatch)|포인터와 연결된 `CCmdTarget` 개체에 대한 `IDispatch` 포인터를 반환합니다.|
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|기본 디스패치 인터페이스 ID를 가져옵니다.|
|[CCmdTarget::GetIDispatch](#getidispatch)|개체와 연결된 `IDispatch` 개체에 대한 `CCmdTarget` 포인터를 반환합니다.|
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|개체가 제공하는 형식 정보 인터페이스 수를 검색합니다.|
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|지정된 된 GUID에 해당 하는 형식 설명을 검색 합니다.|
|[CCmdTarget::GetTypeLib](#gettypelib)|형식 라이브러리에 대한 포인터를 가져옵니다.|
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|형식 라이브러리 캐시를 가져옵니다.|
|[CCmdTarget::Invoke허용됨](#isinvokeallowed)|자동화 메서드 호출을 활성화합니다.|
|[CCmdTarget::예상결과](#isresultexpected)|자동화 함수가 값을 반환해야 하는 경우 0이 아닌 값을 반환합니다.|
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|명령 메시지를 라우팅하고 디스패치합니다.|
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|마지막 OLE 참조가 해제된 후 정리합니다.|
|[CCmdTarget::복원대기커](#restorewaitcursor)|모래시계 커서를 복원합니다.|

## <a name="remarks"></a>설명

메시지 맵은 명령 또는 메시지를 처리하기 위해 작성하는 멤버 함수에 라우팅합니다. 명령은 메뉴 항목, 명령 단추 또는 가속기 키의 메시지입니다.

에서 파생 된 `CCmdTarget` 주요 프레임 워크 클래스는 [CView,](../../mfc/reference/cview-class.md) [CWinApp,](../../mfc/reference/cwinapp-class.md) [CDocument,](../../mfc/reference/cdocument-class.md) [CWnd](../../mfc/reference/cwnd-class.md)및 [CFrameWnd](../../mfc/reference/cframewnd-class.md)를 포함합니다. 새 클래스가 메시지를 처리하려는 경우 이러한 `CCmdTarget`파생 클래스 중 하나에서 클래스를 파생시다. `CCmdTarget` 직접 클래스를 파생하는 경우는 거의 없습니다.

명령 대상 `OnCmdMsg` 및 라우팅에 대한 개요는 명령 [대상,](../../mfc/command-targets.md)명령 [라우팅](../../mfc/command-routing.md)및 매핑 [메시지를](../../mfc/mapping-messages.md)참조하십시오.

`CCmdTarget`에는 모래 시계 커서의 표시를 처리하는 멤버 기능이 포함됩니다. 명령이 실행되는 데 눈에 띄는 시간 간격이 걸릴 것으로 예상되는 경우 모래 시계 커서를 표시합니다.

메시지 맵과 유사한 디스패치 맵은 OLE `IDispatch` 자동화 기능을 노출하는 데 사용됩니다. 이 인터페이스를 노출하면 다른 응용 프로그램(예: Visual Basic)을 응용 프로그램에 호출할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="ccmdtargetbeginwaitcursor"></a><a name="beginwaitcursor"></a>CCmdTarget::시작대기커

명령이 실행되는 데 눈에 띄는 시간 간격이 걸릴 것으로 예상되는 경우 이 함수를 호출하여 커서를 모래 시계로 표시합니다.

```cpp
void BeginWaitCursor();
```

### <a name="remarks"></a>설명

프레임워크는 이 함수를 호출하여 `CDocument` 개체가 파일에 로드되거나 저장되는 경우와 같이 사용 중임을 사용자에게 표시합니다.

처리와 `BeginWaitCursor` 같은 `OnSetCursor` 다른 작업이 커서를 변경할 수 있기 때문에 의 동작이 단일 메시지 처리기 외부에서 항상 효과적인 것은 아닙니다.

이전 `EndWaitCursor` 커서를 복원하려면 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="ccmdtargetccmdtarget"></a><a name="ccmdtarget"></a>CCmdTarget::CCmdTarget

`CCmdTarget` 개체를 생성합니다.

```
CCmdTarget();
```

## <a name="ccmdtargetdooleverb"></a><a name="dooleverb"></a>CCmdTarget::DoOleVerb

OLE 동사에 의해 지정된 작업을 수행합니다.

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
동사를 호출한 이벤트(예: 두 번 클릭)를 설명하는 [MSG](/windows/win32/api/winuser/ns-winuser-msg) 구조에 대한 포인터입니다.

*hWnd부모*<br/>
개체가 포함된 문서 창의 핸들입니다.

*Lprect*<br/>
*hwndParent에서*오브젝트의 경계 사각형을 정의하는 좌표를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터.

### <a name="return-value"></a>Return Value

TRUE 성공, 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 [IOleObject::DoVerb의](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb)구현입니다. 가능한 작업은 [CCmdTarget::EnumOleVerbs에](#enumoleverbs)의해 열거됩니다.

## <a name="ccmdtargetenableautomation"></a><a name="enableautomation"></a>CCmdTarget::인에이블 자동화

개체에 대한 OLE 자동화를 사용하도록 설정하려면 이 함수를 호출합니다.

```cpp
void EnableAutomation();
```

### <a name="remarks"></a>설명

이 함수는 일반적으로 개체의 생성자에서 호출 되며 디스패치 맵 클래스에 대 한 선언 된 경우에 호출 해야 합니다. 자동화에 대한 자세한 내용은 [자동화 클라이언트](../../mfc/automation-clients.md) 및 자동화 [서버](../../mfc/automation-servers.md)문서를 참조하십시오.

## <a name="ccmdtargetenableconnections"></a><a name="enableconnections"></a>CCmdTarget::인에이블커넥션

연결 지점에서 이벤트를 발생시면 됩니다.

```cpp
void EnableConnections();
```

### <a name="remarks"></a>설명

연결 점을 활성화하려면 파생 클래스의 생성자에서 이 멤버 함수를 호출합니다.

## <a name="ccmdtargetenabletypelib"></a><a name="enabletypelib"></a>CCmdTarget::인에이블타입Lib

개체의 형식 라이브러리를 활성화합니다.

```cpp
void EnableTypeLib();
```

### <a name="remarks"></a>설명

형식 정보를 제공하는 경우 -derived 개체의 생성자에서 이 멤버 함수를 호출합니다. `CCmdTarget`

## <a name="ccmdtargetendwaitcursor"></a><a name="endwaitcursor"></a>CCmdTarget::종료웨이트커서

모래 시계 커서에서 `BeginWaitCursor` 이전 커서로 돌아가기 위해 멤버 함수를 호출한 후 이 함수를 호출합니다.

```cpp
void EndWaitCursor();
```

### <a name="remarks"></a>설명

프레임워크는 모래 시계 커서를 호출한 후에도 이 멤버 함수를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="ccmdtargetenumoleverbs"></a><a name="enumoleverbs"></a>CCmdTarget::에누몰레베브

개체의 OLE 동사를 연수합니다.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>매개 변수

*ppenumOleVerb*<br/>
[IEnumOLEVERB](/windows/win32/api/oleidl/nn-oleidl-ienumoleverb) 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 개체가 하나 이상의 OLE 동사를 지원하는 \* 경우(이 경우 *ppenumOleVerb는* 열거체 인터페이스를 `IEnumOLEVERB` 가리킵니다), 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 [IOleObject::AnumVerbs의](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs)구현입니다.

## <a name="ccmdtargetfromidispatch"></a><a name="fromidispatch"></a>CCmdTarget:::FromI디스패치

이 함수를 호출하여 클래스의 자동화 멤버 함수에서 받은 `IDispatch` `CCmdTarget` 포인터를 `IDispatch` 개체의 인터페이스를 구현하는 개체에 매핑합니다.

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>매개 변수

*lpDispatch*<br/>
`IDispatch` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

*lpDispatch와* `CCmdTarget` 연결된 개체에 대한 포인터입니다. 이 함수는 개체가 `IDispatch` Microsoft Foundation 클래스 `IDispatch` 개체로 인식되지 않으면 NULL을 반환합니다.

### <a name="remarks"></a>설명

이 함수의 결과는 멤버 함수에 `GetIDispatch`대한 호출의 역입니다.

## <a name="ccmdtargetgetdispatchiid"></a><a name="getdispatchiid"></a>CCmdTarget::GetDispatchIID

기본 디스패치 인터페이스 ID를 가져옵니다.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>매개 변수

*pIID*<br/>
인터페이스 ID에 대한 포인터([GUID](/windows/win32/api/guiddef/ns-guiddef-guiddef-guid-guid-guid.)

### <a name="return-value"></a>Return Value

TRUE 성공, 그렇지 않으면 거짓. 성공하면 \* *pIID가* 기본 디스패치 인터페이스 ID로 설정됩니다.

### <a name="remarks"></a>설명

파생 클래스는 이 멤버 함수를 재정의해야 `GetDispatchIID` 합니다(재정의하지 않으면 FALSE를 반환합니다). [COleControl](../../mfc/reference/colecontrol-class.md)을 참조하십시오.

## <a name="ccmdtargetgetidispatch"></a><a name="getidispatch"></a>CCmdTarget::GetIDispatch

이 멤버 함수를 `IDispatch` 호출하여 `IDispatch` 포인터를 반환하거나 참조로 포인터를 사용하는 자동화 메서드에서 포인터를 검색합니다. `IDispatch`

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>매개 변수

*bAddRef*<br/>
개체에 대한 참조 수를 증분할지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

개체와 연결된 `IDispatch` 포인터입니다.

### <a name="remarks"></a>설명

생성자에서 `EnableAutomation` 호출하는 개체의 경우 자동화를 사용하도록 설정하면 이 함수는 인터페이스를 통해 통신하는 클라이언트가 사용하는 Foundation Class 구현에 `IDispatch` 대한 포인터를 `IDispatch` 반환합니다. 이 함수를 호출하면 포인터에 대한 참조가 자동으로 추가되므로 [IUnknown:AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)를 호출할 필요가 없습니다.

## <a name="ccmdtargetgettypeinfocount"></a><a name="gettypeinfocount"></a>CCmdTarget::GetTypeInfoCount

개체가 제공하는 형식 정보 인터페이스 수를 검색합니다.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Return Value

형식 정보 인터페이스의 수입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 기본적으로 [IDispatch::GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount).

파생 클래스는 제공된 형식 정보 인터페이스(0 또는 1)의 수를 반환하기 위해 이 함수를 재정의해야 합니다. 재정의하지 않으면 `GetTypeInfoCount` 0을 반환합니다. 재정의 하려면 `GetTypeLib` 및 `GetTypeLibCache`도 구현 하는 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) 매크로를 사용 합니다.

## <a name="ccmdtargetgettypeinfoofguid"></a><a name="gettypeinfoofguid"></a>CCmdTarget::GetTypeInfoOfGuid

지정된 된 GUID에 해당 하는 형식 설명을 검색 합니다.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>매개 변수

*Lcid*<br/>
로캘 식별자 `LCID`().

*guid*<br/>
[GUID](/windows/win32/api/guiddef/ns-guiddef-guiddef-guid-guid.) 형식 설명입니다.

*ppTypeInfo*<br/>
인터페이스에 대한 포인터입니다. `ITypeInfo`

### <a name="return-value"></a>Return Value

호출의 성공 또는 실패를 나타내는 HRESULT입니다. 성공하면 \* *ppTypeInfo형식* 정보 인터페이스를 가리킵니다.

## <a name="ccmdtargetgettypelib"></a><a name="gettypelib"></a>CCmdTarget::GetTypeLib

형식 라이브러리에 대한 포인터를 가져옵니다.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>매개 변수

*Lcid*<br/>
LCID(로캘 식별자)입니다.

*ppTypeLib*<br/>
인터페이스에 대한 포인터에 `ITypeLib` 대한 포인터입니다.

### <a name="return-value"></a>Return Value

호출의 성공 또는 실패를 나타내는 HRESULT입니다. 성공하면 \* *ppTypeLib형식* 라이브러리 인터페이스를 가리킵니다.

### <a name="remarks"></a>설명

파생 클래스는 이 멤버 함수를 재정의해야 `GetTypeLib` 합니다(재정의되지 않은 경우 TYPE_E_CANTLOADLIBRARY 반환). `GetTypeInfoCount` 및 `GetTypeLibCache`도 구현하는 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) 매크로를 사용합니다.

## <a name="ccmdtargetgettypelibcache"></a><a name="gettypelibcache"></a>CCmdTarget::GetTypeLib캐시

형식 라이브러리 캐시를 가져옵니다.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Return Value

`CTypeLibCache` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

파생 클래스는 이 멤버 함수를 재정의해야 `GetTypeLibCache` 합니다(재정의되지 않은 경우 NULL을 반환). `GetTypeInfoCount` 및 `GetTypeLib`도 구현하는 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) 매크로를 사용합니다.

## <a name="ccmdtargetisinvokeallowed"></a><a name="isinvokeallowed"></a>CCmdTarget::Invoke허용됨

이 함수는 지정된 자동화 메서드(dispid로 식별)를 호출할 수 있는지 확인하기 `IDispatch::Invoke` 위해 MFC의 구현에 의해 호출됩니다. *dispid*

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>매개 변수

*디스피드 (것)들*<br/>
디스패치 ID입니다.

### <a name="return-value"></a>Return Value

TRUE 메서드를 호출할 수 있는 경우, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

TRUE를 `IsInvokeAllowed` `Invoke` 반환하면 메서드를 호출합니다. 그렇지 `Invoke` 않으면 E_UNEXPECTED 반환하여 실패합니다.

파생 클래스는 이 함수를 재정의하여 적절한 값을 반환할 수 있습니다(재정의하지 않은 경우 `IsInvokeAllowed` TRUE를 반환함). 특히 [COleControl을 참조하십시오::Invoke허용](../../mfc/reference/colecontrol-class.md#isinvokeallowed).

## <a name="ccmdtargetisresultexpected"></a><a name="isresultexpected"></a>CCmdTarget::예상결과

클라이언트가 자동화 함수에 대한 호출에서 반환 값을 예상하는지 여부를 확인하는 데 사용합니다. `IsResultExpected`

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Return Value

자동화 함수가 값을 반환해야 하는 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

OLE 인터페이스는 클라이언트가 함수 호출의 결과를 사용하거나 무시하는지 여부에 대한 정보를 MFC에 `IsResultExpected`제공하며, MFC는 이 정보를 사용하여 에 대한 호출 결과를 확인합니다. 반환 값의 생산이 시간 또는 리소스 집약적인 경우 반환 값을 계산하기 전에 이 함수를 호출하여 효율성을 높일 수 있습니다.

이 함수는 클라이언트가 호출한 자동화 함수에서 호출하는 경우 다른 자동화 함수에서 유효한 반환 값을 얻을 수 있도록 한 번만 0을 반환합니다.

`IsResultExpected`에서는 자동화 함수 호출이 진행 중일 때 호출된 경우 비영도 값을 반환합니다.

## <a name="ccmdtargetoncmdmsg"></a><a name="oncmdmsg"></a>CCmdTarget::OnCmdMsg

명령 메시지를 라우팅 및 디스패치하고 명령 사용자 인터페이스 개체의 업데이트를 처리하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
명령 ID를 포함합니다.

*nCode*<br/>
명령 알림 코드를 식별합니다. *nCode*의 값에 대한 자세한 내용은 **비고를** 참조하십시오.

*pExtra*<br/>
*nCode*의 값에 따라 사용됩니다. *pExtra에*대한 자세한 내용은 **비고를** 참조하십시오.

*pHandlerInfo*<br/>
NULL이 아닌 `OnCmdMsg` 경우 명령을 디스패치하는 대신 *pHandlerInfo* 구조의 *pTarget* 및 *pmf* 멤버를 채웁니다. 일반적으로 이 매개 변수는 NULL이어야 합니다.

### <a name="return-value"></a>Return Value

메시지가 처리되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

프레임워크 명령 아키텍처의 주요 구현 루틴입니다.

런타임에 `OnCmdMsg` 다른 개체에 명령을 디스패치하거나 실제 메시지 맵 조회를 수행하는 루트 클래스를 `CCmdTarget::OnCmdMsg`호출하여 명령 자체를 처리합니다. 기본 명령 라우팅에 대한 전체 설명은 [메시지 처리 및 매핑 항목을](../../mfc/message-handling-and-mapping.md)참조하십시오.

드문 경우지만 이 멤버 함수를 재정의하여 프레임워크의 표준 명령 라우팅을 확장할 수 있습니다. 명령 라우팅 아키텍처에 대한 고급 세부 정보는 [기술 참고 21을](../../mfc/tn021-command-and-message-routing.md) 참조하십시오.

재정의하는 `OnCmdMsg`경우 *nCode,* 명령 알림 코드 및 *pExtra에*대한 적절한 값을 제공해야 *nCode*합니다. 다음 표에는 해당 값이 나열되어 있습니다.

|*n코드* 값|*p추가* 값|
|-------------------|--------------------|
|CN_COMMAND|[Ccmdui](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|CN_UPDATE_COMMAND_UI|CCmdUI\*|
|CN_OLECOMMAND|[콜레cm두이](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

## <a name="ccmdtargetonfinalrelease"></a><a name="onfinalrelease"></a>CCmdTarget::최종 릴리스

개체에 대한 마지막 OLE 참조가 해제될 때 프레임워크에서 호출됩니다.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>설명

이 상황에 대 한 특별 한 처리를 제공 하려면이 함수를 재정의 합니다. 기본 구현은 개체를 삭제합니다.

## <a name="ccmdtargetrestorewaitcursor"></a><a name="restorewaitcursor"></a>CCmdTarget::복원대기커

시스템 커서가 변경된 후(예: 긴 작업 중에 메시지 상자를 열고 닫힌 후) 이 함수를 호출하여 적절한 모래시계 커서를 복원합니다.

```cpp
void RestoreWaitCursor();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)<br/>
[C문서 클래스](../../mfc/reference/cdocument-class.md)<br/>
[CDoc템플릿 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[CWinApp 클래스](../../mfc/reference/cwinapp-class.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[올레디스패치드라이버 클래스](../../mfc/reference/coledispatchdriver-class.md)
