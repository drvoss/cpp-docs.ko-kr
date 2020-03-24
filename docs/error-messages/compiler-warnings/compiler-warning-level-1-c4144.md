---
title: 컴파일러 경고 (수준 1) C4144
ms.date: 11/04/2016
f1_keywords:
- C4144
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
ms.openlocfilehash: 99902edee371704c57a772e1b62f7ec4f41afb36
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163691"
---
# <a name="compiler-warning-level-1-c4144"></a>컴파일러 경고 (수준 1) C4144

' expression ': 관계식을 switch 식으로 변환 합니다.

지정 된 관계형 식이 [switch](../../cpp/switch-statement-cpp.md) 문의 제어 식으로 사용 되었습니다. 연결 된 case 문에는 부울 값이 제공 됩니다. 다음 샘플에서는 C4144를 생성 합니다.

```cpp
// C4144.cpp
// compile with: /W1
int main()
{
   int i = 0;
   switch(!i) {   // C4144, remove the ! to resolve
      case 1:
         break;
      default:
         break;
   }
}
```
