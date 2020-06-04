---
title: CMapStringToOb 클래스
ms.date: 11/04/2016
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
ms.openlocfilehash: 6520d1c38701647ae51450b9b9800a7cd2701b7a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754586"
---
# <a name="cmapstringtoob-class"></a>CMapStringToOb 클래스

고유한 `CString` 개체를 `CObject` 포인터에 매핑하는 사전 컬렉션 클래스입니다.

## <a name="syntax"></a>구문

```
class CMapStringToOb : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMapStringToOb::GetCount](#getcount)|이 맵의 요소 수를 반환합니다.|
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|해시 테이블의 현재 요소 수를 결정합니다.|
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|반복에 대한 다음 요소를 가져옵니다.|
|[CMapStringToOb::GetSize](#getsize)|이 맵의 요소 수를 반환합니다.|
|[CMapStringToOb::GetStart위치](#getstartposition)|첫 번째 요소의 위치를 반환합니다.|
|[CMapStringToOb::해시키](#hashkey)|지정된 키의 해시 값을 계산합니다.|
|[CMapStringToOb::이니티해시테이블](#inithashtable)|해시 테이블을 초기화합니다.|
|[CMapStringToOb::비어 있음](#isempty)|빈 맵 조건(요소 없음)에 대한 테스트입니다.|
|[CMapStringToOb::조회](#lookup)|void 포인터 키를 기반으로 void 포인터를 찾습니다. 가리키는 엔터티가 아닌 포인터 값은 키 비교에 사용됩니다.|
|[CMapStringToOb::조회키](#lookupkey)|지정된 키 값과 연결된 키에 대한 참조를 반환합니다.|
|[CMapStringToOb::제거모두](#removeall)|이 맵에서 모든 요소를 제거합니다.|
|[CMapStringToOb::제거키](#removekey)|키에 의해 지정된 요소를 제거합니다.|
|[CMapStringToOb::SetAt](#setat)|요소를 맵에 삽입합니다. 일치하는 키가 발견되면 기존 요소를 대체합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CMapStringToOb::연산자 \[\]](#operator_at)|맵에 요소를 삽입합니다. `SetAt`|

## <a name="remarks"></a>설명

맵에 쌍(요소)을 `CString` -  `CObject*` 삽입한 후에는 문자열이나 `CString` 값을 키로 사용하여 쌍을 효율적으로 검색하거나 삭제할 수 있습니다. 맵의 모든 요소를 반복할 수도 있습니다.

위치 형식의 변수는 모든 맵 변형에서 대체 항목 액세스에 사용됩니다. 위치를 사용하여 항목을 "기억"하고 맵을 반복할 수 있습니다. 이 반복은 키 값에 의해 순차적이라고 생각할 수 있습니다. 그것이 아니야. 검색된 요소의 시퀀스는 확정되지 않습니다.

`CMapStringToOb`는 serialization 및 요소 덤프를 지원하기 위해 `IMPLEMENT_SERIAL` 매크로를 통합합니다. 맵이 오버로드된 삽입() **<<** 연산자 또는 `Serialize` 멤버 함수를 사용하여 아카이브에 저장되는 경우 각 요소가 차례로 직렬화됩니다.

맵의 개별 `CString` 요소(값 및 `CObject` 내용)의 진단 덤프가 필요한 경우 덤프 컨텍스트의 깊이를 1 이상으로 설정해야 합니다.

개체가 `CMapStringToOb` 삭제되거나 해당 요소가 제거되면 `CString` 개체와 포인터가 `CObject` 제거됩니다. 포인터에서 `CObject` 참조하는 개체는 소멸되지 않습니다.

맵 클래스 파생은 목록 파생과 유사합니다. 특수 목적 목록 클래스의 파생에 대한 그림은 문서 [컬렉션을](../../mfc/collections.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>요구 사항

**헤더:** afxcoll.h

## <a name="cmapstringtoobcmapstringtoob"></a><a name="cmapstringtoob"></a>CMapStringToOb::CMapStringToOb

빈 `CString`-to-map을 `CObject*` 생성합니다.

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
맵 확장을 위한 메모리 할당 세분성을 지정합니다.

### <a name="remarks"></a>설명

맵이 증가함에 따라 *메모리는 nBlockSize* 항목 단위로 할당됩니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb:: CMapStringToOb`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **= 10);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord (INT_PTR** `nBlockSize` **= 10);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr (INT_PTR** `nBlockSize` **= 10);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString (INT_PTR** `nBlockSize` **= 10);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb (INT_PTR** `nBlockSize` **= 10);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

## <a name="cmapstringtoobgetcount"></a><a name="getcount"></a>CMapStringToOb::GetCount

맵에 있는 요소 수를 결정합니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Return Value

이 맵의 요소 수입니다.

### <a name="remarks"></a>설명

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::GetCount`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR 겟카운트()**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR 겟카운트()**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR 겟카운트()**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR 겟카운트()**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR 겟카운트()**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR 겟카운트()**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

## <a name="cmapstringtoobgethashtablesize"></a><a name="gethashtablesize"></a>CMapStringToOb::GetHashTableSize

해시 테이블의 현재 요소 수를 결정합니다.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Return Value

해시 테이블의 요소 수를 반환합니다.

### <a name="remarks"></a>설명

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::GetHashTableSize`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize () const;**|

## <a name="cmapstringtoobgetnextassoc"></a><a name="getnextassoc"></a>CMapStringToOb::GetNextAssoc

*rNextPosition에서*맵 요소를 검색한 다음 *rNextPosition를* 업데이트하여 맵의 다음 요소를 참조합니다.

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>매개 변수

*rNextPosition*<br/>
이전 `GetNextAssoc` 또는 `GetStartPosition` 호출에서 반환된 POSITION 값에 대한 참조를 지정합니다.

*rKey*<br/>
검색된 요소(문자열)의 반환된 키를 지정합니다.

*Rvalue*<br/>
검색된 `CObject` 요소(포인터)의 반환된 값을 지정합니다. 이 매개 변수에 대한 자세한 내용은 비고를 참조하십시오.

### <a name="remarks"></a>설명

이 함수는 맵의 모든 요소를 반복하는 데 가장 유용합니다. 위치 시퀀스가 반드시 키 값 시퀀스와 같지는 않습니다.

검색된 요소가 맵의 마지막 요소인 경우 *rNextPosition의* 새 값이 NULL로 설정됩니다.

*rValue* 매개 변수의 경우 다음 예제와 같이 컴파일러에 필요한 개체 형식을 **CObject로\*** 캐스팅해야 합니다.

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

템플릿을 기반으로 `GetNextAssoc` 하는 맵의 경우 마찬가지입니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::GetNextAssoc`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**무효 GetNextAssoc (위치&** *rNextPosition,* **void\* ** *rKey,* **void\* ** *rValue)* **const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**[위치&** *=위치&* **==\* ** =&*rKey* **, WORD&** *rValue)* **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**[위치=** *rNextPosition* **&, cString&** *rKey,* **무효\* ** *rValue]* **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**[위치=** *rNextPosition* **&] cString&** *rKey,* **CString&** *rValue)* **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**[위치&** **=워드&** *rKey,* **CObject\* ** *rValue)* **) const;** *rNextPosition*|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**[위치=** *rNextPosition* **&]=&** *rKey,* **무효\* ** *rValue)* **) const;**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

## <a name="cmapstringtoobgetsize"></a><a name="getsize"></a>CMapStringToOb::GetSize

맵 요소 수를 반환합니다.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Return Value

맵의 항목 수입니다.

### <a name="remarks"></a>설명

맵의 요소 수를 검색하려면 이 메서드를 호출합니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::GetSize`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

## <a name="cmapstringtoobgetstartposition"></a><a name="getstartposition"></a>CMapStringToOb::GetStart위치

호출에 전달할 수 있는 POSITION 값을 반환하여 `GetNextAssoc` 맵 반복을 시작합니다.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Return Value

맵을 반복하기 위한 시작 위치를 나타내는 위치 값; 또는 맵이 비어 있으면 NULL이 됩니다.

### <a name="remarks"></a>설명

반복 시퀀스는 예측할 수 없습니다. 따라서 "맵의 첫 번째 요소"는 특별한 의미가 없습니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::GetStartPosition`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**위치 GetStartPosition() const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**위치 GetStartPosition() const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**위치 GetStartPosition() const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**위치 GetStartPosition() const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**위치 GetStartPosition() const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**위치 GetStartPosition() const;**|

### <a name="example"></a>예제

[CMapStringToOb::GetNextAssoc에](#getnextassoc)대한 예제를 참조하십시오.

## <a name="cmapstringtoobhashkey"></a><a name="hashkey"></a>CMapStringToOb::해시키

지정된 키의 해시 값을 계산합니다.

```
UINT HashKey(LPCTSTR key) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
해시 값을 계산할 키입니다.

### <a name="return-value"></a>Return Value

키의 해시 값

### <a name="remarks"></a>설명

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::HashKey`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT 해시키(void)** <strong>\*</strong> `key` **const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT 해시키(void)** <strong>\*</strong> `key` **const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT 해시키(LPCTSTR)** `key` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT 해시키(LPCTSTR)** `key` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT 해시키 (워드)** `key` **const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT 해시키 (워드)** `key` **const;**|

## <a name="cmapstringtoobinithashtable"></a><a name="inithashtable"></a>CMapStringToOb::이니티해시테이블

해시 테이블을 초기화합니다.

```cpp
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>매개 변수

*해시 사이즈*<br/>
해시 테이블의 항목 수입니다.

*bAllocNow*<br/>
TRUE인 경우 초기화 시 해시 테이블을 할당합니다. 그렇지 않으면 필요할 때 테이블이 할당됩니다.

### <a name="remarks"></a>설명

최상의 성능을 위해 해시 테이블 크기는 소수여야 합니다. 충돌을 최소화하려면 크기가 가장 큰 예상 데이터 집합보다 약 20% 커야 합니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::InitHashTable`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**무효 InitHashTable (UINT,** `hashSize` **BOOL** `bAllocNow` **= TRUE);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**무효 InitHashTable (UINT,** `hashSize` **BOOL** `bAllocNow` **= TRUE);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**무효 InitHashTable (UINT,** `hashSize` **BOOL** `bAllocNow` **= TRUE);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**무효 InitHashTable (UINT,** `hashSize` **BOOL** `bAllocNow` **= TRUE);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**무효 InitHashTable (UINT,** `hashSize` **BOOL** `bAllocNow` **= TRUE);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**무효 InitHashTable (UINT,** `hashSize` **BOOL** `bAllocNow` **= TRUE);**|

## <a name="cmapstringtoobisempty"></a><a name="isempty"></a>CMapStringToOb::비어 있음

맵이 비어 있는지 여부를 결정합니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Return Value

이 맵에 요소가 없는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[RemoveAll에](#removeall)대한 예제를 참조하십시오.

### <a name="remarks"></a>설명

다음 표에서는 **CMapStringToOb:: IsEmpty**와 유사한 다른 멤버 함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty() const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty() const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty() const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty() const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty() const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty() const;**|

## <a name="cmapstringtooblookup"></a><a name="lookup"></a>CMapStringToOb::조회

값을 `CObject` 기반으로 포인터를 `CString` 반환합니다.

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
조회할 요소를 식별하는 문자열 키를 지정합니다.

*Rvalue*<br/>
조회된 요소에서 반환된 값을 지정합니다.

### <a name="return-value"></a>Return Value

요소가 발견된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

`Lookup`해싱 알고리즘을 사용하여 정확히 일치하는 키(값)를 `CString` 사용하여 맵 요소를 빠르게 찾을 수 있습니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::LookUp`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL 조회(void,** <strong>\*</strong> `key` **\* void)** `rValue` **const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL 조회(void,** <strong>\*</strong> `key` **WORD&)** `rValue` **const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL 조회(LPCTSTR,** `key` **\* 무효)** `rValue` **const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL 조회 (LPCTSTR,** `key` **cString&)** `rValue` **const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL 조회(WORD** `key` **,\* CObject)** `rValue` **const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL 조회(WORD,** `key` **\* void)** `rValue` **const;**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

## <a name="cmapstringtooblookupkey"></a><a name="lookupkey"></a>CMapStringToOb::조회키

지정된 키 값과 연결된 키에 대한 참조를 반환합니다.

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
조회할 요소를 식별하는 문자열 키를 지정합니다.

*rKey*<br/>
관련 키에 대한 참조입니다.

### <a name="return-value"></a>Return Value

키가 발견되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

연관된 요소를 맵에서 제거한 후 또는 맵이 파괴된 후 키에 대한 참조를 사용하는 것은 안전하지 않습니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb:: LookupKey`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL 조회키 (LPCTSTR,** `key` **LPCTSTR&)** `rKey` **const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL 조회키 (LPCTSTR,** `key` **LPCTSTR&)** `rKey` **const;**|

## <a name="cmapstringtooboperator--"></a><a name="operator_at"></a>CMapStringToOb::연산자 [

멤버 함수를 `SetAt` 편리하게 대체합니다.

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>Return Value

개체에 대한 포인터에 `CObject` 대한 참조입니다. 또는 맵이 비어 있거나 *키가* 범위를 벗어난 경우 NULL입니다.

### <a name="remarks"></a>설명

따라서 할당 문(l-값)의 왼쪽에서만 사용할 수 있습니다. 지정된 키가 있는 맵 요소가 없는 경우 새 요소가 만들어집니다.

맵에서 키가 찾을 수 없기 때문에 이 연산자와 동등한 "오른쪽"(r-value)이 없습니다. 요소 `Lookup` 검색을 위해 멤버 함수를 사용합니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::operator []`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|<strong>void\*&\[ \* 연산자](void;</strong> `key` ** \)**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD&\[연산자](void;** <strong>\*</strong> `key` ** \)**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**무효\*&\[연산자 ](lpctstr;** `key` ** \)**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString&\[연산자 ](lpctstr;** `key` ** \)**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*&\[연산자](단어;** `key` ** \)**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*&\[연산자](단어;** `key` ** \)**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

## <a name="cmapstringtoobremoveall"></a><a name="removeall"></a>CMapStringToOb::제거모두

이 맵에서 모든 요소를 제거하고 키 `CString` 오브젝트를 파괴합니다.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>설명

각 `CObject` 키에서 참조하는 개체는 소멸되지 않습니다. 참조된 `RemoveAll` `CObject` 개체가 소멸되었는지 확인할 수 없는 경우 이 함수는 메모리 누수의 원인이 될 수 있습니다.

맵이 이미 비어 있는 경우 함수가 올바르게 작동합니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::RemoveAll`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**무효 제거모든 ();**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**무효 제거모든 ();**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**무효 제거모든 ();**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**무효 제거모든 ();**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**무효 제거모든 ();**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**무효 제거모든 ();**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

## <a name="cmapstringtoobremovekey"></a><a name="removekey"></a>CMapStringToOb::제거키

제공된 키에 해당하는 맵 항목을 찾습니다. 그런 다음 키가 발견되면 항목을 제거합니다.

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
맵 조회에 사용되는 문자열을 지정합니다.

### <a name="return-value"></a>Return Value

항목이 발견되어 성공적으로 제거된 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이로 인해 개체가 `CObject` 다른 곳에서 삭제되지 않으면 메모리 누수가 발생할 수 있습니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::RemoveKey`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL 제거키 (무효);** <strong>\*</strong> `key` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL 제거키 (무효);** <strong>\*</strong> `key` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL 리모크키 (LPCTSTR);** `key` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL 리모크키 (LPCTSTR);** `key` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL 제거키 (단어);** `key` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL 제거키 (단어);** `key` **);**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

## <a name="cmapstringtoobsetat"></a><a name="setat"></a>CMapStringToOb::SetAt

기본 은 맵에 요소를 삽입하는 것을 의미합니다.

```cpp
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
새 요소의 키인 문자열을 지정합니다.

*newValue*<br/>
새 요소의 `CObject` 값인 포인터를 지정합니다.

### <a name="remarks"></a>설명

첫째, 키가 위를 쳐다 보입니다. 키가 발견되면 해당 값이 변경됩니다. 그렇지 않으면 새 키-값 요소가 만들어집니다.

다음 표에서는 와 유사한 다른 멤버 `CMapStringToOb::SetAt`함수를 보여 주며 있습니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**무효 SetAt (무효,** <strong>\*</strong> `key` <strong>\*</strong> `newValue` **무효);** **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**무효 SetAt (무효** <strong>\*</strong> `key` **, 워드);** `newValue` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**무효 SetAt (LPCTSTR,** `key` <strong>\*</strong> `newValue` **무효);** **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**무효 세타 (LPCTSTR,** `key` **LPCTSTR);** `newValue` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**무효 SetAt (WORD** `key` **, CObject);** <strong>\*</strong> `newValue` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**무효 SetAt (WORD** `key` **, 무효);** <strong>\*</strong> `newValue` **);**|

### <a name="example"></a>예제

모든 컬렉션 예제에 사용된 `CAge` 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]

이 프로그램의 결과는 다음과 같습니다.

```Output
before Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $493C 11
[Bart] = a CAge at $4654 13
after Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $49C0 12
[Bart] = a CAge at $4654 13
```

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C맵프트르토프트어 클래스](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord 클래스](../../mfc/reference/cmapptrtoword-class.md)<br/>
[C맵스트링토프트 클래스](../../mfc/reference/cmapstringtoptr-class.md)<br/>
[CMapString토스트링 클래스](../../mfc/reference/cmapstringtostring-class.md)<br/>
[CMapWordToOb 클래스](../../mfc/reference/cmapwordtoob-class.md)<br/>
[C맵워드토프트르 클래스](../../mfc/reference/cmapwordtoptr-class.md)
