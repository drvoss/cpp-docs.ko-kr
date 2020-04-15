---
title: CComApartment 클래스
ms.date: 11/04/2016
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
ms.openlocfilehash: 13141d27592f6f40ea7b0529c61baba2fe83a10a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321113"
---
# <a name="ccomapartment-class"></a>CComApartment 클래스

이 클래스는 스레드 풀린 EXE 모듈에서 아파트 관리를 지원합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CComApartment
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CCom아파트먼트::CCom아파트먼트](#ccomapartment)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComApartment::아파트먼트](#apartment)|스레드의 시작 주소를 표시합니다.|
|[CComApartment::겟록카운트](#getlockcount)|스레드의 현재 잠금 수를 반환합니다.|
|[CComApartment::잠금](#lock)|스레드의 잠금 수를 증가시입니다.|
|[CComApartment::잠금 해제](#unlock)|스레드의 잠금 수를 감소시입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComApartment:m_dwThreadID](#m_dwthreadid)|스레드의 식별자를 포함합니다.|
|[CComApartment:m_hThread](#m_hthread)|스레드의 핸들을 포함합니다.|
|[CComApartment:m_nLockCnt](#m_nlockcnt)|스레드의 현재 잠금 수를 포함합니다.|

## <a name="remarks"></a>설명

`CComApartment`[CComAutoThreadModule에서](../../atl/reference/ccomautothreadmodule-class.md) 스레드 풀린 EXE 모듈의 아파트를 관리하는 데 사용됩니다. `CComApartment`는 스레드의 잠금 수를 증분하고 감소시키는 메서드를 제공합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomapartmentapartment"></a><a name="apartment"></a>CComApartment::아파트먼트

스레드의 시작 주소를 표시합니다.

```
DWORD Apartment();
```

### <a name="return-value"></a>Return Value

항상 0입니다.

### <a name="remarks"></a>설명

[CComAutoThreadModule 동안 자동으로 설정::초기화](../../atl/reference/ccomautothreadmodule-class.md#init).

## <a name="ccomapartmentccomapartment"></a><a name="ccomapartment"></a>CCom아파트먼트::CCom아파트먼트

생성자입니다.

```
CComApartment();
```

### <a name="remarks"></a>설명

데이터 멤버 `CComApartment` m_nLockCnt [m_nLockCnt](#m_nlockcnt) 초기화 하고 [m_hThread.](#m_hthread)

## <a name="ccomapartmentgetlockcount"></a><a name="getlockcount"></a>CComApartment::겟록카운트

스레드의 현재 잠금 수를 반환합니다.

```
LONG GetLockCount();
```

### <a name="return-value"></a>Return Value

스레드의 잠금 개수입니다.

## <a name="ccomapartmentlock"></a><a name="lock"></a>CComApartment::잠금

스레드의 잠금 수를 증가시입니다.

```
LONG Lock();
```

### <a name="return-value"></a>Return Value

진단 또는 테스트에 유용할 수 있는 값입니다.

### <a name="remarks"></a>설명

[CComAutoThreadModule::Lock에](../../atl/reference/ccomautothreadmodule-class.md#lock)의해 호출됩니다.

스레드의 잠금 수는 통계 목적으로 사용됩니다.

## <a name="ccomapartmentm_dwthreadid"></a><a name="m_dwthreadid"></a>CComApartment:m_dwThreadID

스레드의 식별자를 포함합니다.

```
DWORD m_dwThreadID;
```

## <a name="ccomapartmentm_hthread"></a><a name="m_hthread"></a>CComApartment:m_hThread

스레드의 핸들을 포함합니다.

```
HANDLE m_hThread;
```

## <a name="ccomapartmentm_nlockcnt"></a><a name="m_nlockcnt"></a>CComApartment:m_nLockCnt

스레드의 현재 잠금 수를 포함합니다.

```
LONG m_nLockCnt;
```

## <a name="ccomapartmentunlock"></a><a name="unlock"></a>CComApartment::잠금 해제

스레드의 잠금 수를 감소시입니다.

```
LONG Unlock();
```

### <a name="return-value"></a>Return Value

진단 또는 테스트에 유용할 수 있는 값입니다.

### <a name="remarks"></a>설명

[CComAutoThreadModule:::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).

스레드의 잠금 수는 통계 목적으로 사용됩니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
