---
title: 컴파일러 오류 C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: 8a040e649074e115b1b86ea56db6c9ef48f4c0d0
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520476"
---
# <a name="compiler-error-c3389"></a>컴파일러 오류 C3389

> /clr: pure 또는/clr: safe에는 __declspec (*키워드*)를 사용할 수 없습니다.

## <a name="remarks"></a>설명

**`/clr:pure`** 및 **`/clr:safe`** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

[`__declspec`](../../cpp/declspec.md)사용 되는 한정자는 프로세스별 상태를 의미 합니다.  [`/clr:pure`](../../build/reference/clr-common-language-runtime-compilation.md)는 상태를 나타냅니다 [`appdomain`](../../cpp/appdomain.md) .  따라서 *키워드* 한정자를 사용 하 여 변수를 선언 **`__declspec`** 하 고로 컴파일하는 것은 **`/clr:pure`** 허용 되지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3389를 생성 합니다.

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```
