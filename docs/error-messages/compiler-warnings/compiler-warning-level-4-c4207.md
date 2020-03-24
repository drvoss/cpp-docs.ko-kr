---
title: 컴파일러 경고(수준 4) C4207
ms.date: 11/04/2016
f1_keywords:
- C4207
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
ms.openlocfilehash: 1ff669512f85dfed9bab307c2986e7858285461d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161388"
---
# <a name="compiler-warning-level-4-c4207"></a>컴파일러 경고(수준 4) C4207

비표준 확장이 사용 됨: 확장 이니셜라이저 형식입니다.

Microsoft 확장 (/Ze)을 사용 하면 중괄호 안에 문자열을 사용 하 여 `char`의 크기 배열 배열을 초기화할 수 있습니다.

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
