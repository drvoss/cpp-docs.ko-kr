---
title: CSimpleMapEqualHelperFalse 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
ms.openlocfilehash: b6bf1d4e3be849004e13e593fb5f4b5cb87f8123
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330738"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse 클래스

이 클래스는 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스의 도우미입니다.

## <a name="syntax"></a>구문

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(정적) 두 키를 같음으로 테스트합니다.|
|[CSimpleMapEqual도움말거짓::IsEqualValue](#isequalvalue)|(정적) false를 반환합니다.|

## <a name="remarks"></a>설명

이 특성 클래스는 `CSimpleMap` 클래스에 대한 보충입니다. `CSimpleMap` 개체에 포함된 두 요소, 특히 두 개의 값 요소 또는 두 개의 키 요소를 비교하는 메서드를 제공합니다.

값 비교는 항상 false를 반환하며 참조된 경우 false 인수로 호출됩니다. `ATLASSERT` 같음 테스트가 충분히 정의되지 않은 경우 이 클래스는 키/값 쌍을 포함하는 맵이 대부분의 메서드에 대해 올바르게 작동하지만 [CSimpleMap::FindVal과](../../atl/reference/csimplemap-class.md#findval)같은 비교에 의존하는 메서드에 대해 잘 정의된 방식으로 실패하도록 허용합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 아시프콜.h

## <a name="csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a>CSimpleMapEqualHelperFalse::IsEqualKey

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

### <a name="remarks"></a>설명

이 메서드는 [CSimpleArrayEqual도움말을 호출합니다.](../../atl/reference/csimplearrayequalhelper-class.md)

## <a name="csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a>CSimpleMapEqual도움말거짓::IsEqualValue

false를 반환합니다.

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>Return Value

false를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 항상 false를 `ATLASSERT` 반환 하 고 참조 하는 경우 false의 인수와 함께 호출 됩니다. 그 `CSimpleMapEqualHelperFalse::IsEqualValue` 목적은 같음 테스트가 적절하게 정의되지 않은 경우 비교를 사용하여 메서드가 잘 정의된 방식으로 실패하도록 하는 것입니다.

## <a name="see-also"></a>참고 항목

[CSimpleMapEqualHelper 클래스](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
