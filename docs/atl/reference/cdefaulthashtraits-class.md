---
title: CDefaultHashTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: 43932092621d44cfc8b07270df92e2765665f23f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327081"
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits 클래스

이 클래스는 해시 값을 계산하기 위한 정적 함수를 제공합니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDefault해시해협::해시](#hash)|(정적) 지정된 요소에 대한 해시 값을 계산하려면 이 함수를 호출합니다.|

## <a name="remarks"></a>설명

이 클래스에는 지정된 요소에 대한 해시 값을 반환하는 단일 정적 함수가 포함되어 있습니다. 이 클래스는 [CDefaultElementTraits 클래스에서](../../atl/reference/cdefaultelementtraits-class.md)사용됩니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cdefaulthashtraitshash"></a><a name="hash"></a>CDefault해시해협::해시

지정된 요소에 대한 해시 값을 계산하려면 이 함수를 호출합니다.

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>매개 변수

*요소*<br/>
요소입니다.

### <a name="return-value"></a>Return Value

해시 값을 반환합니다.

### <a name="remarks"></a>설명

기본 해싱 알고리즘은 매우 간단합니다: 반환 값은 요소 번호입니다. 더 복잡한 알고리즘이 필요한 경우 이 함수를 재정의합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
