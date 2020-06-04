---
title: 속성 맵 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
ms.openlocfilehash: 56fdb02939a99e396b9000705753e2475b80f6dc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326098"
---
# <a name="property-map-macros"></a>속성 맵 매크로

이러한 매크로는 속성 맵 및 항목을 정의합니다.

|||
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|ATL 속성 맵의 시작 부분을 표시합니다.|
|[PROP_DATA_ENTRY](#prop_data_entry)|ActiveX 컨트롤의 범위 또는 차원을 나타냅니다.|
|[PROP_ENTRY_TYPE](#prop_entry_type)|속성 설명, 속성 DISPID 및 속성 페이지 CLSID를 속성 맵에 입력합니다.|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|속성 설명, 속성 DISPID, 속성 페이지 CLSID 및 `IDispatch` IID를 속성 맵에 입력합니다.|
|[PROP_PAGE](#prop_page)|속성 페이지 CLSID를 속성 맵에 입력합니다.|
|[END_PROP_MAP](#end_prop_map)|ATL 속성 맵의 끝을 표시합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="begin_prop_map"></a><a name="begin_prop_map"></a>BEGIN_PROP_MAP

오브젝트의 속성 맵의 시작 부분에 표시합니다.

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
【인】 속성 맵을 포함하는 클래스를 지정합니다.

### <a name="remarks"></a>설명

속성 맵에는 속성 설명, 속성 DISPID, 속성 페이지 CLSID 및 `IDispatch` IID가 저장됩니다. 클래스 [IPerPropertyBrowsingImpl,](../../atl/reference/iperpropertybrowsingimpl-class.md) [IPersistPropertyBagImpl,](../../atl/reference/ipersistpropertybagimpl-class.md) [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)및 [ISpecifyPropertyPagesImpl은](../../atl/reference/ispecifypropertypagesimpl-class.md) 속성 맵을 사용하여 이 정보를 검색하고 설정합니다.

ATL 프로젝트 마법사를 사용하여 개체를 만들 때 마법사는 BEGIN_PROP_MAP 다음에 [END_PROP_MAP](#end_prop_map)지정하여 빈 속성 맵을 만듭니다.

속성 맵을 사용하는 개체에 사용자 인터페이스가 없을 수 있으므로 익스텐트(BEGIN_PROP_MAP 속성 맵의 범위(즉, 차원)를 저장하지 않습니다. 개체가 사용자 인터페이스를 사용하여 ActiveX 컨트롤인 경우 익스텐트가 있습니다. 이 경우 속성을 제공 하려면 속성 맵에 [PROP_DATA_ENTRY](#prop_data_entry) 지정 해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

## <a name="prop_data_entry"></a><a name="prop_data_entry"></a>PROP_DATA_ENTRY

ActiveX 컨트롤의 범위 또는 차원을 나타냅니다.

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>매개 변수

*szDesc*<br/>
【인】 속성 설명입니다.

*멤버*<br/>
【인】 범위를 포함하는 데이터 멤버; 예를 들어, `m_sizeExtent`을 참조하십시오.

*vt*<br/>
【인】 속성의 VARIANT 형식을 지정합니다.

### <a name="remarks"></a>설명

이 매크로를 사용하면 지정된 데이터 멤버가 유지됩니다.

ActiveX 컨트롤을 만들 때 마법사는 속성 맵 매크로 [BEGIN_PROP_MAP](#begin_prop_map) 및 속성 맵 매크로 [END_PROP_MAP](#end_prop_map)전에 이 매크로를 삽입합니다.

### <a name="example"></a>예제

다음 예제에서는 개체()`m_sizeExtent`의 범위가 유지되고 있습니다.

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

## <a name="prop_entry_type"></a><a name="prop_entry_type"></a>PROP_ENTRY_TYPE

이 매크로를 사용하여 속성 설명, 속성 DISPID 및 속성 페이지 CLSID를 개체의 속성 맵에 입력합니다.

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>매개 변수

*szDesc*<br/>
【인】 속성 설명입니다.

*디스피드 (것)들*<br/>
【인】 숙소의 디스피드.

*clsid*<br/>
【인】 연결된 속성 페이지의 CLSID입니다. 연결된 속성 페이지가 없는 속성에 대해 CLSID_NULL 특수 값을 사용합니다.

*vt*<br/>
【인】 속성의 형식입니다.

### <a name="remarks"></a>설명

PROP_ENTRY 매크로가 안전하지 않았고 더 이상 사용되지 않았습니다. PROP_ENTRY_TYPE 대체되었습니다.

[BEGIN_PROP_MAP](#begin_prop_map) 매크로는 속성 맵의 시작 부분을 표시합니다. [END_PROP_MAP](#end_prop_map) 매크로는 끝을 표시합니다.

### <a name="example"></a>예제

[BEGIN_PROP_MAP](#begin_prop_map)에 대한 예제를 참조하십시오.

## <a name="prop_entry_type_ex"></a><a name="prop_entry_type_ex"></a>PROP_ENTRY_TYPE_EX

[PROP_ENTRY_TYPE](#prop_entry_type)유사하지만 개체가 여러 이중 인터페이스를 지원하는 경우 특정 IID를 지정할 수 있습니다.

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>매개 변수

*szDesc*<br/>
【인】 속성 설명입니다.

*디스피드 (것)들*<br/>
【인】 숙소의 디스피드.

*clsid*<br/>
【인】 연결된 속성 페이지의 CLSID입니다. 연결된 속성 페이지가 없는 속성에 대해 CLSID_NULL 특수 값을 사용합니다.

*아이드 디스패치*<br/>
【인】 속성을 정의하는 이중 인터페이스의 IID입니다.

*vt*<br/>
【인】 속성의 형식입니다.

### <a name="remarks"></a>설명

PROP_ENTRY_EX 매크로가 안전하지 않았고 더 이상 사용되지 않았습니다. PROP_ENTRY_TYPE_EX 대체되었습니다.

[BEGIN_PROP_MAP](#begin_prop_map) 매크로는 속성 맵의 시작 부분을 표시합니다. [END_PROP_MAP](#end_prop_map) 매크로는 끝을 표시합니다.

### <a name="example"></a>예제

다음 예제에서는 다음에 `IMyDual1` 대한 항목에 `IMyDual2`대한 항목을 그룹합니다. 이중 인터페이스로 그룹화하면 성능이 향상됩니다.

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

## <a name="prop_page"></a><a name="prop_page"></a>PROP_PAGE

이 매크로를 사용하여 속성 페이지 CLSID를 개체의 속성 맵에 입력합니다.

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
【인】 속성 페이지의 CLSID입니다.

### <a name="remarks"></a>설명

PROP_PAGE [PROP_ENTRY_TYPE](#prop_entry_type)비슷하지만 속성 설명이나 DISPID가 필요하지 않습니다.

> [!NOTE]
> PROP_ENTRY_TYPE 또는 [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)CLSID를 이미 입력한 경우 PROP_PAGE 추가 항목을 만들 필요가 없습니다.

[BEGIN_PROP_MAP](#begin_prop_map) 매크로는 속성 맵의 시작 부분을 표시합니다. [END_PROP_MAP](#end_prop_map) 매크로는 끝을 표시합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

## <a name="end_prop_map"></a><a name="end_prop_map"></a>END_PROP_MAP

오브젝트의 속성 맵의 끝을 표시합니다.

```
END_PROP_MAP()
```

### <a name="remarks"></a>설명

ATL 프로젝트 마법사를 사용하여 개체를 만들 때 마법사는 END_PROP_MAP 뒤에 [BEGIN_PROP_MAP](#begin_prop_map) 지정하여 빈 속성 맵을 만듭니다.

### <a name="example"></a>예제

[BEGIN_PROP_MAP](#begin_prop_map)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
