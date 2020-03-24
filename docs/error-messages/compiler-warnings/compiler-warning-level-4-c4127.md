---
title: 컴파일러 경고(수준 4) C4127
ms.date: 10/16/2019
f1_keywords:
- C4127
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
ms.openlocfilehash: 9d4397c11c4d2f0f9013c7df914cbc4be9fd4e9d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198486"
---
# <a name="compiler-warning-level-4-c4127"></a>컴파일러 경고(수준 4) C4127

> 조건식이 상수입니다.

## <a name="remarks"></a>주의

**If** 문 또는 **while** 루프의 제어 식이 상수로 계산 됩니다. Visual Studio 2015 업데이트 3부터 일반적인 자연 스러운 사용으로 인해, 1 또는 **true** 와 같은 trivial 상수는 식에서 연산의 결과가 아닌 경우 경고를 트리거하지 않습니다.

루프를 중간에 종료 하기 때문에 **while** 루프의 제어 식이 상수인 경우 **while** 루프를 **for** loop로 바꾸는 것이 좋습니다. **For** 루프의 초기화, 종료 테스트 및 루프 증분을 생략할 수 있습니다. 이렇게 하면 `while(1)`와 마찬가지로 루프가 무한 하 고 **for** 문의 본문에서 루프를 종료할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4127를 생성 하는 두 가지 방법을 보여 주고 for 루프를 사용 하 여 경고를 방지 하는 방법을 보여 줍니다.

```cpp
// C4127.cpp
// compile with: /W4
#include <stdio.h>
int main() {
   if (true) {}           // OK in VS2015 update 3 and later
   if (1 == 1) {}         // C4127
   while (42) { break; }  // C4127

   // OK
   for ( ; ; ) {
      printf("test\n");
      break;
   }
}
```

이 경고는 컴파일 시간 상수가 조건식에서 사용 되는 경우에도 발생할 수 있습니다.

```cpp
#include <string>

using namespace std;

template<size_t S, class T>
void MyFunc()
{
   if (sizeof(T) >= S) // C4127. "Consider using 'if constexpr' statement instead"
   {
   }
}

class Foo
{
   int i;
   string s;
};

int main()
{
   Foo f;
   MyFunc<4, Foo>();
}
```
