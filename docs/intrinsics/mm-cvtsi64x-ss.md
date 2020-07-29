---
title: _mm_cvtsi64x_ss
ms.date: 09/02/2019
f1_keywords:
- _mm_cvtsi64x_ss
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
ms.openlocfilehash: a8227fcb482267946ea7ba08ee352c43e1ac6f6e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218002"
---
# <a name="_mm_cvtsi64x_ss"></a>_mm_cvtsi64x_ss

**Microsoft 전용**

64 비트 정수 변환의 x64 확장 버전을 스칼라 단 정밀도 부동 소수점 값 () 명령으로 생성 합니다 `cvtsi2ss` .

## <a name="syntax"></a>구문

```C
__m128 _mm_cvtsi64x_ss(
   __m128 a,
   __int64 b
);
```

### <a name="parameters"></a>매개 변수

*은*\
진행 **`__m128`** 네 개의 단 정밀도 부동 소수점 값을 포함 하는 구조체입니다.

*b*\
진행 부동 소수점 값으로 변환할 64 비트 정수입니다.

## <a name="return-value"></a>반환 값

**`__m128`** 변환 결과에 해당 하는 첫 번째 부동 소수점 값을 갖는 구조체입니다. 다른 세 값 *은에서 변경*되지 않은 상태로 복사 됩니다.

## <a name="requirements"></a>요구 사항

|Intrinsic|Architecture|
|---------------|------------------|
|`_mm_cvtsi64x_ss`|X64|

**헤더 파일** \<intrin.h>

## <a name="remarks"></a>설명

**`__m128`** 구조체는 xmm 레지스터를 나타내므로 내장 함수는 시스템 메모리의 *b* 값을 xmm 레지스터로 이동할 수 있도록 허용 합니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

## <a name="example"></a>예제

```cpp
// _mm_cvtsi64x_ss.cpp
// processor: x64

#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtsi64x_ss)

int main()
{
    __m128 a;
    __int64 b = 54;

    a.m128_f32[0] = 0;
    a.m128_f32[1] = 0;
    a.m128_f32[2] = 0;
    a.m128_f32[3] = 0;
    a = _mm_cvtsi64x_ss(a, b);

    printf_s( "%lf %lf %lf %lf\n",
              a.m128_f32[0], a.m128_f32[1],
              a.m128_f32[2], a.m128_f32[3] );
}
```

```Output
54.000000 0.000000 0.000000 0.000000
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[__m128](../cpp/m128.md)\
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
