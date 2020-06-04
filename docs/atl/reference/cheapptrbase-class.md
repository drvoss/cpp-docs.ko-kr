---
title: CHeapPtrBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
ms.openlocfilehash: e247b4f488411ffdcde5d1d9016436c9c36fe793
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747685"
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase 클래스

이 클래스는 여러 스마트 힙 포인터 클래스의 기초를 형성합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
힙에 저장할 개체 유형입니다.

*할당자*<br/>
사용할 메모리 할당 클래스입니다. 기본적으로 CRT 루틴은 메모리를 할당하고 사용 해제하는 데 사용됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CHeapPtrBase::~CHeapPtrBase](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CHeapPtrBase::할당바이트](#allocatebytes)|메모리를 할당하려면 이 메서드를 호출합니다.|
|[CHeapPtrBase::연결](#attach)|이 메서드를 호출하여 기존 포인터의 소유권을 가져가 십시오.|
|[CHeapPtrBase::D에타흐](#detach)|포인터의 소유권을 해제하려면 이 메서드를 호출합니다.|
|[CHeapPtrBase::무료](#free)|이 메서드를 호출하여 을 가리키는 `CHeapPtrBase`개체를 삭제합니다.|
|[CHeapPtrBase::재할당바이트](#reallocatebytes)|메모리를 다시 할당하려면 이 메서드를 호출합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CHeapPtrBase::연산자 T*](#operator_t_star)|캐스트 연산자입니다.|
|[CHeapPtrBase::연산자 &](#operator_amp)|& 연산자|
|[CHeapPtrBase::연산자 ->](#operator_ptr)|구성원간 포인터 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CHeapPtrBase::m_pData](#m_pdata)|포인터 데이터 멤버 변수입니다.|

## <a name="remarks"></a>설명

이 클래스는 여러 스마트 힙 포인터 클래스의 기초를 형성합니다. 파생 클래스(예: [CHeapPtr](../../atl/reference/cheapptr-class.md) 및 [CComHeapPtr)는](../../atl/reference/ccomheapptr-class.md)자체 생성자 및 연산자()를 추가합니다. 구현 예제는 이러한 클래스를 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

## <a name="cheapptrbaseallocatebytes"></a><a name="allocatebytes"></a>CHeapPtrBase::할당바이트

메모리를 할당하려면 이 메서드를 호출합니다.

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*n바이트*<br/>
할당할 메모리 바이트 수입니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 메모리가 성공적으로 할당된 경우 true를 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수가 현재 기존 값을 가리키는 경우 어설션 오류가 발생합니다. 즉, NULL과 같지 않습니다.

## <a name="cheapptrbaseattach"></a><a name="attach"></a>CHeapPtrBase::연결

이 메서드를 호출하여 기존 포인터의 소유권을 가져가 십시오.

```cpp
void Attach(T* pData) throw();
```

### <a name="parameters"></a>매개 변수

*Pdata*<br/>
개체는 `CHeapPtrBase` 이 포인터의 소유권을 차지합니다.

### <a name="remarks"></a>설명

개체가 `CHeapPtrBase` 포인터의 소유권을 가져가면 포인터와 할당된 데이터가 범위를 벗어날 때 자동으로 삭제됩니다.

디버그 빌드에서 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수가 현재 기존 값을 가리키는 경우 어설션 오류가 발생합니다. 즉, NULL과 같지 않습니다.

## <a name="cheapptrbasecheapptrbase"></a><a name="dtor"></a>CHeapPtrBase::~CHeapPtrBase

소멸자입니다.

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제합니다.

## <a name="cheapptrbasedetach"></a><a name="detach"></a>CHeapPtrBase::D에타흐

포인터의 소유권을 해제하려면 이 메서드를 호출합니다.

```
T* Detach() throw();
```

### <a name="return-value"></a>Return Value

포인터의 복사본을 반환합니다.

### <a name="remarks"></a>설명

포인터의 소유권을 해제하고 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수를 NULL로 설정하고 포인터의 복사본을 반환합니다.

## <a name="cheapptrbasefree"></a><a name="free"></a>CHeapPtrBase::무료

이 메서드를 호출하여 을 가리키는 `CHeapPtrBase`개체를 삭제합니다.

```cpp
void Free() throw();
```

### <a name="remarks"></a>설명

가리키는 개체가 `CHeapPtrBase` 해제되고 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수가 NULL로 설정됩니다.

## <a name="cheapptrbasem_pdata"></a><a name="m_pdata"></a>CHeapPtrBase::m_pData

포인터 데이터 멤버 변수입니다.

```
T* m_pData;
```

### <a name="remarks"></a>설명

이 멤버 변수에는 포인터 정보가 있습니다.

## <a name="cheapptrbaseoperator-amp"></a><a name="operator_amp"></a>CHeapPtrBase::연산자&amp;

& 연산자

```
T** operator&() throw();
```

### <a name="return-value"></a>Return Value

개체가 가리키는 개체의 주소를 `CHeapPtrBase` 반환합니다.

## <a name="cheapptrbaseoperator--gt"></a><a name="operator_ptr"></a>CHeapPtrBase::연산자 -&gt;

구성원간 포인터 연산자입니다.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Return Value

[CHeapPtrBase::m_pData](#m_pdata) 멤버 변수의 값을 반환합니다.

### <a name="remarks"></a>설명

이 연산자를 사용하여 개체가 가리키는 `CHeapPtrBase` 클래스의 메서드를 호출합니다. 디버그 빌드에서 NULL을 `CHeapPtrBase` 가리키는 경우 어설션 오류가 발생합니다.

## <a name="cheapptrbaseoperator-t"></a><a name="operator_t_star"></a>CHeapPtrBase::연산자 T*

캐스트 연산자입니다.

```
operator T*() const throw();
```

### <a name="remarks"></a>설명

반환 [CHeapPtrBase::m_pData](#m_pdata).

## <a name="cheapptrbasereallocatebytes"></a><a name="reallocatebytes"></a>CHeapPtrBase::재할당바이트

메모리를 다시 할당하려면 이 메서드를 호출합니다.

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*n바이트*<br/>
바이트로 할당할 새 메모리 양입니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 메모리가 성공적으로 할당된 경우 true를 반환합니다.

## <a name="see-also"></a>참조

[CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)<br/>
[CComHeapPtr 클래스](../../atl/reference/ccomheapptr-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
