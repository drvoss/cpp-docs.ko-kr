---
title: 메시지 맵 매크로(ATL)
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::ALT_MSG_MAP
- atlwin/ATL::BEGIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_ALT
- atlwin/ATL::CHAIN_MSG_MAP_ALT_MEMBER
- atlwin/ATL::CHAIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_DYNAMIC
- atlwin/ATL::CHAIN_MSG_MAP_MEMBER
- atlwin/ATL::COMMAND_CODE_HANDLER
- atlwin/ATL::COMMAND_HANDLER
- atlwin/ATL::COMMAND_ID_HANDLER
- atlwin/ATL::COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::COMMAND_RANGE_HANDLER
- atlwin/ATL::DECLARE_EMPTY_MSG_MAP
- atlwin/ATL::DEFAULT_REFLECTION_HANDLER
- atlwin/ATL::END_MSG_MAP
- atlwin/ATL::FORWARD_NOTIFICATIONS
- atlwin/ATL::MESSAGE_HANDLER
- atlwin/ATL::MESSAGE_RANGE_HANDLER
- atlwin/ATL::NOTIFY_CODE_HANDLER
- atlwin/ATL::NOTIFY_HANDLER
- atlwin/ATL::NOTIFY_ID_HANDLER
- atlwin/ATL::NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::NOTIFY_RANGE_HANDLER
- atlwin/ATL::REFLECT_NOTIFICATIONS
- atlwin/ATL::REFLECTED_COMMAND_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_ID_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_ID_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_HANDLER
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
ms.openlocfilehash: 157812fa6625869c86dd8a27156a2970a3dc8d4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326224"
---
# <a name="message-map-macros-atl"></a>메시지 맵 매크로(ATL)

이러한 매크로는 메시지 맵과 항목을 정의합니다.

|||
|-|-|
|[ALT_MSG_MAP](#alt_msg_map)|대체 메시지 맵의 시작을 표시합니다.|
|[BEGIN_MSG_MAP](#begin_msg_map)|기본 메시지 맵의 시작을 표시합니다.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|기본 클래스의 대체 메시지 맵으로 체인합니다.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|클래스의 데이터 멤버에서 대체 메시지 맵으로 체인합니다.|
|[CHAIN_MSG_MAP](#chain_msg_map)|기본 클래스의 기본 메시지 맵에 대한 체인입니다.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|런타임에 다른 클래스의 메시지 맵에 대한 체인입니다.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|클래스의 데이터 멤버의 기본 메시지 맵으로 체인합니다.|
|[COMMAND_CODE_HANDLER](#command_code_handler)|알림 코드에 따라 처리기 함수에 WM_COMMAND 메시지를 매핑합니다.|
|[COMMAND_HANDLER](#command_handler)|알림 코드와 메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 처리기 함수에 WM_COMMAND 메시지를 매핑합니다.|
|[COMMAND_ID_HANDLER](#command_id_handler)|메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 처리기 함수에 WM_COMMAND 메시지를 매핑합니다.|
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|알림 코드와 연속적인 제어 식별자를 기반으로 처리기 함수에 WM_COMMAND 메시지를 매핑합니다.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|연속적인 제어 식별자 범위를 기반으로 처리기 함수에 WM_COMMAND 메시지를 매핑합니다.|
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|빈 메시지 맵을 구현합니다.|
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|그렇지 않으면 처리되지 않은 반사된 메시지에 대한 기본 처리기를 제공합니다.|
|[END_MSG_MAP](#end_msg_map)|메시지 맵의 끝을 표시합니다.|
|[FORWARD_NOTIFICATIONS](#forward_notifications)|알림 메시지를 부모 창으로 전달합니다.|
|[MESSAGE_HANDLER](#message_handler)|처리기 함수에 Windows 메시지를 매핑합니다.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|처리기 함수에 연속된 범위의 Windows 메시지를 매핑합니다.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|알림 코드에 따라 처리기 함수에 WM_NOTIFY 메시지를 매핑합니다.|
|[NOTIFY_HANDLER](#notify_handler)|알림 코드 및 컨트롤 식별자를 기반으로 처리기 함수에 WM_NOTIFY 메시지를 매핑합니다.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|컨트롤 식별자를 기반으로 처리기 함수에 WM_NOTIFY 메시지를 매핑합니다.|
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|알림 코드및 연속적인 제어 식별자 범위를 기반으로 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|연속적인 제어 식별자 범위를 기반으로 처리기 함수에 WM_NOTIFY 메시지를 매핑합니다.|
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|알림 메시지를 보낸 창으로 다시 반영합니다.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|알림 코드를 기반으로 반영된 WM_COMMAND 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|알림 코드와 메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 반영된 WM_COMMAND 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 반영된 WM_COMMAND 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|알림 코드 및 연속적인 제어 식별자를 기반으로 반영된 WM_COMMAND 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|연속적인 제어 식별자 범위를 기반으로 반영된 WM_COMMAND 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|알림 코드에 따라 반영된 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|알림 코드 및 컨트롤 식별자를 기반으로 반영된 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|컨트롤 식별자를 기반으로 반영된 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|알림 코드 및 연속적인 제어 식별자를 기반으로 반영된 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|연속적인 제어 식별자 범위를 기반으로 반영된 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="alt_msg_map"></a><a name="alt_msg_map"></a>ALT_MSG_MAP

대체 메시지 맵의 시작을 표시합니다.

```
ALT_MSG_MAP(msgMapID)
```

### <a name="parameters"></a>매개 변수

*msgMapID*<br/>
【인】 메시지 맵 식별자입니다.

### <a name="remarks"></a>설명

ATL은 숫자로 각 메시지 맵을 식별합니다. 기본 메시지 맵(BEGIN_MSG_MAP 매크로로 선언됨)은 0으로 식별됩니다. 대체 메시지 맵은 *msgMapID*로 식별됩니다.

메시지 맵은 창으로 전송된 메시지를 처리하는 데 사용됩니다. 예를 들어 [CContainedWindow를](../../atl/reference/ccontainedwindowt-class.md) 사용하면 포함된 개체에서 메시지 맵의 식별자를 지정할 수 있습니다. [CContainedWindow::WindowProc다음이](ccontainedwindowt-class.md#windowproc) 메시지 맵을 사용 하 여 포함 된 창의 메시지를 적절 한 처리기 함수 또는 다른 메시지 맵에 지시 합니다. 처리기 함수를 선언하는 매크로 목록은 [BEGIN_MSG_MAP](#begin_msg_map)을 참조하십시오.

항상 BEGIN_MSG_MAP 함께 메시지 맵을 시작합니다. 그런 다음 후속 대체 메시지 맵을 선언할 수 있습니다.

[END_MSG_MAP](#end_msg_map) 매크로는 메시지 맵의 끝을 표시합니다. BEGIN_MSG_MAP END_MSG_MAP 인스턴스는 항상 정확히 하나입니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 기본 메시지 맵과 하나의 대체 메시지 맵을 보여 주며 각 예제에는 하나의 처리기 함수가 포함되어 있습니다.

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

다음 예제에서는 두 개의 대체 메시지 맵을 보여 주십습니다. 기본 메시지 맵이 비어 있습니다.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="begin_msg_map"></a><a name="begin_msg_map"></a>BEGIN_MSG_MAP

기본 메시지 맵의 시작을 표시합니다.

```
BEGIN_MSG_MAP(theClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
【인】 메시지 맵을 포함하는 클래스의 이름입니다.

### <a name="remarks"></a>설명

[CWindowImpl::WindowProc는](cwindowimpl-class.md#windowproc) 기본 메시지 맵을 사용하여 창으로 전송된 메시지를 처리합니다. 메시지 맵은 메시지를 적절한 처리기 함수 또는 다른 메시지 맵으로 안내합니다.

다음 매크로는 메시지를 처리기 함수에 매핑합니다. 이 *함수는 Class*에 정의되어야 합니다.

|매크로|Description|
|-----------|-----------------|
|[MESSAGE_HANDLER](#message_handler)|처리기 함수에 Windows 메시지를 매핑합니다.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|처리기 함수에 연속된 범위의 Windows 메시지를 매핑합니다.|
|[COMMAND_HANDLER](#command_handler)|알림 코드와 메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 처리기 함수에 WM_COMMAND 메시지를 매핑합니다.|
|[COMMAND_ID_HANDLER](#command_id_handler)|메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 처리기 함수에 WM_COMMAND 메시지를 매핑합니다.|
|[COMMAND_CODE_HANDLER](#command_handler)|알림 코드에 따라 처리기 함수에 WM_COMMAND 메시지를 매핑합니다.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 처리기 함수에 연속WM_COMMAND 메시지 범위를 매핑합니다.|
|[NOTIFY_HANDLER](#notify_handler)|알림 코드 및 컨트롤 식별자를 기반으로 처리기 함수에 WM_NOTIFY 메시지를 매핑합니다.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|컨트롤 식별자를 기반으로 처리기 함수에 WM_NOTIFY 메시지를 매핑합니다.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|알림 코드에 따라 처리기 함수에 WM_NOTIFY 메시지를 매핑합니다.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|컨트롤 식별자를 기반으로 연속 WM_NOTIFY 메시지 범위를 처리기 함수에 매핑합니다.|

다음 매크로는 메시지를 다른 메시지 맵으로 안내합니다. 이 프로세스를 "체인"이라고 합니다.

|매크로|Description|
|-----------|-----------------|
|[CHAIN_MSG_MAP](#chain_msg_map)|기본 클래스의 기본 메시지 맵에 대한 체인입니다.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|클래스의 데이터 멤버의 기본 메시지 맵으로 체인합니다.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|기본 클래스의 대체 메시지 맵으로 체인합니다.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|클래스의 데이터 멤버에서 대체 메시지 맵으로 체인합니다.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|런타임에 다른 클래스의 기본 메시지 맵으로 체인을 설정합니다.|

다음 매크로는 부모 창에서 "반영된" 메시지를 직접"합니다. 예를 들어 컨트롤은 일반적으로 처리를 위해 부모 창으로 알림 메시지를 보내지만 부모 창은 메시지를 컨트롤에 다시 반영할 수 있습니다.

|매크로|Description|
|-----------|-----------------|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|알림 코드와 메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 반영된 WM_COMMAND 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 반영된 WM_COMMAND 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|알림 코드를 기반으로 반영된 WM_COMMAND 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|연속적인 제어 식별자 범위를 기반으로 반영된 WM_COMMAND 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|알림 코드 및 연속적인 제어 식별자를 기반으로 반영된 WM_COMMAND 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|알림 코드 및 컨트롤 식별자를 기반으로 반영된 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|컨트롤 식별자를 기반으로 반영된 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|알림 코드에 따라 반영된 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|연속적인 제어 식별자 범위를 기반으로 반영된 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|알림 코드 및 연속적인 제어 식별자를 기반으로 반영된 WM_NOTIFY 메시지를 처리기 함수에 매핑합니다.|

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]

개체가 `CMyExtWindow` WM_PAINT 메시지를 받으면 실제 처리를 `CMyExtWindow::OnPaint` 위해 메시지가 전달됩니다. 메시지가 `OnPaint` 추가 처리가 필요하다는 것을 나타내는 경우 메시지가 `CMyBaseWindow`의 기본 메시지 맵으로 이동합니다.

기본 메시지 맵 외에도 [ALT_MSG_MAP.](#alt_msg_map) 항상 BEGIN_MSG_MAP 함께 메시지 맵을 시작합니다. 그런 다음 후속 대체 메시지 맵을 선언할 수 있습니다. 다음 예제에서는 기본 메시지 맵과 하나의 대체 메시지 맵을 보여 주며 각 예제에는 하나의 처리기 함수가 포함되어 있습니다.

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

다음 예제에서는 두 개의 대체 메시지 맵을 보여 주십습니다. 기본 메시지 맵이 비어 있습니다.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

[END_MSG_MAP](#end_msg_map) 매크로는 메시지 맵의 끝을 표시합니다. BEGIN_MSG_MAP END_MSG_MAP 인스턴스는 항상 정확히 하나입니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="chain_msg_map_alt"></a><a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT

메시지 맵에서 항목을 정의합니다.

```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```

### <a name="parameters"></a>매개 변수

*체인 클래스*<br/>
【인】 메시지 맵을 포함하는 기본 클래스의 이름입니다.

*msgMapID*<br/>
【인】 메시지 맵 식별자입니다.

### <a name="remarks"></a>설명

CHAIN_MSG_MAP_ALT 기본 클래스의 대체 메시지 맵으로 메시지를 지시합니다. [ALT_MSG_MAP(msgMapID)를](#alt_msg_map)사용하여 이 대체 메시지 맵을 선언해야 합니다. 기본 클래스의 기본 메시지 [맵(BEGIN_MSG_MAP](#begin_msg_map)선언됨)으로 메시지를 배달하려면 CHAIN_MSG_MAP 사용합니다. 예를 들어 [CHAIN_MSG_MAP](#chain_msg_map)를 참조하십시오.

> [!NOTE]
> 항상 BEGIN_MSG_MAP 함께 메시지 맵을 시작합니다. 그런 다음 ALT_MSG_MAP 함께 후속 대체 메시지 맵을 선언할 수 있습니다. [END_MSG_MAP](#end_msg_map) 매크로는 메시지 맵의 끝을 표시합니다. 모든 메시지 맵에는 정확히 하나의 BEGIN_MSG_MAP 및 END_MSG_MAP 인스턴스가 있어야 합니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="chain_msg_map_alt_member"></a><a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER

메시지 맵에서 항목을 정의합니다.

```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```

### <a name="parameters"></a>매개 변수

*체인 멤버*<br/>
【인】 메시지 맵을 포함하는 데이터 멤버의 이름입니다.

*msgMapID*<br/>
【인】 메시지 맵 식별자입니다.

### <a name="remarks"></a>설명

CHAIN_MSG_MAP_ALT_MEMBER 데이터 멤버의 대체 메시지 맵으로 메시지를 배달합니다. [ALT_MSG_MAP(msgMapID)를](#alt_msg_map)사용하여 이 대체 메시지 맵을 선언해야 합니다. BEGIN_MSG_MAP 선언된 데이터 멤버의 기본 메시지 맵으로 메시지를 배달하려면 CHAIN_MSG_MAP_MEMBER 사용합니다. [BEGIN_MSG_MAP](#begin_msg_map) 예를 들어 [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)를 참조하십시오.

> [!NOTE]
> 항상 BEGIN_MSG_MAP 함께 메시지 맵을 시작합니다. 그런 다음 ALT_MSG_MAP 함께 후속 대체 메시지 맵을 선언할 수 있습니다. [END_MSG_MAP](#end_msg_map) 매크로는 메시지 맵의 끝을 표시합니다. 모든 메시지 맵에는 정확히 하나의 BEGIN_MSG_MAP 및 END_MSG_MAP 인스턴스가 있어야 합니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="chain_msg_map"></a><a name="chain_msg_map"></a>CHAIN_MSG_MAP

메시지 맵에서 항목을 정의합니다.

```
CHAIN_MSG_MAP(theChainClass)
```

### <a name="parameters"></a>매개 변수

*체인 클래스*<br/>
【인】 메시지 맵을 포함하는 기본 클래스의 이름입니다.

### <a name="remarks"></a>설명

CHAIN_MSG_MAP 기본 클래스의 기본 메시지 [맵(BEGIN_MSG_MAP](#begin_msg_map)선언됨)으로 메시지를 안내합니다. 기본 클래스의 대체 메시지 [맵(ALT_MSG_MAP](#alt_msg_map)선언됨)으로 메시지를 배달하려면 [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)을 사용합니다.

> [!NOTE]
> 항상 BEGIN_MSG_MAP 함께 메시지 맵을 시작합니다. 그런 다음 ALT_MSG_MAP 함께 후속 대체 메시지 맵을 선언할 수 있습니다. [END_MSG_MAP](#end_msg_map) 매크로는 메시지 맵의 끝을 표시합니다. 모든 메시지 맵에는 정확히 하나의 BEGIN_MSG_MAP 및 END_MSG_MAP 인스턴스가 있어야 합니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]

이 예제에서는 다음을 보여 줍니다.

- 창 프로시저가 `CMyClass`'기본 메시지 맵'을 사용하고 있고 `OnPaint` 메시지를 처리하지 `CMyBaseClass`않는 경우 메시지는 처리를 위한 기본 메시지 맵으로 이동됩니다.

- 창 프로시저가 에서 `CMyClass`첫 번째 대체 메시지 맵을 `CMyBaseClass`사용하는 경우 모든 메시지는 기본 메시지 맵으로 이동합니다.

- 창 프로시저가 `CMyClass`두 번째 대체 메시지 `OnChar` 맵을 사용하고 있고 메시지를 처리하지 않는 경우 `CMyBaseClass`메시지가 에서 지정된 대체 메시지 맵으로 이동됩니다. `CMyBaseClass`ALT_MSG_MAP(1)로 이 메시지 맵을 선언해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="chain_msg_map_dynamic"></a><a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC

메시지 맵에서 항목을 정의합니다.

```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```

### <a name="parameters"></a>매개 변수

*다이나체인ID*<br/>
【인】 개체의 메시지 맵에 대한 고유 식별자입니다.

### <a name="remarks"></a>설명

CHAIN_MSG_MAP_DYNAMIC 런타임에 메시지를 다른 개체의 기본 메시지 맵으로 안내합니다. 개체 및 해당 메시지 맵은 [CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry)를 통해 정의하는 *dynaChainID와*연결됩니다. CHAIN_MSG_MAP_DYNAMIC 사용하려면 클래스를 `CDynamicChain` 파생시켜야 합니다. 예를 들어 [CDynamicChain](../../atl/reference/cdynamicchain-class.md) 개요를 참조하십시오.

> [!NOTE]
> 항상 [BEGIN_MSG_MAP](#begin_msg_map)함께 메시지 맵을 시작합니다. 그런 다음 ALT_MSG_MAP 함께 후속 대체 메시지 맵을 선언할 수 있습니다. [END_MSG_MAP](#end_msg_map) 매크로는 메시지 맵의 끝을 표시합니다. 모든 메시지 맵에는 정확히 하나의 BEGIN_MSG_MAP 및 END_MSG_MAP 인스턴스가 있어야 합니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="chain_msg_map_member"></a><a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER

메시지 맵에서 항목을 정의합니다.

```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```

### <a name="parameters"></a>매개 변수

*체인 멤버*<br/>
【인】 메시지 맵을 포함하는 데이터 멤버의 이름입니다.

### <a name="remarks"></a>설명

CHAIN_MSG_MAP_MEMBER 메시지를 데이터 멤버의 기본 메시지 [맵(BEGIN_MSG_MAP](#begin_msg_map)선언됨)으로 안내합니다. 데이터 멤버의 대체 메시지 [맵(ALT_MSG_MAP](#alt_msg_map)선언됨)으로 메시지를 배달하려면 [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)을 사용합니다.

> [!NOTE]
> 항상 BEGIN_MSG_MAP 함께 메시지 맵을 시작합니다. 그런 다음 ALT_MSG_MAP 함께 후속 대체 메시지 맵을 선언할 수 있습니다. [END_MSG_MAP](#end_msg_map) 매크로는 메시지 맵의 끝을 표시합니다. 모든 메시지 맵에는 정확히 하나의 BEGIN_MSG_MAP 및 END_MSG_MAP 인스턴스가 있어야 합니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]

이 예제에서는 다음을 보여 줍니다.

- 창 프로시저가 `CMyClass`'기본 메시지 맵'을 사용하고 있고 `OnPaint` 메시지를 처리하지 `m_obj`않는 경우 메시지는 처리를 위한 기본 메시지 맵으로 이동됩니다.

- 창 프로시저가 에서 `CMyClass`첫 번째 대체 메시지 맵을 `m_obj`사용하는 경우 모든 메시지는 기본 메시지 맵으로 이동합니다.

- 창 프로시저가 `CMyClass`두 번째 대체 메시지 `OnChar` 맵을 사용하고 있고 메시지를 처리하지 않는 경우 `m_obj`메시지는 의 지정된 대체 메시지 맵으로 이동됩니다. 클래스는 `CMyContainedClass` ALT_MSG_MAP(1)로 이 메시지 맵을 선언해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="command_code_handler"></a><a name="command_code_handler"></a>COMMAND_CODE_HANDLER

[COMMAND_HANDLER](#command_handler)비슷하지만 알림 코드에만 WM_COMMAND [메시지를](/windows/win32/menurc/wm-command) 매핑합니다.

```
COMMAND_CODE_HANDLER(code, func)
```

### <a name="parameters"></a>매개 변수

*코드*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="command_handler"></a><a name="command_handler"></a>COMMAND_HANDLER

메시지 맵에서 항목을 정의합니다.

```
COMMAND_HANDLER(id, code, func)
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 메뉴 항목, 컨트롤 또는 가속기의 식별자입니다.

*코드*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

COMMAND_HANDLER 알림 코드 및 컨트롤 식별자를 기반으로 지정된 처리기 함수에 [WM_COMMAND](/windows/win32/menurc/wm-command) 메시지를 매핑합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]

COMMAND_HANDLER 매크로에 지정된 모든 함수는 다음과 같이 정의되어야 합니다.

`LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`

전에 `CommandHandler` TRUE로 `bHandled` 설정된 메시지 맵이 호출됩니다. 메시지를 `CommandHandler` 완전히 처리하지 못하면 메시지가 `bHandled` 추가 처리가 필요함을 나타내기 위해 FALSE로 설정해야 합니다.

> [!NOTE]
> 항상 [BEGIN_MSG_MAP](#begin_msg_map)함께 메시지 맵을 시작합니다. 그런 다음 [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) 매크로는 메시지 맵의 끝을 표시합니다. 모든 메시지 맵에는 정확히 하나의 BEGIN_MSG_MAP 및 END_MSG_MAP 인스턴스가 있어야 합니다.

COMMAND_HANDLER 외에도 [MESSAGE_HANDLER](#message_handler) 사용하여 식별자 나 코드에 관계없이 WM_COMMAND 메시지를 매핑 할 수 있습니다. 이 경우 `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` 모든 WM_COMMAND 메시지를 `OnHandlerFunction`로 지시합니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="command_id_handler"></a><a name="command_id_handler"></a>COMMAND_ID_HANDLER

[COMMAND_HANDLER](#command_handler)비슷하지만 메뉴 항목, 컨트롤 또는 가속기의 식별자만 을 기반으로 [WM_COMMAND](/windows/win32/menurc/wm-command) 메시지를 매핑합니다.

```
COMMAND_ID_HANDLER(id, func)
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 메시지를 보내는 메뉴 항목, 컨트롤 또는 가속기의 식별자입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="command_range_code_handler"></a><a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER

[COMMAND_RANGE_HANDLER](#command_range_handler)비슷하지만 컨트롤 범위에서 단일 처리기 함수에 대한 특정 알림 코드가 있는 [메시지를 WM_COMMAND](/windows/win32/menurc/wm-command) 매핑합니다.

```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```

### <a name="parameters"></a>매개 변수

*idFirst*<br/>
【인】 연속 범위의 컨트롤 식별자의 시작을 표시합니다.

*idLast*<br/>
【인】 연속 된 컨트롤 식별자의 끝을 표시 합니다.

*코드*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

이 범위는 메시지를 보내는 메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="command_range_handler"></a><a name="command_range_handler"></a>COMMAND_RANGE_HANDLER

[COMMAND_HANDLER](#command_handler)비슷하지만 다양한 컨트롤에서 단일 처리기 함수로 [WM_COMMAND](/windows/win32/menurc/wm-command) 메시지를 매핑합니다.

```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```

### <a name="parameters"></a>매개 변수

*idFirst*<br/>
【인】 연속 범위의 컨트롤 식별자의 시작을 표시합니다.

*idLast*<br/>
【인】 연속 된 컨트롤 식별자의 끝을 표시 합니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

이 범위는 메시지를 보내는 메뉴 항목, 컨트롤 또는 가속기의 식별자를 기반으로 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="declare_empty_msg_map"></a><a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP

빈 메시지 맵을 선언합니다.

```
DECLARE_EMPTY_MSG_MAP()
```

### <a name="remarks"></a>설명

DECLARE_EMPTY_MSG_MAP [매크로BEGIN_MSG_MAP](#begin_msg_map) [호출하고](#end_msg_map) END_MSG_MAP 빈 메시지 맵을 만드는 편리한 매크로입니다.

[!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]

## <a name="default_reflection_handler"></a><a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER

반영된 메시지를 받을 자식 창(컨트롤)에 대한 기본 처리기를 제공합니다. 처리기가 처리되지 않은 메시지를 `DefWindowProc`에 제대로 전달합니다.

```
DEFAULT_REFLECTION_HANDLER()
```

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="end_msg_map"></a><a name="end_msg_map"></a>END_MSG_MAP

메시지 맵의 끝을 표시합니다.

```
END_MSG_MAP()
```

### <a name="remarks"></a>설명

항상 [BEGIN_MSG_MAP](#begin_msg_map) 매크로를 사용하여 메시지 맵의 시작을 표시합니다. [ALT_MSG_MAP](#alt_msg_map) 사용하여 후속 대체 메시지 맵을 선언합니다.

BEGIN_MSG_MAP END_MSG_MAP 인스턴스는 항상 정확히 하나입니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 기본 메시지 맵과 하나의 대체 메시지 맵을 보여 주며 각 예제에는 하나의 처리기 함수가 포함되어 있습니다.

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

다음 예제에서는 두 개의 대체 메시지 맵을 보여 주십습니다. 기본 메시지 맵이 비어 있습니다.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="forward_notifications"></a><a name="forward_notifications"></a>FORWARD_NOTIFICATIONS

알림 메시지를 부모 창으로 전달합니다.

```
FORWARD_NOTIFICATIONS()
```

### <a name="remarks"></a>설명

이 매크로를 메시지 맵의 일부로 지정합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="message_handler"></a><a name="message_handler"></a>MESSAGE_HANDLER

메시지 맵에서 항목을 정의합니다.

```
MESSAGE_HANDLER( msg, func )
```

### <a name="parameters"></a>매개 변수

*메시지*<br/>
【인】 Windows 메시지입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

MESSAGE_HANDLER 지정된 처리기 함수에 Windows 메시지를 매핑합니다.

MESSAGE_HANDLER 매크로에 지정된 모든 함수는 다음과 같이 정의되어야 합니다.

`LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`

전에 `MessageHandler` TRUE로 `bHandled` 설정된 메시지 맵이 호출됩니다. 메시지를 `MessageHandler` 완전히 처리하지 못하면 메시지가 `bHandled` 추가 처리가 필요함을 나타내기 위해 FALSE로 설정해야 합니다.

> [!NOTE]
> 항상 [BEGIN_MSG_MAP](#begin_msg_map)함께 메시지 맵을 시작합니다. 그런 다음 [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) 매크로는 메시지 맵의 끝을 표시합니다. 모든 메시지 맵에는 정확히 하나의 BEGIN_MSG_MAP 및 END_MSG_MAP 인스턴스가 있어야 합니다.

MESSAGE_HANDLER 외에도 [COMMAND_HANDLER](#command_handler) [NOTIFY_HANDLER](#notify_handler) 사용하여 [각각 WM_COMMAND](/windows/win32/menurc/wm-command) 및 [WM_NOTIFY](/windows/win32/controls/wm-notify) 메시지를 매핑할 수 있습니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="message_range_handler"></a><a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER

[MESSAGE_HANDLER](#message_handler)비슷하지만 Windows 메시지 범위를 단일 처리기 함수에 매핑합니다.

```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```

### <a name="parameters"></a>매개 변수

*MSGFirst*<br/>
【인】 연속된 메시지 범위의 시작을 표시합니다.

*msgLast*<br/>
【인】 연속된 메시지 범위의 끝을 표시합니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="notify_code_handler"></a><a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER

[NOTIFY_HANDLER](#notify_handler)비슷하지만 알림 코드에만 WM_NOTIFY [메시지를](/windows/win32/controls/wm-notify) 매핑합니다.

```
NOTIFY_CODE_HANDLER(cd, func)
```

### <a name="parameters"></a>매개 변수

*cd*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="notify_handler"></a><a name="notify_handler"></a>NOTIFY_HANDLER

메시지 맵에서 항목을 정의합니다.

```
NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 메시지를 보내는 컨트롤의 식별자입니다.

*cd*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

NOTIFY_HANDLER 알림 코드 및 컨트롤 식별자를 기반으로 지정된 처리기 함수에 [WM_NOTIFY](/windows/win32/controls/wm-notify) 메시지를 매핑합니다.

NOTIFY_HANDLER 매크로에 지정된 모든 함수는 다음과 같이 정의되어야 합니다.

`LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`

전에 `NotifyHandler` TRUE로 `bHandled` 설정된 메시지 맵이 호출됩니다. 메시지를 `NotifyHandler` 완전히 처리하지 못하면 메시지가 `bHandled` 추가 처리가 필요함을 나타내기 위해 FALSE로 설정해야 합니다.

> [!NOTE]
> 항상 [BEGIN_MSG_MAP](#begin_msg_map)함께 메시지 맵을 시작합니다. 그런 다음 [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) 매크로는 메시지 맵의 끝을 표시합니다. 모든 메시지 맵에는 정확히 하나의 BEGIN_MSG_MAP 및 END_MSG_MAP 인스턴스가 있어야 합니다.

NOTIFY_HANDLER 외에도 [MESSAGE_HANDLER](#message_handler) 사용하여 식별자 나 코드에 관계없이 WM_NOTIFY 메시지를 매핑 할 수 있습니다. 이 경우 `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` 모든 WM_NOTIFY 메시지를 `OnHandlerFunction`로 향합니다.

ATL에서 메시지 맵을 사용하는 것에 대한 자세한 내용은 [메시지 맵을](../../atl/message-maps-atl.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="notify_id_handler"></a><a name="notify_id_handler"></a>NOTIFY_ID_HANDLER

[NOTIFY_HANDLER](#notify_handler)비슷하지만 컨트롤 식별자만 을 기반으로 [WM_NOTIFY](/windows/win32/controls/wm-notify) 메시지를 매핑합니다.

```
NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 메시지를 보내는 컨트롤의 식별자입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="notify_range_code_handler"></a><a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER

[NOTIFY_RANGE_HANDLER](#notify_range_handler)비슷하지만 컨트롤 범위에서 단일 처리기 함수에 이르는 특정 알림 코드가 있는 [WM_NOTIFY](/windows/win32/controls/wm-notify) 메시지를 매핑합니다.

```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>매개 변수

*idFirst*<br/>
【인】 연속 범위의 컨트롤 식별자의 시작을 표시합니다.

*idLast*<br/>
【인】 연속 된 컨트롤 식별자의 끝을 표시 합니다.

*cd*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

이 범위는 메시지를 보내는 컨트롤의 식별자를 기반으로 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="notify_range_handler"></a><a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER

[NOTIFY_HANDLER](#notify_handler)비슷하지만 다양한 컨트롤에서 단일 처리기 함수에 [WM_NOTIFY](/windows/win32/controls/wm-notify) 메시지를 매핑합니다.

```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>매개 변수

*idFirst*<br/>
【인】 연속 범위의 컨트롤 식별자의 시작을 표시합니다.

*idLast*<br/>
【인】 연속 된 컨트롤 식별자의 끝을 표시 합니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

이 범위는 메시지를 보내는 컨트롤의 식별자를 기반으로 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflect_notifications"></a><a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS

알림 메시지를 보낸 자식 창(컨트롤)에 다시 반영합니다.

```
REFLECT_NOTIFICATIONS()
```

### <a name="remarks"></a>설명

이 매크로를 부모 창의 메시지 맵의 일부로 지정합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflected_command_code_handler"></a><a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER

[COMMAND_CODE_HANDLER](#command_code_handler)비슷하지만 부모 창에서 반사되는 명령을 매핑합니다.

```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```

### <a name="parameters"></a>매개 변수

*코드*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflected_command_handler"></a><a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER

[COMMAND_HANDLER](#command_handler)비슷하지만 부모 창에서 반사되는 명령을 매핑합니다.

```
REFLECTED_COMMAND_HANDLER( id, code, func )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 메뉴 항목, 컨트롤 또는 가속기의 식별자입니다.

*코드*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflected_command_id_handler"></a><a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER

[COMMAND_ID_HANDLER](#command_id_handler)비슷하지만 부모 창에서 반사되는 명령을 매핑합니다.

```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 메뉴 항목, 컨트롤 또는 가속기의 식별자입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflected_command_range_code_handler"></a><a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER

[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)비슷하지만 부모 창에서 반사되는 명령을 매핑합니다.

```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```

### <a name="parameters"></a>매개 변수

*idFirst*<br/>
【인】 연속 범위의 컨트롤 식별자의 시작을 표시합니다.

*idLast*<br/>
【인】 연속 된 컨트롤 식별자의 끝을 표시 합니다.

*코드*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflected_command_range_handler"></a><a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER

[COMMAND_RANGE_HANDLER](#command_range_handler)비슷하지만 부모 창에서 반사되는 명령을 매핑합니다.

```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>매개 변수

*idFirst*<br/>
【인】 연속 범위의 컨트롤 식별자의 시작을 표시합니다.

*idLast*<br/>
【인】 연속 된 컨트롤 식별자의 끝을 표시 합니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflected_notify_code_handler"></a><a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER

[NOTIFY_CODE_HANDLER](#notify_code_handler)비슷하지만 부모 창에서 알림이 반영됩니다.

```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```

### <a name="parameters"></a>매개 변수

*cd*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflected_notify_handler"></a><a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER

[NOTIFY_HANDLER](#notify_handler)비슷하지만 부모 창에서 알림이 반영됩니다.

```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 메뉴 항목, 컨트롤 또는 가속기의 식별자입니다.

*cd*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflected_notify_id_handler"></a><a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER

[NOTIFY_ID_HANDLER](#notify_id_handler)비슷하지만 부모 창에서 알림이 반영됩니다.

```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 메뉴 항목, 컨트롤 또는 가속기의 식별자입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflected_notify_range_code_handler"></a><a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER

[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)비슷하지만 부모 창에서 알림이 반영됩니다.

```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>매개 변수

*idFirst*<br/>
【인】 연속 범위의 컨트롤 식별자의 시작을 표시합니다.

*idLast*<br/>
【인】 연속 된 컨트롤 식별자의 끝을 표시 합니다.

*cd*<br/>
【인】 알림 코드입니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="reflected_notify_range_handler"></a><a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER

[NOTIFY_RANGE_HANDLER](#notify_range_handler)비슷하지만 부모 창에서 알림이 반영됩니다.

```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>매개 변수

*idFirst*<br/>
【인】 연속 범위의 컨트롤 식별자의 시작을 표시합니다.

*idLast*<br/>
【인】 연속 된 컨트롤 식별자의 끝을 표시 합니다.

*func*<br/>
【인】 메시지 처리기 함수의 이름입니다.

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
