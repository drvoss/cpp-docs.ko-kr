---
title: 컴파일러 오류 C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: eabed85c61eaaa43b0106e0011f0357ece2e1ae1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221174"
---
# <a name="compiler-error-c2505"></a>컴파일러 오류 C2505

' symbol ': ' __declspec (한정자) '은 (는) 전역 개체 또는 정적 데이터 멤버의 선언 또는 정의에만 적용할 수 있습니다.

**`__declspec`** 전역 범위 에서만 사용 하도록 디자인 된 한정자는 함수에서 사용 되었습니다.

자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [process](../../cpp/process.md)를 참조하세요.

다음 샘플에서는 C2505를 생성 합니다.

```cpp
// C2505.cpp
// compile with: /clr

// OK
__declspec(process) int ii;
__declspec(appdomain) int jj;

int main() {
   __declspec(process) int i;   // C2505
   __declspec(appdomain) int j;   // C2505
}
```
