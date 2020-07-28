---
title: 컴파일러 오류 C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: a0a993069a0bd232154cf6c1b365c0828d9bede8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220251"
---
# <a name="compiler-error-c2719"></a>컴파일러 오류 C2719

'parameter': __declspec(align('#'))를 사용하는 정식 매개 변수는 정렬되지 않습니다.

[Align](../../cpp/align-cpp.md) **`__declspec`** 한정자는 함수 매개 변수에서 허용 되지 않습니다. 함수 매개 변수 맞춤은 사용되는 호출 규칙에 의해 제어됩니다. 자세한 내용은 [호출 규칙](../../cpp/calling-conventions.md)을 참조 하세요.

다음 샘플에서는 C2719 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```
