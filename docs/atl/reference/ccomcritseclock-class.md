---
title: CComCritSecLock 클래스
ms.date: 11/04/2016
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
ms.openlocfilehash: 4b2ef093c1142b592ad2a6605a08bd8c34a643ea
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748078"
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock 클래스

이 클래스는 임계 섹션 개체를 잠그고 잠금을 해제하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>매개 변수

*TLock*<br/>
잠그고 잠금을 해제할 개체입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComCritSecLock::CComCritSecLock](#ctor)|생성자입니다.|
|[CComCritSecLock::~CComCritSecLock](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComCritSecLock::잠금](#lock)|이 메서드를 호출하여 임계 섹션 개체를 잠급전지.|
|[CComCritSecLock::잠금 해제](#unlock)|이 메서드를 호출하여 임계 섹션 개체의 잠금을 해제합니다.|

## <a name="remarks"></a>설명

이 클래스를 사용하여 [CComCriticalSection 클래스 또는 CComAutoCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 클래스보다 더 안전한 방법으로 개체를 잠그고 잠금을 [해제합니다.](../../atl/reference/ccomautocriticalsection-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomcritseclockccomcritseclock"></a><a name="ctor"></a>CComCritSecLock::CComCritSecLock

생성자입니다.

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>매개 변수

*cs*<br/>
임계 섹션 개체입니다.

*b초기 잠금*<br/>
초기 잠금 상태: **true는** 잠긴 것을 의미합니다.

### <a name="remarks"></a>설명

임계 단면 오브젝트를 초기화합니다.

## <a name="ccomcritseclockccomcritseclock"></a><a name="dtor"></a>CComCritSecLock::~CComCritSecLock

소멸자입니다.

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>설명

임계 단면 오브젝트의 잠금을 해제합니다.

## <a name="ccomcritseclocklock"></a><a name="lock"></a>CComCritSecLock::잠금

이 메서드를 호출하여 임계 섹션 개체를 잠급전지.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Return Value

개체가 성공적으로 잠긴 경우 S_OK 반환하거나 오류에 대한 오류 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

개체가 이미 잠겨 있는 경우 디버그 빌드에서 ASSERT 오류가 발생합니다.

## <a name="ccomcritseclockunlock"></a><a name="unlock"></a>CComCritSecLock::잠금 해제

이 메서드를 호출하여 임계 섹션 개체의 잠금을 해제합니다.

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>설명

개체가 이미 잠금 해제된 경우 디버그 빌드에서 ASSERT 오류가 발생합니다.

## <a name="see-also"></a>참조

[CComCriticalsection 클래스](../../atl/reference/ccomcriticalsection-class.md)<br/>
[CComAutoCriticalSection 클래스](../../atl/reference/ccomautocriticalsection-class.md)
