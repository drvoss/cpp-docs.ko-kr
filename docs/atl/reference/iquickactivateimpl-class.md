---
title: IQuickActivateImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
ms.openlocfilehash: 7e1984249caf66e2986341f9c9f7a939d7039125
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329548"
---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl 클래스

이 클래스는 컨테이너의 제어 초기화를 단일 호출로 결합합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IQuickActivateImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IQuickActivateImpl:::GetContentExtent](#getcontentextent)|실행 중인 컨트롤에 대한 현재 표시 크기를 검색합니다.|
|[IQuickActivateImpl::QuickActivate](#quickactivate)|로드중인 컨트롤의 빠른 초기화를 수행합니다.|
|[IQuickActivateImpl::설정콘텐츠범위](#setcontentextent)|컨테이너에 할당된 디스플레이 공간의 양을 제어합니다.|

## <a name="remarks"></a>설명

[IQuickActivate](/windows/win32/api/ocidl/nn-ocidl-iquickactivate) 인터페이스는 컨테이너가 단일 호출에서 초기화를 결합하여 컨트롤을 로드할 때 지연을 방지하는 데 도움이 됩니다. `QuickActivate` 메서드를 통해 컨테이너는 컨트롤에 필요한 모든 인터페이스에 대한 포인터를 포함하는 [QACONTAINER](/windows/win32/api/ocidl/ns-ocidl-qacontainer) 구조체에 대한 포인터를 전달할 수 있습니다. 반환시 컨트롤은 컨테이너에서 사용되는 자체 인터페이스에 대한 포인터를 보유하는 [QACONTROL](/windows/win32/api/ocidl/ns-ocidl-qacontrol) 구조에 대한 포인터를 다시 전달합니다. 클래스는 `IQuickActivateImpl` 디버그 `IQuickActivate` 빌드에서 `IUnknown` 덤프 장치에 정보를 전송하여 구현 및 구현의 기본 구현을 제공합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="iquickactivateimplgetcontentextent"></a><a name="getcontentextent"></a>IQuickActivateImpl:::GetContentExtent

실행 중인 컨트롤에 대한 현재 표시 크기를 검색합니다.

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>설명

크기는 컨트롤의 전체 렌더링을 위한 것이며 HIMETRIC 단위로 지정됩니다.

[IQuickActivate::GetContentWindows](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) SDK에서 익스텐트를 참조하십시오.

## <a name="iquickactivateimplquickactivate"></a><a name="quickactivate"></a>IQuickActivateImpl::빠른 활성화

로드중인 컨트롤의 빠른 초기화를 수행합니다.

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>설명

구조에는 컨트롤에 필요한 인터페이스와 일부 주변 속성의 값에 대한 포인터가 포함되어 있습니다. 반환 시 컨트롤은 컨테이너에 필요한 자체 인터페이스에 대한 포인터와 추가 상태 정보를 포함하는 [QACONTROL](/windows/win32/api/ocidl/ns-ocidl-qacontrol) 구조에 대한 포인터를 전달합니다.

[IQuickActivate::Windows](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-quickactivate) SDK에서 빠른 활성화를 참조하십시오.

## <a name="iquickactivateimplsetcontentextent"></a><a name="setcontentextent"></a>IQuickActivateImpl::설정콘텐츠범위

컨테이너에 할당된 디스플레이 공간의 양을 제어합니다.

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>설명

크기는 HIMETRIC 단위로 지정됩니다.

[IQuickActivate::Windows](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) SDK에서 설정콘텐츠익을 참조하십시오.

## <a name="see-also"></a>참고 항목

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
