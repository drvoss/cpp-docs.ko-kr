---
title: 컴파일러 오류 C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: 97f3290ef8bcb6a91442effdbf84261c03545ce2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87209528"
---
# <a name="compiler-error-c2218"></a>컴파일러 오류 C2218

> '__vectorcall'은 '/arch:IA32'와 함께 사용할 수 없습니다.

**`__vectorcall`** 호출 규칙은 SSE2 (스트리밍 SIMD 확장 2) 이상을 포함 하는 x86 및 x64 프로세서의 네이티브 코드 에서만 지원 됩니다. 자세한 내용은 [`__vectorcall`](../../cpp/vectorcall.md)를 참조하세요.

이 오류를 해결하려면 컴파일러 옵션을 대상 SSE2, AVX 또는 AVX2 명령 집합으로 변경합니다. 자세한 내용은 [ `/arch` (x86)](../../build/reference/arch-x86.md)를 참조 하세요.
