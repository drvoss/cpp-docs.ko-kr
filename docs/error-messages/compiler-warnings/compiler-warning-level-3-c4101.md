---
title: 컴파일러 경고 (수준 3) C4101
ms.date: 11/04/2016
f1_keywords:
- C4101
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
ms.openlocfilehash: 0ac34fbaf4cbb54583394dff5b8645fe56b8b9cd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199047"
---
# <a name="compiler-warning-level-3-c4101"></a>컴파일러 경고 (수준 3) C4101

' identifier ': 참조 되지 않은 지역 변수입니다.

지역 변수는 사용 되지 않습니다. 이 경고는 다음과 같은 명백한 상황에서 발생 합니다.

```cpp
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

그러나 클래스의 인스턴스를 통해 **정적** 멤버 함수를 호출 하는 경우에도이 경고가 발생 합니다.

```cpp
// C4101b.cpp
// compile with:  /W3
struct S {
   static int func()
   {
      return 1;
   }
};

int main() {
   S si;   // C4101, si is never used
   int y = si.func();
   return y;
}
```

이 경우 컴파일러는 `si`에 대 한 정보를 사용 하 여 **정적** 함수에 액세스 하지만 클래스의 인스턴스는 **정적** 함수를 호출 하는 데 필요 하지 않습니다. 따라서 경고가 발생 합니다. 이 경고를 해결 하려면 다음을 수행 합니다.

- 컴파일러가 `func`호출에서 `si`의 인스턴스를 사용 하는 생성자를 추가 합니다.

- `func`정의에서 **static** 키워드를 제거 합니다.

- **정적** 함수 `int y = S::func();`명시적으로 호출 합니다.
