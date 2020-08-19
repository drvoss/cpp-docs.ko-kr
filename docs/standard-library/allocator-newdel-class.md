---
title: allocator_newdel 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- stdext::allocators::allocator_newdel
helpviewer_keywords:
- stdext::allocators [C++], allocator_newdel
- stdext::allocator_newdel
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
ms.openlocfilehash: 30e0f7902a8af435b46aaedf0b38661b7a6604a8
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562599"
---
# <a name="allocator_newdel-class"></a>allocator_newdel 클래스

는 **operator delete** 를 사용 하 여 메모리 블록을 할당 취소 하 고 **new 연산자** 를 사용 하 여 메모리 블록을 할당 하는 할당자를 구현 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Type>
class allocator_newdel;
```

### <a name="parameters"></a>매개 변수

*입력할*\
할당자에 의해 할당된 요소 형식입니다.

## <a name="remarks"></a>설명

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl) 매크로는 다음 문에서이 클래스를 *name* 매개 변수로 전달 합니다.`ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`

## <a name="requirements"></a>요구 사항

**헤더:**\<allocators>

**네임스페이스:** stdext

## <a name="see-also"></a>참고 항목

[\<allocators>](allocators-header.md)
