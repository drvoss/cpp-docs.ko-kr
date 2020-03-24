---
title: 컴파일러 경고(수준 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 77efeae27a67ea844759fd9980801d3daf788e89
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200262"
---
# <a name="compiler-warning-level-1-c4076"></a>컴파일러 경고(수준 1) C4076

> '*type modifier*': '*typename*' 형식과 함께 사용할 수 없습니다.

## <a name="remarks"></a>주의

**부호가** 있거나 **부호가 없는**형식 한정자는 정수가 아닌 형식과 함께 사용할 수 없습니다. *형식 한정자* 는 무시 됩니다.

## <a name="example"></a>예제

다음 샘플에서는 C4076를 생성 합니다. 이 문제를 해결 하려면 **부호 없는** 형식 한정자를 제거 합니다.

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```
