---
title: CAutoRevertImpersonation 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
ms.openlocfilehash: ea119436fd36d0814c05f1b48380028ad3f63f0c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748247"
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation 클래스

이 클래스는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체가 범위를 벗어날 때 가장하지 않는 상태로 되돌아갑니다.

## <a name="syntax"></a>구문

```
class CAutoRevertImpersonation
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C자동되사칭::자동 되반전 사칭](#cautorevertimpersonation)|`CAutoRevertImpersonation` 개체 생성|
|[CAutoRevert 사칭::~CAutoRevert사칭](#dtor)|개체를 삭제하고 액세스 토큰 가장을 되돌리합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C자동 되반전 사칭::첨부](#attach)|액세스 토큰의 가장 회귀를 자동화합니다.|
|[CAutoRevert 사칭::D](#detach)|자동 가장 회귀를 취소합니다.|
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|이 개체와 연결된 액세스 토큰 전류를 검색합니다.|

## <a name="remarks"></a>설명

[액세스 토큰은](/windows/win32/SecAuthZ/access-tokens) 프로세스 또는 스레드의 보안 컨텍스트를 설명하는 개체이며 Windows NT 또는 Windows 2000 시스템에 로그온한 각 사용자에게 할당됩니다. 이러한 액세스 토큰은 `CAccessToken` 클래스와 함께 나타낼 수 있습니다.

액세스 토큰을 가장해야 하는 경우가 있습니다. 이 클래스는 편의를 위해 제공되지만 액세스 토큰의 가장을 수행하지는 않습니다. 가장되지 않은 상태로 자동 회귀를 수행합니다. 토큰 액세스 가장은 여러 가지 방법으로 수행할 수 있기 때문입니다.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="cautorevertimpersonationattach"></a><a name="attach"></a>C자동 되반전 사칭::첨부

액세스 토큰의 가장 회귀를 자동화합니다.

```cpp
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>매개 변수

*팻*<br/>
[CAccessToken](../../atl/reference/caccesstoken-class.md) 개체의 주소를 자동으로 되돌릴 수 있습니다.

### <a name="remarks"></a>설명

이 메서드는 [CAutoRevert사칭](../../atl/reference/cautorevertimpersonation-class.md) 개체가 NULL `CAccessToken` 포인터로 만들어졌거나 [Detach가](#detach) 이전에 호출된 경우에만 사용해야 합니다. 간단한 경우이 메서드를 사용할 필요가 없습니다.

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="cautorevertimpersonation"></a>C자동되사칭::자동 되반전 사칭

`CAutoRevertImpersonation` 개체를 생성합니다.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>매개 변수

*팻*<br/>
[CAccessToken](../../atl/reference/caccesstoken-class.md) 개체의 주소를 자동으로 되돌릴 수 있습니다.

### <a name="remarks"></a>설명

액세스 토큰의 실제 가장은 `CAutoRevertImpersonation` 개체를 만들기 전에 별도로 수행해야 합니다. 이 가장은 개체가 `CAutoRevertImpersonation` 범위를 벗어날 때 자동으로 되돌아갑니다.

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="dtor"></a>CAutoRevert 사칭::~CAutoRevert사칭

개체를 삭제하고 액세스 토큰 가장을 되돌리합니다.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>설명

구성 시 또는 [Attach](#attach) 메서드를 통해 제공된 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체에 대해 현재 적용되는 가장을 되돌리킵니다. 연결되지 `CAccessToken` 않은 경우 소멸자는 아무런 영향을 미치지 않습니다.

## <a name="cautorevertimpersonationdetach"></a><a name="detach"></a>CAutoRevert 사칭::D

자동 가장 회귀를 취소합니다.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>Return Value

연결이 없는 경우 이전에 연결된 [CAccessToken](../../atl/reference/caccesstoken-class.md)또는 NULL의 주소입니다.

### <a name="remarks"></a>설명

**Detach를** 호출하면 `CAutoRevertImpersonation` 이 개체와 연결된 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체에 대해 현재 적용되는 가장이 되돌리게 됩니다. `CAutoRevertImpersonation`은 그런 다음 다시 [연결](#attach) 사용하여 동일한 또는 다른 `CAccessToken` 개체에 영향을 주지않고 소멸시킬 수 있습니다.

## <a name="cautorevertimpersonationgetaccesstoken"></a><a name="getaccesstoken"></a>C자동 되반전 사칭::GetAccessToken

이 개체와 연결된 액세스 토큰 전류를 검색합니다.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>Return Value

연결이 없는 경우 이전에 연결된 [CAccessToken](../../atl/reference/caccesstoken-class.md)또는 NULL의 주소입니다.

### <a name="remarks"></a>설명

개체의 가장을 다시 전환하는 것을 포함하는 목적으로 이 메서드를 `CAccessToken` 호출하는 경우 대신 [Detach](#detach) 메서드를 사용해야 합니다.

## <a name="see-also"></a>참조

[ATL보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[토큰 액세스](/windows/win32/SecAuthZ/access-tokens)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
