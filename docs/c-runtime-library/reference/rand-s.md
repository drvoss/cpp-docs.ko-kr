---
title: rand_s
ms.date: 4/2/2020
api_name:
- rand_s
- _o_rand_s
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- rand_s
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: b11a40dd9dc58964df77330767a55aa95a179319
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338198"
---
# <a name="rand_s"></a>rand_s

의사 난수를 생성합니다. 이것은 [CRT의 보안 기능에](../../c-runtime-library/security-features-in-the-crt.md)설명 된 대로 보안 향상 기능 [rand의](rand.md)보다 안전한 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>매개 변수

*랜덤 밸류값*<br/>
생성된 값을 보유하는 정수에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

정상적으로 실행되는 경우 0이고 그렇지 않으면 오류 코드입니다. 입력 포인터 _randomValue가_ null 포인터인 경우 함수는 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 함수는 **EINVAL을** 반환하고 **errno를** **EINVAL로**설정합니다. 다른 이유로 함수가 실패하면 *_randomValue가_ 0으로 설정됩니다.

## <a name="remarks"></a>설명

**rand_s** 함수는 입력 포인터에 **UINT_MAX** 범위 0에 의사 임의 정수를 씁니다. **rand_s** 함수는 운영 체제를 사용하여 암호화된 보안 난수를 생성합니다. [srand](srand.md) 함수에 의해 생성된 시드를 사용하지 않으며 [rand가](rand.md)사용하는 난수 시퀀스에 영향을 미치지 않습니다.

**rand_s** 함수는 다음 예제와 같이 함수에 대한 inclusion 문 앞에 상 **_CRT_RAND_S수를** 정의해야 합니다.

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s** Windows XP 및 이후 에서만 사용할 수 있는 [RtlGenRandom](/windows/win32/api/ntsecapi/nf-ntsecapi-rtlgenrandom) API에 따라 달라집니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**rand_s**|\<stdlib.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_rand_s.c
// This program illustrates how to generate random
// integer or floating point numbers in a specified range.

// Remembering to define _CRT_RAND_S prior
// to inclusion statement.
#define _CRT_RAND_S

#include <stdlib.h>
#include <stdio.h>
#include <limits.h>

int main( void )
{
    int             i;
    unsigned int    number;
    double          max = 100.0;
    errno_t         err;

    // Display 10 random integers in the range [ 1,10 ].
    for( i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %u\n", (unsigned int) ((double)number /
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);
    }

    printf_s("\n");

    // Display 10 random doubles in [0, max).
    for (i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %g\n", (double) number /
                          ((double) UINT_MAX + 1) * max );
    }
}
```

### <a name="sample-output"></a>샘플 출력

```Output
10
4
5
2
8
2
5
6
1
1

32.6617
29.4471
11.5413
6.41924
20.711
60.2878
61.0094
20.1222
80.9192
65.0712
```

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[랜드](rand.md)<br/>
[srand](srand.md)<br/>
