---
title: _mkgmtime, _mkgmtime32, _mkgmtime64
description: _Mkgmtime, _mkgmtime32 및 _mkgmtime64 C 런타임 라이브러리 함수에 대해 설명 하 고이 함수를 사용 하는 방법에 대 한 예제를 제공 합니다.
ms.date: 4/2/2020
api_name:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
- _o__mkgmtime32
- _o__mkgmtime64
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
helpviewer_keywords:
- mkgmtime32 function
- time functions
- mkgmtime function
- _mkgmtime function
- converting times
- mkgmtime64 function
- _mkgmtime64 function
- _mkgmtime32 function
- time, converting
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
ms.openlocfilehash: cc8ccfc628a0f0c5dd649dbb5cf3bd0b552b5d11
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216884"
---
# <a name="_mkgmtime-_mkgmtime32-_mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64

Tm이 나타내는 UTC 시간을 **`struct`** **tm** **time_t** 형식이 나타내는 utc 시간으로 변환 합니다.

## <a name="syntax"></a>구문

```C
time_t _mkgmtime(
   struct tm* timeptr
);
__time32_t _mkgmtime32(
   struct tm* timeptr
);
__time64_t _mkgmtime64(
   struct tm* timeptr
);
```

### <a name="parameters"></a>매개 변수

*timeptr*\
변환할 UTC 시간에 대 한 포인터 **`struct`** **tm** 입니다.

## <a name="return-value"></a>Return Value

1970 년 1 월 1 일 자정 이후 경과 된 시간 (초)을 나타내는 **__time64_t** **__time32_t** 또는 utc (협정 세계시) 형식의 수량입니다. 날짜가 범위를 벗어난 경우 (설명 섹션 참조) 또는 입력을 유효한 시간으로 해석할 수 없는 경우 반환 값은-1입니다.

## <a name="remarks"></a>설명

**_Mkgmtime32** 및 **_MKGMTIME64** 함수는 utc 시간을 utc 시간을 나타내는 **__time32_t** 또는 **__time64_t** 형식으로 변환 합니다. 현지 시간을 UTC 시간으로 변환 하려면 **mktime**, **_mktime32**및 **_mktime64** 를 대신 사용 합니다.

**_mkgmtime** 은 **_mkgmtime64**으로 계산 되는 인라인 함수 이며 **time_t** **__time64_t**와 동일 합니다. 컴파일러가 **time_t** 이전 32 비트 **time_t**으로 해석 해야 하는 경우 **_USE_32BIT_TIME_T**를 정의할 수 있습니다. 2038 년 1 월 18 일 후 응용 프로그램이 실패 하 고 32 비트 **time_t**의 최대 범위인 응용 프로그램이 실패할 수 있으므로 권장 하지 않습니다. 64 비트 플랫폼에서는 허용 되지 않습니다.

전달 된 시간 구조는 **_mktime** 함수에 의해 변경 되는 것과 동일한 방식으로 다음과 같이 변경 됩니다. **tm_wday** 및 **tm_yday** 필드는 **tm_mday** 및 **tm_year**값을 기준으로 새 값으로 설정 됩니다. 시간이 UTC로 간주 되기 때문에 **tm_isdst** 필드는 무시 됩니다.

**_Mkgmtime32** 함수의 범위는 자정부터 1970 1 월 1 일 자정부터 23:59:59 년 1 월 18 일 2038, utc 까지의 시간입니다. **_Mkgmtime64** 범위는 자정, 1970 1 월 1 일 자정부터 23:59:59 년 12 월 31 일, 3000, utc 사이입니다. 범위를 벗어난 날짜의 반환 값은-1입니다. **_Mkgmtime** 범위는 **_USE_32BIT_TIME_T** 정의 되었는지 여부에 따라 달라 집니다. 정의 되지 않은 경우 (기본값) 범위는 **_mkgmtime64**와 동일 합니다. 그렇지 않으면 범위는 **_mkgmtime32**의 32 비트 범위로 제한 됩니다.

**Gmtime** 와 **localtime** 는 모두 변환에 공통 정적 버퍼를 사용 합니다. 이 버퍼를 **_mkgmtime**에 제공 하면 이전 내용이 제거 됩니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="examples"></a>예제

```C
// crt_mkgmtime.c
#include <stdio.h>
#include <time.h>

int main()
{
    struct tm t1, t2;
    time_t now, mytime, gmtime;
    char buff[30];

    time( & now );

    _localtime64_s( &t1, &now );
    _gmtime64_s( &t2, &now );

    mytime = mktime(&t1);
    gmtime = _mkgmtime(&t2);

    printf("Seconds since midnight, January 1, 1970\n");
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);

    /* Use asctime_s to display these times. */

    _localtime64_s( &t1, &mytime );
    asctime_s( buff, sizeof(buff), &t1 );
    printf( "Local Time: %s\n", buff );

    _gmtime64_s( &t2, &gmtime );
    asctime_s( buff, sizeof(buff), &t2 );
    printf( "Greenwich Mean Time: %s\n", buff );

}
```

```Output
Seconds since midnight, January 1, 1970
My time: 1171588492
GM time (UTC): 1171588492

Local Time: Thu Feb 15 17:14:52 2007

Greenwich Mean Time: Fri Feb 16 01:14:52 2007
```

다음 예제에서는 **_mkgmtime**하 여 불완전 한 구조체를 채우는 방법을 보여 줍니다. 요일 및 연도에 대 한 값을 계산 합니다.

```C
// crt_mkgmtime2.c
#include <stdio.h>
#include <time.h>
#include <memory.h>

int main()
{
    struct tm t1, t2;
    time_t gmtime;
    char buff[30];

    memset(&t1, 0, sizeof(struct tm));
    memset(&t2, 0, sizeof(struct tm));

    t1.tm_mon = 1;
    t1.tm_isdst = 0;
    t1.tm_year = 103;
    t1.tm_mday = 12;

    // The day of the week and year will be incorrect in the output here.
    asctime_s( buff, sizeof(buff), &t1);
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

    gmtime = _mkgmtime(&t1);

    // The correct day of the week and year were determined.
    asctime_s( buff, sizeof(buff), &t1);
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

}
```

```Output
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003
t.tm_yday = 0
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003
t.tm_yday = 42
```

## <a name="see-also"></a>참고 항목

[시간 관리](../../c-runtime-library/time-management.md)\
[asctime, _wasctime](asctime-wasctime.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[time, _time32, _time64](time-time32-time64.md)
