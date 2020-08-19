---
title: make_unsigned 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 46b785b20d2ca8ff2de0dfa678b543fa7493aa92
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561754"
---
# <a name="make_unsigned-class"></a>make_unsigned 클래스

형식을 만들거나 형식의 크기보다 크거나 같은 부호가 없는 가장 작은 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>매개 변수

*트*\
수정할 형식입니다.

## <a name="remarks"></a>설명

형식 한정자의 인스턴스는가 true 인 경우 *T* 인 수정 된 형식을 보유 `is_unsigned<T>` 합니다. 그렇지 않은 경우 가장 작은 부호 있는 형식 `ST`이며, 여기서 `sizeof (T) <= sizeof (ST)`입니다.

## <a name="requirements"></a>요구 사항

**헤더:**\<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고 항목

[<type_traits>](../standard-library/type-traits.md)
