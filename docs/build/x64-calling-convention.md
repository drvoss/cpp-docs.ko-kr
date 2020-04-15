---
title: x64 호출 규칙
description: 기본 x64 ABI 호출 규칙에 대한 세부 정보입니다.
ms.date: 12/17/2018
ms.assetid: 41ca3554-b2e3-4868-9a84-f1b46e6e21d9
ms.openlocfilehash: caf22172ea5e9c20280bce8e508d72fd30c00c5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335135"
---
# <a name="x64-calling-convention"></a>x64 호출 규칙

이 섹션에서는 한 함수(호출자)가 x64 코드의 다른 함수(호출 수신 자)를 호출하는 데 사용하는 표준 프로세스 및 규칙을 설명합니다.

## <a name="calling-convention-defaults"></a>규칙 호출 기본값

x64 응용 프로그램 바이너리 인터페이스(ABI)는 기본적으로 4개의 레지스터 빠른 호출 규칙을 사용합니다. 콜 스택에 해당 레지스터를 저장하는 callees용 섀도우 저장소로 공간이 할당됩니다. 함수 호출에 대한 인수와 해당 인수에 사용되는 레지스터 사이에는 엄격한 일대일 대응이 있습니다. 8바이트에 맞지 않거나 1, 2, 4 또는 8바이트가 아닌 모든 인수는 참조로 전달되어야 합니다. 단일 인수는 여러 레지스터에 분산되지 않습니다. x87 레지스터 스택은 사용되지 않으며 호출 한 곳에서 사용할 수 있지만 함수 호출 에서 휘발성으로 간주되어야 합니다. 모든 부동 점 작업은 16개의 XMM 레지스터를 사용하여 수행됩니다. 정수 인수는 레지스터 RCX, RDX, R8 및 R9에서 전달됩니다. 부동점 인수는 XMM0L, XMM1L, XMM2L 및 XMM3L로 전달됩니다. 16바이트 인수는 참조로 전달됩니다. 매개 변수 전달은 [매개 변수 전달에](#parameter-passing)자세히 설명되어 있습니다. 이러한 레지스터 외에도 RAX, R10, R11, XMM4 및 XMM5는 휘발성으로 간주됩니다. 다른 모든 레지스터는 비휘발성입니다. 레지스터 사용법은 레지스터 [사용](../build/x64-software-conventions.md#register-usage) 및 [발신자/호출 수신자 저장 레지스터에 자세히 설명되어 있습니다.](#callercallee-saved-registers)

프로토타입 함수의 경우 모든 인수는 전달하기 전에 예상되는 호출 유형으로 변환됩니다. 호출자는 매개 변수에 매개 변수에 대한 공간을 할당해야 하며 호출 수신이 많은 매개 변수를 차지하지 않더라도 항상 4개의 레지스터 매개 변수를 저장할 수 있는 충분한 공간을 할당해야 합니다. 이 규칙은 프로토타입이 없는 C 언어 함수 및 vararg C/C++ 함수에 대한 지원을 간소화합니다. vararg 또는 프로토타입이 없는 함수의 경우 부동 점 값을 해당 범용 레지스터에 복제해야 합니다. 처음 4개 이상의 모든 매개 변수는 호출 전에 섀도 저장소 후 스택에 저장되어야 합니다. 바라그 함수 세부 사항은 [바라그에서](#varargs)찾을 수 있습니다. 프로토타입이 없는 함수 정보는 [프로토타입이 없는 함수에 자세히 설명되어 있습니다.](#unprototyped-functions)

## <a name="alignment"></a>맞춤

대부분의 구조는 자연스러운 정렬에 맞춰 정렬됩니다. 주요 예외는 성능을 향상시키기 `malloc` 위해 `alloca` 16바이트로 정렬되는 스택 포인터 및 메모리입니다. 16바이트 이상의 정렬은 수동으로 수행해야 하지만 16바이트는 XMM 작업의 일반적인 정렬 크기이므로 이 값은 대부분의 코드에서 작동해야 합니다. 구조 레이아웃 및 정렬에 대한 자세한 내용은 [유형 및 저장소](../build/x64-software-conventions.md#types-and-storage)를 참조하십시오. 스택 레이아웃에 대한 자세한 내용은 [x64 스택 사용량을](../build/stack-usage.md)참조하십시오.

## <a name="unwindability"></a>해제 가능성

리프 함수는 비휘발성 레지스터를 변경하지 않는 함수입니다. 리프가 아닌 함수는 예를 들어 함수를 호출하거나 로컬 변수에 추가 스택 공간을 할당하여 비휘발성 RSP를 변경할 수 있습니다. 예외가 처리될 때 비휘발성 레지스터를 복구하려면 임의의 명령에서 함수를 제대로 해제하는 방법을 설명하는 정적 데이터에 비리프 함수에 추가해야 합니다. 이 데이터는 *pdata*또는 프로시저 데이터로 저장되며, 이 데이터는 *xdata,* 예외 처리 데이터를 참조합니다. xdata에는 해제 정보가 포함되어 있으며 추가 pdata 또는 예외 처리기 함수를 가리킬 수 있습니다. 프롤로그와 에필로그는 xdata에서 제대로 설명할 수 있도록 매우 제한됩니다. 스택 포인터는 리프 함수를 제외한 모든 코드 영역에서 16바이트로 정렬되어야 합니다. 리프 함수는 반환을 시뮬레이션하기만 하면 해제될 수 있으므로 pdata 및 xdata가 필요하지 않습니다. 함수 프롤로그 및 에필로그의 적절한 구조에 대한 자세한 내용은 [x64 프롤로그 및 에필로그를](../build/prolog-and-epilog.md)참조하십시오. 예외 처리 및 pdata 및 xdata의 예외 처리 및 해제에 대한 자세한 내용은 [x64 예외 처리를](../build/exception-handling-x64.md)참조하십시오.

## <a name="parameter-passing"></a>매개 변수 전달

처음 네 개의 정수 인수는 레지스터에 전달됩니다. 정수 값은 각각 RCX, RDX, R8 및 R9에서 왼쪽에서 오른쪽 순서로 전달됩니다. 인수 5 이상은 스택에 전달됩니다. 모든 인수는 레지스터에서 올바르게 정당화되므로 예약 자는 레지스터의 위쪽 비트를 무시하고 필요한 레지스터의 일부만 액세스할 수 있습니다.

처음 네 매개 변수의 부동 점 및 이중 정밀도 인수는 위치에 따라 XMM0 - XMM3로 전달됩니다. 정수는 VARARGS 인수의 경우를 제외하고 일반적으로 해당 위치에 사용되는 RCX, RDX, R8 및 R9을 등록합니다. 자세한 내용은 [바라그](#varargs)를 참조하십시오. 마찬가지로 XMM0 - XMM3 레지스터는 해당 인수가 정수 또는 포인터 형식인 경우 무시됩니다.

[__m128](../cpp/m128.md) 형식, 배열 및 문자열은 즉시 값으로 전달되지 않습니다. 대신 호출자에서 할당한 메모리에 포인터가 전달됩니다. 크기 8, 16, 32 또는 64비트 및 __m64 유형의 구조체 및 조합은 동일한 크기의 정수인 것처럼 전달됩니다. 다른 크기의 구조체 또는 공용 구조체는 호출자가 할당한 메모리에 대한 포인터로 전달됩니다. _m128 포함하여 \_포인터로 전달된 이러한 집계 형식의 경우 호출자 할당된 임시 메모리가 16바이트 정렬되어야 합니다.

스택 공간을 할당하지 않고 다른 함수를 호출하지 않는 내장 함수는 다른 휘발성 레지스터를 사용하여 추가 레지스터 인수를 전달하는 경우가 있습니다. 이러한 최적화는 컴파일러와 내장 함수 구현 간의 긴밀한 바인딩을 통해 가능합니다.

필요한 경우 레지스터 매개 변수를 그림자 공간에 덤프하는 경우 를 사용합니다.

다음 표에는 매개 변수가 전달되는 방법을 요약합니다.

|매개 변수 형식|통과 방법|
|--------------------|----------------|
|부동 소수점|처음 4개의 파라미터 - XMM0에서 XMM3까지. 다른 스택에 전달.|
|정수|처음 4 매개 변수 - RCX, RDX, R8, R9. 다른 스택에 전달.|
|집계(8, 16, 32 또는 64비트) 및 __m64|처음 4 매개 변수 - RCX, RDX, R8, R9. 다른 스택에 전달.|
|집계(기타)|포인터로. RCX, RDX, R8 및 R9에서 포인터로 전달된 처음 4개의 매개 변수|
|__m128|포인터로. RCX, RDX, R8 및 R9에서 포인터로 전달된 처음 4개의 매개 변수|

### <a name="example-of-argument-passing-1---all-integers"></a>인수 전달 1의 예 - 모든 정수

```cpp
func1(int a, int b, int c, int d, int e);
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack
```

### <a name="example-of-argument-passing-2---all-floats"></a>인수 전달 2의 예 - 모든 부동

```cpp
func2(float a, double b, float c, double d, float e);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack
```

### <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>인수 전달 의 예 3 - 혼합 int및 수레

```cpp
func3(int a, double b, int c, float d);
// a in RCX, b in XMM1, c in R8, d in XMM3
```

### <a name="example-of-argument-passing-4--__m64-__m128-and-aggregates"></a>4 -__m64, \__m128 및 집계를 전달하는 인수의 예

```cpp
func4(__m64 a, _m128 b, struct c, float d);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3
```

## <a name="varargs"></a>Varargs

매개 변수가 varargs(예: 타원 인수)를 통해 전달되는 경우 다섯 번째 및 후속 인수를 스택에 유출하는 것을 포함하여 일반 레지스터 매개 변수 전달 규칙이 적용됩니다. 주소가 있는 인수를 덤프하는 것은 callee의 책임입니다. 부동 점 값의 경우 정수 레지스터와 부동 점 레지스터 모두 값을 포함해야 합니다.

## <a name="unprototyped-functions"></a>프로토타입화되지 않은 함수

완전히 프로토타입화되지 않은 함수의 경우 호출자는 정수 값과 부동 점 값을 이중 정밀도로 전달합니다. 부동 점 값의 경우 정수 레지스터와 부동 점 레지스터 모두 float 값을 포함합니다.

```cpp
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="return-values"></a>반환 값

64비트에 맞을 수 있는 스칼라 반환 값은 RAX를 통해 반환됩니다. 여기에는 __m64 유형이 포함됩니다. 부동 부동, 배 및 [__m128,](../cpp/m128.md) [__m128i,](../cpp/m128i.md) [__m128d](../cpp/m128d.md) 같은 벡터 형식을 포함한 비 스칼라 유형은 XMM0으로 반환됩니다. RAX 또는 XMM0에 반환되는 값에서 사용되지 않는 비트의 상태는 정의되지 않습니다.

사용자 정의 형식은 전역 함수 및 정적 멤버 함수 값으로 반환될 수 있습니다. RAX에서 사용자 정의 형식을 값별로 반환하려면 길이가 1, 2, 4, 8, 16, 32 또는 64비트여야 합니다. 또한 사용자 정의 생성자, 소멸자 또는 복사 할당 연산자가 없어야 합니다. 개인 또는 보호된 비정적 데이터 멤버없음; 참조 형식의 비정적 데이터 멤버가 없습니다. 기본 클래스가 없습니다. 가상 함수없음; 이러한 요구 사항을 충족하지 않는 데이터 멤버가 없습니다. 이것은 기본적으로 C++03 POD 형식의 정의입니다. C++11 표준에서 정의가 변경되었므로 이 테스트에는 `std::is_pod` 사용하지 않는 것이 좋습니다. 그렇지 않으면 호출자는 메모리를 할당하고 반환 값에 대한 포인터를 첫 번째 인수로 전달하는 책임을 집니다. 그런 다음 후속 인수가 오른쪽으로 하나씩 이동됩니다. RAX에서 호출 수신자에 의해 동일한 포인터가 반환되어야 합니다.

이러한 예에서는 지정된 선언을 사용하여 함수에 대해 매개 변수 및 반환 값이 전달되는 방식을 보여 줍니다.

### <a name="example-of-return-value-1---64-bit-result"></a>반환 값 1 - 64비트 결과의 예

```Output
__int64 func1(int a, float b, int c, int d, int e);
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,
// callee returns __int64 result in RAX.
```

### <a name="example-of-return-value-2---128-bit-result"></a>반환 값 2 - 128비트 결과의 예

```Output
__m128 func2(float a, double b, int c, __m64 d);
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,
// callee returns __m128 result in XMM0.
```

### <a name="example-of-return-value-3---user-type-result-by-pointer"></a>반환 값 3의 예 - 포인터에 의한 사용자 유형 결과

```Output
struct Struct1 {
   int j, k, l;    // Struct1 exceeds 64 bits.
};
Struct1 func3(int a, double b, int c, float d);
// Caller allocates memory for Struct1 returned and passes pointer in RCX,
// a in RDX, b in XMM2, c in R9, d pushed on the stack;
// callee returns pointer to Struct1 result in RAX.
```

### <a name="example-of-return-value-4---user-type-result-by-value"></a>반환 값 4의 예 - 값별 사용자 유형 결과

```Output
struct Struct2 {
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.
};
Struct2 func4(int a, double b, int c, float d);
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;
// callee returns Struct2 result by value in RAX.
```

## <a name="callercallee-saved-registers"></a>발신자/전화 통화 저장 레지스터

레지스터 RAX, RCX, RDX, R8, R9, R10, R11, XMM0-5 및 YMM0-15 및 ZMM0-15의 상부는 휘발성으로 간주되며 기능 호출시 파괴된 것으로 간주되어야 합니다(전체 프로그램 최적화와 같은 분석에 의해 안전이 입증되지 않는 한). AVX512VL에서 ZMM, YMM 및 XMM 레지스터 16-31은 휘발성입니다.

레지스터 RBX, RBP, RDI, RSI, RSP, R12, R13, R14, R15 및 XMM6-15는 비휘발성으로 간주되며 이를 사용하는 함수에 의해 저장및 복원되어야 합니다.

## <a name="function-pointers"></a>함수 포인터

함수 포인터는 단순히 각 함수의 레이블에 대한 포인터입니다. 함수 포인터에 대한 목치(TOC) 요구 사항은 없습니다.

## <a name="floating-point-support-for-older-code"></a>이전 코드에 대한 부동 지점 지원

MMX 및 플로팅 포인트 스택 레지스터(MM0-MM7/ST0-ST7)는 컨텍스트 스위치에서 유지됩니다. 이러한 레지스터에 대한 명시적 호출 규칙은 없습니다. 이러한 레지스터의 사용은 커널 모드 코드에서 엄격하게 금지됩니다.

## <a name="fpcsr"></a>FpCsr

레지스터 상태는 또한 x87 FPU 제어 단어를 포함한다. 호출 규칙에 따라 이 레지스터는 비휘발성으로 지정됩니다.

x87 FPU 제어 워드 레지스터는 프로그램 실행 시작 시 다음과 같은 표준 값으로 설정됩니다.

| 비트\[등록] | 설정 |
|-|-|
| FPCSR\[0:6] | 예외 마스크 모두 1의 (모든 예외 마스크) |
| FPCSR\[7] | 예약 - 0 |
| FPCSR\[8:9] | 정밀 도조 - 10B(이중 정밀도) |
| FPCSR\[10:11] | 반올림 컨트롤 - 0 (가장 가까운 라운드) |
| FPCSR\[12] | 무한대 제어 - 0 (사용되지 않음) |

FPCSR 내의 필드를 수정하는 호출 수신자는 호출자에게 반환하기 전에 해당 필드를 복원해야 합니다. 또한 이러한 필드를 수정한 호출자는 동의에 따라 수정된 값을 기대하지 않는 한 호출 을 호출하기 전에 해당 필드를 표준 값으로 복원해야 합니다.

컨트롤 플래그의 비변동성에 대한 규칙에는 두 가지 예외가 있습니다.

1. 주어진 함수의 문서화된 목적이 비휘발성 FpCr 플래그를 수정하는 함수에서

1. 이러한 규칙을 위반하면 전체 프로그램 분석을 통해 이러한 규칙을 위반하지 않는 프로그램과 동일하게 작동되는 프로그램이 생성됩니다.

## <a name="mxcsr"></a>MxCsr

레지스터 상태에는 MCXR도 포함됩니다. 호출 규칙은 이 레지스터를 휘발성 부분과 비휘발성 부분으로 나눕니다. 휘발성 부분은 MXCSR\[0:5]의 6개 상태 플래그로 구성되며, 나머지 레지스터인\[MXCSR 6:15는 비휘발성으로 간주됩니다.

비휘발성 부분은 프로그램 실행 시작 시 다음과 같은 표준 값으로 설정됩니다.

| 비트\[등록] | 설정 |
|-|-|
| MXCSR\[6] | 비정상은 영점 - 0 |
| MXCSR\[7:12] | 예외 마스크 모두 1의 (모든 예외 마스크) |
| MXCSR\[13:14] | 반올림 컨트롤 - 0 (가장 가까운 라운드) |
| MXCSR\[15] | 마스크 된 언더 플로우의 경우 0으로 플러시 - 0 (꺼져 있음) |

MXCSR 내의 비휘발성 필드를 수정하는 호출 수신자는 호출자에게 반환하기 전에 복원해야 합니다. 또한 이러한 필드를 수정한 호출자는 동의에 따라 수정된 값을 기대하지 않는 한 호출 을 호출하기 전에 해당 필드를 표준 값으로 복원해야 합니다.

컨트롤 플래그의 비변동성에 대한 규칙에는 두 가지 예외가 있습니다.

- 주어진 함수의 문서화된 목적이 비휘발성 MxCsr 플래그를 수정하는 함수에서

- 이러한 규칙을 위반하면 전체 프로그램 분석을 통해 이러한 규칙을 위반하지 않는 프로그램과 동일하게 작동되는 프로그램이 생성됩니다.

함수 설명서에 구체적으로 설명하지 않는 한 함수 경계에서 MXCSR의 휘발성 부분의 상태에 대해 가정할 수 없습니다.

## <a name="setjmplongjmp"></a>세짓프/롱지프

setjmpex.h 또는 setjmp.h를 포함하는 경우 [setjmp](../c-runtime-library/reference/setjmp.md) 또는 [longjmp에](../c-runtime-library/reference/longjmp.md) 대한 모든 호출은 소멸자 `__finally` 및 호출을 호출하는 해제를 초래합니다.  이는 setjmp.h를 포함하여 `__finally` 절과 소멸자가 호출되지 않는 x86과 다릅니다.

현재 스택 `setjmp` 포인터, 비휘발성 레지스터 및 McXCr 레지스터를 보존하기 위한 호출입니다.  가장 `longjmp` 최근 `setjmp` 호출 사이트로 돌아가서 스택 포인터, 비휘발성 레지스터 및 McxCr 레지스터를 재설정하여 가장 최근 `setjmp` 호출에 의해 보존된 상태로 다시 호출합니다.

## <a name="see-also"></a>참고 항목

[x64 소프트웨어 규칙](../build/x64-software-conventions.md)
