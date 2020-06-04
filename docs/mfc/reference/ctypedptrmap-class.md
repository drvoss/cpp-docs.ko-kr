---
title: CTypedPtrMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
ms.openlocfilehash: 410f0101fd0f8cda271fe0f2353b06b9e8d773b8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754368"
---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap 클래스

`CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`및 `CMapStringToPtr`포인터-맵 클래스 개체에 대해 형식 안전 "래퍼"를 제공합니다.

## <a name="syntax"></a>구문

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
형식이 있는 포인터 맵 클래스의 기본 클래스입니다. 포인터 맵 클래스 `CMapPtrToPtr`(, `CMapPtrToWord` `CMapWordToPtr`또는)여야 `CMapStringToPtr`합니다.

*키*<br/>
맵의 키로 사용되는 개체의 클래스입니다.

*값*<br/>
맵에 저장된 개체의 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|반복에 대한 다음 요소를 가져옵니다.|
|[CTypedPtrMap::조회](#lookup)|을 `KEY` 기반으로 를 `VALUE`반환합니다.|
|[CTypedPtrMap::제거키](#removekey)|키에 의해 지정된 요소를 제거합니다.|
|[CTypedPtrMap::SetAt](#setat)|요소를 맵에 삽입합니다. 일치하는 키가 발견되면 기존 요소를 대체합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CTypedPtrMap::연산자 \[\]](#operator_at)|맵에 요소를 삽입합니다.|

## <a name="remarks"></a>설명

사용 시 `CTypedPtrMap`C++ 형식 검사 기능을 사용하면 일치하지 않는 포인터 유형으로 인한 오류를 제거할 수 있습니다.

모든 `CTypedPtrMap` 함수가 인라인이기 때문에 이 템플릿을 사용하면 코드의 크기 나 속도에 큰 영향을 미치지 않습니다.

사용에 `CTypedPtrMap`대한 자세한 내용은 [문서 컬렉션](../../mfc/collections.md) 및 템플릿 기반 [클래스를](../../mfc/template-based-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

## <a name="ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a>CTypedPtrMap::GetNextAssoc

에서 `rNextPosition`맵 요소를 검색한 `rNextPosition` 다음 업데이트하여 맵의 다음 요소를 참조합니다.

```cpp
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
이전 `GetNextAssoc` 또는 `BASE_CLASS` **::GetStartPosition** 호출에서 반환된 위치 값에 대한 참조를 지정합니다.

*키*<br/>
맵 키의 유형을 지정하는 템플릿 매개 변수입니다.

*rKey*<br/>
검색된 요소의 반환된 키를 지정합니다.

*값*<br/>
맵 값의 유형을 지정하는 템플릿 매개 변수입니다.

*Rvalue*<br/>
검색된 요소의 반환된 값을 지정합니다.

### <a name="remarks"></a>설명

이 함수는 맵의 모든 요소를 반복하는 데 가장 유용합니다. 위치 시퀀스가 반드시 키 값 시퀀스와 같지는 않습니다.

검색된 요소가 맵의 마지막 요소인 경우 새 `rNextPosition` 값은 NULL로 설정됩니다.

이 인라인 `BASE_CLASS`함수는 **::GetNextAssoc**.

## <a name="ctypedptrmaplookup"></a><a name="lookup"></a>CTypedPtrMap::조회

`Lookup`해싱 알고리즘을 사용하여 정확히 일치하는 키가 있는 맵 요소를 빠르게 찾습니다.

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
이 맵 클래스의 기본 클래스를 지정하는 템플릿 매개 변수입니다.

*key*<br/>
살펴볼 요소의 키입니다.

*값*<br/>
이 맵에 저장된 값의 유형을 지정하는 템플릿 매개 변수입니다.

*Rvalue*<br/>
검색된 요소의 반환된 값을 지정합니다.

### <a name="return-value"></a>Return Value

요소가 발견된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 인라인 `BASE_CLASS`함수는 **::Lookup을**호출합니다.

## <a name="ctypedptrmapoperator--"></a><a name="operator_at"></a>CTypedPtrMap::연산자 [

이 연산자는 할당 문(l-값)의 왼쪽에서만 사용할 수 있습니다.

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>매개 변수

*값*<br/>
이 맵에 저장된 값의 유형을 지정하는 템플릿 매개 변수입니다.

*BASE_CLASS*<br/>
이 맵 클래스의 기본 클래스를 지정하는 템플릿 매개 변수입니다.

*key*<br/>
맵에서 조회하거나 생성할 요소의 키입니다.

### <a name="remarks"></a>설명

지정된 키가 있는 맵 요소가 없는 경우 새 요소가 만들어집니다. 맵에서 키가 찾을 수 없기 때문에 이 연산자와 동등한 "오른쪽"(r-value)이 없습니다. 요소 `Lookup` 검색을 위해 멤버 함수를 사용합니다.

## <a name="ctypedptrmapremovekey"></a><a name="removekey"></a>CTypedPtrMap::제거키

이 멤버 `BASE_CLASS`함수는 **::RemoveKey**를 호출합니다.

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>매개 변수

*키*<br/>
맵 키의 유형을 지정하는 템플릿 매개 변수입니다.

*key*<br/>
제거할 요소에 대한 키입니다.

### <a name="return-value"></a>Return Value

항목이 발견되어 성공적으로 제거된 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

더 자세한 설명은 [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)를 참조하십시오.

## <a name="ctypedptrmapsetat"></a><a name="setat"></a>CTypedPtrMap::SetAt

이 멤버 `BASE_CLASS`함수는 **::SetAt 를 호출합니다.**

```cpp
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>매개 변수

*키*<br/>
맵 키의 유형을 지정하는 템플릿 매개 변수입니다.

*key*<br/>
newValue의 키 값을 지정합니다.

*newValue*<br/>
새 요소의 값인 개체 포인터를 지정합니다.

### <a name="remarks"></a>설명

더 자세한 설명은 [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)를 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C맵프트르토프트어 클래스](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord 클래스](../../mfc/reference/cmapptrtoword-class.md)<br/>
[C맵워드토프트르 클래스](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[C맵스트링토프트 클래스](../../mfc/reference/cmapstringtoptr-class.md)
