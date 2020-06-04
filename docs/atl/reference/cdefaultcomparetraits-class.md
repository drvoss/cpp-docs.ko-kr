---
title: CDefaultCompareTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
ms.openlocfilehash: 8262800ef613424c37c53931d97dd4b1b1a71321
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327069"
---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits 클래스

이 클래스는 기본 요소 비교 함수를 제공합니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CDefaultCompareTraits
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C기본비교특성::비교요소](#compareelements)|(정적) 이 함수를 호출하여 두 요소를 같음으로 비교합니다.|
|[C기본비교특성::비교요소정렬](#compareelementsordered)|(정적) 이 함수를 호출하여 더 크고 작은 요소를 결정합니다.|

## <a name="remarks"></a>설명

이 클래스에는 컬렉션 클래스 개체에 저장된 요소를 비교하기 위한 두 가지 정적 함수가 포함되어 있습니다. 이 클래스는 [CDefaultElementTraits 클래스에서](../../atl/reference/cdefaultelementtraits-class.md)사용됩니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cdefaultcomparetraitscompareelements"></a><a name="compareelements"></a>C기본비교특성::비교요소

이 함수를 호출하여 두 요소를 같음으로 비교합니다.

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>매개 변수

*요소 1*<br/>
첫 번째 요소입니다.

*요소2*<br/>
두 번째 요소입니다.

### <a name="return-value"></a>Return Value

요소가 같으면 true를 반환하고 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은**==** 같음 () 연산자입니다. 단순 데이터 형식이 아닌 개체의 경우 이 함수를 재정의해야 할 수 있습니다.

## <a name="cdefaultcomparetraitscompareelementsordered"></a><a name="compareelementsordered"></a>C기본비교특성::비교요소정렬

이 함수를 호출하여 더 크고 작은 요소를 결정합니다.

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>매개 변수

*요소 1*<br/>
첫 번째 요소입니다.

*요소2*<br/>
두 번째 요소입니다.

### <a name="return-value"></a>Return Value

다음 표를 기반으로 정수반환합니다.

|조건|반환 값|
|---------------|------------------|
|*요소1* < *요소2*|<0|
|*요소1* == *요소2*|0|
|*요소1* > *요소2*|>0|

### <a name="remarks"></a>설명

이 함수의 기본 **==** 구현은 **\<** 에서 **>** 및 연산자를 사용합니다. 단순 데이터 형식이 아닌 개체의 경우 이 함수를 재정의해야 할 수 있습니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
