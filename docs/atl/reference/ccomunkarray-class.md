---
title: CComUnkArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
ms.openlocfilehash: c1d2f0296394d3979ef4f152e3f902c89adf5b45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327300"
---
# <a name="ccomunkarray-class"></a>CComUnkArray 클래스

이 클래스는 포인터를 저장하며 `IUnknown` [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스의 매개 변수로 사용되도록 설계되었습니다.

## <a name="syntax"></a>구문

```
template<unsigned int nMaxSize>
class CComUnkArray
```

#### <a name="parameters"></a>매개 변수

*n맥스 사이즈*<br/>
정적 배열에 `IUnknown` 보유할 수 있는 최대 포인터 수입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComUnkArray::CComunkArray](#ccomunkarray)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComUnkArray::추가](#add)|이 메서드를 호출하여 배열에 포인터를 `IUnknown` 추가합니다.|
|[CComUnkArray::시작](#begin)|컬렉션의 첫 번째 `IUnknown` 포인터에 대한 포인터를 반환합니다.|
|[CComUnkArray::끝](#end)|컬렉션의 마지막 `IUnknown` 포인터를 지나 하나의 포인터에 대한 포인터를 반환합니다.|
|[CComUnkArray::겟쿠키](#getcookie)|지정된 `IUnknown` 포인터와 연결된 쿠키를 얻으려면 이 메서드를 호출합니다.|
|[CComUnkArray::Get알 수 없음](#getunknown)|지정된 쿠키와 연결된 `IUnknown` 포인터를 얻으려면 이 메서드를 호출합니다.|
|[CComUnkArray::제거](#remove)|배열에서 포인터를 `IUnknown` 제거 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

`CComUnkArray`연결 지점에 각각 `IUnknown` 인터페이스인 고정된 수의 포인터를 보유합니다. `CComUnkArray`[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스의 매개 변수로 사용할 수 있습니다. `CComUnkArray<1>`는 하나의 연결 `CComUnkArray` 지점에 최적화된 템플릿 전문화입니다.

[Begin](#begin) 및 [end](#end)`CComUnkArray`메서드를 사용하여 모든 연결 지점의 루프를 반복할 수 있습니다 (예: 이벤트가 발생 하는 경우).

연결 점 프록시 생성 자동화에 대한 자세한 내용은 [객체에 연결 점 추가를](../../atl/adding-connection-points-to-an-object.md) 참조하십시오.

> [!NOTE]
> **참고 사항** 클래스 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) 연결 포인트가 있는 컨트롤을 만들 때 **클래스 추가** 마법사에서 사용 됩니다. 연결 점 의 수를 수동으로 지정하려면 `CComDynamicUnkArray` 참조를 `CComUnkArray<` *n에서 n으로* `>` *변경합니다.*

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomunkarrayadd"></a><a name="add"></a>CComUnkArray::추가

이 메서드를 호출하여 배열에 포인터를 `IUnknown` 추가합니다.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
이 메서드를 호출하여 배열에 포인터를 `IUnknown` 추가합니다.

### <a name="return-value"></a>Return Value

배열이 새 포인터를 포함할 만큼 충분히 크지 않은 경우 새로 추가된 포인터와 연결된 쿠키 또는 0을 반환합니다.

## <a name="ccomunkarraybegin"></a><a name="begin"></a>CComUnkArray::시작

`IUnknown` 인터페이스 포인터 컬렉션의 시작 부분에 대한 포인터를 반환합니다.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Return Value

인터페이스 포인터에 `IUnknown` 대한 포인터입니다.

### <a name="remarks"></a>설명

컬렉션에는 로컬로 로컬로 `IUnknown`저장된 인터페이스에 대한 포인터가 포함되어 있습니다. 각 `IUnknown` 인터페이스를 실제 인터페이스 유형으로 캐스팅한 다음 호출합니다. 먼저 인터페이스를 쿼리할 필요가 없습니다.

인터페이스를 `IUnknown` 사용하기 전에 NULL이 아닌지 확인해야 합니다.

## <a name="ccomunkarrayccomunkarray"></a><a name="ccomunkarray"></a>CComUnkArray::CComunkArray

생성자입니다.

```
CComUnkArray();
```

### <a name="remarks"></a>설명

컬렉션을 보유하도록 `nMaxSize` `IUnknown` 설정하고 NULL에 대한 포인터를 초기화합니다.

## <a name="ccomunkarrayend"></a><a name="end"></a>CComUnkArray::끝

컬렉션의 마지막 `IUnknown` 포인터를 지나 하나의 포인터에 대한 포인터를 반환합니다.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Return Value

인터페이스 포인터에 `IUnknown` 대한 포인터입니다.

### <a name="remarks"></a>설명

`CComUnkArray` 메서드는 `begin` `end` 이벤트가 발생될 때와 같은 모든 연결 지점을 반복하는 데 사용할 수 있습니다.

[!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]

## <a name="ccomunkarraygetcookie"></a><a name="getcookie"></a>CComUnkArray::겟쿠키

지정된 `IUnknown` 포인터와 연결된 쿠키를 얻으려면 이 메서드를 호출합니다.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>매개 변수

*ppFind*<br/>
연결된 `IUnknown` 쿠키가 필요한 포인터입니다.

### <a name="return-value"></a>Return Value

`IUnknown` 일치하는 `IUnknown` 포인터가 없는 경우 포인터와 연결된 쿠키 또는 0을 반환합니다.

### <a name="remarks"></a>설명

동일한 `IUnknown` 포인터의 인스턴스가 두 개 이상인 경우 이 함수는 첫 번째 포인터에 대한 쿠키를 반환합니다.

## <a name="ccomunkarraygetunknown"></a><a name="getunknown"></a>CComUnkArray::Get알 수 없음

지정된 쿠키와 연결된 `IUnknown` 포인터를 얻으려면 이 메서드를 호출합니다.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>매개 변수

*dwCookie*<br/>
연결된 `IUnknown` 포인터가 필요한 쿠키입니다.

### <a name="return-value"></a>Return Value

일치하는 `IUnknown` 쿠키가 없는 경우 포인터 또는 NULL을 반환합니다.

## <a name="ccomunkarrayremove"></a><a name="remove"></a>CComUnkArray::제거

배열에서 포인터를 `IUnknown` 제거 하려면이 메서드를 호출 합니다.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>매개 변수

*dwCookie*<br/>
배열에서 제거할 `IUnknown` 포인터를 참조하는 쿠키입니다.

### <a name="return-value"></a>Return Value

포인터가 제거된 경우 TRUE를 반환하고 FALSE를 반환합니다.

## <a name="see-also"></a>참고 항목

[CComDynamicUnkArray 클래스](../../atl/reference/ccomdynamicunkarray-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
