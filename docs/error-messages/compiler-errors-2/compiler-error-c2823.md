---
title: 컴파일러 오류 C2823
ms.date: 11/04/2016
f1_keywords:
- C2823
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
ms.openlocfilehash: c277437bdc4622e7ae8a63eb9b0a553e0079bc02
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225386"
---
# <a name="compiler-error-c2823"></a>컴파일러 오류 C2823

> typedef 템플릿이 잘못 되었습니다.

템플릿은 정의에서 허용 되지 않습니다 **`typedef`** .

## <a name="example"></a>예제

다음 샘플에서는 C2823를 생성 하 고이를 해결 하는 한 가지 방법을 보여 줍니다.

```cpp
// C2823.cpp
template<class T>
typedef struct x {
   T i;   // C2823 can't use T, specify data type and delete template
   int i;   // OK
} x1;
```
