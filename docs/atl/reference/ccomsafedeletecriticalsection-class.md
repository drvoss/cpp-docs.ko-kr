---
title: CComSafeDeleteCriticalSection 클래스
ms.date: 11/04/2016
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
ms.openlocfilehash: cb0dc440fc0e79e0023b5fbd6e4ca2345d031d3d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327373"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection 클래스

이 클래스는 임계 섹션 개체의 소유권을 가져오고 해제하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComSafeDelete임계 섹션::CComSafeDelete임계 섹션](#ccomsafedeletecriticalsection)|생성자입니다.|
|[CComSafeDelete임계 섹션::~CComSafeDelete임계 섹션](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComSafeDelete임계 섹션::정립](#init)|임계 단면 객체를 만들고 초기화합니다.|
|[CComSafeDelete임계 섹션::잠금](#lock)|임계 단면 객체의 소유권을 가져옵니다.|
|[CComSafeDelete임계 섹션::용어](#term)|임계 섹션 개체에서 사용하는 시스템 리소스를 해제합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_bInitialized](#m_binitialized)|내부 `CRITICAL_SECTION` 개체가 초기화되었는지 여부를 플래그합니다.|

## <a name="remarks"></a>설명

`CComSafeDeleteCriticalSection`클래스 [CComCriticalSection에서](../../atl/reference/ccomcriticalsection-class.md)파생됩니다. 그러나 `CComSafeDeleteCriticalSection` [CComCriticalSection에](../../atl/reference/ccomcriticalsection-class.md)대한 추가 안전 메커니즘을 제공합니다.

인스턴스가 `CComSafeDeleteCriticalSection` 범위를 벗어나거나 메모리에서 명시적으로 삭제되면 기본 중요 섹션 개체가 여전히 유효한 경우 자동으로 정리됩니다. 또한 [CComSafeDeleteCriticalSection::Term](#term) 메서드는 기본 임계 섹션 개체가 아직 할당되지 않았거나 메모리에서 이미 해제된 경우 정상적으로 종료됩니다.

중요한 섹션 도우미 클래스에 대한 자세한 내용은 [CComCriticalSection을](../../atl/reference/ccomcriticalsection-class.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="ccomsafedeletecriticalsection"></a>CComSafeDelete임계 섹션::CComSafeDelete임계 섹션

생성자입니다.

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>설명

[m_bInitialized](#m_binitialized) 데이터 멤버를 FALSE로 설정합니다.

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="dtor"></a>CComSafeDelete임계 섹션::~CComSafeDelete임계 섹션

소멸자입니다.

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>설명

[m_bInitialized](#m_binitialized) 데이터 `CRITICAL_SECTION` 멤버가 TRUE로 설정된 경우 메모리에서 내부 개체를 해제합니다.

## <a name="ccomsafedeletecriticalsectioninit"></a><a name="init"></a>CComSafeDelete임계 섹션::정립

[Init의](/visualstudio/debugger/init) 기본 클래스 구현을 호출하고 성공하면 [m_bInitialized](#m_binitialized) TRUE로 설정합니다.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Return Value

[CComCriticalSection::Init의 결과를 반환합니다.](../../atl/reference/ccomcriticalsection-class.md#init)

## <a name="ccomsafedeletecriticalsectionlock"></a><a name="lock"></a>CComSafeDelete임계 섹션::잠금

Lock의 기본 클래스 구현을 [호출합니다.](ccomcriticalsection-class.md#lock)

```
HRESULT Lock();
```

### <a name="return-value"></a>Return Value

[CComCriticalSection::Lock의](../../atl/reference/ccomcriticalsection-class.md#lock)결과를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 [m_bInitialized](#m_binitialized) 데이터 멤버가 입력 시 TRUE로 설정된 것으로 가정합니다. 이 조건이 충족되지 않으면 디버그 빌드에서 어설션이 생성됩니다.

함수의 동작에 대한 자세한 내용은 [CComCriticalSection:Lock](../../atl/reference/ccomcriticalsection-class.md#lock)을 참조하십시오.

## <a name="ccomsafedeletecriticalsectionm_binitialized"></a><a name="m_binitialized"></a>CComSafeDelete임계 섹션::m_bInitialized

내부 `CRITICAL_SECTION` 개체가 초기화되었는지 여부를 플래그합니다.

```
bool m_bInitialized;
```

### <a name="remarks"></a>설명

`m_bInitialized` 데이터 멤버는 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) 클래스와 연결된 기본 `CRITICAL_SECTION` 개체의 유효성을 추적하는 데 사용됩니다. 이 `CRITICAL_SECTION` 플래그가 TRUE로 설정되지 않은 경우 기본 개체는 메모리에서 해제하려고 시도하지 않습니다.

## <a name="ccomsafedeletecriticalsectionterm"></a><a name="term"></a>CComSafeDelete임계 섹션::용어

내부 `CRITICAL_SECTION` 개체가 유효한 경우 [CComCriticalSection::Term의](../../atl/reference/ccomcriticalsection-class.md#term) 기본 클래스 구현을 호출합니다.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Return Value

[CComCriticalSection::term의](../../atl/reference/ccomcriticalsection-class.md#term)결과를 반환하거나 입력 시 [m_bInitialized](#m_binitialized) false로 설정된 경우 S_OK.

### <a name="remarks"></a>설명

내부 `CRITICAL_SECTION` 개체가 유효하지 않은 경우에도 이 메서드를 호출해도 안전합니다. [m_bInitialized](#m_binitialized) 데이터 멤버가 TRUE로 설정된 경우 이 클래스의 소멸자가 이 메서드를 호출합니다.

## <a name="see-also"></a>참고 항목

[CComCriticalsection 클래스](../../atl/reference/ccomcriticalsection-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
