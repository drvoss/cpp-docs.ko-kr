---
title: IUMSThreadProxy 구조체
ms.date: 11/04/2016
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
ms.openlocfilehash: 2e748b1da02394e1f70afd8b92947e1291957c62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368079"
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy 구조체

실행 스레드에 대한 추상화입니다. 해당 스케줄러에 UMS(사용자 모드 예약 가능) 스레드를 부여하려는 경우 스케줄러 정책 요소 `SchedulerKind`의 값을 `UmsThreadDefault`로 설정하고 `IUMSScheduler` 인터페이스를 구현합니다. UMS 스레드는 Windows 7 이상 버전의 64비트 운영 체제에서만 지원됩니다.

## <a name="syntax"></a>구문

```cpp
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IUMS스레드 프록시::엔터크리티컬 리전](#entercriticalregion)|임계 영역을 입력하기 위해 호출됩니다. 임계 영역 내에서 스케줄러는 리전 중에 발생하는 비동기 차단 작업을 관찰하지 않습니다. 즉, UMS 스레드에 대한 페이지 오류, 스레드 일시 중단, 커널 비동기 프로시저 호출(APC) 등에 대해 스케줄러를 다시 입력하지 않습니다.|
|[IUMS스레드프록시::엔터하이퍼크리티컬리](#enterhypercriticalregion)|초임계 영역을 입력하기 위해 호출됩니다. 매우 중요한 영역 내부에 있으면 스케줄러는 리전 중에 발생하는 차단 작업을 관찰하지 않습니다. 이는 스케줄러가 UMS 스레드에 대한 함수 호출 차단, 차단되는 잠금 가져오기 시도, 페이지 폴트, 스레드 보류, 커널 비동기 프로시저 호출(APC) 등에 재진입되지 않음을 의미합니다.|
|[IUMS스레드 프록시::엑시트크리티컬 리전](#exitcriticalregion)|중요 영역을 종료하기 위해 호출됩니다.|
|[IUMS스레드프록시::엑시트하이퍼크리티컬리](#exithypercriticalregion)|초임계 영역을 종료하기 위해 호출됩니다.|
|[IUMS스레드 프록시::GetCriticalRegionType](#getcriticalregiontype)|스레드 프록시가 내에 있는 중요 영역의 종류를 반환합니다. 초임계 영역은 중요 영역의 수퍼세트이므로 코드가 임계 영역을 입력한 다음 `InsideHyperCriticalRegion` 초임계 영역이 반환됩니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[아이스레드프록시](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a>IUMSThread프록시::엔터크리티컬리리

임계 영역을 입력하기 위해 호출됩니다. 임계 영역 내에서 스케줄러는 리전 중에 발생하는 비동기 차단 작업을 관찰하지 않습니다. 즉, UMS 스레드에 대한 페이지 오류, 스레드 일시 중단, 커널 비동기 프로시저 호출(APC) 등에 대해 스케줄러를 다시 입력하지 않습니다.

```cpp
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>Return Value

임계 영역의 새로운 깊이입니다. 중요 영역은 재진입합니다.

## <a name="iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a>IUMSThread프록시::엔터하이퍼크리티컬리리 방법

초임계 영역을 입력하기 위해 호출됩니다. 매우 중요한 영역 내부에 있으면 스케줄러는 리전 중에 발생하는 차단 작업을 관찰하지 않습니다. 이는 스케줄러가 UMS 스레드에 대한 함수 호출 차단, 차단되는 잠금 가져오기 시도, 페이지 폴트, 스레드 보류, 커널 비동기 프로시저 호출(APC) 등에 재진입되지 않음을 의미합니다.

```cpp
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Return Value

초임계 영역의 새로운 깊이입니다. 매우 중요한 영역은 재진입입니다.

### <a name="remarks"></a>설명

스케줄러는 호출하는 메서드와 해당 지역에서 획득하는 잠금에 대해 매우 주의해야 합니다. 이러한 지역의 코드가 스케줄러가 스케줄링을 담당하는 잠금에 대해 차단하는 경우 교착 상태가 발생할 수 있습니다.

## <a name="iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a>IUMSThread프록시::엑시트크리티컬리 리전 방법

중요 영역을 종료하기 위해 호출됩니다.

```cpp
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>Return Value

임계 영역의 새로운 깊이입니다. 중요 영역은 재진입합니다.

## <a name="iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a>IUMSThread프록시::엑시트하이퍼크리티컬리 방법

초임계 영역을 종료하기 위해 호출됩니다.

```cpp
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Return Value

초임계 영역의 새로운 깊이입니다. 매우 중요한 영역은 재진입입니다.

## <a name="iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a>IUMSThread프록시::GetCriticalRegionType 방법

스레드 프록시가 내에 있는 중요 영역의 종류를 반환합니다. 초임계 영역은 중요 영역의 수퍼세트이므로 코드가 임계 영역을 입력한 다음 `InsideHyperCriticalRegion` 초임계 영역이 반환됩니다.

```cpp
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>Return Value

스레드 프록시가 있는 중요 영역의 유형입니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[IUMSScheduler 구조체](iumsscheduler-structure.md)
