---
title: 컴파일러 경고 (수준 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: c90ad202e193f21955d396dd2aff6b39d3a968c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174338"
---
# <a name="compiler-warning-level-2-c4094"></a>컴파일러 경고 (수준 2) C4094

태그가 없는 ' token '은 기호를 선언 하지 않았습니다.

컴파일러가 태그가 없는 구조체, 공용 구조체 또는 클래스를 사용 하 여 빈 선언을 검색 했습니다. 선언이 무시 됩니다.

## <a name="example"></a>예제

```cpp
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

이 조건은 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 오류를 생성 합니다.
