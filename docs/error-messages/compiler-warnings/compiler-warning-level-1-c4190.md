---
title: 컴파일러 경고 (수준 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: 6d110aa70a470382e274546e95599804fa3bc7d6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199877"
---
# <a name="compiler-warning-level-1-c4190"></a>컴파일러 경고 (수준 1) C4190

' identifier1 '에 C 링크를 지정 했으나 C와 호환 되지 않는 UDT ' identifier2 '를 반환 합니다.

함수 또는 함수 포인터는 UDT (사용자 정의 형식, 클래스, 구조체, 열거형 또는 공용 구조체)를 반환 형식으로 사용 하 고 "C" 링크를 `extern` 합니다. 이는 다음과 같은 경우에 유효 합니다.

- 이 함수에 대 한 모든 호출은 C++에서 발생 합니다.

- 함수 정의는에 C++있습니다.

## <a name="example"></a>예제

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```
