---
title: timespec_get, _timespec32_get, _timespec64_get1
ms.date: 4/2/2020
api_name:
- timespec_get
- _timespec32_get
- _timespec64_get
- _o__timespec32_get
- _o__timespec64_get
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
- timespec_get
- _timespec32_get
- _timespec64_get
- time/timespec_get
- time/_timespec32_get
- time/_timespec64_get
- timespec
- _timespec32
- _timespec64
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
ms.openlocfilehash: fc6d91b076f2dd2e25c55d9cf7062e81c3fab11a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362494"
---
# <a name="timespec_get-_timespec32_get-_timespec64_get"></a>timespec_get, _timespec32_get, _timespec64_get

첫 번째 인수를 통해 지정된 간격을 지정된 기본 시간을 기준으로 현재 일정 시간으로 설정합니다.

## <a name="syntax"></a>구문

```C
int timespec_get(
    struct timespec* const time_spec,
    int const base
);
int _timespec32_get(
    struct _timespec32* const time_spec,
    int const base
);
int _timespec64_get(
    struct _timespec64* const time_spec,
    int const base
);
```

### <a name="parameters"></a>매개 변수

*time_spec*<br/>
epoch 시작 이후 지난 시간(초 및 나노초)으로 설정된 구조체 포인터입니다.

*base*<br/>
기본 시간을 지정하는 0이 아닌 구현 특정 값입니다.

## <a name="return-value"></a>Return Value

*성공하는* 경우 base값은 0을 반환합니다.

## <a name="remarks"></a>설명

**timespec_get** 함수는 *time_spec* 인수로 가리키는 구조체의 현재 시간을 설정합니다. 이 구조체의 모든 버전에는 **tv_sec** **및 tv_nsec**두 멤버가 있습니다. **tv_sec** 값은 *기본에*의해 지정된 시대의 시작 이후, 시스템 클럭의 해상도로 반올림, 나노 초의 정수 수에 **tv_nsec** 초의 정수로 설정됩니다.

**마이크로소프트 특정**

이러한 함수는 *기본* 값으로 **TIME_UTC** 지원합니다. 이렇게 하면 *time_spec* 값이 1970년 1월 1일 자정, 조정된 유니버설 타임(UTC) 이후의 초 및 나노초 수로 설정됩니다. **구조체** **_timespec32** **tv_sec** **__time32_t** 값입니다. **구조체** **_timespec64** **tv_sec** **__time64_t** 값입니다. **구조체** **시간 tv_sec**전처리기 매크로 _USE_32BIT_TIME_T 정의되는지 여부에 따라 길이가 32비트 또는 64비트인 **time_t** 유형입니다. **tv_sec** **timespec_get** 함수는 _USE_32BIT_TIME_T 정의된 경우 **_timespec32_get** 호출하는 인라인 함수입니다. 그렇지 않으면 **_timespec64_get**호출합니다.

**끝 마이크로 소프트 특정**

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**timespec_get,** **_timespec32_get,** **_timespec64_get**|C: \<time.h>, C++: \<ctime> 또는 \<time.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
