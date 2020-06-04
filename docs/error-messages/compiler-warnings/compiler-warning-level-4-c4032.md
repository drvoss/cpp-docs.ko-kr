---
title: 컴파일러 경고 (수준 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: 84bfef28de2899a216616a6a5d9fb15422f2afec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185414"
---
# <a name="compiler-warning-level-4-c4032"></a>컴파일러 경고 (수준 4) C4032

' number ' 형식 매개 변수의 형식이 서로 다릅니다.

매개 변수 형식은 기본 프로 모션을 통해 이전 선언의 형식과 호환 되지 않습니다.

이 오류는 ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md))의 오류 이며 Microsoft 확장 (/ze)에서 경고가 발생 합니다.

## <a name="example"></a>예제

```c
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```
