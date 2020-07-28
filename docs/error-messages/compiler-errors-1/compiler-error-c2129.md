---
title: 컴파일러 오류 C2129
ms.date: 11/04/2016
f1_keywords:
- C2129
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
ms.openlocfilehash: 9cf414200dcfad8ae617e16e111bd26b19a315a6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220433"
---
# <a name="compiler-error-c2129"></a>컴파일러 오류 C2129

' function ' 정적 함수가 선언 되었지만 정의 되지 않았습니다.

정의 되지 않은 함수에 대해 전방 참조가 생성 됩니다 **`static`** .

**`static`** 함수는 파일 범위 내에서 정의 되어야 합니다. 함수가 다른 파일에 정의 되어 있는 경우에는 선언 해야 **`extern`** 합니다.
