---
title: Container Class::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 1fa3fe7dee10f3033b84a671fdc35c193cd6ec3c
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257899"
---
# <a name="container-classerase"></a>Container Class::erase

> [!NOTE]
> Microsoft C++ 설명서의 이 항목은 C++ 표준 라이브러리에서 사용되는 컨테이너의 비기능적 예제입니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

요소를 지웁니다.

## <a name="syntax"></a>구문

```cpp
iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>주의

첫 번째 멤버 함수는 *_Where*에서 가리키는 제어 되는 시퀀스의 요소를 제거 합니다. 두 번째 멤버 함수는 [`first`, `last`]의 범위에서 제어되는 시퀀스의 요소를 제거합니다. 둘 다 제거된 요소 다음에 남아 있는 첫 번째 요소를 지정하는 반복기를 반환하거나, 이러한 요소가 없는 경우 [end](../standard-library/container-class-end.md)를 반환합니다.

복사 작업에서 예외를 throw하는 경우에만 멤버 함수는 예외를 throw합니다.

## <a name="see-also"></a>참고 항목

[샘플 컨테이너 클래스](../standard-library/sample-container-class.md)
