---
title: 컴파일러 경고(수준 1) C4180
ms.date: 11/04/2016
f1_keywords:
- C4180
helpviewer_keywords:
- C4180
ms.assetid: 40c91bd4-37f1-4d59-a4f3-d5ddab68239b
ms.openlocfilehash: f542951424325db727fc6d4ba7ac449095bdac83
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175963"
---
# <a name="compiler-warning-level-1-c4180"></a>컴파일러 경고(수준 1) C4180

함수 형식에 적용되는 한정자가 의미가 없으므로 무시됩니다.

**const**와 같은 한정자가 `typedef`로 정의된 함수 형식에 적용되었습니다.

## <a name="example"></a>예제

```cpp
// C4180.cpp
// compile with: /W1 /c
typedef int FuncType(void);

// the const qualifier cannot be applied to the
// function type FuncType
const FuncType f;   // C4180
```
