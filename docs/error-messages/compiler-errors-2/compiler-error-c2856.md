---
title: 컴파일러 오류 C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: c88610607083ecfaf5f20cd585b479991fa51b44
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201897"
---
# <a name="compiler-error-c2856"></a>컴파일러 오류 C2856

\#pragma hdrstop은 #if 블록 내부에 있을 수 없습니다.

`hdrstop` pragma는 조건부 컴파일 블록의 본문 안에 배치할 수 없습니다.

`#pragma hdrstop` 문을 `#if/#endif` 블록에 포함 되지 않은 영역으로 이동 합니다.
