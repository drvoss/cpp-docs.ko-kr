---
title: 컴파일러 오류 C3001
ms.date: 11/04/2016
f1_keywords:
- C3001
helpviewer_keywords:
- C3001
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
ms.openlocfilehash: 737754eb314b577ac73e91a5aab1ad31773fc5f3
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302213"
---
# <a name="compiler-error-c3001"></a>컴파일러 오류 C3001

'error_text': OpenMP 지시문 이름이 필요합니다.

`omp` pragma 뒤에 지시문이 와야 합니다.

다음 샘플에서는 C3001을 생성합니다.

```c
// C3001.c
// compile with: /openmp
int main()
{
   #pragma omp   // C3001 missing token
}
```
