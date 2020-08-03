---
title: x64 호출 규칙
description: 기본 x64 호출 규칙의 세부 정보입니다.
ms.date: 07/06/2020
ms.assetid: 41ca3554-b2e3-4868-9a84-f1b46e6e21d9
ms.openlocfilehash: b615d2e4473fed1d090b7411211c08b0b824bc8f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87200857"
---
# <a name="x64-calling-convention"></a>x64 호출 규칙

이 섹션에서는 x64 코드에서 한 함수(호출자)가 다른 함수 (호출 수신자)를 호출하는 데 사용하는 표준 프로세스 및 규칙에 대해 설명합니다.

## <a name="calling-convention-defaults"></a>호출 규칙 기본값

x64 ABI(애플리케이션 이진 인터페이스)는 기본적으로 4레지스터 빠른 호출 규칙을 사용합니다. 공백은 호출 스택에서 호출 수신자가 해당 레지스터를 저장하는 섀도 저장소로 할당됩니다.

함수 호출의 인수와 해당 인수에 사용되는 레지스터 사이에는 엄격한 일대일 대응이 있습니다. 8바이트에 맞지 않거나 1, 2, 4 또는 8바이트가 아닌 인수는 참조로 전달되어야 합니다. 단일 인수는 여러 레지스터에 분산되지 않습니다.

x87 레지스터 스택이 사용되지 않습니다. 이 클래스는 호출 수신자가 사용할 수 있지만 함수 호출에서 휘발성으로 간주합니다. 모든 부동 소수점 연산은 16개의 XMM 레지스터를 사용하여 수행됩니다.

정수 인수는 레지스터 RCX, RDX, R8 및 R9에서 전달됩니다. 부동 소수점 인수는 XMM0L, XMM1L, XMM2L 및 XMM3L에서 전달됩니다. 16바이트 인수는 참조로 전달됩니다. 매개 변수 전달은 [매개 변수 전달](#parameter-passing)에 자세히 설명되어 있습니다. 해당 레지스터 외에 RAX, R10, R11, XMM4 및 XMM5는 휘발성으로 간주합니다. 레지스터 사용은 [레지스터 사용](../build/x64-software-conventions.md#register-usage) 및 [호출자/호출 수신자 저장 레지스터](#callercallee-saved-registers)에 자세히 설명되어 있습니다.

프로토타입화된 함수의 경우 모든 인수가 예상된 호출 수신자 형식으로 변환된 후 전달됩니다. 호출자는 호출 수신자에 매개 변수 공간을 할당하는 작업을 담당합니다. 호출자는 호출 수신자가 많은 매개 변수를 사용하지 않는 경우에도 4개의 레지스터 매개 변수를 저장할 수 있는 충분한 공간을 언제나 할당해야 합니다. 이 규칙은 프로토타입화되지 않은 C 언어 함수 및 vararg C/C++ 함수에 대한 지원을 간소화합니다. Vararg 또는 프로토타입화되지 않은 함수의 경우 모든 부동 소수점 값은 해당하는 범용 레지스터에서 중복되어야 합니다. 처음 4개를 초과하는 매개 변수는 호출 전에 섀도 저장소 뒤의 스택에 저장되어야 합니다. Vararg 함수 세부 정보는 [Varargs](#varargs)에서 찾을 수 있습니다. 프로토타입화되지 않은 함수 정보는 [프로토타입화되지 않은 함수](#unprototyped-functions)에 자세히 설명되어 있습니다.

## <a name="alignment"></a>맞춤

대부분의 구조체는 해당 자연 맞춤에 맞춥니다. 기본 예외는 스택 포인터와 `malloc` 또는 `alloca` 메모리로, 성능을 지원하기 위해 16바이트로 맞춥니다. 16바이트 이상의 맞춤은 수동으로 수행해야 합니다. 16바이트는 XMM 작업의 일반적인 맞춤 크기이므로 대부분의 코드에서 이 값이 유효합니다. 구조체 레이아웃 및 맞춤에 대한 자세한 내용은 [형식 및 스토리지](../build/x64-software-conventions.md#types-and-storage)를 참조하세요. 스택 레이아웃에 대한 자세한 내용은 [x64 스택 사용](../build/stack-usage.md)을 참조하세요.

## <a name="unwindability"></a>해제 가능성

리프 함수는 비휘발성 레지스터를 변경하지 않는 함수입니다. 리프가 아닌 함수는 함수를 호출하여 비휘발성 RSP를 변경할 수 있습니다. 또는 로컬 변수용 추가 스택 공간을 할당하여 RSP를 변경할 수 있습니다. 예외가 처리될 때 비휘발성 레지스터를 복구하려면 정적 데이터로 리프가 아닌 함수에 주석을 추가해야 합니다. 데이터는 임의 명령에서 함수를 적절하게 해제하는 방법을 설명합니다. 이 데이터는 *pdata* 또는 프로시저 데이터로 저장됩니다. 이 데이터는 *xdata*, 즉 예외 처리 데이터를 참조합니다. xdata는 해제 정보를 포함하며 추가 pdata 또는 예외 처리기 함수를 가리킬 수 있습니다.

프롤로그 및 에필로그는 xdata에서 적절하게 설명할 수 있도록 매우 제한적입니다. 스택 포인터는 리프 함수 내부를 제외하고 에필로그 또는 프롤로그의 일부가 아닌 코드 영역에서 16바이트로 맞춰져 있어야 합니다. 리프 함수는 단순히 반환을 시뮬레이션하여 해제할 수 있으므로 pdata 및 xdata는 필요하지 않습니다. 함수 프롤로그 및 에필로그의 적절한 구조체에 대한 자세한 내용은 [x64 프롤로그 및 에필로그](../build/prolog-and-epilog.md)를 참조하세요. 예외 처리와 pdata/xdata의 예외 처리 및 해제에 대한 자세한 내용은 [x64 예외 처리](../build/exception-handling-x64.md)를 참조하세요.

## <a name="parameter-passing"></a>매개 변수 전달

기본적으로 x64 호출 규칙은 처음 네 개의 인수를 레지스터의 함수에 전달합니다. 해당 인수에 사용되는 레지스터는 인수의 위치와 형식에 따라 달라집니다. 나머지 인수는 오른쪽에서 왼쪽으로 스택에서 푸시됩니다.

가장 왼쪽 네 개 위치의 정수 값 인수는 왼쪽에서 오른쪽으로 각각 RCX, RDX, R8 및 R9에서 전달됩니다. 앞에서 설명한 대로 다섯 번째 이상의 인수가 스택에서 전달됩니다. 레지스터의 모든 정수 인수는 오른쪽에 맞춥니다. 따라서 호출 수신자는 레지스터의 상위 비트를 무시하고 필요한 레지스터 부분만 액세스할 수 있습니다.

처음 4개 매개 변수의 부동 소수점 및 배정밀도 인수는 위치에 따라 XMM0-XMM3에서 전달됩니다. 부동 소수점 값은 varargs 인수가 있는 경우 정수 레지스터 RCX, RDX, R8 및 R9에만 배치됩니다. 자세한 내용은 [Varargs](#varargs)를 참조하세요. 마찬가지로 XMM0-XMM3 레지스터는 해당 인수가 정수 또는 포인터 형식일 때 무시됩니다.

[`__m128`](../cpp/m128.md) 형식, 배열 및 문자열은 즉시 실행 값에 의해 전달되지 않습니다. 대신, 호출자가 할당한 메모리에 포인터가 전달됩니다. 크기 8, 16, 32 또는 64비트의 구조체 및 공용 구조체와 **`__m64`** 형식은 동일한 크기의 정수인 것처럼 전달됩니다. 다른 크기의 구조체 또는 공용 구조체는 호출자가 할당한 메모리에 대한 포인터로 전달됩니다. **`__m128`** 을 포함하여 포인터로 전달된 이 집계 형식의 경우 호출자가 할당하는 임시 메모리는 16바이트 맞춤이어야 합니다.

스택 공간을 할당하지 않고 다른 함수를 호출하지 않는 내장 함수는 다른 휘발성 레지스터를 사용하여 추가 레지스터 인수를 전달하는 경우도 있습니다. 이 최적화는 컴파일러와 내장 함수 구현 간의 긴밀한 바인딩 때문에 가능합니다.

호출 수신자는 필요한 경우 레지스터 매개 변수를 섀도 공간에 덤프해야 합니다.

다음 표에는 왼쪽에서 형식 및 위치별로 매개 변수를 전달하는 방법이 요약되어 있습니다.

| 매개 변수 유형 | 다섯 번째 이상 | 네 번째 | 세 번째 | second | 가장 왼쪽 |
|-|-|-|-|-|-|
| 부동 소수점 | 스택 | XMM3 | XMM2 | XMM1 | XMM0 |
| integer | 스택 | R9 | R8 | RDX | RCX |
| 집계(8, 16, 32 또는 64비트) 및 **`__m64`** | 스택 | R9 | R8 | RDX | RCX |
| 기타 집계, 포인터로 | 스택 | R9 | R8 | RDX | RCX |
| **`__m128`** , 포인터로 | 스택 | R9 | R8 | RDX | RCX |

### <a name="example-of-argument-passing-1---all-integers"></a>인수 전달 예제 1 - 모두 정수

```cpp
func1(int a, int b, int c, int d, int e, int f);
// a in RCX, b in RDX, c in R8, d in R9, f then e pushed on stack
```

### <a name="example-of-argument-passing-2---all-floats"></a>인수 전달 예제 2 - 모두 부동

```cpp
func2(float a, double b, float c, double d, float e, float f);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, f then e pushed on stack
```

### <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>인수 전달 예제 3 - 정수 및 부동 혼합

```cpp
func3(int a, double b, int c, float d, int e, float f);
// a in RCX, b in XMM1, c in R8, d in XMM3, f then e pushed on stack
```

### <a name="example-of-argument-passing-4---__m64-__m128-and-aggregates"></a>인수 전달 예제 4 - `__m64`, `__m128` 및 집계

```cpp
func4(__m64 a, __m128 b, struct c, float d, __m128 e, __m128 f);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3,
// ptr to f pushed on stack, then ptr to e pushed on stack
```

## <a name="varargs"></a>Varargs

Varargs를 통해 매개 변수를 전달하는 경우(예: 줄임표 인수) 일반 레지스터 매개 변수 전달 규칙이 적용됩니다. 해당 규칙에는 스택에 다섯 번째 이상 인수를 분산하는 작업이 포함됩니다. 해당 주소를 사용하는 인수를 덤프하는 것은 호출 수신자의 책임입니다. 부동 소수점 값에 대해서만, 호출 수신자가 정수 레지스터의 값을 필요로 하는 경우 정수 레지스터와 부동 소수점 레지스터 모두에 값이 포함되어야 합니다.

## <a name="unprototyped-functions"></a>프로토타입화되지 않은 함수

완전히 프로토타입화되지 않은 함수의 경우 호출자는 정수 값은 정수로, 부동 소수점 값은 배정밀도로 전달합니다. 부동 소수점 값에 대해서만, 호출 수신자가 정수 레지스터의 값을 필요로 하는 경우 정수 레지스터와 부동 소수점 레지스터 모두에 부동 값이 포함됩니다.

```cpp
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="return-values"></a>반환 값

**`__m64`** 형식을 포함하여 64비트에 맞출 수 있는 스칼라 반환 값은 RAX를 통해 반환됩니다. float, double 및 벡터 형식(예: [`__m128`](../cpp/m128.md), [`__m128i`](../cpp/m128i.md), [`__m128d`](../cpp/m128d.md))을 포함하는 스칼라 이외의 형식은 XMM0에 반환됩니다. RAX 또는 XMM0에 반환되는 값에서 사용되지 않는 비트의 상태는 정의되지 않습니다.

사용자 정의 형식은 전역 함수 및 정적 멤버 함수 값으로 반환될 수 있습니다. 사용자 정의 형식을 RAX 값으로 반환하려면 길이가 1, 2, 4, 8, 16, 32 또는 64비트여야 합니다. 또한 사용자 정의 생성자, 소멸자 또는 복사 대입 연산자가 없어야 합니다. 프라이빗 또는 보호된 비정적 데이터 멤버와 참조 형식의 비정적 데이터 멤버를 포함할 수 없습니다. 기본 클래스 또는 가상 함수를 포함할 수 없습니다. 또한 해당 요구 사항을 충족하는 데이터 멤버만 포함할 수 있습니다. 이 정의는 기본적으로 C++03 POD 형식과 동일합니다. C++11 표준에서 이 정의가 변경되었으므로 이 테스트에는 `std::is_pod`를 사용하지 않는 것이 좋습니다. 그러지 않으면 호출자는 반환 값용으로 메모리를 할당하고 이에 대한 포인터를 첫 번째 인수에 전달해야 합니다. 그런 다음, 나머지 인수가 오른쪽으로 하나씩 이동됩니다. RAX에서 호출 수신자에 의해 동일한 포인터가 반환되어야 합니다.

이러한 예에서는 지정된 선언을 사용하여 함수에 대해 매개 변수 및 반환 값이 전달되는 방식을 보여 줍니다.

### <a name="example-of-return-value-1---64-bit-result"></a>반환 값 예제 1 – 64비트 결과

```Output
__int64 func1(int a, float b, int c, int d, int e);
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,
// callee returns __int64 result in RAX.
```

### <a name="example-of-return-value-2---128-bit-result"></a>반환 값 예제 2 – 128비트 결과

```Output
__m128 func2(float a, double b, int c, __m64 d);
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,
// callee returns __m128 result in XMM0.
```

### <a name="example-of-return-value-3---user-type-result-by-pointer"></a>반환 값 예제 3 – 포인터별 사용자 형식 결과

```Output
struct Struct1 {
   int j, k, l;    // Struct1 exceeds 64 bits.
};
Struct1 func3(int a, double b, int c, float d);
// Caller allocates memory for Struct1 returned and passes pointer in RCX,
// a in RDX, b in XMM2, c in R9, d pushed on the stack;
// callee returns pointer to Struct1 result in RAX.
```

### <a name="example-of-return-value-4---user-type-result-by-value"></a>반환 값 예제 4 – 값별 사용자 형식 결과

```Output
struct Struct2 {
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.
};
Struct2 func4(int a, double b, int c, float d);
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;
// callee returns Struct2 result by value in RAX.
```

## <a name="callercallee-saved-registers"></a>호출자/호출 수신자 저장 레지스터

x64 ABI는 레지스터 RAX, RCX, RDX, R8, R9, R10, R11 및 XMM0-XMM5를 휘발성으로 간주합니다. 있는 경우 YMM0-YMM15 및 ZMM0-ZMM15의 상위 부분도 휘발성입니다. AVX512VL에서 ZMM, YMM 및 XMM 레지스터 16-31도 휘발성입니다. 전체 프로그램 최적화와 같은 분석으로 안전성을 입증할 수 없는 경우 휘발성 레지스터는 함수 호출 시 소멸된 것으로 간주합니다.

x64 ABI는 레지스터 RBX, RBP, RDI, RSI, RSP, R12, R13, R14, R15 및 XMM6-XMM15를 비휘발성으로 간주합니다. 해당 레지스터는 레지스터를 사용하는 함수를 통해 저장 및 복원해야 합니다.

## <a name="function-pointers"></a>함수 포인터

함수 포인터는 단순히 해당 함수의 레이블에 대한 포인터입니다. 함수 포인터에 대한 TOC(목차) 요구 사항이 없습니다.

## <a name="floating-point-support-for-older-code"></a>이전 코드를 위한 부동 소수점 지원

MMX 및 부동 소수점 스택 레지스터(MM0-MM7/ST0-ST7)는 컨텍스트 전환 간에 유지됩니다. 해당 레지스터에 대한 명시적 호출 규칙은 없습니다. 이러한 레지스터는 커널 모드 코드에서 사용이 엄격하게 금지됩니다.

## <a name="fpcsr"></a>FPCSR

레지스터 상태에는 x87 FPU 제어 단어도 포함됩니다. 호출 규칙은 이 레지스터를 비휘발성으로 지시합니다.

x87 FPU 제어 단어 레지스터는 프로그램 실행이 시작될 때 다음 표준 값을 사용하여 설정됩니다.

| Register\[bits] | 설정 |
|-|-|
| FPCSR\[0:6] | 예외는 모든 1을 마스킹(모든 예외가 마스킹됨) |
| FPCSR\[7] | 예약됨 - 0 |
| FPCSR\[8:9] | 정밀도 제어 - 10B(배정밀도) |
| FPCSR\[10:11] | 반올림 제어 - 0(가장 가까운 수로 반올림) |
| FPCSR\[12] | 무한대 제어 - 0(사용 안 함) |

FPCSR 내의 필드를 수정하는 호출 수신자는 호출자에게 반환하기 전에 해당 필드를 복원해야 합니다. 또한 호출 수신자에 수정된 값이 필요한 경우를 제외하고는 해당 필드를 수정한 호출자가 호출 수신자를 호출하기 전에 해당 필드를 표준 값으로 복원해야 합니다.

제어 플래그의 비휘발성에 대한 규칙에는 두 가지 예외가 있습니다.

- 지정된 함수의 문서화된 목적이 비휘발성 FPCSR 플래그를 수정하는 함수인 경우

- 해당 규칙을 위반하는 프로그램이 규칙을 위반하지 않는 프로그램과 동일하게 동작함이 전체 프로그램 분석 등을 통해 입증 가능한 경우

## <a name="mxcsr"></a>MXCSR

레지스터 상태에는 MXCSR도 포함됩니다. 호출 규칙은 이 레지스터를 휘발성 부분과 비휘발성 부분으로 나눕니다. 휘발성 부분은 MXCSR\[0:5]의 6가지 상태 플래그로 구성되며, MXCSR\[6:15]의 나머지 부분은 비휘발성으로 간주됩니다.

비휘발성 부분은 프로그램 실행이 시작될 때 다음 표준 값으로 설정됩니다.

| Register\[bits] | 설정 |
|-|-|
| MXCSR\[6] | Denormal이 0 - 0 |
| MXCSR\[7:12] | 예외는 모든 1을 마스킹(모든 예외가 마스킹됨) |
| MXCSR\[13:14] | 반올림 제어 - 0(가장 가까운 수로 반올림) |
| MXCSR\[15] | 마스킹된 언더플로의 경우 0으로 플러시 - 0(해제) |

MXCSR 내의 비휘발성 필드를 수정하는 호출 수신자는 호출자에게 반환하기 전에 해당 필드를 복원해야 합니다. 또한 호출 수신자에 수정된 값이 필요한 경우를 제외하고는 해당 필드를 수정한 호출자가 호출 수신자를 호출하기 전에 해당 필드를 표준 값으로 복원해야 합니다.

제어 플래그의 비휘발성에 대한 규칙에는 두 가지 예외가 있습니다.

- 지정된 함수의 문서화된 목적이 비휘발성 MXCSR 플래그를 수정하는 함수인 경우

- 해당 규칙을 위반하는 프로그램이 규칙을 위반하지 않는 프로그램과 동일하게 동작함이 전체 프로그램 분석 등을 통해 입증 가능한 경우

함수 설명서에서 명시적으로 설명하지 않는 한 함수 경계 간에 MXCSR 레지스터의 휘발성 부분 상태를 가정하지 않습니다.

## <a name="setjmplongjmp"></a>setjmp/longjmp

setjmpex.h 또는 setjmp.h를 포함하는 경우 [`setjmp`](../c-runtime-library/reference/setjmp.md) 또는 [`longjmp`](../c-runtime-library/reference/longjmp.md)에 대한 모든 호출에서 소멸자 및 **`__finally`** 호출을 호출하는 해제가 발생합니다.  이 동작은 x86과 다릅니다. x86에서는 setjmp.h를 포함하는 경우 **`__finally`** 절과 소멸자가 호출되지 않습니다.

`setjmp` 호출은 현재 스택 포인터, 비휘발성 레지스터 및 MXCSR 레지스터를 유지합니다.  `longjmp` 호출은 가장 최근의 `setjmp` 호출 사이트로 돌아가 스택 포인터, 비휘발성 레지스터 및 MXCSR 레지스터를 가장 최근의 `setjmp` 호출에 의해 유지된 상태로 다시 설정합니다.

## <a name="see-also"></a>참조

[x64 소프트웨어 규칙](../build/x64-software-conventions.md)
