---
title: gmtime, _gmtime32, _gmtime64
ms.date: 4/2/2020
api_name:
- _gmtime32
- gmtime
- _gmtime64
- _o__gmtime32
- _o__gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
ms.openlocfilehash: afa46e583437ebace8edd3a54a6d85e61e02854c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344095"
---
# <a name="gmtime-_gmtime32-_gmtime64"></a>gmtime, _gmtime32, _gmtime64

**time_t** 시간 값을 **tm** 구조로 변환합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>매개 변수

*소스 타임*<br/>
저장된 시간에 대한 포인터입니다. 시간은 1970년 1월 1일 자정(00:00:00)(UTC(협정 세계시)) 이후 경과한 시간(초)으로 표현됩니다.

## <a name="return-value"></a>Return Value

[tm](../../c-runtime-library/standard-types.md) 형식의 구조체에 대한 포인터입니다. 반환된 구조체의 필드는 현지 시간이 아닌 UTC에서 *sourceTime* 인수의 평가된 값을 보유합니다. 각 구조 필드는 다음과 같이 **int**형식입니다.

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
|**tm_isdst**|**항상 0 gmtime**.|

**gmtime,** [mktime,](mktime-mktime32-mktime64.md) [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md)및 [현지 시간의](localtime-localtime32-localtime64.md) 32 비트 및 64 비트 버전 모두 변환을 위해 스레드당 하나의 공통 **tm** 구조를 사용합니다. 이러한 함수 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다. *sourceTime이* 1970년 1월 1일 자정 이전의 날짜를 나타내는 경우 **gmtime은** **NULL을**반환합니다. 반환되는 오류가 없습니다.

**__time64_t** 구조를 사용하는 **_gmtime64**UTC 23:59:59, 3000년 12월 31일, UTC까지 날짜를 표현할 수 _gmtime32 반면, 2038년 1월 18일 23:59:59까지만 날짜를 나타낼 수 있습니다. **_gmtime32** 1970년 1월 1일 자정은 두 함수 모두에 대한 날짜 범위의 하한입니다.

**gmtime은** **_gmtime64**평가하는 인라인 함수이며 **time_t** **_USE_32BIT_TIME_T** 정의되지 않는 한 **__time64_t** 동일합니다. 컴파일러가 **time_t** 이전 32비트 **time_t**강제로 해석해야 하는 **__time32_t**경우 **_USE_32BIT_TIME_T**정의할 수 있지만 이렇게 하면 **time_t** **gmtime이** **_gmtime32** 줄 에 __time32_t time_t. 이 방법은 64비트 플랫폼에서 허용되지 않고 2038년 1월 18일 이후 애플리케이션이 작동하지 않을 수 있기 때문에 권장되지 않습니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. *sourceTime이* null 포인터이거나 *sourceTime* 값이 음수인 경우 이러한 함수는 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 함수는 **NULL을** 반환하고 **errno를** **EINVAL로**설정합니다.

## <a name="remarks"></a>설명

**_gmtime32** 함수는 *sourceTime* 값을 세분화하고 TIME에 정의된 형식 **tm의**정적으로 할당된 구조에 저장합니다. H. *sourceTime의* 값은 일반적으로 [시간](time-time32-time64.md) 함수에 대한 호출에서 가져옵니다.

> [!NOTE]
> 대부분의 경우 대상 환경에서는 일광 절약 시간이 적용되는지 확인하려고 합니다. C 런타임 라이브러리에서는 DST(일광 절약 시간) 계산 구현을 위한 미국 규칙이 사용된다고 가정합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 C 헤더|필수 C++ 헤더|
|-------------|---------------------|-|
|**gmtime**, **_gmtime32**, **_gmtime64**|\<time.h>|\<> 또는 \<time.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_gmtime.c
// compile with: /W3
// This program uses _gmtime64 to convert a long-
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm *newtime;
   __int64 ltime;
   char buff[80];

   _time64( &ltime );

   // Obtain coordinated universal time:
   newtime = _gmtime64( &ltime ); // C4996
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s
   asctime_s( buff, sizeof(buff), newtime );
   printf( "Coordinated universal time is %s\n", buff );
}
```

```Output
Coordinated universal time is Tue Feb 12 23:11:31 2002
```

## <a name="see-also"></a>참고 항목

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
