---
title: 모든&gt; 함수를 &lt;합니다.
ms.date: 04/04/2019
f1_keywords:
- any/std::any_cast
- any/std::make_any
- any/std::swap
ms.openlocfilehash: bb5f8b4411477cfcd33613ee0395227dced784f6
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78875912"
---
# <a name="ltanygt-functions"></a>모든&gt; 함수를 &lt;합니다.

## <a name="any_cast"></a>any_cast

개체를 any로 만듭니다.

```cpp
template<class T>
    T any_cast(const any& operand);
template<class T>
    T any_cast(any& operand);
template<class T>
    T any_cast(any&& operand);
template<class T>
    const T* any_cast(const any* operand) noexcept;
template<class T>
    T* any_cast(any* operand) noexcept;
```

## <a name="make_any"></a>make_any

값을 사용하고 any 개체를 만듭니다.

```cpp
template <class T, class... Args>
    any make_any(Args&& ...args);
template <class T, class U, class... Args>
    any make_any(initializer_list<U> il, Args&& ...args);
```

## <a name="swap"></a>스왑을

두 개체의 요소를 교환 합니다.

```cpp
void swap(any& left, any& right) noexcept;
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`any` 형식의 개체입니다.

*오른쪽*\
`any` 형식의 개체입니다.
