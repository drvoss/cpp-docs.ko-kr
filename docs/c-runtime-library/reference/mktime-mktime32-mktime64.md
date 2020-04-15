---
title: mktime, _mktime32, _mktime64
ms.date: 4/2/2020
api_name:
- _mktime32
- mktime
- _mktime64
- _o__mktime32
- _o__mktime64
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
- mktime
- _mktime64
helpviewer_keywords:
- _mktime32 function
- mktime function
- time functions
- mktime64 function
- converting times
- mktime32 function
- _mktime64 function
- time, converting
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
ms.openlocfilehash: b0981f33d70945083eacd28eb7517e80b3f2539f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338710"
---
# <a name="mktime-_mktime32-_mktime64"></a>mktime, _mktime32, _mktime64

현지 시간을 달력 값으로 변환합니다.

## <a name="syntax"></a>구문

```C
time_t mktime(
   struct tm *timeptr
);
__time32_t _mktime32(
   struct tm *timeptr
);
__time64_t _mktime64(
   struct tm *timeptr
);
```

### <a name="parameters"></a>매개 변수

*timeptr*<br/>
시간 구조에 대한 포인터입니다. [asctime](asctime-wasctime.md)을 참조하세요.

## <a name="return-value"></a>Return Value

**_mktime32** [time_t](../../c-runtime-library/standard-types.md)형식의 값으로 인코딩된 지정된 일정 시간을 반환합니다. *timeptr이* 1970년 1월 1일 자정 이전의 날짜를 참조하거나 달력 시간을 나타낼 수 없는 경우 **_mktime32** -1 캐스트를 입력 **time_t**반환합니다. **_mktime32** 사용하고 *timeptr이* 2038년 1월 18일 23:59:59 이후의 날짜를 참조하는 경우, 조정된 유니버설 타임(UTC)은 -1 캐스트를 **time_t**입력하기 위해 반환합니다.

**_mktime64** *timeptr이* UTC 23:59:59, 3000년 12월 31일 이후의 날짜를 참조하는 경우 **__time64_t** 입력하기 위해 -1 캐스트를 반환합니다.

## <a name="remarks"></a>설명

**mktime,** **_mktime32** 및 **_mktime64** 함수는 *timeptr에* 의해 가리키는 제공된 시간 구조(불완전함)를 정규화된 값을 가진 완전히 정의된 구조로 변환한 다음 **time_t** 달력 시간 값으로 변환합니다. 변환된 시간은 [time](time-time32-time64.md) 함수가 반환한 값과 인코딩이 동일합니다. *timeptr* 구조의 **tm_wday** 및 **tm_yday** 구성요소의 원래 값은 무시되고 다른 구성요소의 원래 값은 정상 범위로 제한되지 않습니다.

**mktime은** **_USE_32BIT_TIME_T** 정의되지 않는 한 **_mktime64**것과 동일한 인라인 함수이며, 이 경우 **_mktime32**.

UTC를 조정한 후 **_mktime32** 1970년 1월 1일 자정부터 2038년 1월 18일 23:59:59까지의 날짜를 처리합니다. **_mktime64** 1970년 1월 1일 자정부터 23:59:59, 3000년 12월 31일 자정까지 의 날짜를 처리합니다. 이렇게 조정하면 지정한 날짜가 범위 내에 있더라도 이러한 함수가 -1(time_t, **__time32_t** 또는 **__time64_t**캐스트)로 반환될 수 있습니다. **time_t** 예를 들어 UTC보다 2시간 빠른 이집트의 카이로에 있으면 *timeptr*에 지정한 날짜에서 먼저 2시간을 뺍니다. 그러면 해당 날짜가 범위를 벗어날 수 있습니다.

이러한 함수는 tm 구조의 유효성을 검사하고 시간 구조를 채우는 데 사용할 수 있습니다. 성공하면 이러한 함수는 **tm_wday** 및 **tm_yday** 값을 적절히 설정하고 다른 구성 요소를 지정된 달력 시간을 나타내도록 설정하지만 해당 값은 정상 범위로 강제합니다. **tm_mday** 최종 값은 **tm_mon** **tm_year** 결정될 때까지 설정되지 않습니다. **tm** 구조 시간을 지정할 때 **tm_isdst** 필드를 다음과 같은 것으로 설정합니다.

- 0은 표준 시간이 적용 중임을 나타냅니다.

- 0보다 큰 값은 일광 절약 시간이 적용 중임을 나타냅니다.

- 0보다 작은 값은 C 런타임 라이브러리 코드가 표준 시간 또는 일광 절약 시간이 적용 중인지 여부를 컴퓨팅하도록 합니다.

C 런타임 라이브러리는 [TZ](tzset.md) 환경 변수에서 일광 절약 시간 동작을 결정합니다. **TZ가** 설정되지 않은 경우 Win32 API 호출 [GetTimeZoneInformation는](/windows/win32/api/timezoneapi/nf-timezoneapi-gettimezoneinformation) 운영 체제에서 일광 절약 시간 정보를 얻는 데 사용됩니다. 이러한 정보를 가져오지 못하면 라이브러리에서는 일광 절약 시간 계산 구현을 위한 미국의 규칙이 사용된다고 가정합니다. **tm_isdst** 필수 필드입니다. 이 필드를 설정하지 않으면 해당 값이 정의되지 않고 이러한 함수의 반환 값을 예측할 수 없습니다. *timeptrasasst* **tm** 구조를 가리키는 경우 [asctime,](asctime-wasctime.md) [gmtime](gmtime-gmtime32-gmtime64.md)또는 [로컬 타임](localtime-localtime32-localtime64.md) (또는 이러한 함수의 변형)에 대한 이전 호출에 의해 반환된 경우 **tm_isdst** 필드에 올바른 값이 포함됩니다.

**gmtime** 및 **로컬 타임** (및 **_gmtime32**, **_gmtime64**, **_localtime32**및 **_localtime64)** 변환에 대 한 스레드 당 단일 버퍼를 사용 합니다. 이 버퍼를 **mktime,** **_mktime32** 또는 **_mktime64**제공하면 이전 내용이 소멸됩니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. *timeptr*이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 함수는 -1을 반환하고 **errno를** **EINVAL로**설정합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**mktime**|\<time.h>|
|**_mktime32**|\<time.h>|
|**_mktime64**|\<time.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_mktime.c
/* The example takes a number of days
* as input and returns the time, the current
* date, and the specified number of days.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm  when;
   __time64_t now, result;
   int        days;
   char       buff[80];

   time( &now );
   _localtime64_s( &when, &now );
   asctime_s( buff, sizeof(buff), &when );
   printf( "Current time is %s\n", buff );
   days = 20;
   when.tm_mday = when.tm_mday + days;
   if( (result = mktime( &when )) != (time_t)-1 ) {
      asctime_s( buff, sizeof(buff), &when );
      printf( "In %d days the time will be %s\n", days, buff );
   } else
      perror( "mktime failed" );
}
```

### <a name="sample-output"></a>샘플 출력

```Output
Current time is Fri Apr 25 13:34:07 2003

In 20 days the time will be Thu May 15 13:34:07 2003
```

## <a name="see-also"></a>참고 항목

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
