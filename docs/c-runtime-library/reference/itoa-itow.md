---
title: _itoa, _itow 기능
ms.date: 4/2/2020
api_name:
- itoa
- _itoa
- ltoa
- _ltoa
- ultoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- _o__i64toa
- _o__i64tow
- _o__itoa
- _o__itow
- _o__ltoa
- _o__ltow
- _o__ui64toa
- _o__ui64tow
- _o__ultoa
- _o__ultow
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
- api-ms-win-crt-convert-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _itoa
- _ltoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- itoa
- ltoa
- ultoa
- i64toa
- ui64toa
- itow
- ltow
- ultow
- i64tow
- ui64tow
- itot
- _itot
- ltot
- _ltot
- ultot
- _ultot
- i64tot
- _i64tot
- ui64tot
- _ui64tot
- _MAX_ITOSTR_BASE16_COUNT
- _MAX_ITOSTR_BASE10_COUNT
- _MAX_ITOSTR_BASE8_COUNT
- _MAX_ITOSTR_BASE2_COUNT
- _MAX_LTOSTR_BASE16_COUNT
- _MAX_LTOSTR_BASE10_COUNT
- _MAX_LTOSTR_BASE8_COUNT
- _MAX_LTOSTR_BASE2_COUNT
- _MAX_ULTOSTR_BASE16_COUNT
- _MAX_ULTOSTR_BASE10_COUNT
- _MAX_ULTOSTR_BASE8_COUNT
- _MAX_ULTOSTR_BASE2_COUNT
- _MAX_I64TOSTR_BASE16_COUNT
- _MAX_I64TOSTR_BASE10_COUNT
- _MAX_I64TOSTR_BASE8_COUNT
- _MAX_I64TOSTR_BASE2_COUNT
- _MAX_U64TOSTR_BASE16_COUNT
- _MAX_U64TOSTR_BASE10_COUNT
- _MAX_U64TOSTR_BASE8_COUNT
- _MAX_U64TOSTR_BASE2_COUNT
helpviewer_keywords:
- _itot function
- ui64toa function
- _ui64toa function
- converting integers
- itot function
- _i64tow function
- _i64toa function
- _itow function
- ui64tow function
- integers, converting
- itoa function
- _ui64tow function
- i64tow function
- itow function
- i64toa function
- converting numbers, to strings
- _itoa function
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
ms.openlocfilehash: 0cc084076c5e39843ecc1afa08671ce6b2f06d1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342705"
---
# <a name="itoa-_itoa-ltoa-_ltoa-ultoa-_ultoa-_i64toa-_ui64toa-_itow-_ltow-_ultow-_i64tow-_ui64tow"></a>itoa, _itoa, ltoa, _ltoa, ultoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, _ultow, _i64tow, _ui64tow

정수를 문자열로 변환합니다. 이러한 함수의 보다 안전한 버전을 사용할 수 있습니다. [_itoa_s, _itow_s 함수를](itoa-s-itow-s.md)참조하십시오.

## <a name="syntax"></a>구문

```C
char * _itoa( int value, char *buffer, int radix );
char * _ltoa( long value, char *buffer, int radix );
char * _ultoa( unsigned long value, char *buffer, int radix );
char * _i64toa( long long value, char *buffer, int radix );
char * _ui64toa( unsigned long long value, char *buffer, int radix );

wchar_t * _itow( int value, wchar_t *buffer, int radix );
wchar_t * _ltow( long value, wchar_t *buffer, int radix );
wchar_t * _ultow( unsigned long value, wchar_t *buffer, int radix );
wchar_t * _i64tow( long long value, wchar_t *buffer, int radix );
wchar_t * _ui64tow( unsigned long long value, wchar_t *buffer, int radix );

// These POSIX versions of the functions have deprecated names:
char * itoa( int value, char *buffer, int radix );
char * ltoa( long value, char *buffer, int radix );
char * ultoa( unsigned long value, char *buffer, int radix );

// The following template functions are C++ only:
template <size_t size>
char *_itoa( int value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( long value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( unsigned long value, char (&buffer)[size], int radix );

template <size_t size>
char *_i64toa( long long value, char (&buffer)[size], int radix );

template <size_t size>
char * _ui64toa( unsigned long long value, char (&buffer)[size], int radix );

template <size_t size>
wchar_t * _itow( int value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ltow( long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ultow( unsigned long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _i64tow( long long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ui64tow( unsigned long long value, wchar_t (&buffer)[size],
   int radix );
```

### <a name="parameters"></a>매개 변수

*value*<br/>
변환할 숫자입니다.

*버퍼*<br/>
변환 결과를 보유하는 버퍼입니다.

*근원*<br/>
범위 2-36에 있어야 하는 *값변환에*사용할 기본입니다.

*크기*<br/>
문자 유형의 단위 버퍼 의 길이입니다. 이 매개 변수는 C++의 *버퍼* 인수에서 유추됩니다.

## <a name="return-value"></a>Return Value

이러한 각 함수는 *버퍼에*대한 포인터를 반환합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

**_itoa**, **_ltoa**_ltoa **_ultoa** **_i64toa**및 **_ui64toa** 함수는 지정된 *값* 인수의 숫자를 null 종료 된 문자 문자열로 변환하고 결과 **(_itoa,** **_ltoa**및 **_ultoa**최대 33 자, **_i64toa** 및 **_ui64toa**65)를 *버퍼에*저장합니다. *radix가* 10이고 *값이* 음수이면 저장된 문자열의 첫 번째**-** 문자는 빼기 기호 ()입니다. **_itow**, **_ltow,** **_ultow, _i64tow,** **_ui64tow** 기능은 각각 **_itoa,** **_ltoa,** **_ultoa,** **_i64toa,** **_ui64toa**의 넓은 문자 버전입니다. **_ultow**

> [!IMPORTANT]
> 이러한 함수는 너무 작은 버퍼의 끝을 지나 쓸 수 있습니다. 버퍼 오버런을 방지하려면 *버퍼가* 변환된 숫자와 후행 null 문자 및 기호 문자를 보유할 수 있을 만큼 충분히 큰지 확인합니다. 이러한 함수를 오용하면 코드에 심각한 보안 문제가 발생할 수 있습니다.

보안 문제에 대한 가능성 때문에 기본적으로 이러한 함수는 사용 중단 경고 [C4996을](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) **유발합니다: 이 함수 또는 변수는 안전하지 않을 수 있습니다. **대신 *safe_function* 사용하는 것이 **좋습니다. 사용 중단을 사용하지 않으려면 _CRT_SECURE_NO_WARNINGS 사용합니다.** 경고 메시지에서 권장하는 *safe_function* 사용하도록 소스 코드를 변경하는 것이 좋습니다. 보안 함수가 많을수록 지정된 버퍼 크기보다 많은 문자를 쓰지 않습니다. 자세한 내용은 [_itoa_s, _itow_s 함수를](itoa-s-itow-s.md)참조하십시오.

사용 중단 경고 없이 이러한 함수를 사용하려면 CRT 헤더를 포함하기 전에 **_CRT_SECURE_NO_WARNINGS** 전처리 매크로를 정의합니다. **/D_CRT_SECURE_NO_WARNINGS** 컴파일러 옵션을 **cl** 명령에 추가하여 개발자 명령 프롬프트의 명령줄에서 이 작업을 수행할 수 있습니다. 그렇지 않으면 원본 파일에서 매크로를 정의합니다. 미리 컴파일된 헤더를 사용하는 경우 미리 컴파일된 헤더 맨 위에 있는 매크로를 정의하려면 파일 *pch.h(Visual* Studio 2017 및 이전)에서*sdafx.h를* 포함합니다. 소스 코드에서 매크로를 정의하려면 이 예제와 같이 CRT 헤더를 포함하기 전에 **#define** 지시문을 사용합니다.

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

C++에서 이러한 함수에는 보다 안전한 함수를 호출하는 템플릿 오버로드가 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

POSIX 이름은 **이토아,** **ltoa**및 **ultoa는** **_itoa,** **_ltoa**및 **_ultoa** 함수에 대한 별칭으로 존재합니다. POSIX 이름은 ISO C의 구현별 전역 함수 이름 규칙을 따르지 않으므로 더 이상 사용되지 않습니다. 기본적으로 이러한 함수는 사용 중단 경고 [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **이 항목의 POSIX 이름이 더 이상 사용되지 않습니다. 대신 ISO C 및 C++ 준수 이름인** *new_name*사용합니다. 소스 코드를 변경하여 이러한 함수, **_itoa_s,** **_ltoa_s**또는 **_ultoa_s**보다 안전한 버전을 사용하는 것이 좋습니다. 자세한 내용은 [_itoa_s, _itow_s 함수를](itoa-s-itow-s.md)참조하십시오.

소스 코드 이식성의 경우 코드에 POSIX 이름을 유지하는 것이 좋습니다. 사용 중단 경고 없이 이러한 함수를 사용하려면 CRT 헤더를 포함하기 전에 **_CRT_NONSTDC_NO_WARNINGS** 및 **_CRT_SECURE_NO_WARNINGS** 전처리 매크로를 모두 정의합니다. **/D_CRT_SECURE_NO_WARNINGS** 및 **/D_CRT_NONSTDC_NO_WARNINGS** 컴파일러 옵션을 **cl** 명령에 추가하여 개발자 명령 프롬프트의 명령줄에서 이 작업을 수행할 수 있습니다. 그렇지 않으면 원본 파일의 매크로를 정의합니다. 미리 컴파일된 헤더를 사용하는 경우 미리 컴파일된 헤더 포함 파일의 맨 위에 있는 매크로를 정의합니다. 소스 코드에서 매크로를 정의하려면 이 예제와 같이 CRT 헤더를 포함하기 전에 **#define** 지시문을 사용합니다.

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>최대 전환 수 매크로

변환을 위한 보안 버퍼를 만드는 데 도움이 되는 CRT에는 몇 가지 편리한 매크로가 포함되어 있습니다. 여러 공통 베이스에 대해 null 종단 및 기호 문자를 포함하여 각 정수 형식의 가능한 가장 긴 값을 변환하는 데 필요한 버퍼의 크기를 정의합니다. 변환 버퍼가 *radix에*의해 지정된 기본에서 변환을 받을 수 있을 만큼 충분히 큰지 확인하려면 버퍼를 할당할 때 이러한 정의된 매크로 중 하나를 사용합니다. 이렇게 하면 정수 형식을 문자열로 변환할 때 버퍼 오버런 오류를 방지할 수 있습니다. 이러한 매크로는 원본에 stdlib.h 또는 wchar.h를 포함할 때 정의됩니다.

문자열 변환 함수에서 이러한 매크로 중 하나를 사용하려면 적절한 문자 형식의 변환 버퍼를 선언하고 정수 형식 및 기본에 대한 매크로 값을 버퍼 차원으로 사용합니다. 이 표에는 나열된 베이스에 대한 각 함수에 적합한 매크로가 나열됩니다.

||||
|-|-|-|
|Functions|radix|Macros|
|**_itoa,** **_itow**|16<br/>10<br/>8<br/>2|**_MAX_ITOSTR_BASE16_COUNT**<br/>**_MAX_ITOSTR_BASE10_COUNT**<br/>**_MAX_ITOSTR_BASE8_COUNT**<br/>**_MAX_ITOSTR_BASE2_COUNT**|
|**_ltoa,** **_ltow**|16<br/>10<br/>8<br/>2|**_MAX_LTOSTR_BASE16_COUNT**<br/>**_MAX_LTOSTR_BASE10_COUNT**<br/>**_MAX_LTOSTR_BASE8_COUNT**<br/>**_MAX_LTOSTR_BASE2_COUNT**|
|**_ultoa**, **_ultow**|16<br/>10<br/>8<br/>2|**_MAX_ULTOSTR_BASE16_COUNT**<br/>**_MAX_ULTOSTR_BASE10_COUNT**<br/>**_MAX_ULTOSTR_BASE8_COUNT**<br/>**_MAX_ULTOSTR_BASE2_COUNT**|
|**_i64toa**, **_i64tow**|16<br/>10<br/>8<br/>2|**_MAX_I64TOSTR_BASE16_COUNT**<br/>**_MAX_I64TOSTR_BASE10_COUNT**<br/>**_MAX_I64TOSTR_BASE8_COUNT**<br/>**_MAX_I64TOSTR_BASE2_COUNT**|
|**_ui64toa**, **_ui64tow**|16<br/>10<br/>8<br/>2|**_MAX_U64TOSTR_BASE16_COUNT**<br/>**_MAX_U64TOSTR_BASE10_COUNT**<br/>**_MAX_U64TOSTR_BASE8_COUNT**<br/>**_MAX_U64TOSTR_BASE2_COUNT**|

이 예제에서는 변환 카운트 매크로를 사용하여 기본 2에 **서명되지 않은 긴 긴** 버퍼를 포함할 수 있을 만큼 큰 버퍼를 정의합니다.

```cpp
#include <wchar.h>
#include <iostream>
int main()
{
    wchar_t buffer[_MAX_U64TOSTR_BASE2_COUNT];
    std:wcout << _ui64tow(0xFFFFFFFFFFFFFFFFull, buffer, 2) << std::endl;
}
```

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_itot**|**_itoa**|**_itoa**|**_itow**|
|**_ltot**|**_ltoa**|**_ltoa**|**_ltow**|
|**_ultot**|**_ultoa**|**_ultoa**|**_ultow**|
|**_i64tot**|**_i64toa**|**_i64toa**|**_i64tow**|
|**_ui64tot**|**_ui64toa**|**_ui64toa**|**_ui64tow**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**이토아,** **루아,** **울토아**|\<stdlib.h>|
|**_itoa,** **_ltoa,** **_ultoa,** **_i64toa,** **_ui64toa**|\<stdlib.h>|
|**_itow,** **_ltow,** **_ultow**, **_i64tow**, **_ui64tow**|\<stdlib.h> 또는 \<wchar.h>|

이러한 기능과 매크로는 Microsoft에 만연합니다. 호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 샘플에서는 일부 정수 변환 함수의 사용을 보여 줍니다. **_CRT_SECURE_NO_WARNINGS** 매크로를 사용하여 C4996을 무음으로 경고합니다.

```C
// crt_itoa.c
// Compile by using: cl /W4 crt_itoa.c
// This program makes use of the _itoa functions
// in various examples.

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>      // for printf
#include <string.h>     // for strnlen
#include <stdlib.h>     // for _countof, _itoa fns, _MAX_COUNT macros

int main(void)
{
    char buffer[_MAX_U64TOSTR_BASE2_COUNT];
    int r;

    for (r = 10; r >= 2; --r)
    {
        _itoa(-1, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _i64toa(-1LL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _ui64toa(0xffffffffffffffffULL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
}
```

```Output
base 10: -1 (2 chars)
base 9: 12068657453 (11 chars)
base 8: 37777777777 (11 chars)
base 7: 211301422353 (12 chars)
base 6: 1550104015503 (13 chars)
base 5: 32244002423140 (14 chars)
base 4: 3333333333333333 (16 chars)
base 3: 102002022201221111210 (21 chars)
base 2: 11111111111111111111111111111111 (32 chars)

base 10: -1 (2 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)

base 10: 18446744073709551615 (20 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)
```

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[_itoa_s, _itow_s 기능](itoa-s-itow-s.md)<br/>
