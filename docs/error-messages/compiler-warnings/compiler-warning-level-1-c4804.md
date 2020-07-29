---
title: 컴파일러 경고(수준 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: aa2cdf0103a1ccc607f2e4a55e1d8f85bb8cc45d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233225"
---
# <a name="compiler-warning-level-1-c4804"></a>컴파일러 경고(수준 1) C4804

' operation ': 연산에 ' bool ' 형식을 안전 하 게 사용 하지 않습니다.

이 경고는 예기치 않은 방식으로 변수나 값을 사용한 경우에 발생 **`bool`** 합니다. 예를 들어 음의 단항 연산자 ( **-** ) 또는 보수 연산자 ()와 같은 연산자를 사용 하는 경우 C4804이 생성 됩니다 `~` . 컴파일러가 식을 계산 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4804를 생성 합니다.

```cpp
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```
