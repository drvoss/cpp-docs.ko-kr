---
title: x64 소프트웨어 규칙
ms.date: 12/17/2018
helpviewer_keywords:
- x64 coding conventions
- Visual C++, x64 calling conventions
ms.assetid: 750f3d97-1706-4840-b2fc-41a007329a08
ms.openlocfilehash: 11d29b6c31ccecfe5b9c51c2f9311213bd4a6732
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865602"
---
# <a name="x64-software-conventions"></a>x64 소프트웨어 규칙

이 섹션에서는 x86 C++ 아키텍처에 대 한 64 비트 확장인 x64의 호출 규칙 방법론에 대해 설명 합니다.

## <a name="overview-of-x64-calling-conventions"></a>X64 호출 규칙 개요

X86과 x 64의 중요 한 두 가지 차이점은 64 비트 주소 지정 기능 및 일반적인 사용을 위한 16 64 비트 레지스터의 플랫 집합입니다. 확장 된 레지스터 집합이 지정 된 경우 x64는 [__fastcall](../cpp/fastcall.md) 호출 규칙 및 RISC 기반 예외 처리 모델을 사용 합니다. `__fastcall` 규칙은 처음 4 개 인수에 레지스터를 사용 하 고 스택 프레임을 사용 하 여 추가 인수를 전달 합니다. 레지스터 사용, 스택 매개 변수, 반환 값 및 스택 해제를 포함 하 여 x64 호출 규칙에 대 한 자세한 내용은 [x64 호출 규칙](x64-calling-convention.md)을 참조 하세요.

## <a name="enable-optimization-for-x64"></a>X64에 최적화 사용

다음 컴파일러 옵션을 사용하면 응용 프로그램을 x64에 대해 최적화할 수 있습니다.

- [/favor(아키텍처에 맞게 최적화)](../build/reference/favor-optimize-for-architecture-specifics.md)

## <a name="types-and-storage"></a>형식 및 저장소

이 단원에서는 x64 아키텍처에 대한 데이터 형식의 저장소와 열거형을 설명합니다.

### <a name="scalar-types"></a>스칼라 형식

모든 맞춤을 사용 하 여 데이터에 액세스할 수 있지만, 성능 손실을 방지 하기 위해 자연 경계 또는 일부 여러 데이터를 정렬 하는 것이 좋습니다. 열거형은 상수 정수 이며 32 비트 정수로 처리 됩니다. 다음 표에서는 다음 맞춤 값을 사용 하 여 맞춤과 관련 된 데이터의 형식 정의와 권장 저장소에 대해 설명 합니다.

- 바이트-8 비트

- Word-16 비트

- 더블 워드-32 비트

- 쿼드 워드-64 비트

- Octaword-128 비트

|||||
|-|-|-|-|
|스칼라 형식|C 데이터 형식|저장소 크기 (바이트)|권장 맞춤|
|**INT8**|**char**|[1,1]|Byte|
|**UINT8**|**unsigned char**|[1,1]|Byte|
|**INT16**|**short**|2|단어|
|**UINT16**|**unsigned short**|2|단어|
|**INT32**|**int**, **long**|4|더블|
|**UINT32**|**unsigned int, unsigned long**|4|더블|
|**푸시하고**|**__int64**|8|워드|
|**작아**|**unsigned __int64**|8|워드|
|**FP32 (단일 전체 자릿수)**|**float**|4|더블|
|**FP64 (배정밀도)**|**double**|8|워드|
|**놓고**|__\*__|8|워드|
|**__m64**|**구조체 __m64**|8|워드|
|**__m128**|**구조체 __m128**|16|Octaword|

### <a name="aggregates-and-unions"></a>집계 및 공용 구조체

배열, 구조체 및 공용 구조체와 같은 다른 형식에는 일관성 있는 집계 및 공용 구조체 저장소 및 데이터 검색을 보장 하는 보다 엄격한 맞춤 요구 사항이 있습니다. 배열, 구조체 및 공용 구조체에 대 한 정의는 다음과 같습니다.

- 배열

   인접 한 데이터 개체의 정렬 된 그룹을 포함 합니다. 각 개체를 *요소*라고 합니다. 배열 내의 모든 요소는 크기와 데이터 형식이 동일 합니다.

- 구조체

   데이터 개체의 정렬 된 그룹을 포함 합니다. 배열의 요소와 달리 구조 내의 데이터 개체는 서로 다른 데이터 형식 및 크기를 가질 수 있습니다. 구조체의 각 데이터 개체를 *멤버*라고 합니다.

- Union

   명명 된 멤버 집합 중 하나를 보유 하는 개체입니다. 명명 된 집합의 멤버는 모든 형식일 수 있습니다. 공용 구조체에 대해 할당 된 저장소는 해당 공용 구조체의 가장 큰 멤버에 필요한 저장소와 맞춤에 필요한 안쪽 여백에 해당 합니다.

다음 표에서는 공용 구조체 및 구조체의 스칼라 멤버에 대해 권장 되는 맞춤을 보여 줍니다.

||||
|-|-|-|
|스칼라 형식|C 데이터 형식|필요한 맞춤|
|**INT8**|**char**|Byte|
|**UINT8**|**unsigned char**|Byte|
|**INT16**|**short**|단어|
|**UINT16**|**unsigned short**|단어|
|**INT32**|**int**, **long**|더블|
|**UINT32**|**unsigned int, unsigned long**|더블|
|**푸시하고**|**__int64**|워드|
|**작아**|**unsigned __int64**|워드|
|**FP32 (단일 전체 자릿수)**|**float**|더블|
|**FP64 (배정밀도)**|**double**|워드|
|**놓고**|<strong>\*</strong>|워드|
|**__m64**|**구조체 __m64**|워드|
|**__m128**|**구조체 __m128**|Octaword|

다음 집계 정렬 규칙이 적용 됩니다.

- 배열의 맞춤은 배열 요소 중 하나의 정렬과 동일 합니다.

- 구조체의 시작 부분이 나 합집합은 개별 멤버의 최대 맞춤입니다. 구조체 또는 공용 구조체 내의 각 멤버는 이전 테이블에 정의 된 적절 한 맞춤에 배치 해야 합니다 .이는 이전 멤버에 따라 암시적 내부 안쪽 여백이 필요할 수 있습니다.

- 구조 크기는 마지막 멤버 뒤의 안쪽 여백이 필요할 수 있는 해당 맞춤의 정수 배수 여야 합니다. 구조체와 공용 구조체를 배열로 그룹화 할 수 있으므로 구조체 또는 공용 구조체의 각 배열 요소는 이전에 결정 된 적절 한 맞춤에서 시작 하 고 끝나야 합니다.

- 이전 규칙이 유지 되는 한 맞춤 요구 사항 보다 더 큰 데이터를 정렬 하는 것이 가능 합니다.

- 개별 컴파일러는 크기의 이유로 구조의 압축을 조정할 수 있습니다. 예를 들어 [/zp (구조체 멤버 맞춤)](../build/reference/zp-struct-member-alignment.md) 를 사용 하면 구조체 압축을 조정할 수 있습니다.

### <a name="examples-of-structure-alignment"></a>구조체 맞춤 예제

다음 네 개의 예제에서는 각각 정렬된 구조체 또는 공용 구조체를 선언하고 관련된 그림에서는 메모리에 있는 해당 구조체 또는 공용 구조체의 레이아웃을 보여 줍니다. 그림의 각 열은 메모리의 바이트를 나타내고 열의 숫자는 해당 바이트의 치환을 나타냅니다. 각 그림의 두 번째 행에 있는 이름은 선언에 있는 변수의 이름에 해당합니다. 회색으로 표시된 열은 지정된 맞춤을 달성하기 위해 필요한 여백입니다.

#### <a name="example-1"></a>예제 1

```C
// Total size = 2 bytes, alignment = 2 bytes (word).

_declspec(align(2)) struct {
    short a;      // +0; size = 2 bytes
}
```

![AMD 변환 예제 1 구조 레이아웃](../build/media/vcamd_conv_ex_1_block.png "AMD 변환 예제 1 구조 레이아웃")

#### <a name="example-2"></a>예제 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![AMD 변환 예제 2 구조 레이아웃](../build/media/vcamd_conv_ex_2_block.png "AMD 변환 예제 2 구조 레이아웃")

#### <a name="example-3"></a>예제 3

```C
// Total size = 12 bytes, alignment = 4 bytes (doubleword).

_declspec(align(4)) struct {
    char a;       // +0; size = 1 byte
    short b;      // +2; size = 2 bytes
    char c;       // +4; size = 1 byte
    int d;        // +8; size = 4 bytes
}
```

![AMD 변환 예제 2 구조 레이아웃](../build/media/vcamd_conv_ex_3_block.png "AMD 변환 예제 2 구조 레이아웃")

#### <a name="example-4"></a>예제 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![AMD 변환 예제 4 union layouit](../build/media/vcamd_conv_ex_4_block.png "AMD 변환 예제 4 union layouit")

### <a name="bitfields"></a>비트 필드

구조체 비트 필드는 64 비트로 제한 되며, 부호 있는 int, unsigned int, int64 또는 unsigned int64 형식일 수 있습니다. 형식 경계를 교차 하는 비트 필드는 비트 필드를 다음 형식 맞춤에 맞추는 비트를 건너뜁니다. 예를 들어 정수 비트 필드는 32 비트 boundry를 넘지 않을 수 있습니다.

### <a name="conflicts-with-the-x86-compiler"></a>X86 컴파일러와 충돌

4바이트보다 큰 데이터 형식은 x86 컴파일러를 사용하여 응용 프로그램을 컴파일할 때 자동으로 스택에 정렬되지 않습니다. x86 컴파일러의 아키텍처는 4바이트 정렬된 스택이기 때문에 4바이트보다 큰 정수(예: 64비트 정수)는 8바이트 주소에 자동으로 정렬할 수 없습니다.

정렬되지 않은 데이터로 작업하는 데는 두 가지 의미가 있습니다.

- 정렬된 위치에 액세스하는 데 걸리는 시간보다 정렬되지 않은 위치에 액세스하는 데 시간이 오래 걸릴 수 있습니다.

- 정렬되지 않은 위치는 연동된 작업에 사용할 수 없습니다.

보다 엄격한 맞춤이 필요한 경우 변수 선언에 `__declspec(align(N))`를 사용 합니다. 이렇게 하면 컴파일러가 사양에 맞게 스택을 동적으로 정렬하게 됩니다. 그러나 스택을 런타임에 동적으로 조정하면 응용 프로그램의 실행 속도가 느려질 수 있습니다.

## <a name="register-usage"></a>사용 등록

X64 아키텍처는 16 개의 범용 레지스터 (정수 레지스터 라고도 함) 뿐만 아니라 부동 소수점 사용에 사용할 수 있는 16 개의 XMM/YMM 레지스터를 제공 합니다. 휘발성 레지스터는 호출자가 호출 중에 제거되는 것으로 가정하는 스크래치 레지스터입니다. 함수 호출 중에 값을 유지하려면 비휘발성 레지스터가 필요합니다. 호출 수신자는 비휘발성 레지스터(사용하는 경우)를 저장해야 합니다.

### <a name="register-volatility-and-preservation"></a>변동성 및 보존 등록

다음 테이블에서는 함수 호출에서 각 레지스터가 사용되는 방법을 설명합니다.

||||
|-|-|-|
|레지스터|Status|관리 그룹을 연결하거나 연결된 관리 그룹의 속성을 편집하려면 관리 작업 영역의|
|RAX|휘발성|반환 값 레지스터|
|RCX|휘발성|첫 번째 정수 인수|
|RDX|휘발성|두 번째 정수 인수|
|R8|휘발성|세 번째 정수 인수|
|R9|휘발성|네 번째 정수 인수|
|R10:R11|휘발성|호출자가 필요에 따라 보존해야 하며 syscall/sysret 명령에 사용됨|
|R12:R15|비휘발성|호출 수신자가 보존해야 함|
|RDI|비휘발성|호출 수신자가 보존해야 함|
|RSI|비휘발성|호출 수신자가 보존해야 함|
|RBX|비휘발성|호출 수신자가 보존해야 함|
|RBP|비휘발성|프레임 포인터로 사용 가능(호출 수신자가 보존해야 함)|
|RSP|비휘발성|스택 포인터|
|XMM0, YMM0|휘발성|첫 번째 FP 인수(`__vectorcall` 사용 시에는 첫 번째 벡터 형식 인수)|
|XMM1, YMM1|휘발성|두 번째 FP 인수(`__vectorcall` 사용 시에는 두 번째 벡터 형식 인수)|
|XMM2, YMM2|휘발성|세 번째 FP 인수(`__vectorcall` 사용 시에는 세 번째 벡터 형식 인수)|
|XMM3, YMM3|휘발성|네 번째 FP 인수(`__vectorcall` 사용 시에는 네 번째 벡터 형식 인수)|
|XMM4, YMM4|휘발성|호출자가 필요에 따라 보존해야 함(`__vectorcall` 사용 시에는 다섯 번째 벡터 형식 인수)|
|XMM5, YMM5|휘발성|호출자가 필요에 따라 보존해야 함(`__vectorcall` 사용 시에는 여섯 번째 벡터 형식 인수)|
|XMM6:XMM15, YMM6:YMM15|비휘발성(XMM), 휘발성(YMM의 위쪽 절반)|호출 수신자가 보존 해야 합니다. YMM 레지스터는 호출자가 필요에 따라 보존해야 함|

함수 종료 시 및 C 런타임 라이브러리 호출 및 Windows 시스템 호출에 대 한 함수 진입에서 CPU 플래그 레지스터의 방향 플래그는 지워지는 것으로 예상 됩니다.

## <a name="stack-usage"></a>스택 사용

X 64의 스택 할당, 맞춤, 함수 형식 및 스택 프레임에 대 한 자세한 내용은 [x64 stack usage](stack-usage.md)를 참조 하세요.

## <a name="prolog-and-epilog"></a>프롤로그 및 에필로그

스택 공간을 할당 하 고, 다른 함수를 호출 하거나, 비휘발성 레지스터를 저장 하거나, 예외 처리를 사용 하는 모든 함수는 해당 함수 테이블 항목과 연결 된 해제 데이터에 설명 된 에필로그에서 주소 제한을 설명 하는 프롤로그를 포함 해야 합니다. 각 종료는 함수를 종료 합니다. X 64에서 필요한 프롤로그 및 에필로그 코드에 대 한 자세한 내용은 [x64 프롤로그 및 에필로그](prolog-and-epilog.md)를 참조 하세요.

## <a name="x64-exception-handling"></a>x64 예외 처리

X64에서 구조적 예외 처리 및 C++ 예외 처리 동작을 구현 하는 데 사용 되는 규칙 및 데이터 구조에 대 한 자세한 내용은 [x64 예외 처리](exception-handling-x64.md)를 참조 하세요.

## <a name="intrinsics-and-inline-assembly"></a>내장 및 인라인 어셈블리

x64 컴파일러의 제약 조건 중 하나는 인라인 어셈블러를 지원하지 않는다는 것입니다. 즉, C 또는 C++로 작성할 수 없는 함수는 컴파일러에서 지원하는 내장 함수나 서브루틴으로 작성해야 합니다. 함수에 따라서는 성능에 큰 영향을 미칠 수도 있습니다. 성능에 중요한 부분을 차지하는 함수는 내장 함수로 구현해야 합니다.

컴파일러에서 지 원하는 내장 함수는 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)에 설명 되어 있습니다.

## <a name="image-format"></a>이미지 형식

X64 실행 가능 이미지 형식은 PE32 +입니다. 실행 가능한 이미지 (Dll 및 Exe)는 최대 2gb로 제한 되므로 32 비트 치환을 사용한 상대 주소 지정을 사용 하 여 정적 이미지 데이터를 처리할 수 있습니다. 이 데이터에는 가져오기 주소 테이블, 문자열 상수, 정적 글로벌 데이터 등이 포함 됩니다.

## <a name="see-also"></a>참고 항목

[호출 규칙](../cpp/calling-conventions.md)
