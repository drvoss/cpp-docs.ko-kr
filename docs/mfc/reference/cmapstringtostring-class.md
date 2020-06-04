---
title: CMapString토스트링 클래스
ms.date: 11/04/2016
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
- AFXCOLL/CMapStringToString::CMapStringToString
- AFXCOLL/CMapStringToString::GetCount
- AFXCOLL/CMapStringToString::GetHashTableSize
- AFXCOLL/CMapStringToString::GetNextAssoc
- AFXCOLL/CMapStringToString::GetSize
- AFXCOLL/CMapStringToString::GetStartPosition
- AFXCOLL/CMapStringToString::HashKey
- AFXCOLL/CMapStringToString::InitHashTable
- AFXCOLL/CMapStringToString::IsEmpty
- AFXCOLL/CMapStringToString::Lookup
- AFXCOLL/CMapStringToString::LookupKey
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToString::RemoveAll
- AFXCOLL/CMapStringToString::RemoveKey
- AFXCOLL/CMapStringToString::SetAt
helpviewer_keywords:
- CMapStringToString [MFC], CPair
- CMapStringToString [MFC], CMapStringToString
- CMapStringToString [MFC], GetCount
- CMapStringToString [MFC], GetHashTableSize
- CMapStringToString [MFC], GetNextAssoc
- CMapStringToString [MFC], GetSize
- CMapStringToString [MFC], GetStartPosition
- CMapStringToString [MFC], HashKey
- CMapStringToString [MFC], InitHashTable
- CMapStringToString [MFC], IsEmpty
- CMapStringToString [MFC], Lookup
- CMapStringToString [MFC], LookupKey
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToString [MFC], RemoveAll
- CMapStringToString [MFC], RemoveKey
- CMapStringToString [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
ms.openlocfilehash: 544154569c50369b805ba296aa975849f245d4ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370126"
---
# <a name="cmapstringtostring-class"></a>CMapString토스트링 클래스

`CString` 개체로 키가 지정된 `CString` 개체의 맵을 지원합니다.

## <a name="syntax"></a>구문

```
class CMapStringToString : public CObject
```

## <a name="members"></a>멤버

의 `CMapStringToString` 멤버 함수는 [클래스 CMapStringToOb의](../../mfc/reference/cmapstringtoob-class.md)멤버 함수와 유사합니다. 이처럼 두 함수가 비슷하므로 `CMapStringToOb` 참조 설명서에서 멤버 함수 관련 사항을 확인할 수 있습니다. 포인터를 `CObject` 반환 값 또는 "출력" 함수 매개 변수로 볼 때마다 **char에**대한 포인터를 대체합니다. 포인터를 `CObject` "입력" 함수 매개 변수로 볼 때마다 **포인터를 char로**대체합니다.

`BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`

예를 들어 위의 코드는

`BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`

### <a name="public-structures"></a>공공 구조물

|속성|Description|
|----------|-----------------|
|[CMapString토스트링::C페어](#cpair)|키 값과 연결된 문자열 개체의 값을 포함하는 중첩된 구조입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMapStringToString::CMapString토스트링](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMapString토스트링::겟카운트](../../mfc/reference/cmapstringtoob-class.md#getcount)|이 맵의 요소 수를 반환합니다.|
|[CMapString토스트링::겟해시테이블크기](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|해시 테이블의 현재 요소 수를 결정합니다.|
|[CMapStringToString::GetnextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|반복에 대한 다음 요소를 가져옵니다.|
|[CMapString토스트링::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|이 맵의 요소 수를 반환합니다.|
|[CMapStringToString::처음부터 시작 위치](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|첫 번째 요소의 위치를 반환합니다.|
|[CMapStringToString::해시키](../../mfc/reference/cmapstringtoob-class.md#hashkey)|지정된 키의 해시 값을 계산합니다.|
|[CMapStringToString::이니티해시테이블](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|해시 테이블을 초기화합니다.|
|[CMapStringToString::비어 있음](../../mfc/reference/cmapstringtoob-class.md#isempty)|빈 맵 조건(요소 없음)에 대한 테스트입니다.|
|[CMapString토스트링::조회](../../mfc/reference/cmapstringtoob-class.md#lookup)|void 포인터 키를 기반으로 void 포인터를 찾습니다. 가리키는 엔터티가 아닌 포인터 값은 키 비교에 사용됩니다.|
|[CMapStringToString::조회키](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|지정된 키 값과 연결된 키에 대한 참조를 반환합니다.|
|[CMapString토스트링::PGetFirstAssoc](#pgetfirstassoc)|맵의 첫 번째 `CString` 포인터를 가져옵니다.|
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|반복을 위해 다음에 `CString` 대한 포인터를 가져옵니다.|
|[CMapString토스트링::P룩업](#plookup)|지정된 값과 `CString` 일치하는 값을 포인터에 반환합니다.|
|[CMapStringToString::모두 제거](../../mfc/reference/cmapstringtoob-class.md#removeall)|이 맵에서 모든 요소를 제거합니다.|
|[CMapStringToString::제거키](../../mfc/reference/cmapstringtoob-class.md#removekey)|키에 의해 지정된 요소를 제거합니다.|
|[CMapStringToString::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|요소를 맵에 삽입합니다. 일치하는 키가 발견되면 기존 요소를 대체합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CMapStringToString::연산자 \[\]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|맵에 요소를 삽입합니다. `SetAt`|

## <a name="remarks"></a>설명

`CMapStringToString`는 serialization 및 요소 덤프를 지원하기 위해 `IMPLEMENT_SERIAL` 매크로를 통합합니다. 맵이 오버로드된 삽입() **<<** 연산자 또는 `Serialize` 멤버 함수를 사용하여 아카이브에 저장되는 경우 각 요소가 차례로 직렬화됩니다.

`CString` -  개별 `CString` 요소의 덤프가 필요한 경우 덤프 컨텍스트의 깊이를 1 이상으로 설정해야 합니다.

개체가 `CMapStringToString` 삭제되거나 해당 요소가 제거되면 개체가 `CString` 적절하게 제거됩니다.

에 대한 `CMapStringToString`자세한 내용은 [컬렉션](../../mfc/collections.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToString`

## <a name="requirements"></a>요구 사항

**헤더:** afxcoll.h

## <a name="cmapstringtostringcpair"></a><a name="cpair"></a>CMapString토스트링::C페어

키 값과 연결된 문자열 개체의 값을 포함합니다.

### <a name="remarks"></a>설명

이 클래스 [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)내에 중첩 된 구조입니다.

구조는 두 개의 필드로 구성됩니다.

- `key`키 유형의 실제 값입니다.

- `value`연결된 개체의 값입니다.

[CMapStringToString::PLookup,](#plookup) [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)및 [CMapStringToString::PGetNextAssoc에서](#pgetnextassoc)반환 값을 저장 하는 데 사용 됩니다.

### <a name="example"></a>예제

  사용의 예는 [CMapStringToString::PLookup](#plookup)에 대한 예제를 참조하십시오.

## <a name="cmapstringtostringpgetfirstassoc"></a><a name="pgetfirstassoc"></a>CMapString토스트링::PGetFirstAssoc

맵 오브젝트의 첫 번째 항목을 반환합니다.

```
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Return Value

맵의 첫 번째 항목에 대한 포인터입니다. [CMapStringToString::CPair](#cpair)를 참조하십시오. 맵이 비어 있으면 값은 NULL입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 맵 오브젝트의 첫 번째 요소를 포인터로 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]

## <a name="cmapstringtostringpgetnextassoc"></a><a name="pgetnextassoc"></a>CMapStringToString::PGetNextAssoc

*pAssocRec로*가리키는 맵 요소를 검색합니다.

```
const CPair *PGetNextAssoc(const CPair* pAssoc) const;

CPair *PGetNextAssoc(const CPair* pAssoc);
```

### <a name="parameters"></a>매개 변수

*파소크 (주)*<br/>
이전 [PGetNextAssoc 또는 PGetFirstAssoc](#pgetnextassoc) 호출에 의해 반환 된 지도 항목을 가리킵니다. [PGetFirstAssoc](#pgetfirstassoc)

### <a name="return-value"></a>Return Value

맵의 다음 항목에 대한 포인터입니다. [CMapStringToString::CPair](#cpair)를 참조하십시오. 요소가 맵의 마지막 요소인 경우 값은 NULL입니다.

### <a name="remarks"></a>설명

맵의 모든 요소를 반복하려면 이 메서드를 호출합니다. 호출을 `PGetFirstAssoc` 사용하여 첫 번째 요소를 검색한 다음 에 대한 `PGetNextAssoc`연속 호출을 사용하여 맵을 반복합니다.

### <a name="example"></a>예제

  [CMapStringToString::PGetFirstAssoc에](#pgetfirstassoc)대한 예제를 참조하십시오.

## <a name="cmapstringtostringplookup"></a><a name="plookup"></a>CMapString토스트링::P룩업

지정된 키에 매핑된 값을 찾습니다.

```
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```

### <a name="parameters"></a>매개 변수

*키*<br/>
검색할 요소에 대한 키에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

지정된 키에 대한 포인터입니다.

### <a name="remarks"></a>설명

지정된 키와 정확히 일치하는 키가 있는 맵 요소를 검색하려면 이 메서드를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]

## <a name="see-also"></a>참고 항목

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
