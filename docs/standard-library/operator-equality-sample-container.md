---
title: operator==(&lt;sample container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
ms.openlocfilehash: 08adfcc770551d3050daa46c870b950e468c95b3
ms.sourcegitcommit: eff68e4e82be292a5664616b16a526df3e9d1cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80150644"
---
# <a name="operator-ltsample-containergt"></a>operator==(&lt;sample container&gt;)

> [!NOTE]
> Microsoft C++ 설명서의 이 항목은 C++ 표준 라이브러리에서 사용되는 컨테이너의 비기능적 예제입니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

오버 로드 `operator==` 클래스 템플릿 [컨테이너](../standard-library/sample-container-class.md)의 두 개체를 비교 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Return Value

[Begin](../standard-library/container-class-begin.md)`, left.`[end](../standard-library/container-class-end.md)`, right.begin)``== right.size && equal(left.``left.`[크기](../standard-library/container-class-size.md) 를 반환 합니다.

## <a name="see-also"></a>참고 항목

[\<sample container>](../standard-library/sample-container.md)
