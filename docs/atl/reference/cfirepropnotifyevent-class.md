---
title: CFirePropNotifyEvent 클래스
ms.date: 11/04/2016
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
ms.openlocfilehash: 1dfce42176341d74ffc7d9b42f856e71b17bf4f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326964"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent 클래스

이 클래스는 제어 속성 변경과 관련하여 컨테이너의 싱크에 알리는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CFirePropNotifyEvent
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFirePropNotifyEvent::Fireon변경](#fireonchanged)|(정적) 컨테이너의 싱크에 제어 속성이 변경되었음을 지정합니다.|
|[CFirePropNotifyEvent::Fireon요청 편집](#fireonrequestedit)|(정적) 컨테이너의 싱크에 컨트롤 속성이 변경될 것이라는 것을 지정합니다.|

## <a name="remarks"></a>설명

`CFirePropNotifyEvent`에는 제어 속성이 변경되었거나 변경될 것이라는 것을 컨테이너의 싱크에 알리는 두 가지 방법이 있습니다.

컨트롤을 구현하는 `IPropertyNotifySink`클래스가 에서 파생된 `CFirePropNotifyEvent` 경우 을 호출하거나 `FireOnRequestEdit` `FireOnChanged`. 컨트롤 클래스에서 `IPropertyNotifySink`파생 되지 않은 경우 이러한 함수에 대 한 호출S_OK 반환 합니다.

컨트롤 을 만드는 것에 대한 자세한 내용은 [ATL 자습서를](../../atl/active-template-library-atl-tutorial.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="cfirepropnotifyeventfireonchanged"></a><a name="fireonchanged"></a>CFirePropNotifyEvent::Fireon변경

지정된 개체 속성이 변경되었음을 연결된 모든 [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 인터페이스(개체의 모든 연결 지점에)를 알립니다.

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
【인】 알림을 보내는 `IUnknown` 개체에 대한 포인터입니다.

*dispID*<br/>
【인】 변경된 속성의 식별자입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

이 함수는 컨트롤이 연결 지점을 지원하지 않는 경우에도 호출해도 안전합니다.

## <a name="cfirepropnotifyeventfireonrequestedit"></a><a name="fireonrequestedit"></a>CFirePropNotifyEvent::Fireon요청 편집

지정된 개체 속성이 변경될 것을 연결된 모든 [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 인터페이스(개체의 모든 연결 지점에)를 알립니다.

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
【인】 알림을 보내는 `IUnknown` 개체에 대한 포인터입니다.

*dispID*<br/>
【인】 변경하려는 속성의 식별자입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

이 함수는 컨트롤이 연결 지점을 지원하지 않는 경우에도 호출해도 안전합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
