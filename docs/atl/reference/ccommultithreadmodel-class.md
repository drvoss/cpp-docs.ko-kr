---
title: CComMultiThreadModel 클래스
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
ms.openlocfilehash: 7ef803439d2d683633e8f9c00810542dd787541e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327664"
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel 클래스

`CComMultiThreadModel`은 변수값을 증분하고 감소시키는 스레드 안전 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
class CComMultiThreadModel
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CComMultiThread 모델::자동 임계 섹션](#autocriticalsection)|참조 클래스 [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|
|[CComMultiThread 모델::중요 섹션](#criticalsection)|참조 클래스 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).|
|[CComMultiThread 모델::스레드 모델NoCS](#threadmodelnocs)|참조 클래스 [CComMultiThreadModelNoCS.](../../atl/reference/ccommultithreadmodelnocs-class.md)|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComMultiThread모델::D](#decrement)|(정적) 스레드 안전 방식으로 지정된 변수의 값을 감소시입니다.|
|[CComMultiThread 모델::증분](#increment)|(정적) 스레드 안전 방식으로 지정된 변수의 값을 증분합니다.|

## <a name="remarks"></a>설명

일반적으로 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 또는 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)의 두 **가지 형식 def** 이름 중 하나를 `CComMultiThreadModel` 사용합니다. 각 **typedef에서** 참조하는 클래스는 다음 표와 같이 사용되는 스레딩 모델에 따라 다릅니다.

|형식 정의|단일 스레딩|아파트 스레딩|무료 스레딩|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S `CComSingleThreadModel`= ; M =`CComMultiThreadModel`

`CComMultiThreadModel`자체는 세 **가지 typedef** 이름을 정의합니다. `AutoCriticalSection`및 `CriticalSection` 중요 섹션의 소유권을 획득하고 해제하는 방법을 제공하는 참조 클래스입니다. `ThreadModelNoCS`참조 클래스 [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md).

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccommultithreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComMultiThread 모델::자동 임계 섹션

을 `CComMultiThreadModel`사용하는 경우 **typedef** 이름은 `AutoCriticalSection` 임계 섹션 개체의 소유권을 가져오고 해제하는 메서드를 제공하는 [CComAutoCriticalSection](ccomautocriticalsection-class.md)클래스를 참조합니다.

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>설명

[CComSingleThread모델](ccomsinglethreadmodel-class.md) 및 [CComMultiThreadModelNoCS에는](ccommultithreadmodelnocs-class.md) 에 `AutoCriticalSection`대한 정의도 포함되어 있습니다. 다음 표에서는 스레딩 모델 클래스와 다음에 참조되는 `AutoCriticalSection`임계 섹션 클래스 간의 관계를 보여 주며 있습니다.

|정의된 클래스|참조된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

`AutoCriticalSection`은 에서 **typedef** 이름 [CriticalSection을](#criticalsection)사용할 수 있습니다. CRT 시작 `AutoCriticalSection` 코드를 제거하려는 경우 전역 개체 또는 정적 클래스 멤버에 지정해서는 안 됩니다.

### <a name="example"></a>예제

다음 코드는 [CComObjectRootEx를](ccomobjectrootex-class.md)모델로 하며 `AutoCriticalSection` 스레딩 환경에서 사용되는 것을 보여 줍니다.

```cpp
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```

다음 표에서는 `InternalAddRef` `Lock` `ThreadModel` 템플릿 매개 변수 및 응용 프로그램에서 사용하는 스레딩 모델에 따라 메서드 및 메서드의 결과를 보여 줄 수 있습니다.

### <a name="threadmodel--ccomobjectthreadmodel"></a>스레드 모델 = CComObject스레드모델

|메서드|단일 또는 아파트 스레딩|무료 스레딩|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|증분은 스레드에서 안전하지 않습니다.|증분은 스레드에서 안전합니다.|
|`Lock`|아무 것도 하지 않습니다. 잠글 수 있는 임계 섹션이 없습니다.|임계 섹션이 잠겨 있습니다.|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>스레드 모델 = CComObject스레드모델::스레드모델NoCS

|메서드|단일 또는 아파트 스레딩|무료 스레딩|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|증분은 스레드에서 안전하지 않습니다.|증분은 스레드에서 안전합니다.|
|`Lock`|아무 것도 하지 않습니다. 잠글 수 있는 임계 섹션이 없습니다.|아무 것도 하지 않습니다. 잠글 수 있는 임계 섹션이 없습니다.|

## <a name="ccommultithreadmodelcriticalsection"></a><a name="criticalsection"></a>CComMultiThread 모델::중요 섹션

을 `CComMultiThreadModel`사용하는 경우 **typedef** 이름은 `CriticalSection` 임계 섹션 개체의 소유권을 가져오고 해제하는 메서드를 제공하는 [CComCriticalSection](ccomcriticalsection-class.md)클래스를 참조합니다.

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>설명

[CComSingleThread모델](ccomsinglethreadmodel-class.md) 및 [CComMultiThreadModelNoCS에는](ccommultithreadmodelnocs-class.md) 에 `CriticalSection`대한 정의도 포함되어 있습니다. 다음 표에서는 스레딩 모델 클래스와 다음에 참조되는 `CriticalSection`임계 섹션 클래스 간의 관계를 보여 주며 있습니다.

|정의된 클래스|참조된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

은 **typedef** 이름 자동 임계 [섹션을](#autocriticalsection)사용할 수 있습니다. `CriticalSection` CRT 시작 `AutoCriticalSection` 코드를 제거하려는 경우 전역 개체 또는 정적 클래스 멤버에 지정해서는 안 됩니다.

### <a name="example"></a>예제

[CComMultiThread 모델::자동 임계 섹션](#autocriticalsection)을 참조하십시오.

## <a name="ccommultithreadmodeldecrement"></a><a name="decrement"></a>CComMultiThread모델::D

이 정적 함수는 Win32 함수 [인터록데어션을](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)호출하여 *p.*

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 감소될 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

감소 결과가 0이면 0을 `Decrement` 반환합니다. 감소 결과가 0이 아닌 경우 반환 값도 0이 아닌 것이지만 감소의 결과와 같지 않을 수 있습니다.

### <a name="remarks"></a>설명

`InterlockedDecrement`이 변수를 동시에 사용하는 스레드를 방지합니다.

## <a name="ccommultithreadmodelincrement"></a><a name="increment"></a>CComMultiThread 모델::증분

이 정적 함수는 Win32 함수 [인터록Increment를](/windows/win32/api/winnt/nf-winnt-interlockedincrement)호출하여 *p로*가리키는 변수의 값을 증가시

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 증분할 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

증분 결과가 0이면 0을 `Increment` 반환합니다. 증분 결과가 0이 아닌 경우 반환 값도 0이 아니지만 증분 결과와 같지 않을 수 있습니다.

### <a name="remarks"></a>설명

`InterlockedIncrement`이 변수를 동시에 사용하는 스레드를 방지합니다.

## <a name="ccommultithreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComMultiThread 모델::스레드 모델NoCS

을 `CComMultiThreadModel`사용하는 경우 **typedef** 이름은 `ThreadModelNoCS` 클래스 [CComMultiThreadModelNoCS를](ccommultithreadmodelnocs-class.md)참조합니다.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>설명

`CComMultiThreadModelNoCS`변수를 증분 및 감소시키는 스레드 안전 메서드를 제공합니다. 그러나 중요한 섹션을 제공하지는 않습니다.

[CComSingleThread모델](ccomsinglethreadmodel-class.md) `CComMultiThreadModelNoCS` 및 에 대한 `ThreadModelNoCS`정의도 포함되어 있습니다. 다음 표에서는 스레딩 모델 클래스와 다음에 참조되는 `ThreadModelNoCS`클래스 간의 관계를 보여 주며 있습니다.

|정의된 클래스|참조된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>예제

[CComMultiThread 모델::자동 임계 섹션](#autocriticalsection)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[CComSingle스레드모델 클래스](ccomsinglethreadmodel-class.md)<br/>
[CComAutoCriticalSection 클래스](ccomautocriticalsection-class.md)<br/>
[CComCriticalsection 클래스](ccomcriticalsection-class.md)<br/>
[클래스 개요](../atl-class-overview.md)
