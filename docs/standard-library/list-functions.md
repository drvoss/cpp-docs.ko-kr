---
title: '&lt;list&gt; 함수 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 04f00a9274018432cd03917ae5485f2d395649e4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78874437"
---
# <a name="ltlistgt-functions"></a>&lt;list&gt; 함수

## <a name="swap"></a>스왑을

두 목록의 요소를 교환합니다.

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`list` 형식의 개체입니다.

*오른쪽*\
`list` 형식의 개체입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `left.swap(right)`를 실행합니다.
