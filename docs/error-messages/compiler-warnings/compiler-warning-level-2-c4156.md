---
title: 컴파일러 경고 (수준 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: b9add4af0fddf8d68bbba0293530f2bb0ce3800d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162090"
---
# <a name="compiler-warning-level-2-c4156"></a>컴파일러 경고 (수준 2) C4156

' delete ' 배열 형식을 사용 하지 않고 배열 식을 삭제 합니다. 배열 형식이 대체 되었습니다.

배열 형식이 아닌 **경우에는 배열을 삭제할 수 없습니다** . 컴파일러가 **delete** 배열을 배열 형식으로 변환 했습니다.

이 경고는 Microsoft 확장 (/Ze)에서 발생 합니다.

## <a name="example"></a>예제

```cpp
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```
