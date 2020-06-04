---
title: 컴파일러 경고(수준 1) C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: 8ac00d3d57f8cf7d6c85f3106dbe9b8c3cb9adf0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162922"
---
# <a name="compiler-warning-level-1-c4342"></a>컴파일러 경고(수준 1) C4342

동작 변경: '*function*'이 호출 되었지만 이전 버전에서는 멤버 연산자가 호출 되었습니다.

Visual Studio 2002 이전 C++ 버전의 visual Studio에서는 멤버가 호출 되었지만이 동작이 변경 되었으며 이제 컴파일러는 네임 스페이스 범위에서 가장 일치 하는 항목을 찾습니다.

멤버 연산자가 있는 경우 컴파일러는 이전에 네임 스페이스 범위 연산자를 고려 하지 않습니다. 네임 스페이스 범위에서 더 잘 일치 하는 경우 현재 컴파일러는이를 올바르게 호출 하지만 이전 컴파일러에서는이를 고려 하지 않습니다.

코드를 현재 버전으로 성공적으로 이식 한 후에는이 경고를 사용 하지 않도록 설정 해야 합니다.  컴파일러는 가양성을 제공할 수 있으며 동작이 변경 되지 않은 코드에 대해이 경고를 생성 합니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.

다음 샘플에서는 C4342를 생성 합니다.

```cpp
// C4342.cpp
// compile with: /EHsc /W1
#include <fstream>
#pragma warning(default: 4342)
using namespace std;
struct X : public ofstream {
   X();
};

X::X() {
   open( "ofs_bug_ev.txt." );
   if ( is_open() ) {
      *this << "Text" << "<-should be text" << endl;   // C4342
      *this << ' ' << "<-should be space symbol" << endl;   // C4342
   }
}

int main() {
   X b;
   b << "Text" << "<-should be text" << endl;
   b << ' ' << "<-should be space symbol" << endl;
}
```
