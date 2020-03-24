---
title: 컴파일러 경고(수준 1) C4391
ms.date: 11/04/2016
f1_keywords:
- C4391
helpviewer_keywords:
- C4391
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
ms.openlocfilehash: 6dc5e2c7a40a276e225d030bc0340fb0bfe25bb5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162727"
---
# <a name="compiler-warning-level-1-c4391"></a>컴파일러 경고(수준 1) C4391

' signature ': 내장 함수의 반환 형식이 잘못 되었습니다. ' type '이 필요 합니다.

컴파일러 내장 함수 선언에 잘못 된 반환 형식이 있습니다. 결과 이미지가 올바르게 실행 되지 않을 수 있습니다.

이 경고를 해결 하려면 선언을 수정 하거나 선언을 삭제 하 고 단순히 적절 한 헤더 파일을 #include 합니다.

다음 샘플에서는 C4391를 생성 합니다.

```cpp
// C4391.cpp
// compile with: /W1
// processor: x86
// uncomment the following line and delete the line that
// generated the warning to resolve
// #include "xmmintrin.h"

#ifdef  __cplusplus
extern "C" {
#endif

extern void _mm_load_ss(float *p);   // C4391

#ifdef  __cplusplus
}
#endif

int main()
{
}
```
