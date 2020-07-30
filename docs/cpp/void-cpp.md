---
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: fddfc2e3295552414a00692006ab12725dc07d52
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213114"
---
# <a name="void-c"></a>void (C++)

함수 반환 형식으로 사용 하는 경우 **`void`** 키워드는 함수가 값을 반환 하지 않도록 지정 합니다. 함수 매개 변수 목록에 사용 되는 경우 **`void`** 함수에서 매개 변수를 사용 하지 않도록 지정 합니다. 포인터 선언에 사용 될 때 **`void`** 포인터가 "universal" 임을 지정 합니다.

포인터 형식이 **void \* **인 경우 포인터는 또는 키워드를 사용 하 여 선언 되지 않은 모든 변수를 가리킬 수 **`const`** 있습니다 **`volatile`** . **Void \* ** 포인터는 다른 형식으로 캐스팅 된 경우에만 역참조 될 수 있습니다. **Void \* ** 포인터는 다른 형식의 데이터 포인터로 변환 될 수 있습니다.

**`void`** 포인터는 c + +의 클래스 멤버가 아닌 함수를 가리킬 수 있습니다.

형식의 변수는 선언할 수 없습니다 **`void`** .

## <a name="example"></a>예제

```cpp
// void.cpp
void vobject;   // C2182
void *pv;   // okay
int *pint; int i;
int main() {
   pv = &i;
   // Cast optional in C required in C++
   pint = (int *)pv;
}
```

## <a name="see-also"></a>참고 항목

[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[기본 제공 형식](../cpp/fundamental-types-cpp.md)
