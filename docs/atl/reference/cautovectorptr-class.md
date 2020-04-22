---
title: CAutoVectorPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
ms.openlocfilehash: fc4bd4ba7a2f41a25679f1da718671f525519708
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748222"
---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr 클래스

이 클래스는 벡터 new 및 delete 연산자를 사용하여 스마트 포인터 개체를 나타냅니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CAutoVectorPtr
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
포인터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[자동 벡터 Ptr:::C자동 벡터Ptr](#cautovectorptr)|생성자입니다.|
|[자동 벡터Ptr::~C자동 벡터Ptr](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[자동 벡터 Ptr::할당](#allocate)|이 메서드를 호출하여 `CAutoVectorPtr`을 가리키는 개체 배열에 필요한 메모리를 할당합니다.|
|[자동 벡터 Ptr::연결](#attach)|이 메서드를 호출하여 기존 포인터의 소유권을 가져가 십시오.|
|[오토벡터Ptr::D에타치](#detach)|포인터의 소유권을 해제하려면 이 메서드를 호출합니다.|
|[자동 벡터 Ptr::무료](#free)|이 메서드를 호출하여 을 가리키는 `CAutoVectorPtr`개체를 삭제합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C자동 벡터 Ptr::연산자 T *](#operator_t__star)|캐스트 연산자입니다.|
|[C자동 벡터Ptr::연산자 =](#operator_eq)|할당 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[자동 벡터 Ptr::m_p](#m_p)|포인터 데이터 멤버 변수입니다.|

## <a name="remarks"></a>설명

이 클래스는 스마트 포인터를 만들고 관리하는 방법을 제공하며, 이 방법은 범위를 벗어날 때 리소스를 자동으로 해제하여 메모리 누수로부터 보호하는 데 도움이 됩니다. `CAutoVectorPtr``CAutoPtr`벡터 [새&#91;&#93;](../../standard-library/new-operators.md#op_new_arr) 및 벡터 `CAutoVectorPtr` 삭제 [&#91;&#93;](../../standard-library/new-operators.md#op_delete_arr) 사용하여 C++ **새** 연산자 대신 메모리를 할당하고 사용 **해 주는** 유일한 차이점은 유사합니다. 컬렉션 클래스가 필요한 경우 [CAutoVectorPtrElementTraits를](../../atl/reference/cautovectorptrelementtraits-class.md) `CAutoVectorPtr` 참조하십시오.

스마트 포인터 클래스를 사용하는 예제는 [CAutoPtr을](../../atl/reference/cautoptr-class.md) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="cautovectorptrallocate"></a><a name="allocate"></a>자동 벡터 Ptr::할당

이 메서드를 호출하여 `CAutoVectorPtr`을 가리키는 개체 배열에 필요한 메모리를 할당합니다.

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>매개 변수

*n엘리먼츠*<br/>
배열의 요소 수입니다.

### <a name="return-value"></a>Return Value

메모리가 성공적으로 할당된 경우 true를 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 [CAutoVectorPtr::m_p](#m_p) 멤버 변수가 현재 기존 값을 가리키는 경우 어설션 오류가 발생합니다. 즉, NULL과 같지 않습니다.

## <a name="cautovectorptrattach"></a><a name="attach"></a>자동 벡터 Ptr::연결

이 메서드를 호출하여 기존 포인터의 소유권을 가져가 십시오.

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
개체는 `CAutoVectorPtr` 이 포인터의 소유권을 차지합니다.

### <a name="remarks"></a>설명

개체가 `CAutoVectorPtr` 포인터의 소유권을 가져가면 포인터와 할당된 데이터가 범위를 벗어날 때 자동으로 삭제됩니다. [CAutoVectorPtr::Detach가](#detach) 호출되면 프로그래머는 할당된 리소스를 해제할 책임이 다시 부여됩니다.

디버그 빌드에서 [CAutoVectorPtr::m_p](#m_p) 멤버 변수가 현재 기존 값을 가리키는 경우 어설션 오류가 발생합니다. 즉, NULL과 같지 않습니다.

## <a name="cautovectorptrcautovectorptr"></a><a name="cautovectorptr"></a>자동 벡터 Ptr:::C자동 벡터Ptr

생성자입니다.

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
기존 포인터입니다.

### <a name="remarks"></a>설명

개체는 `CAutoVectorPtr` 기존 포인터를 사용하여 만들 수 있으며, 이 경우 포인터의 소유권을 이전할 수 있습니다.

## <a name="cautovectorptrcautovectorptr"></a><a name="dtor"></a>자동 벡터Ptr::~C자동 벡터Ptr

소멸자입니다.

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>설명

할당된 리소스를 해제합니다. [자동 벡터 Ptr를 호출 ::무료](#free).

## <a name="cautovectorptrdetach"></a><a name="detach"></a>오토벡터Ptr::D에타치

포인터의 소유권을 해제하려면 이 메서드를 호출합니다.

```
T* Detach() throw();
```

### <a name="return-value"></a>Return Value

포인터의 복사본을 반환합니다.

### <a name="remarks"></a>설명

포인터의 소유권을 해제하고 [CAutoVectorPtr::m_p](#m_p) 멤버 변수를 NULL로 설정하고 포인터의 복사본을 반환합니다. 호출한 `Detach`후에는 `CAutoVectorPtr` 개체가 이전에 책임을 맡았을 수 있는 할당된 리소스를 해제하는 것은 프로그래머의 책임입니다.

## <a name="cautovectorptrfree"></a><a name="free"></a>자동 벡터 Ptr::무료

이 메서드를 호출하여 을 가리키는 `CAutoVectorPtr`개체를 삭제합니다.

```cpp
void Free() throw();
```

### <a name="remarks"></a>설명

가리키는 개체가 `CAutoVectorPtr` 해제되고 [CAutoVectorPtr:m_p](#m_p) 멤버 변수가 NULL로 설정됩니다.

## <a name="cautovectorptrm_p"></a><a name="m_p"></a>자동 벡터 Ptr::m_p

포인터 데이터 멤버 변수입니다.

```
T* m_p;
```

### <a name="remarks"></a>설명

이 멤버 변수에는 포인터 정보가 있습니다.

## <a name="cautovectorptroperator-"></a><a name="operator_eq"></a>C자동 벡터Ptr::연산자 =

할당 연산자입니다.

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
포인터입니다.

### <a name="return-value"></a>Return Value

**\< CAutoVectorPtr T >** 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

할당 연산자는 현재 `CAutoVectorPtr` 포인터에서 개체를 분리하고 새 포인터 *p를*그 자리에 연결합니다.

## <a name="cautovectorptroperator-t-"></a><a name="operator_t__star"></a>C자동 벡터 Ptr::연산자 T *

캐스트 연산자입니다.

```
operator T*() const throw();
```

### <a name="remarks"></a>설명

클래스 템플릿에 정의된 개체 데이터 형식에 대한 포인터를 반환합니다.

## <a name="see-also"></a>참조

[CAutoPtr 클래스](../../atl/reference/cautoptr-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
