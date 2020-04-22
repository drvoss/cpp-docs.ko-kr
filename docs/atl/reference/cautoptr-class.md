---
title: CAutoPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
ms.openlocfilehash: 2fa6eb26c2e2cd569d74c02d8303768b1aeb4f1c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748265"
---
# <a name="cautoptr-class"></a>CAutoPtr 클래스

이 클래스는 스마트 포인터 개체를 나타냅니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <typename T>
class CAutoPtr
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
포인터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[코토프트어::콥트Ptr](#cautoptr)|생성자입니다.|
|[코토프트어::~코오토프트르](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[자동 Ptr::연결](#attach)|이 메서드를 호출하여 기존 포인터의 소유권을 가져가 십시오.|
|[코토프트르::D에타치](#detach)|포인터의 소유권을 해제하려면 이 메서드를 호출합니다.|
|[코토프트르::무료](#free)|이 메서드를 호출하여 을 가리키는 `CAutoPtr`개체를 삭제합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAutoPtr::연산자 T*](#operator_t_star)|캐스트 연산자입니다.|
|[CAutoPtr::연산자 =](#operator_eq)|할당 연산자입니다.|
|[CAutoPtr::연산자->](#operator_ptr)|구성원간 포인터 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[콥트르::m_p](#m_p)|포인터 데이터 멤버 변수입니다.|

## <a name="remarks"></a>설명

이 클래스는 스마트 포인터를 만들고 관리하는 방법을 제공하며, 이 방법은 범위를 벗어날 때 리소스를 자동으로 해제하여 메모리 누수로부터 보호하는 데 도움이 됩니다.

`CAutoPtr`또한, '의 복사 생성자 및 할당 연산자는 대상 포인터에 소스 포인터를 복사하고 NULL로 소스 포인터를 설정, 포인터의 소유권을 전송합니다. 따라서 각각 동일한 포인터를 저장하는 두 개의 `CAutoPtr` 개체를 가질 수 없으므로 동일한 포인터를 두 번 삭제할 가능성이 줄어듭니다.

`CAutoPtr`또한 포인터 컬렉션의 생성을 단순화합니다. 컬렉션 클래스를 파생하고 소멸자를 재정의하는 대신 `CAutoPtr` 개체 컬렉션을 만드는 것이 더 간단합니다. 컬렉션이 삭제되면 개체가 `CAutoPtr` 범위를 벗어나 자동으로 자신을 삭제합니다.

[CHeapPtr](../../atl/reference/cheapptr-class.md) 및 변형은 C++ `CAutoPtr` **새** 연산자 및 삭제 연산자 대신 다른 힙 함수를 사용하여 메모리를 할당하고 사용 **가능한** 메모리를 할당하고 사용하는 것을 제외하고는 과 같은 방식으로 작동합니다. [CAutoVectorPtr은](../../atl/reference/cautovectorptr-class.md) **벡터 new[]** 및 벡터 **delete[]를** 사용하여 메모리를 할당하고 사용 한다는 유일한 차이점과 유사합니다. `CAutoPtr`

스마트 포인터의 배열 이나 목록이 필요한 경우 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 및 [CAutoPtrList를](../../atl/reference/cautoptrlist-class.md) 참조 하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]

## <a name="cautoptrattach"></a><a name="attach"></a>자동 Ptr::연결

이 메서드를 호출하여 기존 포인터의 소유권을 가져가 십시오.

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
개체는 `CAutoPtr` 이 포인터의 소유권을 차지합니다.

### <a name="remarks"></a>설명

개체가 `CAutoPtr` 포인터의 소유권을 가져가면 포인터와 할당된 데이터가 범위를 벗어날 때 자동으로 삭제됩니다. [CAutoPtr::Detach가](#detach) 호출되면 프로그래머는 할당된 리소스를 해제할 책임이 다시 부여됩니다.

디버그 빌드에서 [CAutoPtr:m_p](#m_p) 데이터 멤버가 현재 기존 값을 가리키는 경우 어설션 오류가 발생합니다. 즉, NULL과 같지 않습니다.

### <a name="example"></a>예제

[CAutoPtr 개요의](../../atl/reference/cautoptr-class.md)예제를 참조하십시오.

## <a name="cautoptrcautoptr"></a><a name="cautoptr"></a>코토프트어::콥트Ptr

생성자입니다.

```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<>
CAutoPtr(CAutoPtr<T>& p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
기존 포인터입니다.

*TSrc*<br/>
다른 `CAutoPtr`에서 관리 되는 형식은 현재 개체를 초기화 하는 데 사용 됩니다.

### <a name="remarks"></a>설명

개체는 `CAutoPtr` 기존 포인터를 사용하여 만들 수 있으며, 이 경우 포인터의 소유권을 이전할 수 있습니다.

### <a name="example"></a>예제

[CAutoPtr 개요의](../../atl/reference/cautoptr-class.md)예제를 참조하십시오.

## <a name="cautoptrcautoptr"></a><a name="dtor"></a>코토프트어::~코오토프트르

소멸자입니다.

```
~CAutoPtr() throw();
```

### <a name="remarks"></a>설명

할당된 리소스를 해제합니다. 자동 Ptr 를 호출 [::무료](#free).

## <a name="cautoptrdetach"></a><a name="detach"></a>코토프트르::D에타치

포인터의 소유권을 해제하려면 이 메서드를 호출합니다.

```
T* Detach() throw();
```

### <a name="return-value"></a>Return Value

포인터의 복사본을 반환합니다.

### <a name="remarks"></a>설명

포인터의 소유권을 해제하고 [CAutoPtr:m_p](#m_p) 데이터 멤버 변수를 NULL로 설정하고 포인터의 복사본을 반환합니다. 호출한 `Detach`후에는 `CAutoPtr` 개체가 이전에 재현성을 가정했을 수 있는 할당된 리소스를 해제하는 것은 프로그래머의 요청입니다.

### <a name="example"></a>예제

[CAutoPtr 개요의](../../atl/reference/cautoptr-class.md)예제를 참조하십시오.

## <a name="cautoptrfree"></a><a name="free"></a>코토프트르::무료

이 메서드를 호출하여 을 가리키는 `CAutoPtr`개체를 삭제합니다.

```cpp
void Free() throw();
```

### <a name="remarks"></a>설명

가리키는 개체가 `CAutoPtr` 해제되고 [CAutoPtr:m_p](#m_p) 데이터 멤버 변수가 NULL로 설정됩니다.

## <a name="cautoptrm_p"></a><a name="m_p"></a>콥트르::m_p

포인터 데이터 멤버 변수입니다.

```
T* m_p;
```

### <a name="remarks"></a>설명

이 멤버 변수에는 포인터 정보가 있습니다.

## <a name="cautoptroperator-"></a><a name="operator_eq"></a>CAutoPtr::연산자 =

할당 연산자입니다.

```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```

### <a name="parameters"></a>매개 변수

*P*<br/>
포인터입니다.

*TSrc*<br/>
클래스 유형입니다.

### <a name="return-value"></a>Return Value

**CAutoPtr\< T >** 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

할당 연산자는 현재 `CAutoPtr` 포인터에서 개체를 분리하고 새 포인터 *p를*그 자리에 연결합니다.

### <a name="example"></a>예제

[CAutoPtr 개요의](../../atl/reference/cautoptr-class.md)예제를 참조하십시오.

## <a name="cautoptroperator--gt"></a><a name="operator_ptr"></a>CAutoPtr::연산자 -&gt;

구성원간 포인터 연산자입니다.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Return Value

[CAutoPtr::m_p](#m_p) 데이터 멤버 변수의 값을 반환 합니다.

### <a name="remarks"></a>설명

이 연산자를 사용하여 개체가 가리키는 `CAutoPtr` 클래스의 메서드를 호출합니다. 디버그 빌드에서 NULL을 `CAutoPtr` 가리키는 경우 어설션 오류가 발생합니다.

### <a name="example"></a>예제

[CAutoPtr 개요의](../../atl/reference/cautoptr-class.md)예제를 참조하십시오.

## <a name="cautoptroperator-t"></a><a name="operator_t_star"></a>CAutoPtr::연산자 T*

캐스트 연산자입니다.

```
operator T* () const throw();
```

### <a name="return-value"></a>Return Value

클래스 템플릿에 정의된 개체 데이터 형식에 대한 포인터를 반환합니다.

### <a name="example"></a>예제

[CAutoPtr 개요의](../../atl/reference/cautoptr-class.md)예제를 참조하십시오.

## <a name="see-also"></a>참조

[CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)<br/>
[CAutoVectorPtr 클래스](../../atl/reference/cautovectorptr-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
