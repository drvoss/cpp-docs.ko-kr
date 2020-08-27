---
title: 컴파일러 오류 C2705
description: Microsoft C/c + + 컴파일러 오류 C2705에 대해 설명 합니다.
ms.date: 08/25/2020
f1_keywords:
- C2705
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
ms.openlocfilehash: 40d0f70ee379f5d1347b7443817713a53e097f89
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898743"
---
# <a name="compiler-error-c2705"></a>컴파일러 오류 C2705

> '*label*': ' exception handler block ' 범위로 잘못 점프 했습니다.

## <a name="remarks"></a>설명

실행은 **`try`** / **`catch`** , 또는 블록 내의 레이블로 이동 **`__try`** / **`__except`** **`__try`** / **`__finally`** 합니다. 컴파일러는이 동작을 허용 하지 않습니다. 자세한 내용은 [예외 처리](../../cpp/exception-handling-in-visual-cpp.md)를 참조 하세요.

## <a name="example"></a>예

다음 샘플에서는 C2705를 생성 합니다.

```cpp
// C2705.cpp
int main() {
goto trouble;
   __try {
      trouble: ;   // C2705
   }
   __finally {}

   // try the following line instead
   // trouble: ;
}
```
