---
title: freelist 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
ms.openlocfilehash: 712c1f1638b954d1580eb527dd9eab7401917517
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317200"
---
# <a name="freelist-class"></a>freelist 클래스

메모리 블록의 목록을 관리합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Sz*|할당할 배열의 요소 수입니다.|
|*최대*|사용 가능 목록에 저장할 최대 요소 수를 나타내는 최대 클래스입니다. 최대 클래스는 [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) 또는 [max_variable_size](../standard-library/max-variable-size-class.md)가 될 수 있습니다.|

## <a name="remarks"></a>설명

이 클래스 템플릿은 *최대에*전달된 최대 클래스에 의해 결정된 목록의 최대 길이로 *크기 Sz의* 메모리 블록 목록을 관리합니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[freelist](#freelist)|`freelist` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[팝](#pop)|사용 가능 목록에서 첫 번째 메모리 블록을 제거합니다.|
|[push](#push)|목록에 메모리 블록을 추가합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="freelistfreelist"></a><a name="freelist"></a>자유 목록::자유 목록

`freelist` 형식의 개체를 생성합니다.

```cpp
freelist();
```

### <a name="remarks"></a>설명

## <a name="freelistpop"></a><a name="pop"></a>프리리스트::p

사용 가능 목록에서 첫 번째 메모리 블록을 제거합니다.

```cpp
void *pop();
```

### <a name="return-value"></a>Return Value

목록에서 제거된 메모리 블록의 포인터를 반환합니다.

### <a name="remarks"></a>설명

목록이 비어 있으면 멤버 함수가 NULL을 반환합니다. 그렇지 않으면 목록에서 첫 번째 메모리 블록을 제거합니다.

## <a name="freelistpush"></a><a name="push"></a>프리리스트::p우시

목록에 메모리 블록을 추가합니다.

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Ptr*|사용 가능 목록에 추가할 메모리 블록의 포인터입니다.|

### <a name="return-value"></a>Return Value

**max** 클래스의 함수가 `full` **false를**반환하는 경우 true; 그렇지 않으면 `push` 함수가 **false**를 반환합니다.

### <a name="remarks"></a>설명

max `full` 클래스의 함수가 **false를**반환하는 경우 이 멤버 함수는 *ptr이* 가리키는 메모리 블록을 목록의 헤드에 추가합니다.

## <a name="see-also"></a>참고 항목

[\<할당자>](../standard-library/allocators-header.md)
