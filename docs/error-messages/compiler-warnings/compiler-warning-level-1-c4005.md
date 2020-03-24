---
title: 컴파일러 경고 (수준 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: 4e95f8deeb61c5a4d56e0643beb6a746f848e33e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164731"
---
# <a name="compiler-warning-level-1-c4005"></a>컴파일러 경고 (수준 1) C4005

' identifier ': 매크로 재정의

매크로 식별자는 두 번 정의 됩니다. 컴파일러는 두 번째 매크로 정의를 사용 합니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. `#define` 지시문을 사용 하 여 명령줄 및 코드에서 매크로를 정의 합니다.

1. 포함 파일에서 가져온 매크로

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. 정의 중 하나를 제거 합니다.

1. 두 번째 정의 앞에 [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) 지시어를 사용 합니다.

다음 샘플에서는 C4005를 생성 합니다.

```cpp
// C4005.cpp
// compile with: /W1 /EHsc
#include <iostream>
using namespace std;

#define TEST "test1"
#define TEST "test2"   // C4005 delete or rename to resolve the warning

int main() {
   cout << TEST << endl;
}
```
