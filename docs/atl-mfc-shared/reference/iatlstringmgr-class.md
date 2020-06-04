---
title: IAtlStringMgr 클래스
ms.date: 10/18/2018
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
ms.openlocfilehash: c3fabb7a7a6da4129787d219bd83b2a35fa0c4dd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746599"
---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr 클래스

이 클래스는 메모리 `CStringT` 관리자에 대한 인터페이스를 나타냅니다.

## <a name="syntax"></a>구문

```
__interface IAtlStringMgr
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[할당](#allocate)|새 문자열 데이터 구조를 할당 하려면이 메서드를 호출 합니다.|
|[복제](#clone)|이 메서드를 호출하여 포인터를 새 문자열 관리자로 `CSimpleStringT`반환하여 의 다른 인스턴스와 함께 사용할 수 있습니다.|
|[Free](#free)|문자열 데이터 구조를 해제하려면 이 메서드를 호출합니다.|
|[게닐스트링](#getnilstring)|빈 문자열 `CStringData` 개체에서 사용되는 개체에 대한 포인터를 반환합니다.|
|[재할당](#reallocate)|문자열 데이터 구조를 재할당하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 MFC 독립적인 문자열 클래스에서 사용되는 메모리를 관리합니다. [CSimpleStringT,](../../atl-mfc-shared/reference/csimplestringt-class.md) [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)및 [CFixedStringT와](../../atl-mfc-shared/reference/cfixedstringt-class.md)같은 .

이 클래스를 사용하여 사용자 지정 문자열 클래스에 대한 사용자 지정 메모리 관리자를 구현할 수도 있습니다. 자세한 내용은 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)를 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** 아실프스트스트.h

## <a name="iatlstringmgrallocate"></a><a name="allocate"></a>IAtlStringMgr::할당

새 문자열 데이터 구조를 할당합니다.

```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```

### <a name="parameters"></a>매개 변수

*nAllocLength*<br/>
새 메모리 블록의 문자 수입니다.

*n차사이즈*<br/>
문자열 관리자에서 사용하는 문자 유형의 크기(바이트)입니다.

### <a name="return-value"></a>Return Value

새로 할당된 메모리 블록에 대한 포인터를 반환합니다.

> [!NOTE]
> 예외를 throw하여 실패한 할당에 신호를 주지 마십시오. 대신 NULL을 반환하여 실패한 할당에 대해 신호를 보내야 합니다.

### <a name="remarks"></a>설명

[IAtlStringMgr 호출::무료](#free) 또는 [IAtlStringMgr::ReAllocate](#reallocate) 이 메서드에 의해 할당 된 메모리를 해제 합니다.

> [!NOTE]
> 사용 예제는 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)를 참조하십시오.

## <a name="iatlstringmgrclone"></a><a name="clone"></a>IAtlStringMgr::클론

의 다른 인스턴스와 함께 사용할 새 문자열 `CSimpleStringT`관리자에 대한 포인터를 반환합니다.

```
IAtlStringMgr* Clone() throw();
```

### <a name="return-value"></a>Return Value

`IAtlStringMgr` 개체의 복사본을 반환합니다.

### <a name="remarks"></a>설명

일반적으로 새 문자열에 대 한 문자열 관리자가 필요한 경우 프레임 워크에 의해 호출 됩니다. 대부분의 경우 **이** 포인터가 반환됩니다.

그러나 메모리 관리자가 여러 인스턴스에서 `CSimpleStringT`사용되는 것을 지원하지 않는 경우 공유 가능한 문자열 관리자에 대한 포인터를 반환해야 합니다.

> [!NOTE]
> 사용 예제는 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)를 참조하십시오.

## <a name="iatlstringmgrfree"></a><a name="free"></a>IAtlStringMgr::무료

문자열 데이터 구조를 해제합니다.

```cpp
void Free(CStringData* pData) throw();
```

### <a name="parameters"></a>매개 변수

*Pdata*<br/>
해제할 메모리 블록에 대한 포인터입니다.

### <a name="remarks"></a>설명

할당 [또는](#allocate) [재할당에](../../atl/reference/iatlmemmgr-class.md#reallocate)의해 이전에 할당된 지정된 메모리 블록을 해제합니다.

> [!NOTE]
> 사용 예제는 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)를 참조하십시오.

## <a name="iatlstringmgrgetnilstring"></a><a name="getnilstring"></a>IAtlStringMgr::GetNilString

빈 문자열에 대한 문자열 데이터 구조에 대한 포인터를 반환합니다.

```
CStringData* GetNilString() throw();
```

### <a name="return-value"></a>Return Value

빈 문자열을 `CStringData` 나타내는 데 사용되는 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

빈 문자열의 표현을 반환하려면 이 함수를 호출합니다.

> [!NOTE]
> 사용자 지정 문자열 관리자를 구현할 때 이 함수는 실패해서는 안 됩니다. 문자열 관리자 클래스에 인스턴스를 `CNilStringData` 포함 하 여이 작업을 보장할 수 있습니다 및 해당 인스턴스에 포인터를 반환 합니다.

> [!NOTE]
> 사용 예제는 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)를 참조하십시오.

## <a name="iatlstringmgrreallocate"></a><a name="reallocate"></a>IAtlStringMgr::재할당

문자열 데이터 구조를 재할당합니다.

```
CStringData* Reallocate(
    CStringData* pData,
    int nAllocLength,
    int nCharSize) throw();
```

### <a name="parameters"></a>매개 변수

*Pdata*<br/>
이 메모리 관리자가 이전에 할당한 메모리에 대한 포인터입니다.

*nAllocLength*<br/>
새 메모리 블록의 문자 수입니다.

*n차사이즈*<br/>
문자열 관리자에서 사용하는 문자 유형의 크기(바이트)입니다.

### <a name="return-value"></a>Return Value

새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

*pData에*의해 지정된 기존 메모리 블록의 크기를 조정하려면 이 함수를 호출합니다.

[IAtlStringMgr 호출::이](#free) 메서드에 의해 할당 된 메모리를 해제 무료.

> [!NOTE]
> 사용 예제는 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)를 참조하십시오.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
