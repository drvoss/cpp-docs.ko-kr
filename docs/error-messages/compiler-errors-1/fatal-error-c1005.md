---
title: 심각한 오류 C1005
ms.date: 11/04/2016
f1_keywords:
- C1005
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
ms.openlocfilehash: a8b0fe71dcfb6253327de247d24ef9d90c59181d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204869"
---
# <a name="fatal-error-c1005"></a>심각한 오류 C1005

버퍼에 비해 문자열이 너무 깁니다.

컴파일러 중간 파일의 문자열에서 버퍼를 오버플로했습니다.

[/Fd](../../build/reference/fd-program-database-file-name.md) 또는 [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) 컴파일러 옵션으로 전달한 매개 변수가 256바이트보다 큰 경우 이 오류가 표시될 수 있습니다.
