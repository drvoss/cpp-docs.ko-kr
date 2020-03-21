---
title: x64 호출 규칙
description: 기본 x64 ABI 호출 규칙의 세부 정보입니다.
ms.date: 12/17/2018
ms.assetid: 41ca3554-b2e3-4868-9a84-f1b46e6e21d9
ms.openlocfilehash: 5b9801eff6a9789313d083fdd6ed69c3076643ad
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078077"
---
# <a name="x64-calling-convention"></a>x64 호출 규칙

이 섹션에서는 x64 코드에서 한 함수 (호출자)가 다른 함수 (호출 수신자)를 호출 하는 데 사용 하는 표준 프로세스 및 규칙에 대해 설명 합니다.

## <a name="calling-convention-defaults"></a>규칙 기본값 호출

X64 ABI (응용 프로그램 이진 인터페이스)는 기본적으로 4 레지스터 빠른 호출 규칙을 사용 합니다. 공백은 호출 스택에 해당 레지스터를 저장 하는 호출 스택에 대 한 섀도 저장소로 할당 됩니다. 함수 호출에 대 한 인수와 이러한 인수에 사용 되는 레지스터 사이에는 엄격한 일대일 대응이 있습니다. 8 바이트에 맞지 않거나 1, 2, 4 또는 8 바이트가 아닌 인수는 참조로 전달 되어야 합니다. 단일 인수는 여러 레지스터에 분산 되지 않습니다. X87 등록 스택은 사용 되지 않으며, 호출 수신자가 사용할 수 있지만 함수 호출에서 volatile로 간주 되어야 합니다. 모든 부동 소수점 연산은 16 개의 XMM 레지스터를 사용 하 여 수행 됩니다. 정수 인수는 레지스터 RCX, RDX, R8 및 R 9에 전달 됩니다. 부동 소수점 인수는 XMM0L, XMM1L, XMM2L 및 XMM3L에 전달 됩니다. 16 바이트 인수는 참조로 전달 됩니다. 매개 변수 전달은 [매개 변수 전달](#parameter-passing)에 자세히 설명 되어 있습니다. 이러한 레지스터 외에도 RAX, R10, R 11, XMM4 및 ~ XMM5는 volatile로 간주 됩니다. 다른 모든 레지스터는 volatile이 아닙니다. [사용법 등록 및](../build/x64-software-conventions.md#register-usage) [호출자/호출 수신자 저장 레지스터](#callercallee-saved-registers)에 자세히 설명 되어 있습니다.

프로토타입화된 함수의 경우 모든 인수는 전달되기 전에 필요한 호출 수신자 형식으로 변환됩니다. 호출자는 호출 수신자에 게 매개 변수의 공간을 할당 하는 일을 담당 하며, 호출 수신자가 많은 매개 변수를 사용 하지 않는 경우에도 네 개의 레지스터 매개 변수를 저장할 수 있는 충분 한 공간을 할당 해야 합니다. 이 규칙은 프로토타입화 되지 않은 C 언어 함수 및 vararg C/C++ 함수에 대 한 지원을 간소화 합니다. Vararg 또는 프로토타입화 되지 않은 함수의 경우 부동 소수점 값은 해당 하는 범용 레지스터에서 중복 되어야 합니다. 처음 4 개를 초과 하는 매개 변수는 호출 전에 섀도 저장소 뒤에 스택에 저장 되어야 합니다. Vararg 함수 정보는 [Varargs](#varargs)에서 찾을 수 있습니다. 프로토타입화 되지 않은 함수 정보는 [프로토타입화](#unprototyped-functions)되지 않은 함수에 자세히 설명 되어 있습니다.

## <a name="alignment"></a>맞춤

대부분의 구조는 자연 맞춤에 맞춰 정렬 됩니다. 기본 예외는 스택 포인터와 `malloc` 또는 `alloca` 메모리 이며, 성능을 지원 하기 위해 16 바이트로 정렬 됩니다. 16 바이트 이상의 맞춤은 수동으로 수행 해야 하지만 16 바이트는 XMM 작업의 일반적인 맞춤 크기 이므로 대부분의 코드에 대해이 값이 작동 해야 합니다. 구조 레이아웃 및 정렬에 대 한 자세한 내용은 [형식 및 저장소](../build/x64-software-conventions.md#types-and-storage)를 참조 하세요. 스택 레이아웃에 대 한 자세한 내용은 [x64 stack usage](../build/stack-usage.md)를 참조 하세요.

## <a name="unwindability"></a>Unwindability

리프 함수는 volatile이 아닌 레지스터를 변경 하지 않는 함수입니다. 비-리프 함수는 함수를 호출 하거나 지역 변수에 추가 스택 공간을 할당 하는 등 비휘발성 RSP를 변경할 수 있습니다. 예외가 처리 될 때 비휘발성 레지스터를 복구 하려면 임의 명령에서 함수를 적절 하 게 해제 하는 방법을 설명 하는 정적 데이터로 리프가 아닌 함수에 주석을 추가 해야 합니다. 이 데이터는 *.pdata*또는 프로시저 데이터로 저장 되며,이는 *.xdata*, 예외 처리 데이터를 나타냅니다. .Xdata에는 해제 정보가 포함 되며 추가 .pdata 또는 예외 처리기 함수를 가리킬 수 있습니다. Prologs 및 에필로그는 .xdata에서 적절 하 게 설명할 수 있도록 매우 제한적입니다. 스택 포인터는 리프 함수를 제외 하 고 에필로그 또는 프롤로그의 일부가 아닌 코드 영역의 16 바이트에 정렬 되어야 합니다. 단순히 반환을 시뮬레이션 하 여 리프 함수를 해제할 수 있으므로 .pdata 및 .xdata는 필요 하지 않습니다. 함수 프롤로그 및 에필로그의 적절 한 구조에 대 한 자세한 내용은 [x64 프롤로그 및 에필로그](../build/prolog-and-epilog.md)를 참조 하세요. 예외 처리에 대 한 자세한 내용과 .pdata 및 .xdata의 예외 처리 및 해제에 대 한 자세한 내용은 [x64 예외 처리](../build/exception-handling-x64.md)를 참조 하세요.

## <a name="parameter-passing"></a>매개 변수 전달

처음 네 개의 정수 인수는 레지스터에 전달 됩니다. 정수 값은 각각 RCX, RDX, R8 및 R 9에서 왼쪽에서 오른쪽 순서로 전달 됩니다. 인수 5 이상이 스택에 전달 됩니다. 레지스터의 모든 인수는 오른쪽에 맞춰집니다. 따라서 호출 수신자는 레지스터의 상위 비트를 무시 하 고 필요한 레지스터 부분만 액세스할 수 있습니다.

처음 4 개 매개 변수의 부동 소수점 및 배정밀도 인수는 위치에 따라 XMM0-XMM3에 전달 됩니다. 이러한 위치에 일반적으로 사용 되는 정수 레지스터 RCX, RDX, R8 및 R 9는 varargs 인수의 경우를 제외 하 고는 무시 됩니다. 자세한 내용은 [Varargs](#varargs)를 참조 하십시오. 마찬가지로 XMM0-XMM3 레지스터는 해당 인수가 정수 또는 포인터 형식일 때 무시 됩니다.

[__m128](../cpp/m128.md) 형식, 배열 및 문자열은 즉시 값으로 전달 되지 않습니다. 대신, 호출자가 할당 한 메모리에 포인터가 전달 됩니다. 크기 8, 16, 32 또는 64 비트의 구조체 및 공용 구조체와 __m64 형식은 동일한 크기의 정수인 것 처럼 전달 됩니다. 다른 크기의 구조체 또는 공용 구조체는 호출자가 할당 한 메모리에 대 한 포인터로 전달 됩니다. \__m128를 포함 하 여 포인터로 전달 된 이러한 집계 형식의 경우 호출자가 할당 하는 임시 메모리는 16 바이트 맞춤 이어야 합니다.

스택 공간을 할당 하지 않고 다른 함수를 호출 하지 않는 내장 함수는 다른 일시적 레지스터를 사용 하 여 추가 레지스터 인수를 전달 하는 경우도 있습니다. 이러한 최적화는 컴파일러와 내장 함수 구현 간의 긴밀 한 바인딩 때문에 가능 합니다.

호출 수신자는 필요한 경우 레지스터 매개 변수를 섀도 공간에 덤프 해야 합니다.

다음 표에서는 매개 변수를 전달 하는 방법을 요약 합니다.

|매개 변수 형식|통과 방법|
|--------------------|----------------|
|부동 소수점|처음 4 개 매개 변수-XMM0 ~ XMM3. 스택에서 전달 되는 다른 항목입니다.|
|정수|처음 4 개의 매개 변수-RCX, RDX, R8, R 9. 스택에서 전달 되는 다른 항목입니다.|
|집계 (8, 16, 32 또는 64 비트) 및 __m64|처음 4 개의 매개 변수-RCX, RDX, R8, R 9. 스택에서 전달 되는 다른 항목입니다.|
|집계 (기타)|포인터로 RCX, RDX, R8 및 R 9에서 포인터로 전달 된 처음 4 개의 매개 변수|
|__m128|포인터로 RCX, RDX, R8 및 R 9에서 포인터로 전달 된 처음 4 개의 매개 변수|

### <a name="example-of-argument-passing-1---all-integers"></a>인수 전달 1-모든 정수 예

```cpp
func1(int a, int b, int c, int d, int e);
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack
```

### <a name="example-of-argument-passing-2---all-floats"></a>인수를 전달 하는 예제 2-모든 부동 소수점

```cpp
func2(float a, double b, float c, double d, float e);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack
```

### <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>인수 전달 3의 예-정수 및 부동 소수점 혼합

```cpp
func3(int a, double b, int c, float d);
// a in RCX, b in XMM1, c in R8, d in XMM3
```

### <a name="example-of-argument-passing-4--__m64-__m128-and-aggregates"></a>4 __m64, \__m128 및 집계를 전달 하는 인수의 예

```cpp
func4(__m64 a, _m128 b, struct c, float d);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3
```

## <a name="varargs"></a>Varargs

Varargs를 통해 매개 변수를 전달 하는 경우 (예: 줄임표 인수) 스택에 5 번째 및 후속 인수를 분산 포함 하 여 normal register 매개 변수 전달 규칙이 적용 됩니다. 해당 주소를 사용 하는 인수를 덤프 하는 것은 호출 수신자의 책임입니다. 부동 소수점 값에 대해서만 정수 레지스터와 부동 소수점 레지스터 모두에 값이 포함 되어야 합니다. 단, 호출 수신자가 정수 레지스터의 값을 필요로 하는 경우에 한 합니다.

## <a name="unprototyped-functions"></a>프로토타입화 되지 않은 함수

완전히 프로토타입화 되지 않은 함수의 경우 호출자는 정수 값을 정수 값으로, 부동 소수점 값을 배정밀도로 전달 합니다. 부동 소수점 값에 대해서만 정수 레지스터와 부동 소수점 레지스터 모두에 float 값이 포함 됩니다 .이 경우 호출 수신자에 정수 레지스터의 값이 필요 합니다.

```cpp
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="return-values"></a>반환 값

64 비트에 맞출 수 있는 스칼라 반환 값은 RAX를 통해 반환 됩니다. 여기에는 __m64 형식이 포함 됩니다. Float, double 및 vector 형식 (예: [__m128](../cpp/m128.md), [__m128i](../cpp/m128i.md) [__m128d](../cpp/m128d.md) )을 포함 하는 비 스칼라 형식은 XMM0에서 반환 됩니다. RAX 또는 XMM0에 반환되는 값에서 사용되지 않는 비트의 상태는 정의되지 않습니다.

사용자 정의 형식은 전역 함수 및 정적 멤버 함수 값으로 반환될 수 있습니다. RAX에서 사용자 정의 형식을 값으로 반환 하려면 길이가 1, 2, 4, 8, 16, 32 또는 64 비트 여야 합니다. 또한 사용자 정의 생성자, 소멸자 또는 복사 할당 연산자가 없어야 합니다. 전용 또는 보호 된 비정적 데이터 멤버가 없습니다. 참조 형식의 비정적 데이터 멤버가 없습니다. 기본 클래스 없음 가상 함수 없음 이러한 요구 사항을 충족 하지 않는 데이터 멤버도 없습니다. 이것은 기본적으로 C++03 POD 형식의 정의입니다. 정의는 c + + 11 표준에서 변경 되었으므로이 테스트에 `std::is_pod`을 사용 하지 않는 것이 좋습니다.) 그렇지 않으면 호출자는 메모리를 할당 하 고 반환 값에 대 한 포인터를 첫 번째 인수로 전달 하는 책임을 가정 합니다. 그런 다음 후속 인수가 오른쪽으로 하나씩 이동됩니다. RAX에서 호출 수신자에 의해 동일한 포인터가 반환되어야 합니다.

이러한 예에서는 지정된 선언을 사용하여 함수에 대해 매개 변수 및 반환 값이 전달되는 방식을 보여 줍니다.

### <a name="example-of-return-value-1---64-bit-result"></a>반환 값 1-64 비트 결과의 예

```Output
__int64 func1(int a, float b, int c, int d, int e);
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,
// callee returns __int64 result in RAX.
```

### <a name="example-of-return-value-2---128-bit-result"></a>반환 값 2-128 비트 결과의 예

```Output
__m128 func2(float a, double b, int c, __m64 d);
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,
// callee returns __m128 result in XMM0.
```

### <a name="example-of-return-value-3---user-type-result-by-pointer"></a>반환 값 3의 예-사용자 형식 결과를 포인터로

```Output
struct Struct1 {
   int j, k, l;    // Struct1 exceeds 64 bits.
};
Struct1 func3(int a, double b, int c, float d);
// Caller allocates memory for Struct1 returned and passes pointer in RCX,
// a in RDX, b in XMM2, c in R9, d pushed on the stack;
// callee returns pointer to Struct1 result in RAX.
```

### <a name="example-of-return-value-4---user-type-result-by-value"></a>반환 값 4의 예-값으로 사용자 형식 결과

```Output
struct Struct2 {
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.
};
Struct2 func4(int a, double b, int c, float d);
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;
// callee returns Struct2 result by value in RAX.
```

## <a name="callercallee-saved-registers"></a>호출자/호출 수신자 저장 레지스터

RAX, RCX, RDX, R8, R 9, R10, R 11, XMM0-5의 레지스터와 형식인 경우 YMM0-15 및 ZMM0-15의 위쪽 부분은 volatile로 간주 되므로 함수 호출에 대해 소멸 된 것으로 간주 해야 합니다 (전체 프로그램 최적화와 같은 분석의 안전성 입증 가능한) AVX512VL에서 ZMM, YMM 및 XMM는 16-31을 volatile로 등록 합니다.

레지스터 RBX, RBP, RBP, RBP, RSP, R12, R13, R14, R15 및 XMM6-15는 비휘발성로 간주 되며이를 사용 하는 함수를 사용 하 여 저장 하 고 복원 해야 합니다.

## <a name="function-pointers"></a>함수 포인터

함수 포인터는 각 함수의 레이블에 대한 단순한 포인터입니다. 함수 포인터에 적용되는 TOC(목차) 요구 사항은 없습니다.

## <a name="floating-point-support-for-older-code"></a>이전 코드에 대 한 부동 소수점 지원

MMX와 부동 소수점 스택 레지스터(MM0-MM7/ST0-ST7)는 컨텍스트를 전환해도 유지됩니다. 이러한 레지스터에 대한 명시적인 호출 규칙은 없습니다. 이러한 레지스터는 커널 모드 코드에서만 사용하도록 엄격하게 제한되어 있습니다.

## <a name="fpcsr"></a>FpCsr

등록 상태에는 x87 FPU 제어 단어도 포함 됩니다. 호출 규칙은이 레지스터를 비휘발성로 지시 합니다.

X87 FPU 제어 단어 등록은 프로그램 실행이 시작 될 때 다음 표준 값으로 설정 됩니다.

| \[bits 등록] | 설정 |
|-|-|
| FPCSR\[0:6] | 예외 마스크 모두 1의 (모든 예외는 마스킹 됨) |
| FPCSR\[7] | 예약 됨-0 |
| FPCSR\[8:9] | Precision Control-10B (이중 전체 자릿수) |
| FPCSR\[10:11] | 반올림 제어-0 (가장 가까운 수로 반올림) |
| FPCSR\[12] | 무한대 제어-0 (사용 되지 않음) |

FPCSR 내의 모든 필드를 수정 하는 호출 수신자는 호출자에 게 반환 하기 전에 해당 필드를 복원 해야 합니다. 또한 이러한 필드를 수정한 호출자가 호출 수신자에 게 수정 된 값이 필요한 경우를 제외 하 고는 호출 수신자를 호출 하기 전에 해당 필드를 표준 값으로 복원 해야 합니다.

컨트롤 플래그의 비 변동성에 대 한 규칙에는 두 가지 예외가 있습니다.

1. 지정 된 함수의 문서화 된 목적이 비휘발성 FpCsr 플래그를 수정 하는 함수입니다.

1. 이러한 규칙의 위반으로 인해 프로그램이 전체 프로그램 분석을 통해 위반 되지 않는 프로그램과 동일 하 게 동작 하는 프로그램이 provably 것이 좋습니다.

## <a name="mxcsr"></a>MxCsr

등록 상태는 MxCsr도 포함 합니다. 호출 규칙은이 레지스터를 휘발성 부분과 비휘발성 부분으로 나눕니다. Volatile 부분은 MXCSR\[0:5]의 6 가지 상태 플래그로 구성 되며, MXCSR\[6:15]의 나머지 부분은 비휘발성로 간주 됩니다.

비휘발성 부분은 프로그램 실행이 시작 될 때 다음 표준 값으로 설정 됩니다.

| \[bits 등록] | 설정 |
|-|-|
| MXCSR\[6] | Denormals는 0입니다. |
| MXCSR\[7:12] | 예외 마스크 모두 1의 (모든 예외는 마스킹 됨) |
| MXCSR\[13:14] | 반올림 제어-0 (가장 가까운 수로 반올림) |
| MXCSR\[15] | 마스킹된 언더플로의 경우 0으로 플러시-0 (해제) |

MXCSR 내에서 비휘발성 필드를 수정 하는 호출 수신자는 호출자에 게 반환 하기 전에 해당 필드를 복원 해야 합니다. 또한 이러한 필드를 수정한 호출자가 호출 수신자에 게 수정 된 값이 필요한 경우를 제외 하 고는 호출 수신자를 호출 하기 전에 해당 필드를 표준 값으로 복원 해야 합니다.

컨트롤 플래그의 비 변동성에 대 한 규칙에는 두 가지 예외가 있습니다.

- 지정 된 함수의 문서화 된 목적이 비휘발성 MxCsr 플래그를 수정 하는 함수입니다.

- 이러한 규칙의 위반으로 인해 프로그램이 전체 프로그램 분석을 통해 위반 되지 않는 프로그램과 동일 하 게 동작 하는 프로그램이 provably 것이 좋습니다.

함수 설명서에서 특별히 설명 되지 않은 경우 함수 경계 전체에서 MXCSR의 volatile 부분에 대 한 가정을 만들 수 없습니다.

## <a name="setjmplongjmp"></a>setjmp/longjmp

Setjmpex 또는 setjmp를 포함 하는 경우 [setjmp](../c-runtime-library/reference/setjmp.md) 또는를 호출 하면 소멸자를 호출 하 고 호출을 `__finally` 하는 해제 [가 발생 합니다](../c-runtime-library/reference/longjmp.md) .  이는 x86과 다르며, 여기에서 setjmp를 포함 하면 `__finally` 절과 소멸자가 호출 되지 않습니다.

`setjmp`에 대 한 호출은 현재 스택 포인터, 비휘발성 레지스터 및 MxCsr 레지스터를 유지 합니다.  `longjmp`에 대 한 호출은 가장 최근의 `setjmp` 호출 사이트로 돌아가 스택 포인터, 비휘발성 레지스터 및 MxCsr 레지스터를 가장 최근의 `setjmp` 호출에 의해 유지 된 상태로 다시 설정 합니다.

## <a name="see-also"></a>참고 항목

[x64 소프트웨어 규칙](../build/x64-software-conventions.md)
