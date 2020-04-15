---
title: COM 맵 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
ms.openlocfilehash: c4ce7c7a68c0744ad65ef4914088fa12d3340628
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326689"
---
# <a name="com-map-global-functions"></a>COM 맵 전역 함수

이러한 함수는 COM Map `IUnknown` 구현을 지원합니다.

|||
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|집계되지 않은 `IUnknown` 개체에 위임합니다.|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|인터페이스와 를 비교하기 위한 `IUnknown`효율적인 코드를 생성합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atlinternalqueryinterface"></a><a name="atlinternalqueryinterface"></a>아틀내부 쿼리인터페이스

요청된 인터페이스에 대한 포인터를 검색합니다.

```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*Pthis*<br/>
【인】 에 노출된 인터페이스의 COM 맵이 포함된 개체에 대한 `QueryInterface`포인터입니다.

*펜스 엔트리*<br/>
【인】 사용 가능한 `_ATL_INTMAP_ENTRY` 인터페이스의 맵에 액세스하는 구조의 배열입니다.

*Iid*<br/>
【인】 요청되는 인터페이스의 GUID입니다.

*ppvObject*<br/>
【아웃】 인터페이스를 찾을 수 없는 경우 *iid*또는 NULL에 지정된 인터페이스 포인터에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`AtlInternalQueryInterface`에서는 COM 맵 테이블의 인터페이스만 처리됩니다. 개체가 집계된 경우 `AtlInternalQueryInterface` 알 수 없는 외부로 위임하지 않습니다. 매크로 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) 또는 변형 중 하나를 사용하여 COM 맵 테이블에 인터페이스를 입력할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

## <a name="inlineisequaliunknown"></a><a name="inlineisequaliunknown"></a>인라인IsEqualI알 수 없음

에 대한 테스트의 특별한 경우를 `IUnknown`위해이 함수를 호출합니다.

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>매개 변수

*rguid1*<br/>
【인】 비교할 `IID_IUnknown`GUID입니다.

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)<br/>
[COM 맵 매크로](../../atl/reference/com-map-macros.md)
