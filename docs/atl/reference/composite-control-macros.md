---
title: 복합 제어 매크로
ms.date: 05/06/2019
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
ms.openlocfilehash: 67ad18c07a92cfecca44667908a8488e8c2da234
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331511"
---
# <a name="composite-control-macros"></a>복합 제어 매크로

이러한 매크로는 이벤트 싱크 맵 및 항목을 정의합니다.

|||
|-|-|
|[BEGIN_SINK_MAP](#begin_sink_map)|복합 컨트롤에 대한 이벤트 싱크 맵의 시작 부분을 표시합니다.|
|[END_SINK_MAP](#end_sink_map)|복합 컨트롤에 대한 이벤트 싱크 맵의 끝을 표시합니다.|
|[SINK_ENTRY](#sink_entry)|이벤트 싱크 맵으로 의 입력합니다.|
|[SINK_ENTRY_EX](#sink_entry_ex)|추가 매개 변수가 있는 이벤트 싱크 맵으로 의 입력합니다.|
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (비주얼 스튜디오 2017) iid에 대한 포인터를 취하는 것을 제외하고는 SINK_ENTRY_EX 유사합니다.|
|[SINK_ENTRY_INFO](#sink_entry_info)|[IDispEventSimpleImpl와](../../atl/reference/idispeventsimpleimpl-class.md)함께 사용하기 위해 수동으로 제공된 유형 정보가 있는 이벤트 싱크 맵에 대한 항목입니다.|
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (비주얼 스튜디오 2017) SINK_ENTRY_INFO 이드에 대한 포인터를 취한다는 점을 제외하고는 비슷합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="begin_sink_map"></a><a name="begin_sink_map"></a>BEGIN_SINK_MAP

복합 컨트롤에 대한 이벤트 싱크 맵의 시작을 선언합니다.

```
BEGIN_SINK_MAP(_class)
```

### <a name="parameters"></a>매개 변수

*_class*<br/>
【인】 컨트롤을 지정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>설명

ActiveX 이벤트 싱크의 CE ATL 구현은 HRESULT 형식의 반환 값만 지원하거나 이벤트 처리기 메서드에서 void만 지원합니다. 다른 반환 값은 지원되지 않으며 해당 동작은 정의되지 않습니다.

## <a name="end_sink_map"></a><a name="end_sink_map"></a>END_SINK_MAP

복합 컨트롤에 대한 이벤트 싱크 맵의 끝을 선언합니다.

```
END_SINK_MAP()
```

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>설명

ActiveX 이벤트 싱크의 CE ATL 구현은 HRESULT 형식의 반환 값만 지원하거나 이벤트 처리기 메서드에서 void만 지원합니다. 다른 반환 값은 지원되지 않으며 해당 동작은 정의되지 않습니다.

## <a name="sink_entry"></a><a name="sink_entry"></a>SINK_ENTRY

*id로*식별된 컨트롤의 지정된*이벤트(dispid)에*대해 처리기*함수(fn)를*선언합니다.

```
SINK_ENTRY( id, dispid, fn )
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 컨트롤을 식별합니다.

*디스피드 (것)들*<br/>
【인】 지정된 이벤트를 식별합니다.

*Fn*<br/>
【인】 이벤트 처리기 함수의 이름입니다. 이 함수는 `_stdcall` 호출 규칙을 사용하고 적절한 dispinterface 스타일 시그니처를 가져야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>설명

ActiveX 이벤트 싱크의 CE ATL 구현은 HRESULT 형식의 반환 값만 지원하거나 이벤트 처리기 메서드에서 void만 지원합니다. 다른 반환 값은 지원되지 않으며 해당 동작은 정의되지 않습니다.

## <a name="sink_entry_ex-and-sink_entry_ex_p"></a><a name="sink_entry_ex"></a>SINK_ENTRY_EX 및 SINK_ENTRY_EX_P

*id로*식별된 컨트롤에 대해 디스패치*인터페이스(iid)의*지정된*이벤트(dispid)에*대해 처리기*함수(fn)를*선언합니다.

```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 컨트롤을 식별합니다.

*Iid*<br/>
【인】 디스패치 인터페이스를 식별합니다.

*piid*<br/>
【인】 디스패치 인터페이스에 대한 포인터입니다.

*디스피드 (것)들*<br/>
【인】 지정된 이벤트를 식별합니다.

*Fn*<br/>
【인】 이벤트 처리기 함수의 이름입니다. 이 함수는 `_stdcall` 호출 규칙을 사용하고 적절한 dispinterface 스타일 시그니처를 가져야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]

### <a name="remarks"></a>설명

ActiveX 이벤트 싱크의 CE ATL 구현은 HRESULT 형식의 반환 값만 지원하거나 이벤트 처리기 메서드에서 void만 지원합니다. 다른 반환 값은 지원되지 않으며 해당 동작은 정의되지 않습니다.

## <a name="sink_entry_info-and-sink_entry_info_p"></a><a name="sink_entry_info"></a>SINK_ENTRY_INFO and SINK_ENTRY_INFO_P

이벤트 싱크 맵 내에서 SINK_ENTRY_INFO 매크로를 사용하여 [IDispEventSimpleImpl에서](../../atl/reference/idispeventsimpleimpl-class.md) 필요한 정보를 제공하여 이벤트를 관련 처리기 함수로 라우팅합니다.

```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*id*<br/>
【인】 이벤트 소스를 식별하는 서명되지 않은 정수입니다. 이 값은 관련 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) 기본 클래스에 사용되는 *nID* 템플릿 매개 변수와 일치해야 합니다.

*Iid*<br/>
【인】 디스패치 인터페이스를 식별하는 IID입니다.

*piid*<br/>
【인】 디스패치 인터페이스를 식별하는 IID에 대한 포인터입니다.

*디스피드 (것)들*<br/>
【인】 지정된 이벤트를 식별하는 DISPID입니다.

*Fn*<br/>
【인】 이벤트 처리기 함수의 이름입니다. 이 함수는 `_stdcall` 호출 규칙을 사용하고 적절한 dispinterface 스타일 시그니처를 가져야 합니다.

*info*<br/>
【인】 이벤트 처리기 함수에 대한 정보를 입력합니다. 이 형식 정보는 `_ATL_FUNC_INFO` 구조체에 대한 포인터 형태로 제공됩니다. CC_CDECL `_ATL_FUNC_INFO` 구조의 CALLCONV 필드에 대 한 Windows CE에서 지원 되는 유일한 옵션입니다. 다른 값은 지원되지 않으므로 해당 동작이 정의되지 않습니다.

### <a name="remarks"></a>설명

처음 네 개의 매크로 매개 변수는 [SINK_ENTRY_EX](#sink_entry_ex) 매크로의 매개 변수와 동일합니다. 최종 매개 변수는 이벤트에 대한 형식 정보를 제공합니다. ActiveX 이벤트 싱크의 CE ATL 구현은 HRESULT 형식의 반환 값만 지원하거나 이벤트 처리기 메서드에서 void만 지원합니다. 다른 반환 값은 지원되지 않으며 해당 동작은 정의되지 않습니다.

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)<br/>
[복합 제어 전역 함수](../../atl/reference/composite-control-global-functions.md)
