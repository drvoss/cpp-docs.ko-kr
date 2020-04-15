---
title: CComCriticalsection 클래스
ms.date: 11/04/2016
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
ms.openlocfilehash: f3991d217fbc201bd428ed2522a5c4c25e074928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327962"
---
# <a name="ccomcriticalsection-class"></a>CComCriticalsection 클래스

이 클래스는 임계 섹션 개체의 소유권을 가져오고 해제하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
class CComCriticalSection
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComCriticalsection::CComcriticalsection](#ccomcriticalsection)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComCriticalsection::init](#init)|임계 단면 객체를 만들고 초기화합니다.|
|[CComCriticalSection::Lock](#lock)|임계 단면 객체의 소유권을 가져옵니다.|
|[CComCriticalSection::Term](#term)|임계 섹션 개체에서 사용하는 시스템 리소스를 해제합니다.|
|[CComCriticalSection::Unlock](#unlock)|임계 섹션 개체의 소유권을 해제합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComCriticalSection::m_sec](#m_sec)|CRITICAL_SECTION 개체입니다.|

## <a name="remarks"></a>설명

`CComCriticalSection`크리티컬 섹션을 명시적으로 초기화하고 해제해야 한다는 점을 제외하면 [클래스 CComAutoCriticalSection과](../../atl/reference/ccomautocriticalsection-class.md)유사합니다.

일반적으로 `CComCriticalSection` **typedef** 이름 [CriticalSection을](ccommultithreadmodel-class.md#criticalsection)통해 사용합니다. [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)를 사용하는 경우 이 이름은 `CComCriticalSection`를 참조합니다.

호출 `Lock` 하고 `Unlock` 직접 보다이 클래스를 사용 하는 안전한 방법은 [CComCritSecLock 클래스를](../../atl/reference/ccomcritseclock-class.md) 참조 하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

## <a name="ccomcriticalsectionccomcriticalsection"></a><a name="ccomcriticalsection"></a>CComCriticalsection::CComcriticalsection

생성자입니다.

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>설명

[m_sec](#m_sec) 데이터 멤버를 NULL로 설정합니다.

## <a name="ccomcriticalsectioninit"></a><a name="init"></a>CComCriticalsection::init

win32 함수를 호출 [초기화criticalSection,](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection) [m_sec](#m_sec) 데이터 멤버에 포함 된 임계 섹션 개체를 초기화 하는.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Return Value

성공, E_OUTOFMEMORY 또는 실패에 E_FAIL S_OK 반환합니다.

## <a name="ccomcriticalsectionlock"></a><a name="lock"></a>CComCriticalsection::잠금

스레드가 [m_sec](#m_sec) 데이터 멤버에 포함된 임계 섹션 개체의 소유권을 차지할 때까지 기다리는 Win32 함수 [EnterCriticalSection을](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)호출합니다.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Return Value

성공, E_OUTOFMEMORY 또는 실패에 E_FAIL S_OK 반환합니다.

### <a name="remarks"></a>설명

임계 섹션 개체는 먼저 [Init](#init) 메서드에 대한 호출로 초기화되어야 합니다. 보호된 코드실행이 완료되면 스레드는 [Unlock을](#unlock) 호출하여 임계 섹션의 소유권을 해제해야 합니다.

## <a name="ccomcriticalsectionm_sec"></a><a name="m_sec"></a>CComcriticalsection::m_sec

모든 `CComCriticalSection` 메서드에서 사용되는 임계 섹션 개체를 포함합니다.

```
CRITICAL_SECTION m_sec;
```

## <a name="ccomcriticalsectionterm"></a><a name="term"></a>CComCriticalSection::용어

[m_sec](#m_sec) 데이터 멤버에 포함된 임계 섹션 개체에서 사용하는 모든 리소스를 해제하는 Win32 함수 [DeleteCriticalSection을](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)호출합니다.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

호출된 후에는 `Term` 동기화에 임계 섹션을 더 이상 사용할 수 없습니다.

## <a name="ccomcriticalsectionunlock"></a><a name="unlock"></a>CComCriticalSection::잠금 해제

[m_sec](#m_sec) 데이터 멤버에 포함된 임계 섹션 개체의 소유권을 해제하는 Win32 함수 [LeaveCriticalSection을](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)호출합니다.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

먼저 소유권을 얻으려면 스레드가 [Lock](#lock) 메서드를 호출해야 합니다. 각 호출은 `Lock` 중요 섹션의 소유권을 해제하기 위해 `Unlock` 해당 호출이 필요합니다.

## <a name="see-also"></a>참고 항목

[CComFake임계 섹션 클래스](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComCritSecLock 클래스](../../atl/reference/ccomcritseclock-class.md)
