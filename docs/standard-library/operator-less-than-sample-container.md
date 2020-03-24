---
title: operator&lt;(&lt;sample container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::operator<
- operator<
- std.<
- <
- std.operator<
- std::<
helpviewer_keywords:
- < operator, comparing specific objects
- operator<, valarrays
- < operator
- operator <, valarrays
ms.assetid: 31027dd6-53be-428b-b950-1dcb25393597
ms.openlocfilehash: 6ef43fb762c4da71062fc846048f21c0112bfafc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215269"
---
# <a name="operatorlt-ltsample-containergt"></a>operator&lt;(&lt;sample container&gt;)

> [!NOTE]
> Microsoft C++ 설명서의 이 항목은 C++ 표준 라이브러리에서 사용되는 컨테이너의 비기능적 예제입니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

오버 로드 연산자는 클래스 템플릿 [컨테이너](../standard-library/sample-container-class.md)의 두 개체를 비교 하는 **<** 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
bool operator<(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>반환 값

`lexicographical_compare(left.begin, left.end, right.begin, right.end)`를 반환합니다.

## <a name="see-also"></a>참고 항목

[\<sample container>](../standard-library/sample-container.md)\
[시작](../standard-library/container-class-begin.md)\
[end](../standard-library/container-class-end.md)
