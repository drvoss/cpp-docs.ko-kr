---
title: 컴파일러 경고 (수준 1) C4154
ms.date: 11/04/2016
f1_keywords:
- C4154
helpviewer_keywords:
- C4154
ms.assetid: 4511afeb-e893-4cc6-83b6-4c7a0477f76b
ms.openlocfilehash: 07b4c6e0821c925e70ce1bce1d910f184d658982
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163614"
---
# <a name="compiler-warning-level-1-c4154"></a>컴파일러 경고 (수준 1) C4154

배열 식 삭제 포인터로의 변환을 제공 합니다.

배열에 `delete`를 사용할 수 없으므로 컴파일러가 배열을 포인터로 변환 합니다.

## <a name="example"></a>예제

```cpp
// C4154.cpp
// compile with: /c /W1
int main() {
   int array[ 10 ];
   delete array;   // C4154 can't delete stack object

   int *parray2 = new int [10];
   int (&array2)[10] = (int(&)[10]) parray2;
   delete [] array2;   // C4154

   // try the following line instead
   delete [] &array2;
}
```
