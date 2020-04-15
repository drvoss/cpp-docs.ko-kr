---
title: _mkgmtime, _mkgmtime32, _mkgmtime64
description: _mkgmtime, _mkgmtime32 및 _mkgmtime64 C 런타임 라이브러리 함수를 설명하고 이를 사용하는 방법에 대한 예제를 제공합니다.
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: e8b3170fc0413a878777035fd76aac5eefa7b6bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338768"
---
# <a name="_mkgmtime-_mkgmtime32-_mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64

**구조체** **tm으로** 표시되는 UTC 시간을 **time_t** 유형으로 표시되는 UTC 시간으로 변환합니다.

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

*타임프트르*\
변환할 **구조체** **TM으로** UTC 시간에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

1970년 1월 1일 자정 이후 경과된 초(UTC)를 나타내는 **__time32_t** 또는 **__time64_t** 수량입니다. 날짜가 범위를 벗어났거나(비고 섹션 참조) 입력을 유효한 시간으로 해석할 수 없는 경우 반환 값은 -1입니다.

## <a name="remarks"></a>설명

**_mkgmtime32** **및 _mkgmtime64** 함수는 UTC 시간을 UTC 시간을 **__TIME32_T** 또는 **__time64_t** 유형으로 변환하여 시간을 UTC에 있는 시간을 나타냅니다. 현지 시간을 UTC 시간으로 변환하려면 **mktime**, **_mktime32**및 **_mktime64** 대신 사용합니다.

**_mkgmtime** **_mkgmtime64**평가하는 인라인 함수이며 **time_t** **__time64_t.** 컴파일러가 **time_t** 이전 32비트 **time_t**해석하도록 강제해야 하는 경우 **_USE_32BIT_TIME_T**. 응용 프로그램이 2038년 1월 18일 이후에 실패할 수 있으므로 32비트 **time_t**최대 범위인 이 time_t 권장하지 않습니다. 64비트 플랫폼에서는 전혀 허용되지 않습니다.

전달된 시간 구조는 **_mktime** 함수에 의해 변경되는 것과 같은 방식으로 다음과 같이 변경됩니다: **tm_wday** 및 **tm_yday** 필드는 **tm_mday** 및 **tm_year**값에 따라 새 값으로 설정됩니다. 시간이 UTC로 가정되므로 **tm_isdst** 필드는 무시됩니다.

**_mkgmtime32** 함수의 범위는 1970년 1월 1일 자정부터 UTC, UTC2038년 1월 18일 23:59:59까지입니다. **_mkgmtime64** 범위는 1970년 1월 1일 자정부터 UTC 23:59:59, 3000년 12월 31일, UTC입니다. 범위를 벗어난 날짜는 반환 값이 -1입니다. **_mkgmtime** 범위는 **_USE_32BIT_TIME_T** 정의되는지 여부에 따라 달라집니다. 기본값인 정의되지 않은 경우 범위는 **_mkgmtime64.** 그렇지 않으면 범위는 **_mkgmtime32**32비트 범위로 제한됩니다.

**gmtime과** **로컬 타임** 모두 변환에 공통 정적 버퍼를 사용합니다. **_mkgmtime**이 버퍼를 제공하면 이전 내용이 소멸됩니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="examples"></a>예

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

다음 예제에서는 불완전한 구조가 **_mkgmtime**의해 채워지는 방법을 보여 주었습니다. 요일과 연도의 값을 모두 계산합니다.

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
