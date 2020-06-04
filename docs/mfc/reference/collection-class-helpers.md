---
title: 컬렉션 클래스 도우미
ms.date: 11/04/2016
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
ms.openlocfilehash: 05fe49a4d8e6de92c584d40f3871f3efb906c7c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374808"
---
# <a name="collection-class-helpers"></a>컬렉션 클래스 도우미

컬렉션 클래스 `CMap` `CList`는 `CArray` 요소를 비교, 복사 및 직렬화하는 등의 목적으로 템플릿이 있는 전역 도우미 함수를 사용합니다. `CMap` `CList`에 `CArray`따라 클래스 를 구현하는 과정에서 맵, 목록 또는 배열에 저장된 데이터 유형에 맞게 조정된 버전으로 필요에 따라 이러한 함수를 재정의해야 합니다. 다음과 같은 `SerializeElements`도우미 함수 재정의에 대한 자세한 내용은 [컬렉션: 형식 안전 컬렉션을 만드는 방법](../../mfc/how-to-make-a-type-safe-collection.md)문서를 참조하십시오. `ConstructElements` 더 `DestructElements` 이상 사용되지 않습니다.

Microsoft 재단 클래스 라이브러리는 컬렉션 클래스를 사용자 지정하는 데 도움이 되는 afxtempl.h의 다음과 같은 전역 함수를 제공합니다.

### <a name="collection-class-helpers"></a>컬렉션 클래스 도우미

|||
|-|-|
|[CompareElements](#compareelements)|요소가 동일한지 여부를 나타냅니다.|
|[CopyElements](#copyelements)|한 배열에서 다른 배열로 요소를 복사합니다.|
|[DumpElements](#dumpelements)|스트림 지향 진단 출력을 제공합니다.|
|[해시키](#hashkey)|해시 키를 계산합니다.|
|[SerializeElements](#serializeelements)|아카이브에서 요소를 저장하거나 검색합니다.|

## <a name="compareelements"></a><a name="compareelements"></a>비교 요소

[CList::Find](clist-class.md#not_found.md#clist__find 직접 호출하고 [간접적으로 cmap__lookup](cmap-class.md#lookup) [및 cmap__operator &#91;&#93;](cmap-class.md#operator_at).

```
template<class TYPE, class ARG_TYPE>
BOOL AFXAPI
CompareElements(
    const TYPE* pElement1,
    const ARG_TYPE* pElement2);
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
비교할 첫 번째 요소의 형식입니다.

*pElement1*<br/>
비교할 첫 번째 요소에 대한 포인터입니다.

*ARG_TYPE*<br/>
비교할 두 번째 요소의 형식입니다.

*pElement2*<br/>
비교할 두 번째 요소에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

*pElement1을* 가리키는 개체가 *pElement2가*가리키는 개체와 같으면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

호출은 `CMap` `CMap` 템플릿 매개 변수 *KEY를* 사용하고 *ARG_KEY*.

기본 구현은 * \*pElement1* 및 * \*pElement2*의 비교 결과를 반환합니다. 응용 프로그램에 적합한 방식으로 요소를 비교할 수 있도록 이 함수를 재정의합니다.

C++ 언어는 단순 `==`형식(char, **int,** **float**등)에 대해 비교 연산자() 를 정의하지만 클래스 및 구조체에 대한 비교 연산자는 정의하지 않습니다.**char** 이를 사용하는 컬렉션 `CompareElements` 클래스 중 하나를 사용하거나 인스턴스화하려면 비교 연산자 또는 오버로드를 `CompareElements` 적절한 값을 반환하는 버전으로 정의해야 합니다.

### <a name="requirements"></a>요구 사항

   **헤더:** afxtempl.h

## <a name="copyelements"></a><a name="copyelements"></a>카피 엘리먼트

이 함수는 [CArray:::AEnd](carray-class.md#append) 및 [CArray::Copy에](carray-class.md#copy)의해 직접 호출됩니다.

```
template<class TYPE>
void AFXAPI CopyElements(
    TYPE* pDest,
    const TYPE* pSrc,
    INT_PTR nCount);
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
복사할 요소 유형을 지정하는 템플릿 매개 변수입니다.

*pDest*<br/>
요소가 복사될 대상에 대한 포인터입니다.

*pSrc*<br/>
복사할 요소의 소스에 대한 포인터입니다.

*nCount*<br/>
복사할 요소 수입니다.

### <a name="remarks"></a>설명

기본 구현에서는 단순 할당 **=** 연산자() 를 사용하여 복사 작업을 수행합니다. 복사중인 형식에 오버로드 된 operator=가 없는 경우 기본 구현은 비트로 복사본을 수행합니다.

이 기능 및 기타 도우미 함수 구현에 대한 자세한 내용은 [컬렉션: 형식 안전 컬렉션 을 만드는 방법을](../how-to-make-a-type-safe-collection.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxtempl.h

## <a name="dumpelements"></a><a name="dumpelements"></a>덤프 엘리먼트

재정의할 때 컬렉션 요소에 대한 텍스트 형식으로 스트림 지향 진단 출력을 제공합니다.

```
template<class TYPE>
void  AFXAPI DumpElements(
    CDumpContext& dc,
    const TYPE* pElements,
    INT_PTR nCount);
```

### <a name="parameters"></a>매개 변수

*Dc*<br/>
덤프 요소에 대한 컨텍스트를 덤프합니다.

*유형*<br/>
요소의 형식을 지정하는 템플릿 매개 변수입니다.

*p엘리퍼*<br/>
덤프할 요소에 대한 포인터입니다.

*nCount*<br/>
덤프할 요소 수입니다.

### <a name="remarks"></a>설명

및 `CArray::Dump` `CList::Dump` `CMap::Dump` 함수는 덤프의 깊이가 0보다 큰 경우 이를 호출합니다.

기본 구현은 아무 작업도 수행하지 않습니다. 컬렉션의 요소가 파생된 `CObject`경우 재정의는 일반적으로 컬렉션의 요소를 반복하여 각 요소를 `Dump` 차례로 호출합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxtempl.h

## <a name="hashkey"></a><a name="hashkey"></a>해시키

지정된 키에 대한 해시 값을 계산합니다.

```
template<class ARG_KEY>
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key);
```

### <a name="parameters"></a>매개 변수

*ARG_KEY*<br/>
맵 키에 액세스하는 데 사용되는 데이터 형식을 지정하는 템플릿 매개 변수입니다.

*키*<br/>
해시 값을 계산할 키입니다.

### <a name="return-value"></a>Return Value

키의 해시 값입니다.

### <a name="remarks"></a>설명

이 함수는 [CMap::RemoveKey에](cmap-class.md#removekey) 의해 직접 호출되고 [간접적으로 CMap::조회](cmap-class.md#lookup) 및 [CMap:운영자 &#91;&#93;](cmap-class.md#operator_at).

기본 구현은 *키를* 네 위치로 바로 이동하여 해시 값을 만듭니다. 응용 프로그램에 적합한 해시 값을 반환할 수 있도록 이 함수를 재정의합니다.

### <a name="example"></a>예제

```cpp
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
```

### <a name="requirements"></a>요구 사항

  **헤더** afxtempl.h

## <a name="serializeelements"></a><a name="serializeelements"></a>직렬화요소

[CArray](carray-class.md), [CList](clist-class.md)및 [CMap은](cmap-class.md) 이 함수를 호출하여 요소를 직렬화합니다.

```
template<class TYPE>
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);
```

### <a name="parameters"></a>매개 변수

*유형*<br/>
요소의 형식을 지정하는 템플릿 매개 변수입니다.

*ar*<br/>
보관할 아카이브 개체입니다.

*p엘리퍼*<br/>
보관 중인 요소에 대한 포인터입니다.

*nCount*<br/>
보관중인 요소 수

### <a name="remarks"></a>설명

기본 구현은 약간 읽기 또는 쓰기를 수행합니다.

이 기능 및 기타 도우미 함수 구현에 대한 자세한 내용은 [컬렉션: 형식 안전 컬렉션 을 만드는 방법을](../how-to-make-a-type-safe-collection.md)참조하십시오.

### <a name="example"></a>예제

[문서 컬렉션의 예제를 참조: 형식-안전 컬렉션을 만드는 방법](../how-to-make-a-type-safe-collection.md).

### <a name="requirements"></a>요구 사항

  **헤더** afxtempl.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[CMap 클래스](cmap-class.md)<br/>
[CList 클래스](clist-class.md)<br/>
[CArray 클래스](carray-class.md)
