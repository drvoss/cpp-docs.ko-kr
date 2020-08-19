---
title: allocator_chunklist 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_chunklist
- allocators/stdext::allocators::allocator_chunklist
helpviewer_keywords:
- stdext::allocator_chunklist
- stdext::allocators [C++], allocator_chunklist
ms.assetid: ea72ed0a-dfdb-4c8b-8096-e4baf567b80f
ms.openlocfilehash: 64b419b2565609d8f6018facdbe25d5dee9d94aa
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562625"
---
# <a name="allocator_chunklist-class"></a>allocator_chunklist 클래스

[cache_chunklist](cache-chunklist-class.md) 유형의 캐시를 사용하여 개체에 대한 스토리지 할당 및 해제를 관리하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_chunklist;
```

### <a name="parameters"></a>매개 변수

*입력할*\
할당자에 의해 할당된 요소 형식입니다.

## <a name="remarks"></a>설명

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl) 매크로는 다음 문에서이 클래스를 *name* 매개 변수로 전달 합니다.`ALLOCATOR_DECL(CACHE_CHUNKLIST, SYNC_DEFAULT, allocator_chunklist);`

## <a name="requirements"></a>요구 사항

**헤더:**\<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고 항목

[\<allocators>](allocators-header.md)
