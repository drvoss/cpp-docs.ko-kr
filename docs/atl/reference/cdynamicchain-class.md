---
title: CDynamicChain 클래스
ms.date: 11/04/2016
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
ms.openlocfilehash: 4a72b3b4308ed83dfdc4a2895a04d1fe9a177ce5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327028"
---
# <a name="cdynamicchain-class"></a>CDynamicChain 클래스

이 클래스는 메시지 맵의 동적 체인을 지원하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CDynamicChain
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDynamicChain::CDynamicChain](#cdynamicchain)|생성자입니다.|
|[CDynamicChain::~CDynamicChain](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDynamicChain::콜체인](#callchain)|Windows 메시지를 다른 개체의 메시지 맵으로 보신다.|
|[CDynamicChain::리크체인엔트리](#removechainentry)|컬렉션에서 메시지 맵 항목을 제거합니다.|
|[CDynamicChain::세트체인엔트리](#setchainentry)|컬렉션에 메시지 맵 항목을 추가하거나 기존 항목을 수정합니다.|

## <a name="remarks"></a>설명

`CDynamicChain`는 메시지 맵 컬렉션을 관리하여 런타임에 Windows 메시지를 다른 개체의 메시지 맵으로 지시할 수 있습니다.

메시지 맵의 동적 연결에 대한 지원을 추가하려면 다음을 수행합니다.

- 에서 클래스를 `CDynamicChain`파생합니다. 메시지 맵에서 [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) 매크로를 지정하여 다른 개체의 기본 메시지 맵에 연결합니다.

- [CMessageMap에서](../../atl/reference/cmessagemap-class.md)연결하려는 모든 클래스를 파생합니다. `CMessageMap`을 사용하면 개체가 메시지 맵을 다른 개체에 노출할 수 있습니다.

- 연결할 `CDynamicChain::SetChainEntry` 개체와 연결할 메시지 맵을 식별하기 위해 호출합니다.

예를 들어 클래스가 다음과 같이 정의되어 있다고 가정합니다.

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

그런 다음 `CMyWindow::SetChainEntry`클라이언트는 다음을 호출합니다.

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

여기서 `chainedObj` 연결된 개체이며 `CMessageMap`에서 파생된 클래스의 인스턴스입니다. `myCtl` 이제 `OnPaint` 처리되지 `OnSetFocus`않은 메시지를 받으면 창 프로시저가 메시지를 기본 `chainedObj`메시지 맵으로 지시합니다.

메시지 맵 체인에 대한 자세한 내용은 "ATL 창 클래스"의 [메시지 맵을](../../atl/message-maps-atl.md) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="cdynamicchaincallchain"></a><a name="callchain"></a>CDynamicChain::콜체인

Windows 메시지를 다른 개체의 메시지 맵으로 보신다.

```
BOOL CallChain(
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```

### <a name="parameters"></a>매개 변수

*dwChainID*<br/>
【인】 연결된 개체 및 해당 메시지 맵과 연결된 고유 식별자입니다.

*Hwnd*<br/>
【인】 메시지를 받는 창에 대한 핸들입니다.

*uMsg*<br/>
【인】 창으로 전송된 메시지입니다.

*wParam*<br/>
【인】 추가 메시지 관련 정보입니다.

*lParam*<br/>
【인】 추가 메시지 관련 정보입니다.

*l결과*<br/>
【아웃】 메시지 처리의 결과입니다.

### <a name="return-value"></a>Return Value

TRUE 메시지가 완전히 처리되는 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

창 프로시저를 호출하려면 `CallChain`메시지 맵에서 [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) 매크로를 지정해야 합니다. 예를 들어 [CDynamicChain](../../atl/reference/cdynamicchain-class.md) 개요를 참조하십시오.

`CallChain`*dwChainID* 값을 개체 및 메시지 맵과 연결하려면 [SetChainEntry에](#setchainentry) 대한 이전 호출이 필요합니다.

## <a name="cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a>CDynamicChain::CDynamicChain

생성자입니다.

```
CDynamicChain();
```

## <a name="cdynamicchaincdynamicchain"></a><a name="dtor"></a>CDynamicChain::~CDynamicChain

소멸자입니다.

```
~CDynamicChain();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제합니다.

## <a name="cdynamicchainremovechainentry"></a><a name="removechainentry"></a>CDynamicChain::리크체인엔트리

컬렉션에서 지정된 메시지 맵을 제거합니다.

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>매개 변수

*dwChainID*<br/>
【인】 연결된 개체 및 해당 메시지 맵과 연결된 고유 식별자입니다. 원래 [SetChainEntry](#setchainentry)에 대한 호출을 통해 이 값을 정의합니다.

### <a name="return-value"></a>Return Value

TRUE 메시지 맵이 컬렉션에서 성공적으로 제거된 경우 그렇지 않으면 FALSE입니다.

## <a name="cdynamicchainsetchainentry"></a><a name="setchainentry"></a>CDynamicChain::세트체인엔트리

지정된 메시지 맵을 컬렉션에 추가합니다.

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>매개 변수

*dwChainID*<br/>
【인】 연결된 개체 및 해당 메시지 맵과 연결된 고유 식별자입니다.

*pObject*<br/>
【인】 메시지 맵을 선언하는 연결된 개체에 대한 포인터입니다. 이 개체는 [CMessageMap](../../atl/reference/cmessagemap-class.md)에서 파생되어야 합니다.

*dwMsgMapID*<br/>
【인】 체인된 개체의 메시지 맵의 식별자입니다. 기본값은 0이며 BEGIN_MSG_MAP [선언된](message-map-macros-atl.md#begin_msg_map)기본 메시지 맵을 식별합니다. [ALT_MSG_MAP(msgMapID)로](message-map-macros-atl.md#alt_msg_map)선언된 대체 메시지 맵을 지정하려면 을 전달합니다. `msgMapID`

### <a name="return-value"></a>Return Value

메시지 맵이 컬렉션에 성공적으로 추가된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

*dwChainID* 값이 컬렉션에 이미 있는 경우 해당 관련 개체 및 메시지 맵은 각각 *pObject* 및 *dwMsmapID로*대체됩니다. 그렇지 않으면 새 항목이 추가됩니다.

## <a name="see-also"></a>참고 항목

[크윈도우임플 클래스](../../atl/reference/cwindowimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
