---
title: CSimpleArrayEqualHelper 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: 386b005777b3e31dd74916a41bc5af2ab82df210
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330881"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper 클래스

이 클래스는 [CSimpleArray](../../atl/reference/csimplearray-class.md) 클래스의 도우미입니다.

## <a name="syntax"></a>구문

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
파생 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSimpleArray평등 도우미::IsEqual](#isequal)|(정적) 같음의 두 `CSimpleArray` 개체 요소를 테스트합니다.|

## <a name="remarks"></a>설명

이 특성 클래스는 `CSimpleArray` 클래스에 대한 보충입니다. 개체에 저장된 두 요소를 비교하는 `CSimpleArray` 메서드를 제공합니다. 기본적으로 요소는 **operator=() 를**사용하여 비교되지만 배열에 자체 같음 연산자가 없는 복잡한 데이터 형식이 포함되어 있는 경우 이 클래스를 재정의해야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 아시프콜.h

## <a name="csimplearrayequalhelperisequal"></a><a name="isequal"></a>CSimpleArray평등 도우미::IsEqual

같음의 두 `CSimpleArray` 개체 요소를 테스트합니다.

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>매개 변수

*T1*<br/>
T 형식의 개체입니다.

*t2*<br/>
T 형식의 개체입니다.

### <a name="return-value"></a>Return Value

요소가 같으면 true를 반환하고 그렇지 않으면 false를 반환합니다.

## <a name="see-also"></a>참고 항목

[CSimpleArray 클래스](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse 클래스](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
