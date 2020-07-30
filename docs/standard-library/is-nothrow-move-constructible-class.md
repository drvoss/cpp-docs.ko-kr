---
title: is_nothrow_move_constructible 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
ms.openlocfilehash: 115a1b6c2157a139786c0b8762a9a614bbcd6deb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217729"
---
# <a name="is_nothrow_move_constructible-class"></a>is_nothrow_move_constructible 클래스

형식에 이동 생성자가 있는지 테스트 **`nothrow`** 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_nothrow_move_constructible;
```

### <a name="parameters"></a>매개 변수

*Ty*\
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 *Ty* 형식에 nothrow 이동 생성자가 있는 경우 true이 고 그렇지 않은 경우 false입니다.

## <a name="requirements"></a>요구 사항

**헤더:**\<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고 항목

[<type_traits>](../standard-library/type-traits.md)
