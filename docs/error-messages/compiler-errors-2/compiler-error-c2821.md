---
title: 컴파일러 오류 C2821
ms.date: 11/04/2016
f1_keywords:
- C2821
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
ms.openlocfilehash: d099c4a0f6e1ea77a25213e3873b8a0814e28dcd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201997"
---
# <a name="compiler-error-c2821"></a>컴파일러 오류 C2821

' operator n e w '의 첫 번째 정식 매개 변수는 ' unsigned i n t ' 여야 합니다.

[New 연산자](../../standard-library/new-operators.md#op_new) 의 첫 번째 정식 매개 변수는 unsigned `int`이어야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2821를 생성 합니다.

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```
