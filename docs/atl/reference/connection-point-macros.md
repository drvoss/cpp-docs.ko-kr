---
title: 연결 지점 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
ms.openlocfilehash: 361cf6ab2c7af142c1d57c002681ccf6e4a87bda
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331491"
---
# <a name="connection-point-macros"></a>연결 지점 매크로

이러한 매크로는 연결 점 맵및 항목을 정의합니다.

|||
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|연결 점 맵 항목의 시작 부분을 표시합니다.|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|지도에 연결 점을 입력합니다.|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (비주얼 스튜디오 2017) CONNECTION_POINT_ENTRY 비슷하지만 iid에 대한 포인터를 취합니다.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|연결 점 맵 항목의 끝을 표시합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="begin_connection_point_map"></a><a name="begin_connection_point_map"></a>BEGIN_CONNECTION_POINT_MAP

연결 점 맵 항목의 시작 부분을 표시합니다.

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 연결 점을 포함하는 클래스의 이름입니다.

### <a name="remarks"></a>설명

BEGIN_CONNECTION_POINT_MAP 매크로로 연결 지점 맵을 시작하고 [CONNECTION_POINT_ENTRY 매크로로](#connection_point_entry) 각 연결 지점에 대한 항목을 추가하고 [END_CONNECTION_POINT_MAP](#end_connection_point_map) 매크로로 맵을 완료합니다.

ATL의 연결 점에 대한 자세한 내용은 [연결 지점](../../atl/atl-connection-points.md)을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

## <a name="connection_point_entry-and-connection_point_entry_p"></a><a name="connection_point_entry"></a>CONNECTION_POINT_ENTRY and CONNECTION_POINT_ENTRY_P

지정된 인터페이스에 대한 연결 점을 연결 지점 맵에 입력하여 액세스할 수 있습니다.

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 연결 지점 맵에 추가되는 인터페이스의 GUID입니다.

*piid*<br/>
【인】 추가되는 인터페이스의 GUID에 대한 포인터입니다.

### <a name="remarks"></a>설명

맵의 연결 점 항목은 [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)에서 사용됩니다. 연결 지점 맵을 포함하는 클래스는 `IConnectionPointContainerImpl`에서 상속해야 합니다.

[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) 매크로로 연결 지점 맵을 시작하고, CONNECTION_POINT_ENTRY 매크로로 각 연결 점에 대한 항목을 추가하고, [END_CONNECTION_POINT_MAP](#end_connection_point_map) 매크로로 맵을 완성합니다.

ATL의 연결 점에 대한 자세한 내용은 [연결 지점](../../atl/atl-connection-points.md)을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

## <a name="end_connection_point_map"></a><a name="end_connection_point_map"></a>END_CONNECTION_POINT_MAP

연결 점 맵 항목의 끝을 표시합니다.

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>설명

[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) 매크로로 연결 지점 맵을 [시작하고, CONNECTION_POINT_ENTRY](#connection_point_entry) 매크로로 각 연결 점에 대한 항목을 추가하고, END_CONNECTION_POINT_MAP 매크로로 맵을 완성합니다.

ATL의 연결 점에 대한 자세한 내용은 [연결 지점](../../atl/atl-connection-points.md)을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)<br/>
[연결 지점 전역 함수](../../atl/reference/connection-point-global-functions.md)
