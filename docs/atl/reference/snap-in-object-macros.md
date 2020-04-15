---
title: 스냅인 개체 매크로
ms.date: 11/04/2016
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
ms.openlocfilehash: 6a57cdb3c9b6a4448bc954ff754ac9b18fa0b393
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325866"
---
# <a name="snap-in-object-macros"></a>스냅인 개체 매크로

이러한 매크로는 스냅인 확장을 지원합니다.

|||
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|스냅인 개체에 대한 스냅인 확장 데이터 클래스 맵의 시작 부분을 표시합니다.|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|스냅인 오브젝트에 대한 도구 모음 맵의 시작 부분에 표시합니다.|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|스냅인 개체에 대한 스냅인 확장 데이터 클래스 맵의 끝을 표시합니다.|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|스냅인 오브젝트에 대한 도구 모음 맵의 끝을 표시합니다.|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|스냅인 확장의 데이터 클래스에 대한 데이터 멤버를 만듭니다.|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|스냅인 확장 데이터 클래스를 스냅인 개체의 스냅인 확장 데이터 클래스 맵에 입력합니다.|
|[스내핀메뉴피드](#snapinmenuid)|스냅-인 개체에서 사용하는 컨텍스트 메뉴의 ID를 선언합니다.|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|스냅인 오브젝트의 도구 모음 맵에 도구 모음을 입력합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlsnap.h

## <a name="begin_extension_snapin_nodeinfo_map"></a><a name="begin_extension_snapin_nodeinfo_map"></a>BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

스냅인 확장 데이터 클래스 맵의 시작 부분에 표시합니다.

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
【인】 스냅 인 확장 데이터 클래스의 이름입니다.

### <a name="remarks"></a>설명

BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP 매크로로 스냅인 확장 맵을 [시작하고, EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 매크로를 사용하여 각 스냅인 확장 데이터 유형에 대한 항목을 추가하고, [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 매크로로 맵을 완성합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="begin_snapintoolbarid_map"></a><a name="begin_snapintoolbarid_map"></a>BEGIN_SNAPINTOOLBARID_MAP

스냅인 오브젝트에 대한 도구 모음 ID 맵의 시작을 선언합니다.

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>매개 변수

*_class*<br/>
【인】 스냅-인 개체 클래스를 지정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

## <a name="end_extension_snapin_nodeinfo_map"></a><a name="end_extension_snapin_nodeinfo_map"></a>END_EXTENSION_SNAPIN_NODEINFO_MAP

스냅인 확장 데이터 클래스 맵의 끝을 표시합니다.

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>설명

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 매크로로 스냅인 확장 맵을 [시작하고, EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 매크로를 사용하여 각 확장 스냅인 데이터 유형에 대한 항목을 추가하고, END_EXTENSION_SNAPIN_NODEINFO_MAP 매크로로 맵을 완성합니다.

### <a name="example"></a>예제

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)에 대한 예제를 참조하십시오.

## <a name="end_snapintoolbarid_map"></a><a name="end_snapintoolbarid_map"></a>END_SNAPINTOOLBARID_MAP

스냅인 오브젝트에 대한 도구 모음 ID 맵의 끝을 선언합니다.

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>매개 변수

*_class*<br/>
【인】 스냅-인 개체 클래스를 지정합니다.

### <a name="example"></a>예제

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)에 대한 예제를 참조하십시오.

## <a name="extension_snapin_dataclass"></a><a name="extension_snapin_dataclass"></a>EXTENSION_SNAPIN_DATACLASS

**ISnapInItemImpl**-파생 클래스에 대 한 스냅 인 확장 데이터 클래스에 데이터 멤버를 추가 합니다.

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>매개 변수

*데이터 클래스*<br/>
【인】 스냅인 확장의 데이터 클래스입니다.

### <a name="remarks"></a>설명

이 클래스는 스냅인 확장 데이터 클래스 맵에도 입력해야 합니다. [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 매크로로 스냅인 확장 데이터 클래스 맵을 [시작하고, EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 매크로를 사용하여 각 스냅인 확장 데이터 유형에 대한 항목을 추가하고, [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 매크로로 맵을 완료합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="extension_snapin_nodeinfo_entry"></a><a name="extension_snapin_nodeinfo_entry"></a>EXTENSION_SNAPIN_NODEINFO_ENTRY

스냅인 확장 데이터 클래스 맵에 스냅인 확장 데이터 클래스를 추가합니다.

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>매개 변수

*데이터 클래스*<br/>
【인】 스냅인 확장의 데이터 클래스입니다.

### <a name="remarks"></a>설명

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 매크로로 스냅인 확장 데이터 클래스 맵을 시작하고, EXTENSION_SNAPIN_NODEINFO_ENTRY 매크로를 사용하여 각 스냅인 확장 데이터 유형에 대한 항목을 [추가하고, END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 매크로로 맵을 완성합니다.

### <a name="example"></a>예제

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)에 대한 예제를 참조하십시오.

## <a name="snapinmenuid"></a><a name="snapinmenuid"></a>스내핀메뉴피드

이 매크로를 사용하여 스냅인 개체의 컨텍스트 메뉴 리소스를 선언합니다.

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 스냅인 개체의 컨텍스트 메뉴를 식별합니다.

## <a name="snapintoolbarid_entry"></a><a name="snapintoolbarid_entry"></a>SNAPINTOOLBARID_ENTRY

이 매크로를 사용하여 도구 모음 ID를 스냅인 개체의 도구 모음 ID 맵에 입력합니다.

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 도구 모음 컨트롤을 식별합니다.

### <a name="remarks"></a>설명

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) 매크로는 도구 모음 ID 맵의 시작 부분을 표시합니다. [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) 매크로는 끝을 표시합니다.

### <a name="example"></a>예제

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
