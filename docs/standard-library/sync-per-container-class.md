---
title: sync_per_container 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: 2c60911b5469cbf74944c9f63af44f2351790280
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376556"
---
# <a name="sync_per_container-class"></a>sync_per_container 클래스

각 할당자 개체에 대해 별도의 캐시 개체를 제공하는 [동기화 필터에](../standard-library/allocators-header.md) 대해 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*캐시*|동기화 필터와 연결된 캐시 형식입니다. [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) 또는 [cache_suballoc](../standard-library/cache-suballoc-class.md)일 수 있습니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[equals](#equals)|두 캐시가 같은지 비교합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="sync_per_containerequals"></a><a name="equals"></a>sync_per_container::같음

두 캐시가 같은지 비교합니다.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*캐시*|동기화 필터의 캐시 개체입니다.|
|*기타*|같은지 비교할 캐시 개체입니다.|

### <a name="return-value"></a>Return Value

멤버 함수는 항상 **false**를 반환합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[\<할당자>](../standard-library/allocators-header.md)
