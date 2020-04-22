---
title: CComDynamicUnkArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
ms.openlocfilehash: 51b1d7e81c98bd5dbcf957b1705e7a717bfb9ab0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747984"
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray 클래스

이 클래스는 포인터 `IUnknown` 배열을 저장합니다.

## <a name="syntax"></a>구문

```
class CComDynamicUnkArray
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|생성자입니다. 컬렉션 값을 NULL로 초기화하고 컬렉션 크기를 0으로 초기화합니다.|
|[CComDynamicUnkArray::~CComDynamicUnkArray](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComDynamicUnkArray::Add](#add)|이 메서드를 호출하여 배열에 포인터를 `IUnknown` 추가합니다.|
|[CComDynamicUnkArray::begin](#begin)|컬렉션의 첫 번째 `IUnknown` 포인터에 대한 포인터를 반환합니다.|
|[CComDynamicUnkArray::클리어](#clear)|배열을 비우습니다.|
|[CComDynamicUnk배열::종료](#end)|컬렉션의 마지막 `IUnknown` 포인터를 지나 하나의 포인터에 대한 포인터를 반환합니다.|
|[CComDynamicUnkArray::GetAt](#getat)|지정된 된 인덱스에 요소를 검색 합니다.|
|[CComDynamicUnkArray::GetCookie](#getcookie)|지정된 `IUnknown` 포인터와 연결된 쿠키를 얻으려면 이 메서드를 호출합니다.|
|[CComDynamicUnkArray::GetSize](#getsize)|배열의 길이를 반환합니다.|
|[CComDynamicUnkArray::GetUnknown](#getunknown)|지정된 쿠키와 연결된 `IUnknown` 포인터를 얻으려면 이 메서드를 호출합니다.|
|[CComDynamicUnkArray::제거](#remove)|배열에서 포인터를 `IUnknown` 제거 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

`CComDynamicUnkArray`에는 연결 지점에 각각 `IUnknown` 동적으로 할당된 포인터 배열이 있습니다. `CComDynamicUnkArray`[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스의 매개 변수로 사용할 수 있습니다.

[Begin](#begin) 및 [end](#end)`CComDynamicUnkArray`메서드를 사용하여 모든 연결 지점의 루프를 반복할 수 있습니다 (예: 이벤트가 발생 하는 경우).

연결 점 프록시 생성 자동화에 대한 자세한 내용은 [객체에 연결 점 추가를](../../atl/adding-connection-points-to-an-object.md) 참조하십시오.

> [!NOTE]
> **참고 사항** 클래스는 `CComDynamicUnkArray` 연결 지점이 있는 컨트롤을 만들 때 **클래스 추가** 마법사에서 사용됩니다. 연결 점 의 수를 수동으로 지정하려면 `CComDynamicUnkArray` 참조를 `CComUnkArray<` *n에서 n으로* `>` *변경합니다.*

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomdynamicunkarrayadd"></a><a name="add"></a>CComDynamicUnkArray::추가

이 메서드를 호출하여 배열에 포인터를 `IUnknown` 추가합니다.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
배열에 추가할 `IUnknown` 포인터입니다.

### <a name="return-value"></a>Return Value

새로 추가된 포인터와 연결된 쿠키를 반환합니다.

## <a name="ccomdynamicunkarraybegin"></a><a name="begin"></a>CComDynamicUnkArray::시작

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

## <a name="ccomdynamicunkarrayclear"></a><a name="clear"></a>CComDynamicUnkArray::클리어

배열을 비우습니다.

```cpp
void clear();
```

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="ccomdynamicunkarray"></a>CComDynamicUnkArray::CComDynamicUnkArray

생성자입니다.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>설명

컬렉션 크기를 0으로 설정하고 값을 NULL로 초기화합니다. 소멸자는 필요한 경우 컬렉션을 해제합니다.

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="dtor"></a>CComDynamicUnkArray::~CComDynamicUnkArray

소멸자입니다.

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>설명

클래스 생성자가 할당한 리소스를 해제합니다.

## <a name="ccomdynamicunkarrayend"></a><a name="end"></a>CComDynamicUnk배열::종료

컬렉션의 마지막 `IUnknown` 포인터를 지나 하나의 포인터에 대한 포인터를 반환합니다.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Return Value

인터페이스 포인터에 `IUnknown` 대한 포인터입니다.

## <a name="ccomdynamicunkarraygetat"></a><a name="getat"></a>CComDynamicUnkArray::GetAt

지정된 된 인덱스에 요소를 검색 합니다.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
검색할 요소의 인덱스입니다.

### <a name="return-value"></a>Return Value

[I알 수 없는](/windows/win32/api/unknwn/nn-unknwn-iunknown) 인터페이스에 대 한 포인터입니다.

## <a name="ccomdynamicunkarraygetcookie"></a><a name="getcookie"></a>CComDynamicUnkArray::GetCookie

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

## <a name="ccomdynamicunkarraygetsize"></a><a name="getsize"></a>CComDynamicUnkArray::GetSize

배열의 길이를 반환합니다.

```
int GetSize() const;
```

### <a name="return-value"></a>Return Value

배열의 길이입니다.

## <a name="ccomdynamicunkarraygetunknown"></a><a name="getunknown"></a>CComDynamicUnkArray::Get알 수 없음

지정된 쿠키와 연결된 `IUnknown` 포인터를 얻으려면 이 메서드를 호출합니다.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>매개 변수

*dwCookie*<br/>
연결된 `IUnknown` 포인터가 필요한 쿠키입니다.

### <a name="return-value"></a>Return Value

일치하는 `IUnknown` 쿠키가 없는 경우 포인터 또는 NULL을 반환합니다.

## <a name="ccomdynamicunkarrayremove"></a><a name="remove"></a>CComDynamicUnkArray::제거

배열에서 포인터를 `IUnknown` 제거 하려면이 메서드를 호출 합니다.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>매개 변수

*dwCookie*<br/>
배열에서 제거할 `IUnknown` 포인터를 참조하는 쿠키입니다.

### <a name="return-value"></a>Return Value

포인터가 제거되면 TRUE를 반환합니다. 그렇지 않으면 거짓.

## <a name="see-also"></a>참조

[CComUnkArray 클래스](../../atl/reference/ccomunkarray-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
