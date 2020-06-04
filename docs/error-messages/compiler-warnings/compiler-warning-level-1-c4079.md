---
title: 컴파일러 경고 (수준 1) C4079
ms.date: 11/04/2016
f1_keywords:
- C4079
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
ms.openlocfilehash: 29363ba0467d28d7cdfb4d0cb0be504213b1c86d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200299"
---
# <a name="compiler-warning-level-1-c4079"></a>컴파일러 경고 (수준 1) C4079

예기치 않은 'token' 토큰입니다.

Pragma 인수 목록에서 예기치 않은 구분 토큰이 발생 했습니다. Pragma의 나머지가 무시 되었습니다.

다음 샘플에서는 C4079를 생성 합니다.

```cpp
// C4079.cpp
// compile with: /W1
#pragma warning(disable : 4081)
#pragma pack(c,16)   // C4079

int main() {
}
```
