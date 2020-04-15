---
title: 집계 및 클래스 팩터리 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_AGGREGATABLE
- atlcom/ATL::DECLARE_CLASSFACTORY
- atlcom/ATL::DECLARE_CLASSFACTORY_EX
- atlcom/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- atlcom/ATL::DECLARE_CLASSFACTORY_SINGLETON
- atlcom/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- atlcom/ATL::DECLARE_NOT_AGGREGATABLE
- atlcom/ATL::DECLARE_ONLY_AGGREGATABLE
- atlcom/ATL::DECLARE_POLY_AGGREGATABLE
- atlcom/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- atlcom/ATL::DECLARE_VIEW_STATUS
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
ms.openlocfilehash: 33f33043d1a2c824ada26399365541796178d21d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319331"
---
# <a name="aggregation-and-class-factory-macros"></a>집계 및 클래스 팩터리 매크로

이러한 매크로는 집계를 제어하고 클래스 팩터리를 선언하는 방법을 제공합니다.

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|개체를 집계할 수 있음을 선언합니다(기본값).|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|클래스 팩터리를 ATL 기본 클래스 팩터리인 [CComClassFactory로](../../atl/reference/ccomclassfactory-class.md)선언합니다.|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|클래스 팩터리 개체를 클래스 팩터리로 선언합니다.|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|[CComClassFactory2를](../../atl/reference/ccomclassfactory2-class.md) 클래스 팩터리로 선언합니다.|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|[CComClassFactoryAutoThread를](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리로 선언합니다.|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|[CComClassFactorySingleton을](../../atl/reference/ccomclassfactorysingleton-class.md) 클래스 팩토리로 선언합니다.|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|가상 `GetControllingUnknown` 함수를 선언합니다.|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|개체를 집계할 수 없음을 선언합니다.|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|개체를 집계해야 함을 선언합니다.|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|알 수 없는 외부의 값을 확인하고 개체 집계 가능 여부 또는 집계 가능하지 않음을 적절하게 선언합니다.|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|내부 오브젝트를 구성하는 동안 외부 오브젝트가 삭제되지 않도록 보호합니다.|
|[DECLARE_VIEW_STATUS](#declare_view_status)|컨테이너에 VIEWSTATUS 플래그를 지정합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="declare_aggregatable"></a><a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE

개체를 집계할 수 있음을 지정합니다.

```
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 집계 가능한 것으로 정의하는 클래스의 이름입니다.

### <a name="remarks"></a>설명

[CComCoClass기본](../../atl/reference/ccomcoclass-class.md) 집계 모델을 지정하는 이 매크로가 포함되어 있습니다. 이 기본값을 재정의하려면 클래스 정의에서 [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) 또는 [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) 매크로를 지정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_classfactory"></a><a name="declare_classfactory"></a>DECLARE_CLASSFACTORY

[CComClassFactory를](../../atl/reference/ccomclassfactory-class.md) 클래스 팩터리로 선언합니다.

```
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>설명

[CComCoClass는](../../atl/reference/ccomcoclass-class.md) 이 매크로를 사용하여 개체의 기본 클래스 팩터리를 선언합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

## <a name="ccomclassfactory-class"></a><a name="ccomclassfactory_class"></a>C컴클래스팩토리 클래스

이 클래스는 [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) 인터페이스를 구현합니다.

```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>설명

`CComClassFactory`에서는 특정 CLSID의 개체를 만드는 메서드를 포함 하는 [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) 인터페이스를 구현 하 고 새 개체를 더 빨리 만들 수 있도록 메모리에 클래스 팩터리 잠금을 포함 합니다. `IClassFactory`시스템 레지스트리에 등록하고 CLSID를 할당하는 모든 클래스에 대해 구현되어야 합니다.

ATL 개체는 일반적으로 [CComCoClass에서](../../atl/reference/ccomcoclass-class.md)파생하여 클래스 팩터리를 획득합니다. 이 클래스에는 `CComClassFactory`를 기본 클래스 팩터리로 선언하는 매크로 [DECLARE_CLASSFACTORY](#declare_classfactory) 포함되어 있습니다. 이 기본값을 재정의하려면 클래스 정의에서*DECLARE_CLASSFACTORY XXX* 매크로 중 하나를 지정합니다. 예를 들어 [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) 매크로는 클래스 팩터리에 대해 지정된 클래스를 사용합니다.

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

위의 클래스 정의는 `CMyClassFactory` 개체의 기본 클래스 팩터리로 사용할 지정합니다. `CMyClassFactory`에서 `CComClassFactory` 파생되고 재정의해야 `CreateInstance`합니다.

ATL은 클래스 팩터리를 선언하는 세 가지 다른 매크로를 제공합니다.

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) 라이센스를 통해 생성을 제어하는 [CComClassFactory2를](../../atl/reference/ccomclassfactory2-class.md)사용합니다.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) [CComClassFactoryAutoThread를](../../atl/reference/ccomclassfactoryautothread-class.md)사용하여 여러 아파트에서 개체를 만듭니다.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) 단일 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 개체를 생성하는 [CComClassFactorySingleton을](../../atl/reference/ccomclassfactorysingleton-class.md)사용합니다.

## <a name="declare_classfactory_ex"></a><a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX

클래스 `cf` 팩터리로 선언합니다.

```
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>매개 변수

*Cf*<br/>
【인】 클래스 팩터리 개체를 구현하는 클래스의 이름입니다.

### <a name="remarks"></a>설명

*cf* 매개 변수는 [CComClassFactory에서](../../atl/reference/ccomclassfactory-class.md) 파생되고 메서드를 `CreateInstance` 재정의해야 합니다.

[CComCoClass](../../atl/reference/ccomcoclass-class.md)에는 기본 클래스 팩터리로 `CComClassFactory` 지정하는 [DECLARE_CLASSFACTORY](#declare_classfactory) 매크로가 포함되어 있습니다. 그러나 개체의 클래스 정의에 DECLARE_CLASSFACTORY_EX 매크로를 포함하면 이 기본값을 재정의합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

## <a name="declare_classfactory2"></a><a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2

[CComClassFactory2를](../../atl/reference/ccomclassfactory2-class.md) 클래스 팩터리로 선언합니다.

```
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>매개 변수

*lic*<br/>
【인】 `VerifyLicenseKey`및 . `GetLicenseKey` `IsLicenseValid`

### <a name="remarks"></a>설명

[CComCoClass에는](../../atl/reference/ccomcoclass-class.md) [cComClassFactory를](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 지정하는 [DECLARE_CLASSFACTORY](#declare_classfactory) 매크로가 포함되어 있습니다. 그러나 개체의 클래스 정의에 DECLARE_CLASSFACTORY2 매크로를 포함하면 이 기본값을 재정의합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

## <a name="ccomclassfactory2-class"></a><a name="ccomclassfactory2_class"></a>C컴클래스팩토리2 클래스

이 클래스는 [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) 인터페이스를 구현합니다.

```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>매개 변수

*라이센스*<br/>
다음과 같은 정적 함수를 구현하는 클래스:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>설명

`CComClassFactory2`[IClassFactory의](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) 확장인 [IClassFactory2](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)인터페이스를 구현합니다. `IClassFactory2`라이선스를 통해 개체 생성을 제어합니다. 라이센스가 부여된 컴퓨터에서 실행되는 클래스 팩터리는 런타임 라이센스 키를 제공할 수 있습니다. 이 라이센스 키를 사용하면 전체 컴퓨터 라이센스가 없는 경우 응용 프로그램이 개체를 인스턴스화할 수 있습니다.

ATL 개체는 일반적으로 [CComCoClass에서](../../atl/reference/ccomcoclass-class.md)파생하여 클래스 팩터리를 획득합니다. 이 클래스에는 [CComClassFactory를](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 선언하는 매크로 [DECLARE_CLASSFACTORY](#declare_classfactory)포함됩니다. 을 `CComClassFactory2`사용하려면 개체의 클래스 정의에서 [DECLARE_CLASSFACTORY2](#declare_classfactory2) 매크로를 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`에서 템플릿 매개 `CComClassFactory2`변수를 " 정적 `VerifyLicenseKey` `GetLicenseKey`함수 `IsLicenseValid`를 구현해야 합니다. 다음은 간단한 라이센스 클래스의 예입니다.

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2`라이선스 모두에서 `CComClassFactory2Base` 파생됩니다. *license* `CComClassFactory2Base`에서는 `IClassFactory2` **CComObjectRootEx\< CComGlobalsThread 모델 >에서 파생됩니다. **

## <a name="declare_classfactory_auto_thread"></a><a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD

[CComClassFactoryAutoThread를](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리로 선언합니다.

```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>설명

[CComCoClass에는](../../atl/reference/ccomcoclass-class.md) [cComClassFactory를](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 지정하는 [DECLARE_CLASSFACTORY](#declare_classfactory) 매크로가 포함되어 있습니다. 그러나 개체의 클래스 정의에 DECLARE_CLASSFACTORY_AUTO_THREAD 매크로를 포함하면 이 기본값을 재정의합니다.

여러 아파트(proc 서버)에서 객체를 만들 때 클래스에 DECLARE_CLASSFACTORY_AUTO_THREAD 추가합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="ccomclassfactoryautothread-class"></a><a name="ccomclassfactoryautothread_class"></a>CComClass팩토리오토스레드 클래스

이 클래스는 [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) 인터페이스를 구현하고 여러 아파트에서 개체를 만들 수 있습니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>설명

`CComClassFactoryAutoThread`[CComClassFactory와](../../atl/reference/ccomclassfactory-class.md)유사하지만 여러 아파트에서 개체를 만들 수 있습니다. 이 지원을 활용하려면 [CComAutoThreadModule에서](../../atl/reference/ccomautothreadmodule-class.md)EXE 모듈을 파생합니다.

ATL 개체는 일반적으로 [CComCoClass에서](../../atl/reference/ccomcoclass-class.md)파생하여 클래스 팩터리를 획득합니다. 이 클래스에는 [CComClassFactory를](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 선언하는 매크로 [DECLARE_CLASSFACTORY](#declare_classfactory)포함됩니다. 을 `CComClassFactoryAutoThread`사용하려면 개체의 클래스 정의에서 [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) 매크로를 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="declare_classfactory_singleton"></a><a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON

[CComClassFactorySingleton을](../../atl/reference/ccomclassfactorysingleton-class.md) 클래스 팩토리로 선언합니다.

```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>매개 변수

*obj*<br/>
【인】 클래스 개체의 이름입니다.

### <a name="remarks"></a>설명

[CComCoClass에는](../../atl/reference/ccomcoclass-class.md) [cComClassFactory를](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 지정하는 [DECLARE_CLASSFACTORY](#declare_classfactory) 매크로가 포함되어 있습니다. 그러나 개체의 클래스 정의에 DECLARE_CLASSFACTORY_SINGLETON 매크로를 포함하면 이 기본값을 재정의합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="ccomclassfactorysingleton-class"></a><a name="ccomclassfactorysingleton_class"></a>C컴클래스팩토리싱글톤 클래스

이 클래스는 [CComClassFactory에서](../../atl/reference/ccomclassfactory-class.md) 파생되며 [CComObjectGlobal을](../../atl/reference/ccomobjectglobal-class.md) 사용하여 단일 개체를 생성합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>매개 변수

*T*<br/>
당신의 클래스.

`CComClassFactorySingleton`[CComClassFactory에서](../../atl/reference/ccomclassfactory-class.md) 파생되며 [CComObjectGlobal을](../../atl/reference/ccomobjectglobal-class.md) 사용하여 단일 개체를 생성합니다. 메서드에 대한 `CreateInstance` 각 호출은 인터페이스 포인터에 대해 이 개체를 쿼리하기만 하면 됩니다.

### <a name="remarks"></a>설명

ATL 개체는 일반적으로 [CComCoClass에서](../../atl/reference/ccomcoclass-class.md)파생하여 클래스 팩터리를 획득합니다. 이 클래스에는 `CComClassFactory`를 기본 클래스 팩터리로 선언하는 매크로 [DECLARE_CLASSFACTORY](#declare_classfactory) 포함되어 있습니다. 을 `CComClassFactorySingleton`사용하려면 개체의 클래스 정의에서 [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) 매크로를 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="declare_get_controlling_unknown"></a><a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN

가상 함수를 `GetControllingUnknown`선언합니다.

```
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>설명

정의되지 않은 컴파일러 오류 메시지가 있는 경우 `GetControllingUnknown` 개체에 이 매크로를 `CComAggregateCreator`추가합니다(예: in).

## <a name="declare_not_aggregatable"></a><a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE

개체를 집계할 수 없도록 지정합니다.

```
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 집계할 수 없는 것으로 정의하는 클래스 개체의 이름입니다.

### <a name="remarks"></a>설명

DECLARE_NOT_AGGREGATABLE `CreateInstance` 개체에 집계하려고 시도하는 경우 오류(CLASS_E_NOAGGREGATION)를 반환합니다.

기본적으로 [CComCoClass에는](../../atl/reference/ccomcoclass-class.md) 개체를 집계할 수 있음을 지정하는 [DECLARE_AGGREGATABLE](#declare_aggregatable) 매크로가 포함되어 있습니다. 이 기본 동작을 재정의하려면 클래스 정의에 DECLARE_NOT_AGGREGATABLE 포함합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_only_aggregatable"></a><a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE

개체를 집계해야 함을 지정합니다.

```
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 집계 가능한 것으로정의하는 클래스 개체의 이름입니다.

### <a name="remarks"></a>설명

DECLARE_ONLY_AGGREGATABLE 개체를 집계되지 않은 개체로 `CoCreate` 시도하면 오류(E_FAIL)가 발생합니다.

기본적으로 [CComCoClass에는](../../atl/reference/ccomcoclass-class.md) 개체를 집계할 수 있음을 지정하는 [DECLARE_AGGREGATABLE](#declare_aggregatable) 매크로가 포함되어 있습니다. 이 기본 동작을 재정의하려면 클래스 정의에 DECLARE_ONLY_AGGREGATABLE 포함합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

## <a name="declare_poly_aggregatable"></a><a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE

개체를 만들 때 **CComPolyObject \< ** *x의* **>** 인스턴스가 생성되도록 지정합니다.

```
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 집계 가능 또는 집계 할 수 없는 것으로 정의하는 클래스 개체의 이름입니다.

### <a name="remarks"></a>설명

생성 하는 동안 알 수 없는 외부의 값이 확인 됩니다. NULL인 `IUnknown` 경우 집계되지 않은 개체에 대해 구현됩니다. 외부 알 수 없는 `IUnknown` NULL이 아닌 경우 집계된 개체에 대해 구현됩니다.

DECLARE_POLY_AGGREGATABLE 사용하면 `CComAggObject` 집계된 서비스 및 `CComObject` 집계되지 않은 사례를 모두 처리하지 않아도 됩니다. 단일 `CComPolyObject` 개체는 두 경우를 모두 처리합니다. 즉, vtable 의 복사본 은 모듈에 하나의 복사본과 함수의 복사본 이 하나만 존재합니다. vtable이 큰 경우 모듈 크기를 크게 줄일 수 있습니다. 그러나 vtable이 작으면 집계되거나 집계되지 않은 개체에 최적화되지 않으므로 모듈 크기가 약간 커질 `CComPolyObject` `CComAggObject` 수 `CComObject`있습니다.

DECLARE_POLY_AGGREGATABLE 매크로는 ATL 컨트롤 마법사를 사용하여 전체 컨트롤을 만드는 경우 개체에 자동으로 선언됩니다.

## <a name="declare_protect_final_construct"></a><a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT

내부 집계된 개체가 참조 수를 증가한 다음 개수를 0으로 감소하는 [경우(FinalConstruct](ccomobjectrootex-class.md#finalconstruct)동안) 개체가 삭제되지 않도록 보호합니다.

```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

## <a name="declare_view_status"></a><a name="declare_view_status"></a>DECLARE_VIEW_STATUS

이 매크로를 ATL ActiveX 컨트롤의 컨트롤 클래스에 배치하여 VIEWSTATUS 플래그를 컨테이너에 지정합니다.

```
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>매개 변수

*statusFlags*<br/>
【인】 뷰 상태 플래그입니다. 플래그 목록은 [VIEWSTATUS를](/windows/win32/api/ocidl/ne-ocidl-viewstatus) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
