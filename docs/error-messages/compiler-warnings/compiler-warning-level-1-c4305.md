---
title: 컴파일러 경고(수준 1) C4305
ms.date: 01/17/2018
f1_keywords:
- C4305
helpviewer_keywords:
- C4305
ms.openlocfilehash: 567442bc48487e4f7d1f905f871d15f913646e87
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233290"
---
# <a name="compiler-warning-level-1-c4305"></a>컴파일러 경고(수준 1) C4305

> '*context*': '*type1*'에서 '*type2*' (으)로 잘림

## <a name="remarks"></a>설명

이 경고는 값이 초기화에서 더 작은 형식으로 변환 되거나 생성자 인수로 변환 되어 정보가 손실 될 때 발생 합니다.

## <a name="example"></a>예제

이 샘플은 다음과 같은 두 가지 방법을 보여 줍니다.

```cpp
// C4305.cpp
// Compile by using: cl /EHsc /W4 C4305.cpp

struct item
{
    item(float) {}
};

int main()
{
    float f = 2.71828;          // C4305 'initializing'
    item i(3.14159);            // C4305 'argument'
    return static_cast<int>(f);
}
```

이 문제를 해결 하려면 올바른 형식의 값을 사용 하 여를 초기화 하거나 올바른 형식으로의 명시적 캐스트를 사용 합니다. 예를 들어, **`float`** **`double`** 변수를 초기화 **`float`** 하거나 인수를 사용 하는 생성자에 전달 하기 위해 (부동 소수점 리터럴의 기본 형식) 대신 2.71828 f와 같은 리터럴을 사용 **`float`** 합니다.
