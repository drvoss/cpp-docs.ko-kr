---
title: IPointerInactiveImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: 229b8c6803aa7b3817cb3d95474bde0502829f8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326445"
---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl 클래스

이 클래스는 `IUnknown` [IPointer활성](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) 인터페이스 메서드를 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IPointerInactiveImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IPointer활성 임플::Get활성화정책](#getactivationpolicy)|개체에 대한 현재 활성화 정책을 검색합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IPointer활성 임플::에니액티브마우스무브](#oninactivemousemove)|마우스 포인터가 마우스 포인터 위로 이동했음을 알리는 개체를 표시하여 개체가 마우스 이벤트를 발생시킬 수 있음을 나타냅니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IPointer활성 임플::에니액티브셋세트커서](#oninactivesetcursor)|비활성 개체에 대한 마우스 포인터를 설정합니다. ATL 구현은 E_NOTIMPL 반환합니다.|

## <a name="remarks"></a>설명

비활성 개체는 단순히 로드또는 실행중인 개체입니다. 활성 개체와 달리 비활성 개체는 Windows 마우스 및 키보드 메시지를 받을 수 없습니다. 따라서 비활성 개체는 더 적은 리소스를 사용하며 일반적으로 더 효율적입니다.

[IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) 인터페이스를 사용하면 개체가 비활성 상태로 유지하면서 최소한의 마우스 상호 작용을 지원할 수 있습니다. 이 기능은 컨트롤에 특히 유용합니다.

클래스는 `IPointerInactiveImpl` 단순히 `IPointerInactive` E_NOTIMPL 반환하여 메서드를 구현합니다. 그러나 디버그 `IUnknown` 빌드에서 덤프 장치에 정보를 전송 하 여 구현 합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="ipointerinactiveimplgetactivationpolicy"></a><a name="getactivationpolicy"></a>IPointer활성 임플::Get활성화정책

개체에 대한 현재 활성화 정책을 검색합니다.

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IPointerInactive:Get활성화Windows](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) SDK에서 정책을 참조하십시오.

## <a name="ipointerinactiveimploninactivemousemove"></a><a name="oninactivemousemove"></a>IPointer활성 임플::에니액티브마우스무브

마우스 포인터가 마우스 포인터 위로 이동했음을 알리는 개체를 표시하여 개체가 마우스 이벤트를 발생시킬 수 있음을 나타냅니다.

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IPointer활성::Windows](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) SDK에서 온액티브마우스 이동을 참조하십시오.

## <a name="ipointerinactiveimploninactivesetcursor"></a><a name="oninactivesetcursor"></a>IPointer활성 임플::에니액티브셋세트커서

비활성 개체에 대한 마우스 포인터를 설정합니다.

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IPointerInactive::InInactiveSK에서 설정큐서를](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
