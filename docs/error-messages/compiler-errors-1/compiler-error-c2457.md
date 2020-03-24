---
title: 컴파일러 오류 C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: 40e666b1f2b566ca6309ee7759452647f8101a38
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205246"
---
# <a name="compiler-error-c2457"></a>컴파일러 오류 C2457

> '*macro*': 미리 정의 된 매크로는 함수 본문 외부에 나타날 수 없습니다.

전역 공간에서 [ &#95; &#95;함수&#95;](../../preprocessor/predefined-macros.md)등의 미리 정의 된 매크로를 사용 하려고 했습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2457를 생성 하 고 올바른 사용법도 보여 줍니다.

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```
