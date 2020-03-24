---
title: 컴파일러 오류 C2415
ms.date: 11/04/2016
f1_keywords:
- C2415
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
ms.openlocfilehash: a0cdd528eca8ea267c62e6d44752d29ae16830c4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205623"
---
# <a name="compiler-error-c2415"></a>컴파일러 오류 C2415

피연산자 형식이 잘못 되었습니다.

Opcode는이 형식의 피연산자를 사용 하지 않습니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. Opcode는 사용 되는 피연산자 수를 지원 하지 않습니다. 어셈블리 언어 참조 설명서를 확인 하 여 올바른 피연산자 수를 확인 합니다.

1. 최신 프로세서는 추가 형식으로 명령을 지원 합니다. 최신 프로세서를 사용 하도록 [/arch (최소 CPU 아키텍처)](../../build/reference/arch-minimum-cpu-architecture.md) 옵션을 조정 합니다.
