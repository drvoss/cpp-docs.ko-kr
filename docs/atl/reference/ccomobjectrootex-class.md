---
title: CComObject루트텍스 클래스
ms.date: 11/04/2016
f1_keywords:
- CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::InternalAddRef
- ATLCOM/ATL::InternalRelease
- ATLCOM/ATL::Lock
- ATLCOM/ATL::Unlock
- ATLCOM/ATL::FinalConstruct
- ATLCOM/ATL::FinalRelease
- ATLCOM/ATL::OuterAddRef
- ATLCOM/ATL::OuterQueryInterface
- ATLCOM/ATL::OuterRelease
- ATLCOM/ATL::InternalQueryInterface
- ATLCOM/ATL::ObjectMain
- ATLCOM/ATL::m_dwRef
- ATLCOM/ATL::m_pOuterUnknown
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
ms.openlocfilehash: 87e2d7dca81221f4fac2a5189ecb0effbdceddc2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747908"
---
# <a name="ccomobjectrootex-class"></a>CComObject루트텍스 클래스

이 클래스는 집계되지 않은 개체와 집계되지 않은 개체 모두에 대해 개체 참조 수 관리를 처리하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template<class ThreadModel>
class CComObjectRootEx : public CComObjectRootBase
```

#### <a name="parameters"></a>매개 변수

*스레드 모델*<br/>
메서드가 원하는 스레딩 모델을 구현하는 클래스입니다. *스레드 모델을* [CComSingleThreadModel,](../../atl/reference/ccomsinglethreadmodel-class.md) [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)또는 [CComMultiThreadModel로](../../atl/reference/ccommultithreadmodelnocs-class.md)설정하여 스레딩 모델을 명시적으로 선택할 수 있습니다. *스레드 모델을* [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 또는 [CComGlobalsThreadModel로](atl-typedefs.md#ccomglobalsthreadmodel)설정하여 서버의 기본 스레드 모델을 수락할 수 있습니다.

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CComObjectRootEx](#ccomobjectrootex)|생성자입니다.|
|[내부애드레프](#internaladdref)|집계되지 않은 개체에 대한 참조 수를 증가시입니다.|
|[내부 릴리스](#internalrelease)|집계되지 않은 개체에 대한 참조 수를 삭제합니다.|
|[잠금](#lock)|스레드 모델이 다중 스레드인 경우 임계 단면 개체의 소유권을 얻습니다.|
|[잠금을 해제](#unlock)|스레드 모델이 다중 스레드인 경우 임계 단면 개체의 소유권을 해제합니다.|

### <a name="ccomobjectrootbase-methods"></a>CComObject루트베이스 메소드

|||
|-|-|
|[파이널컨스트럭트](#finalconstruct)|클래스에서 재정의하여 개체에 필요한 초기화를 수행합니다.|
|[최종 릴리스](#finalrelease)|클래스에서 재정의하여 개체에 필요한 정리를 수행합니다.|
|[아우터애드레프](#outeraddref)|집계된 개체에 대한 참조 수를 증가합니다.|
|[외부 쿼리 인터페이스](#outerqueryinterface)|집계된 개체의 `IUnknown` 외부로 위임합니다.|
|[외부 릴리즈](#outerrelease)|집계된 개체에 대한 참조 수를 삭제합니다.|

### <a name="static-functions"></a>정적 함수

|||
|-|-|
|[내부 쿼리 인터페이스](#internalqueryinterface)|집계되지 않은 `IUnknown` 개체에 위임합니다.|
|[개체 메인](#objectmain)|개체 맵에 나열된 파생 클래스에 대해 모듈 초기화 및 종료 중에 호출됩니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_dwRef](#m_dwref)|`m_pOuterUnknown`와 , 공용 구조의 일부입니다. 개체가 집계되지 않은 경우 `AddRef` 참조 `Release`수를 유지합니다.|
|[m_pOuterUnknown](#m_pouterunknown)|`m_dwRef`와 , 공용 구조의 일부입니다. 개체가 집계되어 알 수 없는 외부에 대한 포인터를 보유할 때 사용됩니다.|

## <a name="remarks"></a>설명

`CComObjectRootEx`은 집계되지 않은 개체와 집계된 개체 모두에 대해 개체 참조 수 관리를 처리합니다. 개체가 집계되지 않는 경우 개체 참조 수를 보유하고 개체가 집계되는 경우 알 수 없는 외부포인터를 보유합니다. 집계된 개체의 `CComObjectRootEx` 경우 구성할 내부 개체의 실패를 처리하고 내부 인터페이스가 해제되거나 내부 개체가 삭제될 때 외부 개체가 삭제되지 않도록 보호하는 데 메서드를 사용할 수 있습니다.

COM 서버를 구현하는 클래스는 `CComObjectRootEx` [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)에서 상속해야 합니다.

클래스 정의가 [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) 매크로를 지정하는 경우 ATL은 호출되는 `CComPolyObject<CYourClass>` 시간의 `IClassFactory::CreateInstance` 인스턴스를 만듭니다. 생성 하는 동안 알 수 없는 외부의 값이 확인 됩니다. NULL인 `IUnknown` 경우 집계되지 않은 개체에 대해 구현됩니다. 외부 알 수 없는 `IUnknown` NULL이 아닌 경우 집계된 개체에 대해 구현됩니다.

클래스에서 DECLARE_POLY_AGGREGATABLE 매크로를 지정하지 않으면 ATL은 `CAggComObject<CYourClass>` 집계된 개체에 대한 `CComObject<CYourClass>` 인스턴스 또는 집계되지 않은 개체에 대한 인스턴스를 만듭니다.

이 `CComPolyObject` 사용의 장점은 집계된 `CComAggObject` 서비스 `CComObject` 및 비집계 사례를 처리하기 위해 모듈과 모듈모두에 두 가지를 모두 사용하지 않는 것입니다. 단일 `CComPolyObject` 개체는 두 경우를 모두 처리합니다. 따라서 vtable의 복사본과 함수의 복사본 이 하나만 모듈에 있습니다. vtable이 큰 경우 모듈 크기를 크게 줄일 수 있습니다. 그러나 vtable이 작으면 집계되거나 집계되지 않은 개체에 최적화되지 않으므로 모듈 크기가 약간 커질 `CComPolyObject` `CComAggObject` 수 `CComObject`있습니다.

개체가 집계된 경우 [IUnknown은](/windows/win32/api/unknwn/nn-unknwn-iunknown) `CComAggObject` 또는 `CComPolyObject`에 의해 구현됩니다. 이러한 `QueryInterface`클래스는 `AddRef`"를 `CComObjectRootEx`위임하고 `OuterQueryInterface` `Release` `OuterAddRef`' `OuterRelease` s. 및 알 수 없는 외부로 전달한다. 일반적으로 클래스에서 `CComObjectRootEx::FinalConstruct` 재정의를 사용하여 집계된 개체를 만들고 `CComObjectRootEx::FinalRelease` 집계된 개체를 해제하도록 재정의합니다.

개체가 집계되지 않은 `IUnknown` 경우 또는 `CComObject` `CComPolyObject`에 의해 구현됩니다. 이 `QueryInterface`경우 를 `AddRef`호출하고 `Release` `CComObjectRootEx`'의 `InternalQueryInterface`에 `InternalAddRef`대해 위임하고 `InternalRelease` 실제 작업을 수행합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomobjectrootexccomobjectrootex"></a><a name="ccomobjectrootex"></a>CComObject루트Ex::CComObject루트Ex

생성자는 참조 수를 0으로 초기화합니다.

```
CComObjectRootEx();
```

## <a name="ccomobjectrootexfinalconstruct"></a><a name="finalconstruct"></a>CComObject루트Ex::최종 컨스트럭트

파생 클래스에서 이 메서드를 재정의하여 개체에 필요한 초기화를 수행할 수 있습니다.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Return Value

성공 또는 표준 오류 HRESULT 값 중 하나에 S_OK 반환합니다.

### <a name="remarks"></a>설명

기본적으로 S_OK `CComObjectRootEx::FinalConstruct` 반환하기만 하면 됩니다.

클래스의 생성자 보다는 `FinalConstruct` 초기화를 수행 하는 장점이 있습니다.

- 생성자에서 상태 코드를 반환할 수 없지만 반환 값으로 HRESULT를 `FinalConstruct`반환할 수 있습니다. ATL에서 제공하는 표준 클래스 팩터리를 사용하여 클래스의 개체를 만들 때 이 반환 값이 COM 클라이언트로 다시 전파되어 자세한 오류 정보를 제공할 수 있습니다.

- 클래스의 생성자에서 가상 함수 메커니즘을 통해 가상 함수를 호출할 수 없습니다. 클래스의 생성자에서 가상 함수를 호출하면 상속 계층 구조의 해당 지점에서 정의된 대로 정적으로 해결된 함수 호출이 발생합니다. 순수 가상 함수에 대한 호출은 링커 오류를 초래합니다.

   클래스는 상속 계층 구조에서 가장 파생된 클래스가 아니며 ATL에서 제공하는 파생 클래스에 의존하여 일부 기능을 제공합니다. 초기화가 해당 클래스에서 제공하는 기능을 사용해야 할 가능성이 있지만 클래스의 개체가 다른 개체를 집계해야 하는 경우 해당 클래스의 생성자가 해당 기능에 액세스할 수 없습니다. 가장 파생된 클래스가 완전히 생성되기 전에 클래스의 구성 코드가 실행됩니다.

   그러나 `FinalConstruct` 가장 파생된 클래스가 완전히 생성된 직후에 호출되므로 가상 함수를 호출하고 ATL에서 제공하는 참조 계수 구현을 사용할 수 있습니다.

### <a name="example"></a>예제

일반적으로 집계된 개체를 만들기 위해 `CComObjectRootEx` 파생된 클래스에서 이 메서드를 재정의합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]

시공에 실패하면 오류를 반환할 수 있습니다. 또한 매크로 [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) 사용하여 내부 집계된 개체가 참조 수를 증가한 다음 개수를 0으로 감소하는 경우 외부 개체가 삭제되지 않도록 보호할 수 있습니다.

다음은 집계를 만드는 일반적인 방법입니다.

- 클래스 `IUnknown` 개체에 포인터를 추가하고 생성자의 NULL에 초기화합니다.

- 재정의하여 `FinalConstruct` 집계를 만듭니다.

- [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) `IUnknown` 매크로에 대한 매개 변수로 정의한 포인터를 사용합니다.

- 재재정으로 `FinalRelease` 포인터를 해제합니다. `IUnknown`

## <a name="ccomobjectrootexfinalrelease"></a><a name="finalrelease"></a>CComObject루트Ex::최종 릴리스

파생 클래스에서 이 메서드를 재정의하여 개체에 필요한 정리를 수행할 수 있습니다.

```cpp
void FinalRelease();
```

### <a name="remarks"></a>설명

기본적으로 아무 `CComObjectRootEx::FinalRelease` 것도 수행하지 않습니다.

`FinalRelease` 개체가 호출되는 `FinalRelease` 지점에서 완전히 생성되므로 클래스의 소멸자에 코드를 추가하는 것이 좋습니다. 이렇게 하면 가장 파생된 클래스에서 제공하는 메서드에 안전하게 액세스할 수 있습니다. 이는 삭제하기 전에 집계된 개체를 해제하는 데 특히 중요합니다.

## <a name="ccomobjectrootexinternaladdref"></a><a name="internaladdref"></a>CComObject루트Ex::내부애드레프

집계되지 않은 개체의 참조 수를 1씩 증가합니다.

```
ULONG InternalAddRef();
```

### <a name="return-value"></a>Return Value

진단 및 테스트에 유용할 수 있는 값입니다.

### <a name="remarks"></a>설명

스레드 모델이 다중 스레드인 `InterlockedIncrement` 경우 두 개 이상의 스레드가 동시에 참조 수를 변경하지 못하도록 하는 데 사용됩니다.

## <a name="ccomobjectrootexinternalqueryinterface"></a><a name="internalqueryinterface"></a>CComObject루트Ex::내부 쿼리 인터페이스

요청된 인터페이스에 대한 포인터를 검색합니다.

```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*Pthis*<br/>
【인】 에 노출된 인터페이스의 COM 맵이 포함된 개체에 대한 `QueryInterface`포인터입니다.

*펜스 엔트리*<br/>
【인】 사용 가능한 `_ATL_INTMAP_ENTRY` 인터페이스의 맵에 액세스하는 구조에 대한 포인터입니다.

*Iid*<br/>
【인】 요청되는 인터페이스의 GUID입니다.

*ppvObject*<br/>
【아웃】 인터페이스를 찾을 수 없는 경우 *iid*또는 NULL에 지정된 인터페이스 포인터에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`InternalQueryInterface`에서는 COM 맵 테이블의 인터페이스만 처리됩니다. 개체가 집계된 경우 `InternalQueryInterface` 알 수 없는 외부로 위임하지 않습니다. 매크로 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) 또는 변형 중 하나를 사용하여 COM 맵 테이블에 인터페이스를 입력할 수 있습니다.

## <a name="ccomobjectrootexinternalrelease"></a><a name="internalrelease"></a>CComObject루트Ex::내부 릴리스

집계되지 않은 개체의 참조 수를 1로 감소시입니다.

```
ULONG InternalRelease();
```

### <a name="return-value"></a>Return Value

디버그가 아닌 빌드와 디버그 빌드 모두에서 이 함수는 진단 또는 테스트에 유용할 수 있는 값을 반환합니다. 반환되는 정확한 값은 사용된 운영 체제와 같은 여러 요인에 따라 달라지며 참조 수일 수도 있고 그렇지 않을 수도 있습니다.

### <a name="remarks"></a>설명

스레드 모델이 다중 스레드인 `InterlockedDecrement` 경우 두 개 이상의 스레드가 동시에 참조 수를 변경하지 못하도록 하는 데 사용됩니다.

## <a name="ccomobjectrootexlock"></a><a name="lock"></a>CComObject루트Ex::잠금

스레드 모델이 다중 스레드인 경우 이 메서드는 Win32 API 함수 [EnterCriticalSection을](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)호출하여 스레드가 개인 데이터 멤버를 통해 얻은 중요한 섹션 개체의 소유권을 가져올 때까지 기다립니다.

```cpp
void Lock();
```

### <a name="remarks"></a>설명

보호된 코드실행이 끝나면 스레드는 임계 `Unlock` 섹션의 소유권을 해제하기 위해 호출해야 합니다.

스레드 모델이 단일 스레드인 경우 이 메서드는 아무 것도 수행하지 않습니다.

## <a name="ccomobjectrootexm_dwref"></a><a name="m_dwref"></a>CComObject루트Ex::m_dwRef

4바이트의 메모리에 액세스하는 공용 구조의 일부입니다.

```
long m_dwRef;
```

### <a name="remarks"></a>설명

`m_pOuterUnknown`을 사용하면 공용 구조의 일부가 됩니다.

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

개체가 집계되지 않은 경우 참조 수가 `AddRef` 액세스하여 `Release` 에 `m_dwRef`저장됩니다. 개체가 집계되면 알 수 없는 외부포인터가 [m_pOuterUnknown](#m_pouterunknown)저장됩니다.

## <a name="ccomobjectrootexm_pouterunknown"></a><a name="m_pouterunknown"></a>CComObject루트Ex::m_pOuterUnknown

4바이트의 메모리에 액세스하는 공용 구조의 일부입니다.

```
IUnknown*
    m_pOuterUnknown;
```

### <a name="remarks"></a>설명

`m_dwRef`을 사용하면 공용 구조의 일부가 됩니다.

```
union {
    long m_dwRef;
    IUnknown* m_pOuterUnknown;
};
```

개체가 집계되면 알 수 없는 외부에 대한 `m_pOuterUnknown`포인터가 에 저장됩니다. 개체가 집계되지 않으면 참조 수가 `AddRef` `Release` [액세스되어 m_dwRef](#m_dwref)에 저장됩니다.

## <a name="ccomobjectrootexobjectmain"></a><a name="objectmain"></a>CComObject루트Ex::오브젝트메인

개체 맵에 나열된 각 클래스에 대해 모듈이 초기화될 때 이 함수가 한 번 호출되고 종료될 때 다시 호출됩니다.

```
static void WINAPI ObjectMain(bool bStarting);
```

### <a name="parameters"></a>매개 변수

*b 시작*<br/>
【아웃】 클래스가 초기화되는 경우 TRUE 값입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

*bStarting* 매개 변수의 값은 모듈이 초기화되고 있는지 또는 종료되는지 여부를 나타냅니다. 기본 구현은 `ObjectMain` 아무 것도 하지 않지만 클래스에서 이 함수를 재정의하여 클래스에 할당하려는 리소스를 초기화하거나 정리할 수 있습니다. 클래스의 `ObjectMain` 인스턴스가 요청되기 전에 호출됩니다.

`ObjectMain`DLL의 진입점에서 호출되므로 진입점 함수가 수행할 수 있는 작업 유형이 제한됩니다. 이러한 제한 사항에 대한 자세한 내용은 [DLL 및 Visual C++ 런타임 라이브러리 동작](../../build/run-time-library-behavior.md) 및 [DllMain](/windows/win32/Dlls/dllmain)을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]

## <a name="ccomobjectrootexouteraddref"></a><a name="outeraddref"></a>CComObject루트Ex::아우터애드레프

집계의 알 수 없는 외부의 참조 수를 증가시입니다.

```
ULONG OuterAddRef();
```

### <a name="return-value"></a>Return Value

진단 및 테스트에 유용할 수 있는 값입니다.

## <a name="ccomobjectrootexouterqueryinterface"></a><a name="outerqueryinterface"></a>CComObject루트Ex::외부 쿼리 인터페이스

요청된 인터페이스에 대한 간접 포인터를 검색합니다.

```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 요청되는 인터페이스의 GUID입니다.

*ppvObject*<br/>
【아웃】 집계가 인터페이스를 지원하지 않는 경우 *iid*또는 NULL에 지정된 인터페이스 포인터에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

## <a name="ccomobjectrootexouterrelease"></a><a name="outerrelease"></a>CComObject루트Ex::외부 릴리스

집계의 알 수 없는 외부의 참조 수를 감소시입니다.

```
ULONG OuterRelease();
```

### <a name="return-value"></a>Return Value

디버그가 아닌 빌드에서는 항상 0을 반환합니다. 디버그 빌드에서 진단 또는 테스트에 유용할 수 있는 값을 반환합니다.

## <a name="ccomobjectrootexunlock"></a><a name="unlock"></a>CComObject루트Ex::잠금 해제

스레드 모델이 다중 스레드인 경우 이 메서드는 개인 데이터 멤버를 통해 얻은 임계 섹션 개체의 소유권을 해제하는 Win32 API 함수 [LeaveCriticalSection을](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)호출합니다.

```cpp
void Unlock();
```

### <a name="remarks"></a>설명

소유권을 얻으려면 스레드가 `Lock`를 호출해야 합니다. 각 호출은 `Lock` 중요 섹션의 소유권을 해제하기 위해 `Unlock` 해당 호출이 필요합니다.

스레드 모델이 단일 스레드인 경우 이 메서드는 아무 것도 수행하지 않습니다.

## <a name="see-also"></a>참조

[CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject 클래스](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
