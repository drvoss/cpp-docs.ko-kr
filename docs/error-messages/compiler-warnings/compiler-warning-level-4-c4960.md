---
title: 컴파일러 경고(수준 4) C4960
ms.date: 11/04/2016
f1_keywords:
- C4960
helpviewer_keywords:
- C4960
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
ms.openlocfilehash: 286d3a1953c6c6badf15b712feac99afafe8b0a7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198122"
---
# <a name="compiler-warning-level-4-c4960"></a>컴파일러 경고(수준 4) C4960

'function'이 너무 커서 프로파일링할 수 없습니다.

[/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)를 사용하는 경우 컴파일러에서 65,535개 명령보다 큰 함수를 포함하는 입력 모듈을 발견했습니다. 이렇게 큰 함수는 프로필 기반 최적화에 사용할 수 없습니다.

이 경고를 해결하려면 함수 크기를 줄입니다.
