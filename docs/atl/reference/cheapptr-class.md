---
title: CHeapPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
ms.openlocfilehash: a512aa974cb57072915f887f0c2a20ed1263ffa3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326911"
---
# <a name="cheapptr-class"></a>CHeapPtr 클래스

힙 포인터를 관리하기 위한 스마트 포인터 클래스입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
힙에 저장할 개체 유형입니다.

*할당자*<br/>
사용할 메모리 할당 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[밥프트르:::CHeapPtr](#cheapptr)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CHeapPtr::할당](#allocate)|이 메서드를 호출하여 힙에 메모리를 할당하여 개체를 저장합니다.|
|[CHeapPtr::재할당](#reallocate)|힙에 메모리를 다시 할당하려면 이 메서드를 호출합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CHeapPtr::연산자 =](#operator_eq)|할당 연산자입니다.|

## <a name="remarks"></a>설명

`CHeapPtr`[CHeapPtrBase에서](../../atl/reference/cheapptrbase-class.md) 파생되며 기본적으로 CRT [루틴(CCRTAllocator)을](../../atl/reference/ccrtallocator-class.md)사용하여 메모리를 할당하고 사용합니다. 클래스 [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) 힙 포인터 목록을 생성 하는 데 사용할 수 있습니다. COM 메모리 할당 루틴을 사용하는 [CComHeapPtr을](../../atl/reference/ccomheapptr-class.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

## <a name="cheapptrallocate"></a><a name="allocate"></a>CHeapPtr::할당

이 메서드를 호출하여 힙에 메모리를 할당하여 개체를 저장합니다.

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>매개 변수

*n엘리먼츠*<br/>
할당할 메모리 양을 계산하는 데 사용되는 요소 수입니다. 기본값은 1입니다.

### <a name="return-value"></a>Return Value

메모리가 성공적으로 할당된 경우 true를 반환합니다.

### <a name="remarks"></a>설명

할당자 루틴은 생성자에 정의된 형식의 *nElement* 개체를 저장하기 위해 힙에 충분한 메모리를 예약하는 데 사용됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

## <a name="cheapptrcheapptr"></a><a name="cheapptr"></a>밥프트르:::CHeapPtr

생성자입니다.

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
기존 힙 포인터 `CHeapPtr`또는 .

### <a name="remarks"></a>설명

힙 포인터는 선택적으로 기존 포인터 또는 개체를 `CHeapPtr` 사용하여 만들 수 있습니다. 이 경우 새 `CHeapPtr` 개체는 새 포인터 및 리소스를 관리해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

## <a name="cheapptroperator-"></a><a name="operator_eq"></a>CHeapPtr::연산자 =

대입 연산자입니다.

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
기존 `CHeapPtr` 개체입니다.

### <a name="return-value"></a>Return Value

업데이트된 에 대한 `CHeapPtr`참조를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

## <a name="cheapptrreallocate"></a><a name="reallocate"></a>CHeapPtr::재할당

힙에 메모리를 다시 할당하려면 이 메서드를 호출합니다.

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>매개 변수

*n엘리먼츠*<br/>
할당할 메모리 양을 계산하는 데 사용되는 요소의 새 수입니다.

### <a name="return-value"></a>Return Value

메모리가 성공적으로 할당된 경우 true를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>참고 항목

[CHeapPtrBase 클래스](../../atl/reference/cheapptrbase-class.md)<br/>
[CCRTAllocator 클래스](../../atl/reference/ccrtallocator-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
