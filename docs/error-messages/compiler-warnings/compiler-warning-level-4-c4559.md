---
title: 컴파일러 경고(수준 4) C4559
ms.date: 08/27/2018
f1_keywords:
- C4559
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
ms.openlocfilehash: 0788824dd4180476d81d9682f99fb95883b8c4f0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198343"
---
# <a name="compiler-warning-level-4-c4559"></a>컴파일러 경고(수준 4) C4559

> '*function*': 재정의 함수는 __declspec (*한정자*)를 향상 시킵니다.

## <a name="remarks"></a>주의

함수가 다시 정의 되거나 다시 선언 되었고 두 번째 정의 또는 선언에 **__declspec** 한정자 (*한정자*)가 추가 되었습니다. 이 경고는 정보 제공용입니다. 이 경고를 해결 하려면 정의 중 하나를 삭제 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4559를 생성 합니다.

```cpp
// C4559.cpp
// compile with: /W4 /LD
void f();
__declspec(noalias) void f();   // C4559
```
