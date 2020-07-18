---
title: 컴파일러 경고(수준 1) C4293
description: MSVC 컴파일러 경고 C4293의 원인을 설명 하 고이 문제를 해결 하는 방법을 보여 줍니다.
ms.date: 07/15/2020
f1_keywords:
- C4293
helpviewer_keywords:
- C4293
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
ms.openlocfilehash: 3b5a05d4a744b084f1cc34210a5374962064e85d
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446478"
---
# <a name="compiler-warning-level-1-c4293"></a>컴파일러 경고(수준 1) C4293

> '*operator*': 시프트 횟수가 음수 이거나 너무 큽니다. 정의 되지 않은 동작입니다.

시프트 횟수가 음수 이거나 너무 크면 결과 이미지의 동작이 정의 되지 않습니다.

## <a name="remarks"></a>설명

이 문제를 해결 하려면 첫 번째 피연산자에 대 한 캐스트를 사용 하 여 결과 형식의 크기로 확장할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4293를 생성 하 고 수정 하는 방법을 보여 줍니다.

```cpp
// C4293.cpp
// compile with: /c /W1
unsigned __int64 combine (unsigned lo, unsigned hi)
{
   return (hi << 32) | lo;   // C4293

   // In C, try the following line instead:
   // return ( (unsigned __int64)hi << 32) | lo;
   // In C++, try this line instead:
   // return (static_cast<unsigned __int64>(hi) << 32) | lo;
}
```
