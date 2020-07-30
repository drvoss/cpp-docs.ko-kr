---
title: 컴파일러 오류 C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 023d7f0a5d509c4b301a9985da8ea7feb1f3d203
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228832"
---
# <a name="compiler-error-c3530"></a>컴파일러 오류 C3530

' auto '는 다른 형식 지정자와 함께 사용할 수 없습니다.

형식 지정자는 키워드와 함께 사용 됩니다 **`auto`** .

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 키워드를 사용 하는 변수 선언에는 형식 지정자를 사용 하지 마십시오 **`auto`** .

## <a name="example"></a>예제

다음 예제에서는 C3530가 `x` 키워드와 형식을 모두 사용 하 여 선언 되 **`auto`** **`int`** 고이 예제가 **/zc: auto**를 사용 하 여 컴파일되기 때문에를 생성 합니다.

```cpp
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>참조

[auto 키워드](../../cpp/auto-keyword.md)
