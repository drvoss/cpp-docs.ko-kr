---
title: allocator_suballoc 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_suballoc
- allocators/stdext::allocator_suballoc
helpviewer_keywords:
- allocator_suballoc class
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
ms.openlocfilehash: 47b82a198a52a61bd5558bd59a38b1d328fa67b2
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562586"
---
# <a name="allocator_suballoc-class"></a>allocator_suballoc 클래스

[Cache_suballoc](cache-suballoc-class.md)형식의 캐시 *를 사용 하 여 형식 형식의 개체* 에 대 한 저장소 할당 및 해제를 관리 하는 개체에 대해 설명 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_suballoc;
```

### <a name="parameters"></a>매개 변수

*입력할*\
할당자에 의해 할당된 요소 형식입니다.

## <a name="remarks"></a>설명

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl) 매크로는 다음 문에서이 클래스를 *name* 매개 변수로 전달 합니다.`ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`

## <a name="requirements"></a>요구 사항

**헤더:**\<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고 항목

[\<allocators>](allocators-header.md)
