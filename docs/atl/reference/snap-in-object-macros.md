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
ms.openlocfilehash: 7e006a17ad480ea79f6aeec224278815c8c3f164
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835196"
---
# <a name="snap-in-object-macros"></a>스냅인 개체 매크로

이러한 매크로는 스냅인 확장에 대 한 지원을 제공 합니다.

|Name|설명|
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|스냅인 개체에 대 한 스냅인 확장 데이터 클래스 맵의 시작을 표시 합니다.|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|스냅인 개체에 대 한 도구 모음 맵의 시작을 표시 합니다.|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|스냅인 개체에 대 한 스냅인 확장 데이터 클래스 맵의 끝을 표시 합니다.|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|도구 모음 맵의 끝에 스냅인 개체를 표시 합니다.|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|스냅인 확장의 데이터 클래스에 대 한 데이터 멤버를 만듭니다.|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|스냅인 확장 데이터 클래스를 스냅인 개체의 스냅인 확장 데이터 클래스 맵에 입력 합니다.|
|[SNAPINMENUID](#snapinmenuid)|스냅인 개체에서 사용 하는 상황에 맞는 메뉴의 ID를 선언 합니다.|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|스냅인 개체의 도구 모음 맵에 도구 모음을 입력 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** 고 대/스냅. h

## <a name="begin_extension_snapin_nodeinfo_map"></a><a name="begin_extension_snapin_nodeinfo_map"></a> BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

스냅인 확장 데이터 클래스 맵의 시작을 표시 합니다.

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>매개 변수

*classname*<br/>
진행 스냅인 확장 데이터 클래스의 이름입니다.

### <a name="remarks"></a>설명

BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP 매크로를 사용 하 여 스냅인 확장 맵을 시작 하 고, [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 매크로를 사용 하 여 각 스냅인 확장 데이터 형식에 대 한 항목을 추가 하 고, [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 매크로를 사용 하 여 맵을 완료 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="begin_snapintoolbarid_map"></a><a name="begin_snapintoolbarid_map"></a> BEGIN_SNAPINTOOLBARID_MAP

스냅인 개체에 대 한 도구 모음 ID 맵의 시작을 선언 합니다.

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>매개 변수

*_class*<br/>
진행 스냅인 개체 클래스를 지정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

## <a name="end_extension_snapin_nodeinfo_map"></a><a name="end_extension_snapin_nodeinfo_map"></a> END_EXTENSION_SNAPIN_NODEINFO_MAP

스냅인 확장 데이터 클래스 맵의 끝을 표시 합니다.

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>설명

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 매크로를 사용 하 여 스냅인 확장 맵을 시작 하 고, [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 매크로를 사용 하 여 각 확장 스냅인 데이터 형식에 대 한 항목을 추가 하 고, END_EXTENSION_SNAPIN_NODEINFO_MAP 매크로를 사용 하 여 맵을 완료 합니다.

### <a name="example"></a>예제

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)의 예제를 참조 하세요.

## <a name="end_snapintoolbarid_map"></a><a name="end_snapintoolbarid_map"></a> END_SNAPINTOOLBARID_MAP

스냅인 개체에 대 한 도구 모음 ID 맵의 끝을 선언 합니다.

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>매개 변수

*_class*<br/>
진행 스냅인 개체 클래스를 지정 합니다.

### <a name="example"></a>예제

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)의 예제를 참조 하세요.

## <a name="extension_snapin_dataclass"></a><a name="extension_snapin_dataclass"></a> EXTENSION_SNAPIN_DATACLASS

**ISnapInItemImpl**파생 클래스에 대 한 데이터 멤버를 스냅인 확장 데이터 클래스에 추가 합니다.

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>매개 변수

*Microsoft.visualstudio.ordesigner.dataclass.member*<br/>
진행 스냅인 확장의 데이터 클래스입니다.

### <a name="remarks"></a>설명

이 클래스는 스냅인 확장 데이터 클래스 맵에도 입력 해야 합니다. [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 매크로를 사용 하 여 스냅인 확장 데이터 클래스 맵을 시작 하 고, [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 매크로를 사용 하 여 각 스냅인 확장 데이터 형식에 대 한 항목을 추가 하 고, [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 매크로를 사용 하 여 맵을 완료 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="extension_snapin_nodeinfo_entry"></a><a name="extension_snapin_nodeinfo_entry"></a> EXTENSION_SNAPIN_NODEINFO_ENTRY

스냅인 확장 데이터 클래스 맵에 스냅인 확장 데이터 클래스를 추가 합니다.

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>매개 변수

*Microsoft.visualstudio.ordesigner.dataclass.member*<br/>
진행 스냅인 확장의 데이터 클래스입니다.

### <a name="remarks"></a>설명

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 매크로를 사용 하 여 스냅인 확장 데이터 클래스 맵을 시작 하 고, EXTENSION_SNAPIN_NODEINFO_ENTRY 매크로를 사용 하 여 각 스냅인 확장 데이터 형식에 대 한 항목을 추가 하 고, [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 매크로를 사용 하 여 맵을 완료 합니다.

### <a name="example"></a>예제

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)의 예제를 참조 하세요.

## <a name="snapinmenuid"></a><a name="snapinmenuid"></a> SNAPINMENUID

이 매크로를 사용 하 여 스냅인 개체의 상황에 맞는 메뉴 리소스를 선언 합니다.

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
진행 스냅인 개체의 상황에 맞는 메뉴를 식별 합니다.

## <a name="snapintoolbarid_entry"></a><a name="snapintoolbarid_entry"></a> SNAPINTOOLBARID_ENTRY

이 매크로를 사용 하 여 도구 모음 ID를 스냅인 개체의 도구 모음 ID 맵에 입력할 수 있습니다.

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
진행 Toolbar 컨트롤을 식별 합니다.

### <a name="remarks"></a>설명

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) 매크로는 도구 모음 ID 맵의 시작을 표시 합니다. [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) 매크로는 끝을 표시 합니다.

### <a name="example"></a>예제

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)의 예제를 참조 하세요.

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
