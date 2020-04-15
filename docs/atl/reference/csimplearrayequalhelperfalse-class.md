---
title: CSimpleArrayEqualHelperFalse 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
ms.openlocfilehash: 5eca3145d64895e34b599fbf83834af142b65973
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330894"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse 클래스

이 클래스는 [CSimpleArray](../../atl/reference/csimplearray-class.md) 클래스의 도우미입니다.

## <a name="syntax"></a>구문

```
template <class T>
class CSimpleArrayEqualHelperFalse
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
파생 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSimpleArrayEqual도우미 거짓::IsEqual](#isequal)|(정적) false를 반환합니다.|

## <a name="remarks"></a>설명

이 특성 클래스는 클래스에 대한 보완입니다. `CSimpleArray` 항상 false를 반환하며 참조된 `ATLASSERT` 경우 false 인수로 호출합니다. 같음 테스트가 충분히 정의되지 않은 경우 이 클래스는 요소가 포함된 배열이 대부분의 메서드에 대해 올바르게 작동하지만 [CSimpleArray::Find와](../../atl/reference/csimplearray-class.md#find)같은 비교에 의존하는 메서드에 대해 잘 정의된 방식으로 실패하도록 허용합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 아시프콜.h

## <a name="csimplearrayequalhelperfalseisequal"></a><a name="isequal"></a>CSimpleArrayEqual도우미 거짓::IsEqual

false를 반환합니다.

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>Return Value

false를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 항상 false를 `ATLASSERT` 반환 하 고 참조 하는 경우 false 의 인수와 함께 호출 됩니다. 그 `CSimpleArrayEqualHelperFalse::IsEqual` 목적은 같음 테스트가 적절하게 정의되지 않은 경우 비교를 사용하여 메서드가 잘 정의된 방식으로 실패하도록 하는 것입니다.

## <a name="see-also"></a>참고 항목

[CSimpleArrayEqualHelper 클래스](../../atl/reference/csimplearrayequalhelper-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
