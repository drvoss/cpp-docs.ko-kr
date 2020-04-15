---
title: CMessageMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
ms.openlocfilehash: a822f36d6b6fd49301d8240324e27f0ad9ce52e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326717"
---
# <a name="cmessagemap-class"></a>CMessageMap 클래스

이 클래스를 사용하면 개체의 메시지 맵을 다른 개체에서 액세스할 수 있습니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class ATL_NO_VTABLE CMessageMap
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMessageMap::P로세스윈도우메시지](#processwindowmessage)|-derived 클래스의 `CMessageMap`메시지 맵에 액세스합니다.|

## <a name="remarks"></a>설명

`CMessageMap`는 개체의 메시지 맵을 다른 개체에서 액세스할 수 있는 추상 기본 클래스입니다. 개체가 메시지 맵을 노출하려면 해당 클래스에서 `CMessageMap`파생되어야 합니다.

ATL은 `CMessageMap` 포함된 창 및 동적 메시지 맵 체인을 지원하는 데 사용합니다. 예를 들어 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 개체를 포함하는 모든 `CMessageMap`클래스는 에서 파생되어야 합니다. 다음 코드는 [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) 샘플에서 가져온 것입니다. [CComControl을](../../atl/reference/ccomcontrol-class.md)통해 `CAtlEdit` 클래스는 자동으로 `CMessageMap`에서 파생됩니다.

[!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]

포함된 창은 `m_EditCtrl`을 포함하는 클래스에서 메시지 맵을 `CAtlEdit` 사용하므로 `CMessageMap`에서 파생됩니다.

메시지 맵에 대한 자세한 내용은 "ATL 창 클래스"의 [메시지 맵을](../../atl/message-maps-atl.md) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="cmessagemapprocesswindowmessage"></a><a name="processwindowmessage"></a>CMessageMap::P로세스윈도우메시지

-derived 클래스에서 *dwMsgMapID로* `CMessageMap`식별된 메시지 맵에 액세스합니다.

```
virtual BOOL ProcessWindowMessage(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```

### <a name="parameters"></a>매개 변수

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

*dwMsgMapID*<br/>
【인】 메시지를 처리할 메시지 맵의 식별자입니다. [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)선언된 기본 메시지 맵은 0으로 식별됩니다. [ALT_MSG_MAP(msgMapID)로](message-map-macros-atl.md#alt_msg_map)선언된 대체 메시지 맵은 `msgMapID`에 의해 식별됩니다.

### <a name="return-value"></a>Return Value

TRUE 메시지가 완전히 처리되는 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

[CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 개체또는 메시지 맵에 동적으로 연결되는 개체의 창 프로시저에서 호출됩니다.

## <a name="see-also"></a>참고 항목

[CDynamicChain 클래스](../../atl/reference/cdynamicchain-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
