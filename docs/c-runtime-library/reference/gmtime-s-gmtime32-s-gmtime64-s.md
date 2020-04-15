---
title: gmtime_s, _gmtime32_s, _gmtime64_s
ms.date: 4/2/2020
api_name:
- _gmtime32_s
- gmtime_s
- _gmtime64_s
- _o__gmtime32_s
- _o__gmtime64_s
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
- _gmtime_s
- gmtime64_s
- gmtime32_s
- _gmtime64_s
- gmtime_s
- _gmtime32_s
helpviewer_keywords:
- gmtime_s function
- gmtime32_s function
- time functions
- gmtime64_s function
- _gmtime64_s function
- time structure conversion
- _gmtime_s function
- _gmtime32_s function
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
ms.openlocfilehash: e73d2d3cca852b657631361d8271bec7f9c86ac5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344089"
---
# <a name="gmtime_s-_gmtime32_s-_gmtime64_s"></a>gmtime_s, _gmtime32_s, _gmtime64_s

시간 값을 **tm** 구조로 변환합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t gmtime_s(
   struct tm* tmDest,
   const __time_t* sourceTime
);
errno_t _gmtime32_s(
   struct tm* tmDest,
   const __time32_t* sourceTime
);
errno_t _gmtime64_s(
   struct tm* tmDest,
   const __time64_t* sourceTime
);
```

### <a name="parameters"></a>매개 변수

*tmDest*<br/>
[TM](../../c-runtime-library/standard-types.md) 구조에 대한 포인터입니다. 반환된 구조체의 필드는 현지 시간이 아닌 UTC에서 *타이머* 인수의 평가된 값을 보유합니다.

*소스 타임*<br/>
저장된 시간에 대한 포인터입니다. 시간은 1970년 1월 1일 자정(00:00:00)(UTC(협정 세계시)) 이후 경과한 시간(초)으로 표현됩니다.

## <a name="return-value"></a>Return Value

성공할 경우 0입니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 Errno.h에서 정의됩니다. 이러한 오류 의 목록은 [errno를](../../c-runtime-library/errno-constants.md)참조하십시오.

### <a name="error-conditions"></a>오류 조건

|*tmDest*|*소스 타임*|반환 값|*tmDest의* 값|
|-----------|------------|------------|--------------------|
|**Null**|any|**아인발 ()에인발 (것)**|수정되지 않습니다.|
|**NULL이** 아님(유효한 메모리를 가리킵니다)|**Null**|**아인발 ()에인발 (것)**|모든 필드가 -1로 설정됩니다.|
|**NULL이** 아님|< 0|**아인발 ()에인발 (것)**|모든 필드가 -1로 설정됩니다.|

처음 두 오류 조건의 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다. 실행을 계속할 수 있는 경우 이러한 함수는 **errno를** **EINVAL로** 설정하고 **EINVAL을**반환합니다.

## <a name="remarks"></a>설명

**_gmtime32_s** 함수는 *sourceTime* 값을 세분화하고 Time.h에 정의된 **tm**형식의 구조에 저장합니다. 구조의 주소는 *tmDest로*전달됩니다. *sourceTime의* 값은 일반적으로 [시간](time-time32-time64.md) 함수에 대한 호출에서 가져옵니다.

> [!NOTE]
> 대상 환경에서는 일광 절약 시간이 적용되는지 확인해야 합니다. C 런타임 라이브러리에서는 일광 절약 시간 계산 구현을 위한 미국의 규칙이 사용된다고 가정합니다.

각 구조 필드는 다음 표와 같이 **int**형식입니다.

|필드|Description|
|-|-|
|**tm_sec**|분 후 초 (0 - 59).|
|**tm_min**|시간 후 분 (0 - 59).|
|**tm_hour**|자정 이후 시간 (0 - 23).|
|**tm_mday**|월의 일 (1 - 31).|
|**tm_mon**|월 (0 - 11; 1월 = 0).|
|**tm_year**|연도(현재 연도 - 1900).|
|**tm_wday**|요일 (0 - 6; 일요일 = 0).|
|**tm_yday**|연도의 날 (0 - 365; 1월 1일 = 0).|
|**tm_isdst**|**항상 0 gmtime_s**.|

**__time64_t**구조를 사용하는 **__time64_t** _gmtime64_s 3000년 12월 31일 UTC 23:59:59까지 날짜를 표현할 수 있습니다. **gmtime32_s** 2038년 1월 18일 23:59:59까지만 날짜를 나타냅니다. 1970년 1월 1일 자정은 이러한 두 함수 모두에 대한 날짜 범위의 하한입니다.

**gmtime_s** **_gmtime64_s** 평가하는 인라인 함수이며 **time_t** **__time64_t**동일합니다. 컴파일러가 **time_t** 이전 32비트 **time_t**해석하도록 강제해야 하는 경우 **_USE_32BIT_TIME_T**. 이렇게 하면 **gmtime_s** **_gmtime32_s**줄 지어 있습니다. 2038년 1월 18일 이후에는 애플리케이션에서 오류가 발생할 수 있으므로 이 방식은 사용하지 않는 것이 좋으며, 64비트 플랫폼에서는 이러한 방식이 허용되지 않습니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 C 헤더|필수 C++ 헤더|
|-------------|---------------------|-|
|**gmtime_s**, **_gmtime32_s,** **_gmtime64_s**|\<time.h>|\<> 또는 \<time.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_gmtime64_s.c
// This program uses _gmtime64_s to convert a 64-bit
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime_s to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm newtime;
   __int64 ltime;
   char buf[26];
   errno_t err;

   _time64( &ltime );

   // Obtain coordinated universal time:
   err = _gmtime64_s( &newtime, &ltime );
   if (err)
   {
      printf("Invalid Argument to _gmtime64_s.");
   }

   // Convert to an ASCII representation
   err = asctime_s(buf, 26, &newtime);
   if (err)
   {
      printf("Invalid Argument to asctime_s.");
   }

   printf( "Coordinated universal time is %s\n",
           buf );
}
```

```Output
Coordinated universal time is Fri Apr 25 20:12:33 2003
```

## <a name="see-also"></a>참고 항목

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
