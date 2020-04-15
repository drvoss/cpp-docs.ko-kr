---
title: COM 인터페이스 항목 매크로
ms.date: 03/28/2017
f1_keywords:
- atlcom/ATL::COM_INTERFACE_ENTRY
- atlcom/ATL::COM_INTERFACE_ENTRY_IID
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_BREAK
- atlcom/ATL::COM_INTERFACE_ENTRY_CACHED_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_CHAIN
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_NOINTERFACE
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
ms.openlocfilehash: bb7498f639f463290a4a6593ef7c0fbac09b539b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326685"
---
# <a name="com_interface_entry-macros"></a>COM_INTERFACE_ENTRY 매크로

이러한 매크로는 에서 액세스할 `QueryInterface`수 있도록 개체의 인터페이스를 COM 맵에 입력합니다. COM 맵의 항목 순서는 순서 인터페이스가 동안 일치하는 IID를 `QueryInterface`검사하는 것입니다.

|||
|-|-|
|[COM_INTERFACE_ENTRY](#com_interface_entry)|COM 인터페이스 맵에 인터페이스를 입력합니다.|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|이 매크로를 사용하여 상속의 두 가지를 모호하게 합니다.|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|이 매크로를 사용하여 COM 맵에 인터페이스를 입력하고 IID를 지정합니다.|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|[COM_INTERFACE_ENTRY2](#com_interface_entry2)동일하지만 다른 IID를 지정할 수 있습니다.|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|*iid로* 식별된 인터페이스가 쿼리되면 `COM_INTERFACE_ENTRY_AGGREGATE` 을 `punk`전달합니다.|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)동일하며 IID를 쿼리하면 쿼리를 *펑크로*전달합니다.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)동일하며 *펑크가* NULL인 경우를 제외하고 *clsid에서*설명하는 집계를 자동으로 만듭니다.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)동일하며 IID를 쿼리하면 *쿼리를 펑크로*전달하고 *펑크가* NULL인 경우 *clsid에서*설명하는 집계를 자동으로 만듭니다.|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|지정된 인터페이스가 쿼리될 때 프로그램이 [DebugBreak를](/windows/win32/api/debugapi/nf-debugapi-debugbreak) 호출하도록 합니다.|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|모든 인스턴스에 대한 인터페이스 별 데이터를 저장합니다.|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|찢어짐 인터페이스를 노출합니다.|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|처리가 COM 맵에서 이 항목에 도달하면 기본 클래스의 COM 맵을 처리합니다.|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL의 `QueryInterface` 논리에 연결하기위한 일반적인 메커니즘입니다.|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)동일하며 IID를 쿼리하면 *func에*대한 호출이 발생합니다.|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|E_NOINTERFACE 반환하고 지정된 인터페이스가 쿼리될 때 COM 맵 처리를 종료합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="com_interface_entry"></a><a name="com_interface_entry"></a>COM_INTERFACE_ENTRY

COM 인터페이스 맵에 인터페이스를 입력합니다.

### <a name="syntax"></a>구문

```
COM_INTERFACE_ENTRY( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 클래스 개체의 인터페이스 이름은 직접 파생됩니다.

### <a name="remarks"></a>설명

일반적으로 가장 자주 사용하는 항목 유형입니다.

### <a name="example"></a>예제

```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```

### <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="com_interface_entry2"></a><a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2

이 매크로를 사용하여 상속의 두 가지를 모호하게 합니다.

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 개체에서 노출할 인터페이스의 이름입니다.

*x2*<br/>
【인】 *x가* 노출되는 상속 분기의 이름입니다.

### <a name="remarks"></a>설명

예를 들어 두 개의 이중 인터페이스에서 클래스 개체를 `IDispatch` 파생하는 `IDispatch` 경우 인터페이스 중 하나에서 가져올 수 있으므로 COM_INTERFACE_ENTRY2 사용하여 노출됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

## <a name="com_interface_entry_iid"></a><a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID

이 매크로를 사용하여 COM 맵에 인터페이스를 입력하고 IID를 지정합니다.

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 노출된 인터페이스의 GUID입니다.

*x*<br/>
【인】 vtable이 *iid로*식별된 인터페이스로 노출되는 클래스의 이름입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

## <a name="com_interface_entry2_iid"></a><a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID

[COM_INTERFACE_ENTRY2](#com_interface_entry2)동일하지만 다른 IID를 지정할 수 있습니다.

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 인터페이스에 대해 지정하는 GUID입니다.

*x*<br/>
【인】 클래스 개체가 직접 파생되는 인터페이스의 이름입니다.

*x2*<br/>
【인】 클래스 개체가 직접 파생하는 두 번째 인터페이스의 이름입니다.

## <a name="com_interface_entry_aggregate"></a><a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE

*iid로* 식별된 인터페이스가 쿼리되면 COM_INTERFACE_ENTRY_AGGREGATE *펑크로*전달됩니다.

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 인터페이스의 GUID를 쿼리합니다.

*펑크*<br/>
【인】 포인터의 이름입니다. `IUnknown`

### <a name="remarks"></a>설명

*펑크* 매개 변수는 집계 또는 NULL의 내부 알 수 없는 지점을 가리키는 것으로 가정되며, 이 경우 항목이 무시됩니다. 일반적으로 의 `CoCreate` 집계를 `FinalConstruct`수행할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

## <a name="com_interface_entry_aggregate_blind"></a><a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND

[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)동일하며 IID를 쿼리하면 쿼리를 *펑크로*전달합니다.

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>매개 변수

*펑크*<br/>
【인】 포인터의 이름입니다. `IUnknown`

### <a name="remarks"></a>설명

인터페이스 쿼리에 실패하면 COM 맵의 처리가 계속됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

## <a name="com_interface_entry_autoaggregate"></a><a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE

[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)동일하며 *펑크가* NULL인 경우를 제외하고 *clsid에서*설명하는 집계를 자동으로 만듭니다.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 인터페이스의 GUID를 쿼리합니다.

*펑크*<br/>
【인】 포인터의 이름입니다. `IUnknown` COM 맵을 포함하는 클래스의 구성원이어야 합니다.

*clsid*<br/>
【인】 *펑크가* NULL인 경우 생성될 집계의 식별자입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

## <a name="com_interface_entry_autoaggregate_blind"></a><a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)동일하며 IID를 쿼리하면 *쿼리를 펑크로*전달하고 *펑크가* NULL인 경우 *clsid에서*설명하는 집계를 자동으로 만듭니다.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>매개 변수

*펑크*<br/>
【인】 포인터의 이름입니다. `IUnknown` COM 맵을 포함하는 클래스의 구성원이어야 합니다.

*clsid*<br/>
【인】 *펑크가* NULL인 경우 생성될 집계의 식별자입니다.

### <a name="remarks"></a>설명

인터페이스 쿼리에 실패하면 COM 맵의 처리가 계속됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

## <a name="com_interface_entry_break"></a><a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK

지정된 인터페이스가 쿼리될 때 프로그램이 [DebugBreak를](/windows/win32/api/debugapi/nf-debugapi-debugbreak) 호출하도록 합니다.

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 인터페이스 식별자를 생성하는 데 사용되는 텍스트입니다.

### <a name="remarks"></a>설명

인터페이스 IID는 `IID_` *에 x를* 더하여 생성됩니다. 예를 들어 *x가* `IPersistStorage`있는 경우 IID는 입니다. `IID_IPersistStorage`

## <a name="com_interface_entry_cached_tear_off"></a><a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

모든 인스턴스에 대한 인터페이스 별 데이터를 저장합니다.

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 찢어짐 인터페이스의 GUID입니다.

*x*<br/>
【인】 인터페이스를 구현하는 클래스의 이름입니다.

*펑크*<br/>
【인】 포인터의 이름입니다. `IUnknown` COM 맵을 포함하는 클래스의 구성원이어야 합니다. 클래스 개체의 생성자에서 NULL로 초기화해야 합니다.

### <a name="remarks"></a>설명

인터페이스를 사용하지 않으면 개체의 전체 인스턴스 크기가 낮아집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

## <a name="com_interface_entry_tear_off"></a><a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF

찢어짐 인터페이스를 노출합니다.

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 찢어짐 인터페이스의 GUID입니다.

*x*<br/>
【인】 인터페이스를 구현하는 클래스의 이름입니다.

### <a name="remarks"></a>설명

분리 인터페이스는 해당 인터페이스가 쿼리될 때마다 인스턴스화되는 별도의 개체로 구현됩니다. 일반적으로 인터페이스가 거의 사용되지 않는 경우 인터페이스를 찢어짐으로 빌드하면 주 개체의 모든 인스턴스에 vtable 포인터가 저장됩니다. 참조 수가 0이 되면 찢어짐이 삭제됩니다. 분리를 구현하는 클래스는 파생되어야 `CComTearOffObjectBase` 하며 자체 COM 맵이 있어야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="com_interface_entry_chain"></a><a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN

처리가 COM 맵에서 이 항목에 도달하면 기본 클래스의 COM 맵을 처리합니다.

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
【인】 현재 개체의 기본 클래스입니다.

### <a name="remarks"></a>설명

예를 들어 다음 코드에서 다음을 수행합니다.

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

COM 맵의 첫 번째 항목은 COM 맵을 포함하는 개체의 인터페이스여야 합니다. 따라서 com 맵 항목을 COM_INTERFACE_ENTRY_CHAIN 시작할 수 없으므로 다른 개체의 COM 맵이 **개체의**`COtherObject`COM 맵에**COM_INTERFACE_ENTRY_CHAIN()가** 나타나는 지점에서 검색됩니다. 먼저 다른 개체의 COM 맵을 검색하려면 COM 맵에 대한 `IUnknown` 인터페이스 항목을 추가한 다음 다른 개체의 COM 맵을 연결합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

## <a name="com_interface_entry_func"></a><a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC

ATL의 `QueryInterface` 논리에 연결하기위한 일반적인 메커니즘입니다.

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 노출된 인터페이스의 GUID입니다.

*dw*<br/>
【인】 매개 변수는 *func.*

*func*<br/>
【인】 *id를*반환하는 함수 포인터 .

### <a name="remarks"></a>설명

*iid가* 쿼리된 인터페이스의 IID와 일치하면 *func에서* 지정한 함수가 호출됩니다. 함수에 대한 선언은 다음과 같은 여야 합니다.

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

함수가 호출되면 `pv` 클래스 개체를 가리킵니다. *riid* 매개 변수는 쿼리되는 인터페이스를 `ppv` 참조하며 함수가 인터페이스에 포인터를 저장해야 하는 위치에 대한 포인터이며 *dw는* 항목에 지정한 매개 변수입니다. 함수는 NULL로 설정하고 \* `ppv` 인터페이스를 반환하지 않도록 선택한 경우 E_NOINTERFACE 반환하거나 S_FALSE 합니다. E_NOINTERFACE COM 맵 처리가 종료됩니다. S_FALSE 사용하면 인터페이스 포인터가 반환되지 않더라도 COM 맵 처리가 계속됩니다. 함수가 인터페이스 포인터를 반환하는 경우 S_OK 반환해야 합니다.

## <a name="com_interface_entry_func_blind"></a><a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND

[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)동일하며 IID를 쿼리하면 *func에*대한 호출이 발생합니다.

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>매개 변수

*dw*<br/>
【인】 매개 변수는 *func.*

*func*<br/>
【인】 COM 맵의 이 항목이 처리될 때 호출되는 함수입니다.

### <a name="remarks"></a>설명

오류가 발생할 경우 COM 맵에서 처리가 계속됩니다. 함수가 인터페이스 포인터를 반환하는 경우 S_OK 반환해야 합니다.

## <a name="com_interface_entry_nointerface"></a><a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE

E_NOINTERFACE 반환하고 지정된 인터페이스가 쿼리될 때 COM 맵 처리를 종료합니다.

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 인터페이스 식별자를 생성하는 데 사용되는 텍스트입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 특정 경우에 인터페이스가 사용되지 않도록 할 수 있습니다. 예를 들어 이 매크로를 COM_INTERFACE_ENTRY_AGGREGATE_BLIND 바로 전에 COM 맵에 삽입하여 인터페이스에 대한 쿼리가 집계의 내부 알 수 없는 것으로 전달되지 않도록 할 수 있습니다.

인터페이스 IID는 `IID_` *에 x를* 더하여 생성됩니다. 예를 들어 *x가* `IPersistStorage`있는 경우 IID는 입니다. `IID_IPersistStorage`
