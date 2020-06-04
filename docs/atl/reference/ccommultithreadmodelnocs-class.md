---
title: CComMultiThreadModelNoCS 클래스
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
ms.openlocfilehash: 4d41ffcfccbd7ef65ed86df79bffec1209a88cd3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327661"
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS 클래스

`CComMultiThreadModelNoCS`는 중요한 섹션 잠금 또는 잠금 해제 기능 없이 변수값을 증분하고 감소시키는 스레드 안전 방법을 제공합니다.

## <a name="syntax"></a>구문

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CComMultiThreadModelNoCS::자동 임계 섹션](#autocriticalsection)|참조 클래스 [CComFakecriticalsection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComMultiThreadModelNoCS::중요 섹션](#criticalsection)|참조 `CComFakeCriticalSection`클래스 .|
|[CComMultiThreadModelNoCS::스레드 모델NoCS](#threadmodelnocs)|참조 `CComMultiThreadModelNoCS`클래스 .|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComMultiThreadModelNoCS::D](#decrement)|(정적) 스레드 안전 방식으로 지정된 변수의 값을 감소시입니다.|
|[CComMultiThreadModelNoCS::증분](#increment)|(정적) 스레드 안전 방식으로 지정된 변수의 값을 증분합니다.|

## <a name="remarks"></a>설명

`CComMultiThreadModelNoCS`[CComMultiThreadModel은](../../atl/reference/ccommultithreadmodel-class.md) 변수를 증분 및 감소시키기 위한 스레드 안전 메서드를 제공한다는 점에서 유사합니다. 그러나 `CComMultiThreadModelNoCS`. `Lock` `Unlock`

일반적으로 `CComMultiThreadModelNoCS` `ThreadModelNoCS` **typedef** 이름을 통해 사용합니다. 이 **형식 def는** `CComMultiThreadModelNoCS`에서 `CComMultiThreadModel`정의됩니다. 및 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).

> [!NOTE]
> 전역 **typedef** 이름 [CComObjectThread 모델](atl-typedefs.md#ccomobjectthreadmodel) 및 [CComGlobalsThread Model](atl-typedefs.md#ccomglobalsthreadmodel) 은 을 참조하지 `CComMultiThreadModelNoCS`않습니다.

에 추가 `CComMultiThreadModelNoCS` 된 `AutoCriticalSection` 정의 `CriticalSection`및 . `ThreadModelNoCS` 이 후자의 두 **typedef** 이름은 중요한 섹션을 가져오고 해제하는 것과 관련된 빈 메서드를 제공하는 [CComFakeCriticalSection을](../../atl/reference/ccomfakecriticalsection-class.md)참조합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccommultithreadmodelnocsautocriticalsection"></a><a name="autocriticalsection"></a>CComMultiThreadModelNoCS::자동 임계 섹션

을 `CComMultiThreadModelNoCS`사용하는 경우 **typedef** 이름은 `AutoCriticalSection` [클래스 CComFakeCriticalSection을](../../atl/reference/ccomfakecriticalsection-class.md)참조합니다.

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>설명

임계 `CComFakeCriticalSection` 섹션을 제공하지 않기 때문에 해당 메서드는 아무 것도 수행하지 않습니다.

[CComMultiThread모델](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComSingleThreadModel에도](../../atl/reference/ccomsinglethreadmodel-class.md) 에 `AutoCriticalSection`대한 정의가 포함되어 있습니다. 다음 표에서는 스레딩 모델 클래스와 다음에 참조되는 `AutoCriticalSection`임계 섹션 클래스 간의 관계를 보여 주며 있습니다.

|정의된 클래스|참조된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

`AutoCriticalSection`은 에서 **typedef** 이름 [CriticalSection을](#criticalsection)사용할 수 있습니다. CRT 시작 `AutoCriticalSection` 코드를 제거하려는 경우 전역 개체 또는 정적 클래스 멤버에 지정해서는 안 됩니다.

### <a name="example"></a>예제

[CComMultiThread 모델::자동 임계 섹션](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)을 참조하십시오.

## <a name="ccommultithreadmodelnocscriticalsection"></a><a name="criticalsection"></a>CComMultiThreadModelNoCS::중요 섹션

을 `CComMultiThreadModelNoCS`사용하는 경우 **typedef** 이름은 `CriticalSection` [클래스 CComFakeCriticalSection을](../../atl/reference/ccomfakecriticalsection-class.md)참조합니다.

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>설명

임계 `CComFakeCriticalSection` 섹션을 제공하지 않기 때문에 해당 메서드는 아무 것도 수행하지 않습니다.

[CComMultiThread모델](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComSingleThreadModel에도](../../atl/reference/ccomsinglethreadmodel-class.md) 에 `CriticalSection`대한 정의가 포함되어 있습니다. 다음 표에서는 스레딩 모델 클래스와 다음에 참조되는 `CriticalSection`임계 섹션 클래스 간의 관계를 보여 주며 있습니다.

|정의된 클래스|참조된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

`CriticalSection`은 에서 **typedef** 이름을 `AutoCriticalSection`사용할 수 있습니다. CRT 시작 `AutoCriticalSection` 코드를 제거하려는 경우 전역 개체 또는 정적 클래스 멤버에 지정해서는 안 됩니다.

### <a name="example"></a>예제

[CComMultiThread 모델::자동 임계 섹션](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)을 참조하십시오.

## <a name="ccommultithreadmodelnocsdecrement"></a><a name="decrement"></a>CComMultiThreadModelNoCS::D

이 정적 함수는 Win32 함수 [인터록데어션을](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)호출하여 *p.*

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 감소될 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

감소 결과가 0이면 0을 `Decrement` 반환합니다. 감소 결과가 0이 아닌 경우 반환 값도 0이 아닌 것이지만 감소의 결과와 같지 않을 수 있습니다.

### <a name="remarks"></a>설명

**연동Decrement는** 두 개 이상의 스레드가 동시에 이 변수를 사용하는 것을 방지합니다.

## <a name="ccommultithreadmodelnocsincrement"></a><a name="increment"></a>CComMultiThreadModelNoCS::증분

이 정적 함수는 Win32 함수 [인터록Increment를](/windows/win32/api/winnt/nf-winnt-interlockedincrement)호출하여 *p로*가리키는 변수의 값을 증가시

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 증분할 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

증분 결과가 0이면 **증분은** 0을 반환합니다. 증분 결과가 0이 아닌 경우 반환 값도 0이 아니지만 증분 결과와 같지 않을 수 있습니다.

### <a name="remarks"></a>설명

**연동InlockedIncre는** 두 개 이상의 스레드가 동시에 이 변수를 사용하는 것을 방지합니다.

## <a name="ccommultithreadmodelnocsthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComMultiThreadModelNoCS::스레드 모델NoCS

을 `CComMultiThreadModelNoCS`사용할 때 **typedef** `ThreadModelNoCS` `CComMultiThreadModelNoCS`이름은 단순히 참조합니다.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>설명

[CComMultiThread모델](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComSingleThreadModel에도](../../atl/reference/ccomsinglethreadmodel-class.md) 에 `ThreadModelNoCS`대한 정의가 포함되어 있습니다. 다음 표에서는 스레딩 모델 클래스와 다음에 참조되는 `ThreadModelNoCS`클래스 간의 관계를 보여 주며 있습니다.

|정의된 클래스|참조된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

`ThreadModelNoCS` 의 `CComMultiThreadModelNoCS` 정의는 및 `CComMultiThreadModel` `CComSingleThreadModel`을 와 대칭을 제공한다는 점에 유의하십시오. 예를 들어 다음과 같은 `CComMultiThreadModel::AutoCriticalSection` **형식 def를**선언한 샘플 코드가 있다고 가정합니다.

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

에 대해 `ThreadModel` 지정된 클래스에 `CComMultiThreadModelNoCS`관계없이 `_ThreadModel` (예 :) 그에 따라 해결됩니다.

### <a name="example"></a>예제

[CComMultiThread 모델::자동 임계 섹션](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
