---
title: float_control pragma
description: Float_control pragma 지시문의 사용량과 효과를 설명 합니다. Float_control 지시문은 런타임에 부동 소수점 정확한 의미 체계 및 예외 의미 체계의 상태를 제어 합니다.
ms.date: 11/18/2019
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: 5f907bfeb3f92f788fe951854ddc32accc83ae03
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78166786"
---
# <a name="float_control-pragma"></a>float_control pragma

함수의 부동 소수점 동작을 지정합니다.

## <a name="syntax"></a>구문

> **#pragma float_control**\
> **#pragma float_control (precise,** { **on** | **off** } [ **, push** ] **)** \
> **#pragma float_control (를 제외** 하 고 { **on** | **off** } [ **, push** ] **)** \
> **#pragma float_control (** { **push** | **pop** } **)**

## <a name="options"></a>옵션

**정확한** |  **꺼짐**, **푸시**\
정확한 부동 소수점 의미 체계를 사용 하거나 사용 하지**않도록 (설정) 할지** **여부를 지정**합니다. **/Fp: precise** 컴파일러 옵션의 차이점에 대 한 자세한 내용은 설명 부분을 참조 하세요. 선택적 **푸시** 토큰은 내부 컴파일러 스택에 **float_control** 의 현재 설정을 푸시합니다.

**제외**하 고 | **해제** **시** **푸시**\
부동 소수점 예외 의미 체계를 사용 하거나 사용 하지**않도록 (설정) 할지** **여부를 지정**합니다. 선택적 **푸시** 토큰은 내부 컴파일러 스택에 **float_control** 의 현재 설정을 푸시합니다.

**except** 는 **on**으로 **설정 된 경우** 에만 **on** 으로 설정할 수 있습니다.

**푸시**\
현재 **float_control** 설정을 내부 컴파일러 스택에 푸시합니다.

**pop**\
내부 컴파일러 스택 맨 위에서 **float_control** 설정을 제거 하 고 새 **float_control** 설정 합니다.

## <a name="remarks"></a>설명

**Float_control** pragma는 [/fp](../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션과 동일한 동작을 포함 하지 않습니다. **Float_control** pragma는 부동 소수점 동작의 일부를 제어 합니다. [Fp_contract](../preprocessor/fp-contract.md) 및 [fenv_access](../preprocessor/fenv-access.md) pragma를 조합 하 여 **/fp** 컴파일러 옵션을 다시 만들어야 합니다. 다음 표에서는 각 컴파일러 옵션에 대 한 동일한 pragma 설정을 보여 줍니다.

| | float_control (정확한, \*) | float_control (제외, \*) | fp_contract (\*) | fenv_access (\*) |
|-|-|-|-|-|
| /fp:strict             | on  | on  | 끄기 | on  |
| /fp:precise            | on  | 끄기 | on  | 끄기 |
| /fp:fast               | 끄기 | 끄기 | on  | 끄기 |

즉, 여러 pragma를 조합 하 여 **/fp: fast**, **/fp: precise**, **/fp: strict** 명령줄 옵션을 에뮬레이션 해야 할 수 있습니다.

**Float_control** 를 사용 하 고 부동 소수점 pragma를 **fenv_access** 하는 방법에는 다음과 같은 제한 사항이 있습니다.

- 정확한 의미 체계를 사용 하도록 설정 하는 **경우를** **제외 하 고** 는 **float_control** 만 사용할 수 있습니다. **Float_control** pragma를 사용 하거나 **/fp: precise** 또는 **/fp: strict** 컴파일러 옵션을 사용 하 여 정확한 의미 체계를 사용 하도록 설정할 수 있습니다.

- **Float_control** pragma 또는 **/fp: except** 컴파일러 옵션을 사용 하 여 예외 의미 체계를 사용 하는 경우에는 **float_control** 를 사용 하 여 **정확한** 해제를 설정할 수 없습니다.

- **Float_control** pragma 또는 컴파일러 옵션을 사용 하 여 정확한 의미 체계를 사용 하도록 설정 하지 않으면 **fenv_access** 를 사용 하도록 설정할 수 없습니다.

- **Fenv_access** 사용 하도록 설정 된 경우 **float_control** 를 사용 하 여 **정확한** 기능을 해제할 수 없습니다.

이러한 제한 사항은 일부 부동 소수점 pragma의 순서가 중요 함을 의미 합니다. Pragma를 사용 하 여 빠른 모델에서 엄격한 모델로 이동 하려면 다음 코드를 사용 합니다.

```cpp
#pragma float_control(precise, on)  // enable precise semantics
#pragma fenv_access(on)             // enable environment sensitivity
#pragma float_control(except, on)   // enable exception semantics
#pragma fp_contract(off)            // disable contractions
```

**Float_control** pragma를 사용 하 여 엄격한 모델에서 빠른 모델로 이동 하려면 다음 코드를 사용 합니다.

```cpp
#pragma float_control(except, off)  // disable exception semantics
#pragma fenv_access(off)            // disable environment sensitivity
#pragma float_control(precise, off) // disable precise semantics
#pragma fp_contract(on)             // enable contractions
```

옵션을 지정 하지 않으면 **float_control** 적용 되지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 pragma **float_control**를 사용 하 여 오버플로 부동 소수점 예외를 catch 하는 방법을 보여 줍니다.

```cpp
// pragma_directive_float_control.cpp
// compile with: /EHa
#include <stdio.h>
#include <float.h>

double func( ) {
   return 1.1e75;
}

#pragma float_control (except, on)

int main( ) {
   float u[1];
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);
   if (err != 0)
      printf_s("_controlfp_s failed!\n");

   try  {
      u[0] = func();
      printf_s ("Fail");
      return(1);
   }

   catch (...)  {
      printf_s ("Pass");
      return(0);
   }
}
```

```Output
Pass
```

## <a name="see-also"></a>참고 항목

[Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[fenv_access](../preprocessor/fenv-access.md)\
[fp_contract](../preprocessor/fp-contract.md)
