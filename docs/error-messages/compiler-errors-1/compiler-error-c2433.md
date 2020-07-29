---
title: 컴파일러 오류 C2433
ms.date: 11/04/2016
f1_keywords:
- C2433
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
ms.openlocfilehash: f8cd8d5c165b796dff5260e84a505356f2a74941
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216221"
---
# <a name="compiler-error-c2433"></a>컴파일러 오류 C2433

' identifier ': ' modifier '는 데이터 선언에 사용할 수 없습니다.

**`friend`** **`virtual`** **`inline`** 데이터 선언에는, 및 한정자를 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2433를 생성 합니다.

```cpp
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```
