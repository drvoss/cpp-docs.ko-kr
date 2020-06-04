---
title: 컴파일러 오류 C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: cec92982646c64e6c5b669df328e4836d4f44df8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202104"
---
# <a name="compiler-error-c2812"></a>컴파일러 오류 C2812

> \#가져오기는/clr: pure 및/clr: safe를 사용 하 여 지원 되지 않습니다.

## <a name="remarks"></a>주의

**/Clr: pure** 및 **/clr: safe** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

[#import 지시문](../../preprocessor/hash-import-directive-cpp.md) 은 `#import` 네이티브 컴파일러 지원 라이브러리를 사용 해야 하므로 **/clr: pure** 및 **/clr: safe** 에서 지원 되지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2812를 생성 합니다.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```
