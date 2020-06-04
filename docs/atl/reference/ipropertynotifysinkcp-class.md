---
title: IPropertyNotifySinkCP 클래스
ms.date: 11/04/2016
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
ms.openlocfilehash: c6d98bf5a6dfe5566839eb22bcd2bab2a9c28e4d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329606"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP 클래스

이 클래스는 [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 인터페이스를 연결 가능한 개체의 나가는 인터페이스로 노출합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T, class CDV = CComDynamicUnkArray>
class IPropertyNotifySinkCP
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IPropertyNotifySinkCP`

*CDV*<br/>
연결 점과 싱크 사이의 연결을 관리하는 클래스입니다. 기본값은 무제한 연결을 허용하는 [CComDynamicUnkArray입니다.](../../atl/reference/ccomdynamicunkarray-class.md) 고정된 수의 연결을 지정하는 [CComUnkArray를](../../atl/reference/ccomunkarray-class.md)사용할 수도 있습니다.

## <a name="remarks"></a>설명

`IPropertyNotifySinkCP`기본 클래스인 [IConnectionPointImpl을](../../atl/reference/iconnectionpointimpl-class.md)통해 모든 메서드를 상속합니다.

[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 인터페이스를 사용하면 싱크 개체가 속성 변경에 대한 알림을 받을 수 있습니다. 클래스는 `IPropertyNotifySinkCP` 이 인터페이스를 연결 가능한 개체의 나가는 인터페이스로 노출합니다. 클라이언트는 싱크에 `IPropertyNotifySink` 메서드를 구현 해야 합니다.

인터페이스를 나타내는 `IPropertyNotifySinkCP` 연결 점을 만들려는 경우클래스를 `IPropertyNotifySink` 파생시합니다.

ATL에서 연결 점 사용에 대한 자세한 내용은 [연결 지점](../../atl/atl-connection-points.md)을 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="see-also"></a>참고 항목

[IConnectionPointImpl 클래스](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[IConnectionPointContainerImpl 클래스](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
