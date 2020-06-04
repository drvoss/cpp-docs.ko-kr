---
title: 컴파일러 오류 C2129
ms.date: 11/04/2016
f1_keywords:
- C2129
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
ms.openlocfilehash: a3e2268bfc5597668e8689d093a0c2bb7f18e037
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207287"
---
# <a name="compiler-error-c2129"></a>컴파일러 오류 C2129

' function ' 정적 함수가 선언 되었지만 정의 되지 않았습니다.

정의 되지 않은 `static` 함수에 대 한 전방 참조가 생성 됩니다.

파일 범위 내에서 `static` 함수를 정의 해야 합니다. 함수가 다른 파일에 정의 되어 있으면 `extern`선언 되어야 합니다.
