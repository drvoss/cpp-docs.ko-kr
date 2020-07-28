---
title: 어셈블리 언어 설명
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: 2e993bd48c7ec801abd440676c80a5bd8f7b42ec
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192732"
---
# <a name="assembly-language-comments"></a>어셈블리 언어 설명

**Microsoft 전용**

블록의 명령은 **`__asm`** 어셈블리 언어 주석을 사용할 수 있습니다.

```cpp
__asm mov ax, offset buff ; Load address of buff
```

C 매크로가 단일 논리 줄로 확장되기 때문에 매크로에서 어셈블리 언어 주석을 사용하지 마십시오. ( [C 매크로로 __Asm 블록 정의](../../assembler/inline/defining-asm-blocks-as-c-macros.md)를 참조 하세요.) 블록에는 **`__asm`** c 스타일 주석이 포함 될 수도 있습니다. 자세한 내용은 [__asm 블록에서 c 또는 c + + 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)을 참조 하세요.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[__Asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
