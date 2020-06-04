---
title: 컴파일러 경고(수준 1) C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: f9478caef9eaba9c72dc282179100daf2d94c6d5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185986"
---
# <a name="compiler-warning-level-1-c4612"></a>컴파일러 경고(수준 1) C4612

> 포함 파일 이름에 오류가 있습니다.

## <a name="remarks"></a>설명

파일 이름이 잘못되었거나 누락된 경우 **#pragma include_alias** 에서 이 경고가 발생합니다.

**#Pragma include_alias** 문에 대 한 인수는 따옴표 형식 ("*파일 이름*") 또는 꺾쇠 괄호 형식 (\<*파일 이름*>)을 사용할 수 있지만 둘 다 동일한 양식을 사용 해야 합니다.

## <a name="example"></a>예제

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```
