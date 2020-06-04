---
title: CMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
ms.openlocfilehash: fbb34d4db41ef11cd01a6a8a7f20cafa0e737268
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749080"
---
# <a name="cmap-class"></a>CMap 클래스

고유 키를 값에 매핑하는 사전 컬렉션 클래스입니다.

## <a name="syntax"></a>구문

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>매개 변수

*키*<br/>
맵의 키로 사용되는 개체의 클래스입니다.

*ARG_KEY*<br/>
*KEY* 인수에 사용되는 데이터 형식; 일반적으로 *KEY*에 대한 참조입니다.

*값*<br/>
맵에 저장된 개체의 클래스입니다.

*ARG_VALUE*<br/>
*VALUE* 인수에 사용되는 데이터 형식; 일반적으로 *VALUE에*대한 참조입니다.

## <a name="members"></a>멤버

### <a name="public-structures"></a>공공 구조물

|속성|Description|
|----------|-----------------|
|[CMap:::CPair](#cpair)|키 값과 연결된 개체의 값을 포함하는 중첩된 구조체입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMap::CMap](#cmap)|값을 매핑하는 컬렉션을 구성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMap::GetCount](#getcount)|이 맵의 요소 수를 반환합니다.|
|[CMap::GetHashTableSize](#gethashtablesize)|해시 테이블의 요소 수를 반환합니다.|
|[CMap::GetNextAssoc](#getnextassoc)|반복에 대한 다음 요소를 가져옵니다.|
|[CMap::GetSize](#getsize)|이 맵의 요소 수를 반환합니다.|
|[CMap:::시작 위치](#getstartposition)|첫 번째 요소의 위치를 반환합니다.|
|[CMap:::이니티해시테이블](#inithashtable)|해시 테이블을 초기화하고 크기를 지정합니다.|
|[CMap::비어 있음](#isempty)|빈 맵 조건(요소 없음)에 대한 테스트입니다.|
|[CMap::조회](#lookup)|지정된 키에 매핑된 값을 찾습니다.|
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|첫 번째 요소에 대한 포인터를 반환합니다.|
|[CMap::PGetNextAssoc](#pgetnextassoc)|반복을 위해 다음 요소에 대한 포인터를 가져옵니다.|
|[CMap::P룩업](#plookup)|지정된 값과 일치하는 키에 대한 포인터를 반환합니다.|
|[CMap::모두 제거](#removeall)|이 맵에서 모든 요소를 제거합니다.|
|[CMap::제거키](#removekey)|키에 의해 지정된 요소를 제거합니다.|
|[CMap::SetAt](#setat)|요소를 맵에 삽입합니다. 일치하는 키가 발견되면 기존 요소를 대체합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CMap::연산자 \[\]](#operator_at)|맵에 요소를 삽입합니다. `SetAt`|

## <a name="remarks"></a>설명

맵에 키-값 쌍(요소)을 삽입한 후에는 키를 사용하여 쌍을 효율적으로 검색하거나 삭제하여 액세스할 수 있습니다. 맵의 모든 요소를 반복할 수도 있습니다.

POSITION 형식의 변수는 항목에 대한 대체 액세스에 사용됩니다. 위치를 사용하여 항목을 "기억"하고 맵을 반복할 수 있습니다. 이 반복은 키 값에 의해 순차적이라고 생각할 수 있습니다. 그것이 아니야. 검색된 요소의 시퀀스는 확정되지 않습니다.

이 클래스의 특정 멤버 함수는 클래스의 대부분의 용도에 맞게 `CMap` 사용자 지정해야 하는 전역 도우미 함수를 호출합니다. **MFC 참조의**매크로 및 전역 섹션에서 [컬렉션 클래스 도우미를](../../mfc/reference/collection-class-helpers.md) 참조하십시오.

`CMap`재정의 [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) 는 해당 요소의 직렬화 및 덤프를 지원합니다. 을 사용하여 `Serialize`맵이 아카이브에 저장되면 각 맵 요소가 차례로 직렬화됩니다. `SerializeElements` 도우미 함수의 기본 구현은 약간 쓰기를 수행합니다. 포인터 컬렉션 항목또는 다른 사용자 정의 `CObject` 형식에서 파생된 항목의 직렬화에 대한 자세한 내용은 [방법: 형식 안전 컬렉션 만들기](../../mfc/how-to-make-a-type-safe-collection.md)를 참조하십시오.

맵의 개별 요소(키 및 값)의 진단 덤프가 필요한 경우 덤프 컨텍스트의 깊이를 1 이상으로 설정해야 합니다.

개체가 `CMap` 삭제되거나 해당 요소가 제거되면 키와 값이 모두 제거됩니다.

맵 클래스 파생은 목록 파생과 유사합니다. 특수 목적 목록 클래스의 파생에 대한 그림은 문서 [컬렉션을](../../mfc/collections.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

## <a name="cmapcmap"></a><a name="cmap"></a>CMap::CMap

빈 맵을 생성합니다.

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
맵 확장을 위한 메모리 할당 세분성을 지정합니다.

### <a name="remarks"></a>설명

맵이 증가함에 따라 *메모리는 nBlockSize* 항목 단위로 할당됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

## <a name="cmapcpair"></a><a name="cpair"></a>CMap:::CPair

키 값과 연결된 개체의 값을 포함합니다.

### <a name="remarks"></a>설명

클래스 [CMap](../../mfc/reference/cmap-class.md)내에 중첩된 구조입니다.

구조는 두 개의 필드로 구성됩니다.

- `key`키 유형의 실제 값입니다.

- `value`연결된 개체의 값입니다.

[CMap::PLookup,](#plookup) [CMap::PGetFirstAssoc](#pgetfirstassoc)및 [CMap::PGetNextAssoc에서](#pgetnextassoc)반환 값을 저장하는 데 사용됩니다.

### <a name="example"></a>예제

사용 의 예는 [CMap::PLookup](#plookup)에 대한 예제를 참조하십시오.

## <a name="cmapgetcount"></a><a name="getcount"></a>CMap::GetCount

맵의 요소 수를 검색합니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Return Value

요소의 수입니다.

### <a name="example"></a>예제

[CMap::조회에](#lookup)대한 예제를 참조하십시오.

## <a name="cmapgethashtablesize"></a><a name="gethashtablesize"></a>CMap::GetHashTableSize

맵의 해시 테이블의 요소 수를 결정합니다.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Return Value

해시 테이블의 요소 수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

## <a name="cmapgetnextassoc"></a><a name="getnextassoc"></a>CMap::GetNextAssoc

에서 `rNextPosition`맵 요소를 검색한 `rNextPosition` 다음 업데이트하여 맵의 다음 요소를 참조합니다.

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>매개 변수

*rNextPosition*<br/>
이전 `GetNextAssoc` 또는 `GetStartPosition` 호출에서 반환된 POSITION 값에 대한 참조를 지정합니다.

*키*<br/>
맵 키의 유형을 지정하는 템플릿 매개 변수입니다.

*rKey*<br/>
검색된 요소의 반환된 키를 지정합니다.

*값*<br/>
맵 값의 유형을 지정하는 템플릿 매개변수입니다.

*Rvalue*<br/>
검색된 요소의 반환된 값을 지정합니다.

### <a name="remarks"></a>설명

이 함수는 맵의 모든 요소를 반복하는 데 가장 유용합니다. 위치 시퀀스가 반드시 키 값 시퀀스와 같지는 않습니다.

검색된 요소가 맵의 마지막 요소인 경우 *rNextPosition의* 새 값이 NULL로 설정됩니다.

### <a name="example"></a>예제

[CMap:SetAt](#setat)에 대한 예제를 참조하십시오.

## <a name="cmapgetsize"></a><a name="getsize"></a>CMap::GetSize

맵 요소 수를 반환합니다.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Return Value

맵의 항목 수입니다.

### <a name="remarks"></a>설명

맵의 요소 수를 검색하려면 이 메서드를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapgetstartposition"></a><a name="getstartposition"></a>CMap:::시작 위치

호출에 전달할 수 있는 POSITION 값을 반환하여 `GetNextAssoc` 맵 반복을 시작합니다.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Return Value

맵을 반복하기 위한 시작 위치를 나타내는 위치 값; 또는 맵이 비어 있으면 NULL이 됩니다.

### <a name="remarks"></a>설명

반복 시퀀스는 예측할 수 없습니다. 따라서 "맵의 첫 번째 요소"는 특별한 의미가 없습니다.

### <a name="example"></a>예제

[CMap:SetAt](#setat)에 대한 예제를 참조하십시오.

## <a name="cmapinithashtable"></a><a name="inithashtable"></a>CMap:::이니티해시테이블

해시 테이블을 초기화합니다.

```cpp
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>매개 변수

*해시 사이즈*<br/>
해시 테이블의 항목 수입니다.

*bAllocNow*<br/>
TRUE인 경우 초기화 시 해시 테이블을 할당합니다. 그렇지 않으면 필요할 때 테이블이 할당됩니다.

### <a name="remarks"></a>설명

최상의 성능을 위해 해시 테이블 크기는 소수여야 합니다. 충돌을 최소화하려면 크기가 가장 큰 예상 데이터 집합보다 약 20% 커야 합니다.

### <a name="example"></a>예제

[CMap::조회에](#lookup)대한 예제를 참조하십시오.

## <a name="cmapisempty"></a><a name="isempty"></a>CMap::비어 있음

맵이 비어 있는지 여부를 결정합니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Return Value

이 맵에 요소가 없는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[CMap::RemoveAll에](#removeall)대한 예제를 참조하십시오.

## <a name="cmaplookup"></a><a name="lookup"></a>CMap::조회

지정된 키에 매핑된 값을 찾습니다.

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>매개 변수

*ARG_KEY*<br/>
*키* 값의 형식을 지정하는 템플릿 매개 변수입니다.

*key*<br/>
조회할 요소를 식별하는 키를 지정합니다.

*값*<br/>
조회할 값의 형식을 지정합니다.

*Rvalue*<br/>
조회된 값을 받습니다.

### <a name="return-value"></a>Return Value

요소가 발견된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

`Lookup`해시 알고리즘을 사용하여 지정된 키와 정확히 일치하는 키를 사용하여 맵 요소를 빠르게 찾습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapoperator--"></a><a name="operator_at"></a>CMap::연산자 [ ]

멤버 함수를 `SetAt` 편리하게 대체합니다.

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>매개 변수

*값*<br/>
맵 값의 형식을 지정하는 템플릿 매개 변수입니다.

*ARG_KEY*<br/>
키 값의 형식을 지정하는 템플릿 매개 변수입니다.

*key*<br/>
맵에서 값을 검색하는 데 사용되는 키입니다.

### <a name="remarks"></a>설명

따라서 할당 문(l-값)의 왼쪽에서만 사용할 수 있습니다. 지정된 키가 있는 맵 요소가 없는 경우 새 요소가 만들어집니다.

맵에서 키가 찾을 수 없기 때문에 이 연산자와 동등한 "오른쪽"(r-value)이 없습니다. 요소 `Lookup` 검색을 위해 멤버 함수를 사용합니다.

### <a name="example"></a>예제

[CMap::조회에](#lookup)대한 예제를 참조하십시오.

## <a name="cmappgetfirstassoc"></a><a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc

맵 오브젝트의 첫 번째 항목을 반환합니다.

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Return Value

맵의 첫 번째 항목에 대한 포인터입니다. [CMap::CPair](#cpair)를 참조하십시오. 맵에 항목이 없는 경우 값은 NULL입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 맵 오브젝트의 첫 번째 요소를 포인터로 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

## <a name="cmappgetnextassoc"></a><a name="pgetnextassoc"></a>CMap::PGetNextAssoc

*pAssocRec로*가리키는 맵 요소를 검색합니다.

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>매개 변수

*파소크레트*<br/>
이전 [PGetNextAssoc](#pgetnextassoc) 또는 [CMap::PGetFirstAssoc](#pgetfirstassoc) 호출에 의해 반환 된 지도 항목을 가리킵니다.

### <a name="return-value"></a>Return Value

맵의 다음 항목에 대한 포인터입니다. [CMap::CPair](#cpair)를 참조하십시오. 요소가 맵의 마지막 요소인 경우 값은 NULL입니다.

### <a name="remarks"></a>설명

맵의 모든 요소를 반복하려면 이 메서드를 호출합니다. 호출을 `PGetFirstAssoc` 사용하여 첫 번째 요소를 검색한 다음 에 대한 `PGetNextAssoc`연속 호출을 사용하여 맵을 반복합니다.

### <a name="example"></a>예제

[CMap::PGetFirstAssoc에](#pgetfirstassoc)대한 예제를 참조하십시오.

## <a name="cmapplookup"></a><a name="plookup"></a>CMap::P룩업

지정된 키에 매핑된 값을 찾습니다.

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 요소에 대한 키입니다.

### <a name="return-value"></a>Return Value

키 구조에 대한 포인터; [CMap::CPair](#cpair)를 참조하십시오. 일치하는 일치가 없는 `CMap::PLookup` 경우 NULL을 반환합니다.

### <a name="remarks"></a>설명

지정된 키와 정확히 일치하는 키가 있는 맵 요소를 검색하려면 이 메서드를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

## <a name="cmapremoveall"></a><a name="removeall"></a>CMap::모두 제거

전역 도우미 함수를 `DestructElements`호출하여 이 맵에서 모든 값을 제거합니다.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>설명

맵이 이미 비어 있는 경우 함수가 올바르게 작동합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

## <a name="cmapremovekey"></a><a name="removekey"></a>CMap::제거키

제공된 키에 해당하는 맵 항목을 찾습니다. 그런 다음 키가 발견되면 항목을 제거합니다.

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>매개 변수

*ARG_KEY*<br/>
키 의 형식을 지정하는 템플릿 매개 변수입니다.

*key*<br/>
제거할 요소에 대한 키입니다.

### <a name="return-value"></a>Return Value

항목이 발견되어 성공적으로 제거된 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

`DestructElements` 도우미 함수는 항목을 제거하는 데 사용됩니다.

### <a name="example"></a>예제

[CMap:SetAt](#setat)에 대한 예제를 참조하십시오.

## <a name="cmapsetat"></a><a name="setat"></a>CMap::SetAt

기본 은 맵에 요소를 삽입하는 것을 의미합니다.

```cpp
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>매개 변수

*ARG_KEY*<br/>
*키* 매개 변수의 형식을 지정하는 템플릿 매개 변수입니다.

*key*<br/>
새 요소의 키를 지정합니다.

*ARG_VALUE*<br/>
*newValue* 매개 변수의 형식을 지정 하는 템플릿 매개 변수입니다.

*newValue*<br/>
새 요소의 값을 지정합니다.

### <a name="remarks"></a>설명

첫째, 키가 위를 쳐다 보입니다. 키가 발견되면 해당 값이 변경됩니다. 그렇지 않으면 새 키-값 쌍이 만들어집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
