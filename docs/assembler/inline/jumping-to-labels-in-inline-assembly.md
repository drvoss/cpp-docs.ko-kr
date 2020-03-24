---
title: 인라인 어셈블리에서 레이블로 점프
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembly, jumping to labels
- labels, in inline assembly
- __asm keyword [C++], labels
- case sensitivity, labels in inline assembly
- labels, in __asm blocks
- jumping to labels in inline assembly
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
ms.openlocfilehash: 199156a08af13f4a70793609b37c70b0c95bf9ba
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169333"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>인라인 어셈블리에서 레이블로 점프

**Microsoft 전용**

일반 C 또는 C++ 레이블처럼 `__asm` 블록 레이블의 범위는 블록에만 있는 것이 아니라 해당 레이블이 정의된 함수 전체에 있습니다. 어셈블리 명령 및 `goto` 문 모두 `__asm` 블록 안이나 밖의 레이블로 이동할 수 있습니다.

`__asm` 블록에 정의된 레이블은 대/소문자를 구분하지 않으며, `goto` 문과 어셈블리 명령 모두 대/소문자와 상관없이 이러한 레이블을 참조할 수 있습니다. C 및 C++ 레이블은 `goto` 문에서 사용되는 경우에만 대/소문자를 구분합니다. 어셈블리 명령은 대/소문자에 관계없이 C 또는 C++ 레이블로 이동할 수 있습니다.

다음 코드에는 모든 순열이 나와 있습니다.

```cpp
void func( void )
{
   goto C_Dest;  /* Legal: correct case   */
   goto c_dest;  /* Error: incorrect case */

   goto A_Dest;  /* Legal: correct case   */
   goto a_dest;  /* Legal: incorrect case */

   __asm
   {
      jmp C_Dest ; Legal: correct case
      jmp c_dest ; Legal: incorrect case

      jmp A_Dest ; Legal: correct case
      jmp a_dest ; Legal: incorrect case

      a_dest:    ; __asm label
   }

   C_Dest:       /* C label */
   return;
}
int main()
{
}
```

C 라이브러리 함수 이름을 `__asm` 블록의 레이블로 사용하지 마십시오. 예를 들어 `exit`를 다음과 같이 레이블로 사용하려 할 경우,

```cpp
; BAD TECHNIQUE: using library function name as label
   jne exit
   .
   .
   .
exit:
   ; More __asm code follows
```

**Exit** 는 C 라이브러리 함수의 이름이 기 때문에이 코드로 인해 원하는 위치가 아닌 **종료** 함수로 이동할 수 있습니다.

MASM 프로그램에서 달러 기호(`$`)는 현재 위치 카운터의 역할을 합니다. 이는 현재 어셈블리 되고 있는 명령에 대한 레이블로서 `__asm` 블록에서 긴 조건 점프를 만드는 데 주로 사용됩니다.

```cpp
   jne $+5 ; next instruction is 5 bytes long
   jmp farlabel ; $+5
   .
   .
   .
farlabel:
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[인라인 어셈블러](../../assembler/inline/inline-assembler.md)<br/>
