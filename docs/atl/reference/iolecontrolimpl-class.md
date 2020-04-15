---
title: IOleControlImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
ms.openlocfilehash: 947ec16e91b99cc42cff90abe7df4a5d13576e98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329617"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl 클래스

이 클래스는 `IOleControl` 인터페이스 및 구현의 `IUnknown`기본 구현을 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IOleControlImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IOleControlImpl::동결 이벤트](#freezeevents)|컨테이너가 컨트롤의 이벤트를 무시하거나 수락하는지 여부를 나타냅니다.|
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|컨트롤의 키보드 동작에 대한 정보를 입력합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[아이올레컨트롤임플::온앰비언트프로퍼티체인지](#onambientpropertychange)|하나 이상의 컨테이너의 주변 속성이 변경되었음을 컨트롤에 알립니다. ATL 구현은 S_OK 반환합니다.|
|[아이올레컨트롤임플::온네모닉](#onmnemonic)|사용자가 지정된 키 입력을 눌렀다는 것을 컨트롤에 알립니다. ATL 구현은 E_NOTIMPL 반환합니다.|

## <a name="remarks"></a>설명

클래스는 `IOleControlImpl` [IOleControl](/windows/win32/api/ocidl/nn-ocidl-iolecontrol) 인터페이스의 기본 구현을 `IUnknown` 제공 하며 디버그 빌드에서 덤프 장치에 정보를 전송 하 여 구현 합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="iolecontrolimplfreezeevents"></a><a name="freezeevents"></a>IOleControlImpl::동결 이벤트

`FreezeEvents` ATL 구현에서 TRUE인 경우 `m_nFreezeEvents` `bFreeze` 컨트롤 클래스의 데이터 멤버를 증분하고 FALSE인 `m_nFreezeEvents` `bFreeze` 경우 감소합니다.

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>설명

`FreezeEvents`S_OK 반환합니다.

[IOleControl::Windows](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-freezeevents) SDK의 동결 이벤트를 참조하십시오.

## <a name="iolecontrolimplgetcontrolinfo"></a><a name="getcontrolinfo"></a>IOleControlImpl::GetControlInfo

컨트롤의 키보드 동작에 대한 정보를 입력합니다.

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>설명

[IOleControl:GetControlInfo](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) 윈도우 SDK를 참조하십시오.

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

## <a name="iolecontrolimplonambientpropertychange"></a><a name="onambientpropertychange"></a>아이올레컨트롤임플::온앰비언트프로퍼티체인지

하나 이상의 컨테이너의 주변 속성이 변경되었음을 컨트롤에 알립니다.

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

[IOleControl::OnAmbient속성](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) Windows SDK에서 변경합니다.

## <a name="iolecontrolimplonmnemonic"></a><a name="onmnemonic"></a>아이올레컨트롤임플::온네모닉

사용자가 지정된 키 입력을 눌렀다는 것을 컨트롤에 알립니다.

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IOleControl::Windows](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) SDK에서 온네모닉을 참조하십시오.

## <a name="see-also"></a>참고 항목

[IOleObjectImpl 클래스](../../atl/reference/ioleobjectimpl-class.md)<br/>
[액티브X컨트롤 인터페이스](/windows/win32/com/activex-controls-interfaces)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
