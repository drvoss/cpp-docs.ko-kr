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
ms.openlocfilehash: 2de019f908942a58b232877fcd9eebc4689d8e22
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187481"
---
# <a name="void-c"></a>void (C++)

함수 반환 형식으로 사용 하는 경우 **void** 키워드는 함수가 값을 반환 하지 않도록 지정 합니다. 함수 매개 변수 목록에 사용 되는 경우 **void** 는 함수가 매개 변수를 사용 하지 않도록 지정 합니다. 포인터 선언에 사용 되는 경우 **void** 는 포인터가 "universal" 임을 지정 합니다.

포인터 형식이 **void\*** 이면 포인터는 **const** 또는 **volatile** 키워드를 사용 하 여 선언 되지 않은 모든 변수를 가리킬 수 있습니다. **Void\*** 포인터는 다른 형식으로 캐스팅 된 경우에만 역참조 될 수 있습니다. **Void\*** 포인터를 다른 형식의 데이터 포인터로 변환할 수 있습니다.

**Void** 포인터는 함수를 가리킬 수 있지만의 C++클래스 멤버가 아니어야 합니다.

**Void**형식의 변수는 선언할 수 없습니다.

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

[키워드](../cpp/keywords-cpp.md)<br/>
[기본 제공 형식](../cpp/fundamental-types-cpp.md)
