---
title: __asm 블록에서 연산자 사용
ms.date: 08/30/2018
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
ms.openlocfilehash: b6ac9f7174baf1e0ebe41181c6a6f43e7bb3f5d1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169099"
---
# <a name="using-operators-in-__asm-blocks"></a>__asm 블록에서 연산자 사용

**Microsoft 전용**

`__asm` 블록은 **<<** 연산자와 같은 C++ C 또는 특정 연산자를 사용할 수 없습니다. 그러나 \* 연산자와 같이 C 및 MASM에서 공유 하는 연산자는 어셈블리 언어 연산자로 해석 됩니다. 예를 들어 `__asm` 블록 외부에서 대괄호 ( **[]** )는 바깥쪽 배열 첨자로 해석 됩니다. 여기서 C는 배열의 요소 크기를 자동으로 조정 합니다. `__asm` 블록 안에서 MASM 인덱스 연산자로 표시되며, 이 연산자는 임의의 데이터 개체 또는 레이블(배열만이 아님)로부터 크기를 조절하지 않은 바이트 오프셋을 만듭니다. 다음 코드에서는 차이점을 보여 줍니다.

```cpp
int array[10];

__asm mov array[6], bx ;  Store BX at array+6 (not scaled)

array[6] = 0;         /* Store 0 at array+24 (scaled) */
```

`array`에 대한 첫 번째 참조는 크기가 조정되지 않지만 두 번째 참조는 크기가 조정됩니다. **형식** 연산자를 사용 하 여 상수를 기반으로 크기를 조정할 수 있습니다. 예를 들어 다음 두 개의 문은 동일합니다.

```cpp
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24

array[6] = 0;                   /* Store 0 at array + 24 */
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[__asm 블록에서 C 또는 C++ 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
