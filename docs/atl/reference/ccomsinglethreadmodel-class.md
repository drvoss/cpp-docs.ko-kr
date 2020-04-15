---
title: CComSingle스레드모델 클래스
ms.date: 2/29/2020
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
ms.openlocfilehash: 3d8169c999ba96049bc711033f7ba2ef53989663
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327328"
---
# <a name="ccomsinglethreadmodel-class"></a>CComSingle스레드모델 클래스

이 클래스는 변수값을 증분하고 감소시키는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
class CComSingleThreadModel
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CComSingle스레드 모델::자동 임계 섹션](#autocriticalsection)|참조 클래스 [CComFakecriticalsection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComSingle스레드 모델::중요섹션](#criticalsection)|참조 `CComFakeCriticalSection`클래스 .|
|[CComSingle스레드 모델::스레드 모델NoCS](#threadmodelnocs)|참조 `CComSingleThreadModel`.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComSingle스레드모델::D](#decrement)|지정된 변수의 값을 감소시입니다. 이 구현은 스레드에서 안전하지 않습니다.|
|[CComSingle스레드 모델::증분](#increment)|지정된 변수의 값을 증가시입니다. 이 구현은 스레드에서 안전하지 않습니다.|

## <a name="remarks"></a>설명

`CComSingleThreadModel`에서는 변수 값을 증분및 감소시키는 방법을 제공합니다. [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComMultiThreadModelNoCS와](../../atl/reference/ccommultithreadmodelnocs-class.md)달리 이러한 메서드는 스레드에서 안전하지 않습니다.

일반적으로 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 또는 [CComGlobalsThread Model](atl-typedefs.md#ccomglobalsthreadmodel)중 두 **가지 형식 def** 이름 중 하나를 `CComSingleThreadModel` 사용합니다. 각 **typedef에서** 참조하는 클래스는 다음 표와 같이 사용되는 스레딩 모델에 따라 다릅니다.

|형식 정의|단일 스레딩 모델|아파트 스레딩 모델|무료 스레딩 모델|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S `CComSingleThreadModel`= ; M =`CComMultiThreadModel`

`CComSingleThreadModel`자체는 세 **가지 typedef** 이름을 정의합니다. `ThreadModelNoCS`참조 `CComSingleThreadModel`. `AutoCriticalSection`및 `CriticalSection` 참조 클래스 [CComFakeCriticalSection은](../../atl/reference/ccomfakecriticalsection-class.md)임계 섹션의 소유권을 가져오고 해제하는 것과 관련된 빈 메서드를 제공합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomsinglethreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComSingle스레드 모델::자동 임계 섹션

을 `CComSingleThreadModel`사용하는 경우 **typedef** 이름은 `AutoCriticalSection` [클래스 CComFakeCriticalSection을](../../atl/reference/ccomfakecriticalsection-class.md)참조합니다.

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>설명

임계 `CComFakeCriticalSection` 섹션을 제공하지 않기 때문에 해당 메서드는 아무 것도 수행하지 않습니다.

[CComMultiThread모델](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComMultiThreadModelNoCS에는](../../atl/reference/ccommultithreadmodelnocs-class.md) `AutoCriticalSection`에 대한 정의가 포함되어 있습니다. 다음 표에서는 스레딩 모델 클래스와 다음에 참조되는 `AutoCriticalSection`임계 섹션 클래스 간의 관계를 보여 주며 있습니다.

|정의된 클래스|참조된 클래스|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

`AutoCriticalSection`은 에서 **typedef** 이름 [CriticalSection을](#criticalsection)사용할 수 있습니다. CRT 시작 `AutoCriticalSection` 코드를 제거하려는 경우 전역 개체 또는 정적 클래스 멤버에 지정해서는 안 됩니다.

### <a name="example"></a>예제

[CComMultiThread 모델::자동 임계 섹션](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)을 참조하십시오.

## <a name="ccomsinglethreadmodelcriticalsection"></a><a name="criticalsection"></a>CComSingle스레드 모델::중요섹션

을 `CComSingleThreadModel`사용하는 경우 **typedef** 이름은 `CriticalSection` [클래스 CComFakeCriticalSection을](../../atl/reference/ccomfakecriticalsection-class.md)참조합니다.

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>설명

임계 `CComFakeCriticalSection` 섹션을 제공하지 않기 때문에 해당 메서드는 아무 것도 수행하지 않습니다.

[CComMultiThread모델](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComMultiThreadModelNoCS에는](../../atl/reference/ccommultithreadmodelnocs-class.md) `CriticalSection`에 대한 정의가 포함되어 있습니다. 다음 표에서는 스레딩 모델 클래스와 다음에 참조되는 `CriticalSection`임계 섹션 클래스 간의 관계를 보여 주며 있습니다.

|정의된 클래스|참조된 클래스|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

은 **typedef** 이름 자동 임계 [섹션을](#autocriticalsection)사용할 수 있습니다. `CriticalSection` CRT 시작 `AutoCriticalSection` 코드를 제거하려는 경우 전역 개체 또는 정적 클래스 멤버에 지정해서는 안 됩니다.

### <a name="example"></a>예제

[CComMultiThread 모델::자동 임계 섹션](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)을 참조하십시오.

## <a name="ccomsinglethreadmodeldecrement"></a><a name="decrement"></a>CComSingle스레드모델::D

이 정적 함수는 *p.*

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 감소될 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

감소의 결과입니다.

## <a name="ccomsinglethreadmodelincrement"></a><a name="increment"></a>CComSingle스레드 모델::증분

이 정적 함수는 *p.*

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 증분할 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

증분의 결과입니다.

## <a name="ccomsinglethreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComSingle스레드 모델::스레드 모델NoCS

을 `CComSingleThreadModel`사용할 때 **typedef** `ThreadModelNoCS` `CComSingleThreadModel`이름은 단순히 참조합니다.

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>설명

[CComMultiThread모델](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComMultiThreadModelNoCS에는](../../atl/reference/ccommultithreadmodelnocs-class.md) `ThreadModelNoCS`에 대한 정의가 포함되어 있습니다. 다음 표에서는 스레딩 모델 클래스와 다음에 참조되는 `ThreadModelNoCS`클래스 간의 관계를 보여 주며 있습니다.

|정의된 클래스|참조된 클래스|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>예제

[CComMultiThread 모델::자동 임계 섹션](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
