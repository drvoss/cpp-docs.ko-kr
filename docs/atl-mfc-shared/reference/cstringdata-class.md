---
title: CStringData 클래스
ms.date: 11/04/2016
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
ms.openlocfilehash: f14f1d9c269f06099bd224f582de1f55da33ff0f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746844"
---
# <a name="cstringdata-class"></a>CStringData 클래스

이 클래스는 문자열 개체의 데이터를 나타냅니다.

## <a name="syntax"></a>구문

```
struct CStringData
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[AddRef](#addref)|문자열 데이터 개체의 참조 수를 증가합니다.|
|[데이터](#data)|문자열 개체의 문자 데이터를 검색합니다.|
|[IsLocked](#islocked)|연결된 문자열 개체의 버퍼가 잠겨 있는지 확인합니다.|
|[IsShared](#isshared)|연결된 문자열 개체의 버퍼가 현재 공유되는지 확인합니다.|
|[잠금](#lock)|연결된 문자열 개체의 버퍼를 잠그습니다.|
|[릴리스](#release)|지정된 문자열 개체를 해제합니다.|
|[잠금을 해제](#unlock)|연결된 문자열 개체의 버퍼를 잠금 해제합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[nAllocLength](#nalloclength)|s에서 `XCHAR`할당된 데이터의 길이(null 종료 제외)|
|[n데이터길이](#ndatalength)|s에서 `XCHAR`현재 사용 중인 데이터의 길이(null 종료 제외)|
|[n 참조](#nrefs)|개체의 현재 참조 수입니다.|
|[pStringMgr](#pstringmgr)|이 문자열 개체의 문자열 관리자에 대한 포인터입니다.|

## <a name="remarks"></a>설명

이 클래스는 사용자 지정 문자열 관리자를 구현하는 개발자만 사용해야 합니다. 사용자 지정 문자열 관리자에 대한 자세한 내용은 [메모리 관리 및 CStringT를](../../atl-mfc-shared/memory-management-with-cstringt.md) 참조하십시오.

이 클래스는 [CStringT,](../../atl-mfc-shared/reference/cstringt-class.md) [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)또는 [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) 개체와 같은 상위 문자열 개체와 관련된 다양한 유형의 정보와 데이터를 캡슐화합니다. 모든 상위 문자열 개체에는 연결된 `CStringData` 개체에 대한 포인터가 포함되어 있어 여러 문자열 개체가 동일한 문자열 데이터 개체를 가리킬 수 있습니다. 이 관계는`nRefs` `CStringData` 개체의 참조 개수() 로 표시됩니다.

> [!NOTE]
> 경우에 따라 문자열 형식(예:)은 `CFixedString`하나 이상의 상위 문자열 개체와 문자열 데이터 개체를 공유하지 않습니다. 이에 대한 자세한 내용은 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)를 참조하십시오.

이 데이터는 다음과 구성됩니다.

- 문자열의 메모리 [관리자(IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)형식)입니다.

- 문자열의 현재 [길이(nDataLength)입니다.](#ndatalength)

- 문자열의 할당 된 길이 [(nAllocLength)입니다.](#nalloclength) 성능상의 이유로 현재 문자열 길이와 다를 수 있습니다.

- 개체의 현재 참조 수(nRefs)입니다. [nRefs](#nrefs) `CStringData` 이 값은 동일한 `CStringData` 개체를 공유하는 문자열 개체 수를 결정하는 데 사용됩니다.

- 문자열의 실제 문자 버퍼 [(데이터)입니다.](#data)

   > [!NOTE]
   > 문자열 개체의 실제 문자 버퍼는 문자열 관리자에 의해 할당 `CStringData` 되고 개체에 추가 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** 아실프스트스트.h

## <a name="cstringdataaddref"></a><a name="addref"></a>CStringData::추가 참조

문자열 개체의 참조 수를 증가시입니다.

```cpp
void AddRef() throw();
```

### <a name="remarks"></a>설명

문자열 개체의 참조 수를 증가시입니다.

> [!NOTE]
> 음수 카운트는 문자열 버퍼가 잠겨 있음을 나타내므로 음수 참조 수가 있는 문자열에서 이 메서드를 호출하지 마십시오.

## <a name="cstringdatadata"></a><a name="data"></a>CStringData::data

문자열 개체의 character 버퍼에 대한 포인터를 반환합니다.

```cpp
void* data() throw();
```

### <a name="return-value"></a>Return Value

문자열 개체의 문자 버퍼에 대한 포인터입니다.

### <a name="remarks"></a>설명

연결된 문자열 개체의 현재 문자 버퍼를 반환하려면 이 함수를 호출합니다.

> [!NOTE]
> 이 버퍼는 개체가 `CStringData` 아니라 필요할 때 문자열 관리자에 의해 할당됩니다. 할당되면 버퍼가 문자열 데이터 개체에 추가됩니다.

## <a name="cstringdataislocked"></a><a name="islocked"></a>CStringData::잠금

문자 버퍼가 잠겨 있는지 여부를 결정합니다.

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>Return Value

버퍼가 잠겨 있으면 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 함수를 호출하여 문자열 개체의 character 버퍼가 현재 잠겨 있는지 확인합니다.

## <a name="cstringdataisshared"></a><a name="isshared"></a>CStringData::공유

문자 버퍼가 공유되는지 여부를 결정합니다.

```
bool IsShared() const throw();
```

### <a name="return-value"></a>Return Value

버퍼가 공유되면 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 함수를 호출하여 문자열 데이터 개체의 character 버퍼가 현재 여러 문자열 개체 간에 공유되는지 확인합니다.

## <a name="cstringdatalock"></a><a name="lock"></a>CStringData::잠금

연결된 문자열 개체의 문자 버퍼를 잠급전고 있습니다.

```cpp
void Lock() throw();
```

### <a name="remarks"></a>설명

문자열 데이터 개체의 character 버퍼를 잠그려면 이 함수를 호출합니다. 잠금 및 잠금 해제는 개발자가 캐릭터 버퍼에 직접 액세스해야 하는 경우에 사용됩니다. 잠금의 좋은 예는 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) 및 [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) 의 `CSimpleStringT`메서드에서 설명합니다.

> [!NOTE]
> character 버퍼는 상위 문자열 개체 간에 버퍼가 공유되지 않는 경우에만 잠글 수 있습니다.

## <a name="cstringdatanalloclength"></a><a name="nalloclength"></a>CStringData::nAllocLength

할당된 문자 버퍼의 길이입니다.

```
int nAllocLength;
```

### <a name="remarks"></a>설명

할당된 데이터 버퍼의 길이를 `XCHAR`s로 저장합니다(null 종료 제외).

## <a name="cstringdatandatalength"></a><a name="ndatalength"></a>CStringData::n데이터길이

문자열 개체의 현재 길이입니다.

```
int nDataLength;
```

### <a name="remarks"></a>설명

현재 사용 중인 데이터의 `XCHAR`길이를 s에 저장합니다(null 종료 제외).

## <a name="cstringdatanrefs"></a><a name="nrefs"></a>CStringData::nRefs

문자열 데이터 개체의 참조 수입니다.

```
long nRefs;
```

### <a name="remarks"></a>설명

문자열 데이터 개체의 참조 수를 저장합니다. 이 개수는 문자열 데이터 개체와 연결된 더 높은 문자열 개체수를 나타냅니다. 음수 값은 문자열 데이터 개체가 현재 잠겨 있음을 나타냅니다.

## <a name="cstringdatapstringmgr"></a><a name="pstringmgr"></a>CStringData::p스트링Mgr

연결된 문자열 개체의 메모리 관리자입니다.

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>설명

연결된 문자열 개체에 대한 메모리 관리자를 저장합니다. 메모리 관리자 및 문자열에 대한 자세한 내용은 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)를 참조하십시오.

## <a name="cstringdatarelease"></a><a name="release"></a>CStringData::릴리스

문자열 데이터 개체의 참조 수를 줄입니다.

```cpp
void Release() throw();
```

### <a name="remarks"></a>설명

참조 수가 0에 도달하면 `CStringData` 구조를 해제하여 참조 수를 감소시려면 이 함수를 호출합니다. 이 작업은 일반적으로 문자열 개체가 삭제될 때 수행되므로 더 이상 문자열 데이터 개체를 참조할 필요가 없습니다.

예를 들어 다음 코드는 `CStringData::Release` 다음과 관련된 문자열 `str1`데이터 개체를 호출합니다.

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

## <a name="cstringdataunlock"></a><a name="unlock"></a>CStringData::잠금 해제

연결된 문자열 개체의 문자 버퍼를 잠금 해제합니다.

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>설명

문자열 데이터 개체의 문자 버퍼를 잠금 해제하려면 이 함수를 호출합니다. 버퍼가 잠금 해제되면 공유 가능하며 참조 카운트될 수 있습니다.

> [!NOTE]
> 에 `Lock` 대한 각 호출은 에 해당하는 `Unlock`호출과 일치해야 합니다.

잠금 및 잠금 해제는 개발자가 문자열 데이터를 공유하지 않도록 해야 하는 경우에 사용됩니다. 잠금의 좋은 예는 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) 및 [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) 의 `CSimpleStringT`메서드에서 설명합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
