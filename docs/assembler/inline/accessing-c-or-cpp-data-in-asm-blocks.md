---
title: __asm 블록에서 C 또는 C++ 데이터 액세스
ms.date: 08/30/2018
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
ms.openlocfilehash: b4341f87226118906749dcdb18b9227e68be6a23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318087"
---
# <a name="accessing-c-or-c-data-in-__asm-blocks"></a>__asm 블록에서 C 또는 C++ 데이터 액세스

**마이크로소프트 특정**

인라인 어셈블리를 사용하면 C 또는 C++ 변수를 이름으로 참조할 수 있으므로 매우 편리합니다. `__asm` 블록은 블록이 나타나는 범위에 있는 변수 이름을 비롯한 모든 기호를 참조할 수 있습니다. 예를 들어 C 변수 `var`이 범위에 있는 경우 다음 명령은

```cpp
__asm mov eax, var
```

`var`의 값을 EAX에 저장합니다.

클래스, 구조또는 공용 구조자 멤버에 고유한 `__asm` 이름이 있는 경우 블록은 마침표 **(.** `typedef` ) 연산자 앞에 변수 나 이름을 지정하지 않고 멤버 이름만 사용하여 참조할 수 있습니다. 그러나 멤버 이름이 고유하지 않은 경우에는 마침표 연산자 바로 앞에 변수 또는 `typedef` 이름을 배치해야 합니다. 예를 들어 다음 샘플의 구조체 형식은 `same_name`을 멤버 이름으로 공유합니다.

다음 형식으로 변수를 선언하는 경우

```cpp
struct first_type hal;
struct second_type oat;
```

`same_name`이 고유하지 않기 때문에 `same_name` 멤버에 대한 모든 참조는 변수 이름을 사용해야 합니다. 그러나 `weasel` 멤버에는 고유한 이름이 있으므로 멤버 이름만 사용하여 참조할 수 있습니다.

```cpp
// InlineAssembler_Accessing_C_asm_Blocks.cpp
// processor: x86
#include <stdio.h>
struct first_type
{
   char *weasel;
   int same_name;
};

struct second_type
{
   int wonton;
   long same_name;
};

int main()
{
   struct first_type hal;
   struct second_type oat;

   __asm
   {
      lea ebx, hal
      mov ecx, [ebx]hal.same_name ; Must use 'hal'
      mov esi, [ebx].weasel       ; Can omit 'hal'
   }
   return 0;
}
```

단순히 코딩 편의를 위해 변수 이름을 생략하는 것 입니다. 변수 이름이 있는지 여부에 관계없이 동일한 어셈블리 명령이 생성됩니다.

액세스 제한에 관계없이 C++의 데이터 멤버에 액세스할 수 있습니다. 하지만 멤버 함수를 호출할 수는 없습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[__asm 블록에서 C 또는 C++ 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
