---
title: 방향 플래그
ms.date: 11/04/2016
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
ms.openlocfilehash: 04e096c6a62f806f4c214745a8401b1730eda3a6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443386"
---
# <a name="direction-flag"></a>방향 플래그

방향 플래그(Direction Flag)는 모든 Intel x86 호환 CPU의 고유한 CPU 플래그입니다. 이 플래그는 MOVS, MOVSD, MOVSW 등과 같은 REP(반복) 접두사를 사용하는 모든 어셈블리 명령에 적용됩니다. 방향 플래그가 0으로 설정되어 있다면 해당되는 어셈블리 명령에 제공되는 주소가 증가합니다.

C 런타임 루틴은 방향 플래그가 지워졌다고 가정합니다. C 런타임 함수와 함께 다른 함수를 사용하는 경우 다른 함수에서 방향 플래그를 그대로 두거나 원래 상태로 복원해야 합니다. 진입시 방향 플래그가 0으로 설정될 것으로 예상하면 보다 빠르고 효율적인 런타임 코드가 생성됩니다.

문자열 조작 및 버퍼 조작 루틴과 같은 C 런타임 라이브러리 함수는 방향 플래그가 명확해야 합니다.

## <a name="see-also"></a>참고 항목

[CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)
