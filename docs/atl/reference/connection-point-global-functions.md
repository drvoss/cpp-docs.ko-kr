---
title: 연결 지점 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 6474297f8b9adf04541f7d232fb88d5e52d4e88c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331527"
---
# <a name="connection-point-global-functions"></a>연결 지점 전역 함수

이러한 함수는 연결 점 및 싱크 맵에 대한 지원을 제공합니다.

> [!IMPORTANT]
> 다음 표에 나열된 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlAdvise](#atladvise)|개체의 연결 지점과 클라이언트의 싱크 간에 연결을 만듭니다.|
|[AtlUnadvise](#atlunadvise)|을 통해 `AtlAdvise`설정된 연결을 종료합니다.|
|[AtlAdviseSinkMap](#atladvisesinkmap)|이벤트 싱크 맵에서 항목을 조언하거나 취소합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atladvise"></a><a name="atladvise"></a>아틀어드

개체의 연결 지점과 클라이언트의 싱크 간에 연결을 만듭니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>매개 변수

*punkCP*<br/>
【인】 클라이언트가 `IUnknown` 연결하려는 개체에 대한 포인터입니다.

*pUnk*<br/>
【인】 클라이언트의 에 대한 `IUnknown`포인터입니다.

*Iid*<br/>
【인】 연결 지점의 GUID입니다. 일반적으로 이는 연결 점에서 관리하는 나가는 인터페이스와 동일합니다.

*Pdw*<br/>
【아웃】 연결을 고유하게 식별하는 쿠키에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

싱크는 연결 점에서 지원되는 나가는 인터페이스를 구현합니다. 클라이언트는 *pdw* 쿠키를 사용하여 [연결을 AtlUnadvise로](#atlunadvise)전달하여 연결을 제거합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

## <a name="atlunadvise"></a><a name="atlunadvise"></a>아틀룬어드

[AtlAdvise](#atladvise). 를 통해 설정된 연결을 종료합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>매개 변수

*punkCP*<br/>
【인】 클라이언트가 연결된 `IUnknown` 개체에 대한 포인터입니다.

*Iid*<br/>
【인】 연결 지점의 GUID입니다. 일반적으로 이는 연결 점에서 관리하는 나가는 인터페이스와 동일합니다.

*dw*<br/>
【인】 연결을 고유하게 식별하는 쿠키입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

## <a name="atladvisesinkmap"></a><a name="atladvisesinkmap"></a>아틀어어드싱크맵

개체의 싱크 이벤트 맵에서 모든 항목을 advise하거나 unadvise하려면 이 함수를 호출합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>매개 변수

*Pt*<br/>
【인】 싱크 맵을 포함하는 개체에 대한 포인터입니다.

*bAdvise*<br/>
【인】 모든 싱크 항목을 권장하는 경우 TRUE; 모든 싱크 항목을 권장하지 않는 경우 FALSE입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)<br/>
[연결 지점 매크로](../../atl/reference/connection-point-macros.md)
