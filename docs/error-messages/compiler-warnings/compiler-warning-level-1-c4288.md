---
title: 컴파일러 경고(수준 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: e706a448f4264eceedbb4fa8932c0fc30e88d532
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175742"
---
# <a name="compiler-warning-level-1-c4288"></a>컴파일러 경고(수준 1) C4288

비표준 확장이 사용 됨: ' var ': for 루프에서 선언 된 루프 제어 변수가 for 루프 범위 외부에서 사용 됩니다. 외부 범위의 선언과 충돌 합니다.

[/Ze](../../build/reference/za-ze-disable-language-extensions.md) 및 **/zc: forscope-** 를 사용 하 여 컴파일하는 경우 **for 루프에서** 선언 된 변수 [는 for 루프](../../cpp/for-statement-cpp.md)범위 다음에 사용 되었습니다. 해당 C++ 언어에 대 한 Microsoft 확장을 통해이 변수를 범위 내에 유지할 수 있으며, C4288는 변수의 첫 번째 선언이 사용 되지 않는 것을 알려 줍니다.

하며/ze를 사용 하 여 **for** 루프에서 Microsoft 확장을 지정 하는 방법에 대 한 자세한 내용은 [/zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 를 참조 하세요.

다음 샘플에서는 C4288를 생성 합니다.

```cpp
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```
