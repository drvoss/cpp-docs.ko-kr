---
title: CSimpleMapEqualHelper 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
ms.openlocfilehash: d137a35a517ea93139f036f6e9a7a8de06d518a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330751"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper 클래스

이 클래스는 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스의 도우미입니다.

## <a name="syntax"></a>구문

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>매개 변수

*TKey*<br/>
핵심 요소입니다.

*TVal (주)*<br/>
값 요소입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSimpleMapEqual도우미::이퀄라이크키](#isequalkey)|(정적) 두 키를 같음으로 테스트합니다.|
|[CSimpleMapEqual도우미::IsEqualValue](#isequalvalue)|(정적) 같음에 대해 두 값을 테스트합니다.|

## <a name="remarks"></a>설명

이 특성 클래스는 `CSimpleMap` 클래스에 대한 보충입니다. 같음(특히 키 `CSimpleMap` 및 값 구성 요소)을 비교하는 메서드를 제공합니다. 기본적으로 키와 값은 **operator==()를**사용하여 비교되지만 맵에 자체 같음 연산자가 없는 복잡한 데이터 형식이 포함되어 있는 경우 이 클래스를 재정의하여 필요한 추가 기능을 제공할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** 아시프콜.h

## <a name="csimplemapequalhelperisequalkey"></a><a name="isequalkey"></a>CSimpleMapEqual도우미::이퀄라이크키

두 키를 같음으로 테스트합니다.

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>매개 변수

*k1*<br/>
첫 번째 키입니다.

*k2*<br/>
두 번째 키입니다.

### <a name="return-value"></a>Return Value

키가 같으면 true를 반환하고 그렇지 않으면 false를 반환합니다.

## <a name="csimplemapequalhelperisequalvalue"></a><a name="isequalvalue"></a>CSimpleMapEqual도우미::IsEqualValue

같음에 대해 두 값을 테스트합니다.

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>매개 변수

*v1*<br/>
첫 번째 값입니다.

*v2*<br/>
두 번째 값입니다.

### <a name="return-value"></a>Return Value

값이 같으면 true를 반환하고 false를 반환합니다.

## <a name="see-also"></a>참고 항목

[CSimpleMapEqualHelperFalse 클래스](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
