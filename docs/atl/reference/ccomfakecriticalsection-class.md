---
title: CComFake임계 섹션 클래스
ms.date: 11/04/2016
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
ms.openlocfilehash: 4a5b9ba3551397a9c3d59a343e9c6b55b1c1207e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327848"
---
# <a name="ccomfakecriticalsection-class"></a>CComFake임계 섹션 클래스

이 클래스는 [CComCriticalSection과](../../atl/reference/ccomcriticalsection-class.md) 동일한 메서드를 제공하지만 중요한 섹션을 제공하지는 않습니다.

## <a name="syntax"></a>구문

```
class CComFakeCriticalSection
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComFake 임계 섹션::init](#init)|임계 섹션이 없기 때문에 아무 것도 하지 않습니다.|
|[CComFake임계 섹션::잠금](#lock)|임계 섹션이 없기 때문에 아무 것도 하지 않습니다.|
|[CComFake임계 섹션::용어](#term)|임계 섹션이 없기 때문에 아무 것도 하지 않습니다.|
|[CComFake임계 섹션::잠금 해제](#unlock)|임계 섹션이 없기 때문에 아무 것도 하지 않습니다.|

## <a name="remarks"></a>설명

`CComFakeCriticalSection`[CComCriticalSection에](../../atl/reference/ccomcriticalsection-class.md)있는 메서드를 미러합니다. 그러나 `CComFakeCriticalSection` 중요한 섹션은 제공하지 않습니다. 따라서 메서드는 아무 것도 수행하지 않습니다.

`CComFakeCriticalSection` 일반적으로 `typedef` 이름을 `AutoCriticalSection` 사용하거나 `CriticalSection`. [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는 [CComMultiThreadModelNoCS를](../../atl/reference/ccommultithreadmodelnocs-class.md)사용하는 `typedef` 경우 `CComFakeCriticalSection`이러한 두 이름 모두 참조를 참조합니다. [CComMultiThreadModel을](../../atl/reference/ccommultithreadmodel-class.md)사용하는 경우 각각 [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) 및 `CComCriticalSection`을 참조합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

## <a name="ccomfakecriticalsectioninit"></a><a name="init"></a>CComFake 임계 섹션::init

임계 섹션이 없기 때문에 아무 것도 하지 않습니다.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="ccomfakecriticalsectionlock"></a><a name="lock"></a>CComFake임계 섹션::잠금

임계 섹션이 없기 때문에 아무 것도 하지 않습니다.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="ccomfakecriticalsectionterm"></a><a name="term"></a>CComFake임계 섹션::용어

임계 섹션이 없기 때문에 아무 것도 하지 않습니다.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="ccomfakecriticalsectionunlock"></a><a name="unlock"></a>CComFake임계 섹션::잠금 해제

임계 섹션이 없기 때문에 아무 것도 하지 않습니다.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
