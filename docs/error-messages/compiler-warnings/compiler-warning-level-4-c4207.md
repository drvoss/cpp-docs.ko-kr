---
title: 컴파일러 경고(수준 4) C4207
ms.date: 11/04/2016
f1_keywords:
- C4207
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
ms.openlocfilehash: e694f96d7f6271686d1b2a19e5a12e5e08e1cfbe
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219952"
---
# <a name="compiler-warning-level-4-c4207"></a>컴파일러 경고(수준 4) C4207

비표준 확장이 사용 됨: 확장 이니셜라이저 형식입니다.

Microsoft 확장 (/Ze)을 사용 하면 **`char`** 중괄호 안에 문자열을 사용 하 여의 크기 배열 배열을 초기화할 수 있습니다.

## <a name="example"></a>예제

```c
// C4207.c
// compile with: /W4
char c[] = { 'a', 'b', "cdefg" }; // C4207

int main()
{
}
```

이러한 초기화는 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 유효 하지 않습니다.
