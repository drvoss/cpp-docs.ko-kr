---
title: CAutoPtrArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: 93fc5cfea4ea655e57e785ca234df59fe10d6570
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318887"
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray 클래스

이 클래스는 스마트 포인터 배열을 생성할 때 유용한 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>매개 변수

*전자*<br/>
포인터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[자동 Ptr배열::자동 PtrArray](#cautoptrarray)|생성자입니다.|

## <a name="remarks"></a>설명

이 클래스는 생성자 및 [CAtlArray](../../atl/reference/catlarray-class.md) 및 [CAutoPtrElementTraits에서](../../atl/reference/cautoptrelementtraits-class.md) 메서드를 파생 하여 스마트 포인터를 저장하는 컬렉션 클래스 개체를 만드는 데 도움이 됩니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cautoptrarraycautoptrarray"></a><a name="cautoptrarray"></a>자동 Ptr배열::자동 PtrArray

생성자입니다.

```
CAutoPtrArray() throw();
```

### <a name="remarks"></a>설명

스마트 포인터 배열을 초기화합니다.

## <a name="see-also"></a>참고 항목

[카틀어레이어리 클래스](../../atl/reference/catlarray-class.md)<br/>
[CAutoPtrElementTraits 클래스](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[자동 PtrList 클래스](../../atl/reference/cautoptrlist-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
