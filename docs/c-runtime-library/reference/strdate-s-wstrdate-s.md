---
title: _strdate_s, _wstrdate_s
description: _strdate_s _wstrdate_s 현재 날짜를 버퍼에 넣는 _strdate 및 _wstrdate 함수의 안전한 CRT 버전입니다.
ms.date: 4/2/2020
api_name:
- _strdate_s
- _wstrdate_s
- _o__strdate_s
- _o__wstrdate_s
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
- _strdate_s
- wstrdate_s
- _wstrdate_s
- strdate_s
- _tstrdate_s
helpviewer_keywords:
- dates, copying
- tstrdate_s function
- wstrdate_s function
- _tstrdate_s function
- strdate_s function
- copying dates
- _strdate_s function
- _wstrdate_s function
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
ms.openlocfilehash: b4d977ba3546eae17218c63b1786fd26c784d340
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359828"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

현재 시스템 날짜를 버퍼에 복사합니다. 이러한 함수는 [crT의 보안 기능에](../../c-runtime-library/security-features-in-the-crt.md)설명된 대로 보안 기능이 [향상된 _wstrdate _strdate](strdate-wstrdate.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _strdate_s(
   char *buffer,
   size_t size
);
errno_t _wstrdate_s(
   wchar_t *buffer,
   size_t size
);
template <size_t size>
errno_t _strdate_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrdate_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*버퍼*\
형식이 지정된 날짜 문자열을 넣을 버퍼에 대한 포인터입니다.

*크기*\
문자 단위의 버퍼 크기입니다.

## <a name="return-value"></a>반환 값

성공할 경우 0입니다. 오류 발생 시 반환 값은 오류 코드입니다. 오류 코드는 ERRNO.H에 정의됩니다. 이 함수가 생성하는 정확한 오류는 아래 표를 참조하세요. 오류 코드에 대한 자세한 내용은 [errno](../../c-runtime-library/errno-constants.md)를 참조하세요.

## <a name="error-conditions"></a>오류 조건

|*버퍼*|*크기*|반환 값|*버퍼의* 내용|
|--------------|------------------------|------------|--------------------------|
|**Null**|(임의)|**아인발 ()에인발 (것)**|수정 안 됨|
|**NULL이** 아님(유효한 버퍼를 가리키는)|0|**아인발 ()에인발 (것)**|수정 안 됨|
|**NULL이** 아님(유효한 버퍼를 가리키는)|0 < *크기* < 9|**아인발 ()에인발 (것)**|빈 문자열|
|**NULL이** 아님(유효한 버퍼를 가리키는)|*크기* >= 9|0|설명에 지정된 형식의 현재 날짜|

## <a name="security-issues"></a>보안 문제

크기 *매개* 변수가 9보다 큰 경우 *버퍼에* 대해 유효하지 않은 NULL 이없는 값을 전달하면 액세스 위반이 발생합니다.

실제 *버퍼* 크기보다 큰 *크기에* 대한 값을 전달하면 버퍼 오버런이 발생합니다.

## <a name="remarks"></a>설명

이러한 함수는 **_strdate** 및 **_wstrdate**보다 안전한 버전을 제공합니다. **_strdate_s** 함수는 현재 시스템 날짜를 *버퍼로*가리키는 버퍼로 복사합니다. 두 `mm/dd/yy`자리 `mm` 월의 `dd` 형식은 두 자리 일이며 올해의 마지막 두 `yy` 자리입니다. 예를 들어 `12/05/99` 문자열은 1999년 12월 5일을 나타냅니다. 버퍼의 길이는 9자 이상이어야 합니다.

**_wstrdate_s** **_strdate_s**와이드 문자 버전입니다. **_wstrdate_s** 인수 및 반환 값은 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

*버퍼가* **NULL** 포인터이거나 *크기가* 9자 미만이면 잘못된 매개 변수 처리기가 호출됩니다. [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명되어 있습니다. 실행을 계속할 수 있는 경우 이러한 함수는 -1을 반환합니다. 버퍼가 **NULL이거나** *크기가* 0보다 작거나 같으면 **errno를** **EINVAL로** 설정합니다. 또는 *크기가* 9보다 작으면 **errno를** **ERANGE로** 설정합니다.

C++에서는 이러한 함수의 사용이 템플릿 오버로드로 단순화됩니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있어 *크기* 인수를 지정할 필요가 없습니다. 또한 안전하지 않은 기능을 보다 새롭고 안전한 기능으로 자동으로 대체할 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

이러한 함수의 디버그 라이브러리 버전은 먼저 버퍼를 0xFE로 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mapping"></a>일반 텍스트 루틴 매핑:

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_strdate**|\<time.h>|
|**_wstrdate**|\<time.h> 또는 \<wchar.h>|
|**_strdate_s**|\<time.h>|

## <a name="example"></a>예제

[time](time-time32-time64.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[시간 관리](../../c-runtime-library/time-management.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[시간, _time32, _time64](time-time32-time64.md)\
[_tzset](tzset.md)
