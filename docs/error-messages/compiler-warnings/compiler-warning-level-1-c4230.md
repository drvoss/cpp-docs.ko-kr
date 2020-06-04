---
title: 컴파일러 경고(수준 1) C4230
ms.date: 11/04/2016
f1_keywords:
- C4230
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
ms.openlocfilehash: be402eed4474dd736ab237cfb5c7986741338eec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163273"
---
# <a name="compiler-warning-level-1-c4230"></a>컴파일러 경고(수준 1) C4230

오래 사용: 한정자/한정자가 섞여 있습니다. 한정자 무시 됨

`__cdecl`와 같은 Microsoft 한정자 앞에 한정자를 사용 하는 것은 오래 된 습관입니다.

## <a name="example"></a>예제

```cpp
// C4230.cpp
// compile with: /W1 /LD
int __cdecl const function1();   // C4230 const ignored
```
