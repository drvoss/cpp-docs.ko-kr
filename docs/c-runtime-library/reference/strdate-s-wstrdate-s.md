---
title: _strdate_s, _wstrdate_s
description: _strdate_s 및 _wstrdate_s는 _strdate의 보안 CRT 버전과 현재 날짜를 버퍼에 넣는 _wstrdate 함수의 보안입니다.
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 7fe8d682ab515d5a11e90f0c26e956725644806e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916911"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

현재 시스템 날짜를 버퍼에 복사합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명 된 대로 보안 기능이 향상 된 [_wstrdate _strdate](strdate-wstrdate.md) 버전입니다.

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
형식이 지정 된 날짜 문자열을 넣을 버퍼에 대 한 포인터입니다.

*크기가*\
문자 단위의 버퍼 크기입니다.

## <a name="return-value"></a>반환 값

성공할 경우 0입니다. 오류가 있는 경우 반환 값은 오류 코드입니다. 오류 코드는 ERRNO.H에 정의됩니다. 이 함수가 생성하는 정확한 오류는 아래 표를 참조하세요. 오류 코드에 대한 자세한 내용은 [errno](../../c-runtime-library/errno-constants.md)를 참조하세요.

## <a name="error-conditions"></a>오류 조건

|*버퍼*|*size*|반환 값|*버퍼* 의 내용|
|--------------|------------------------|------------|--------------------------|
|**N**|(임의)|**EINVAL**|수정 안 됨|
|Not **NULL** (올바른 버퍼를 가리킴)|0|**EINVAL**|수정 안 됨|
|Not **NULL** (올바른 버퍼를 가리킴)|0 < *크기* < 9|**EINVAL**|빈 문자열|
|Not **NULL** (올바른 버퍼를 가리킴)|*크기* >= 9|0|설명에 지정된 형식의 현재 날짜|

## <a name="security-issues"></a>보안 문제

*버퍼* 에 대해 NULL이 아닌 잘못 된 값을 전달 하면 *크기* 매개 변수가 9 보다 크면 액세스 위반이 발생 합니다.

*크기* 값을 *버퍼* 의 실제 크기 보다 크게 전달 하면 버퍼 오버런이 발생 합니다.

## <a name="remarks"></a>설명

이러한 함수는 보다 안전한 버전의 **_strdate** 및 **_wstrdate**를 제공 합니다. **_Strdate_s** 함수는 현재 시스템 날짜를 *버퍼*에 의해 가리키는 버퍼에 복사 합니다. 형식이 지정 `mm/dd/yy`됩니다. 여기서 `mm` 은 두 자리 월, `dd` 는 두 자리 일, `yy` 는 연도의 마지막 두 자리 숫자입니다. 예를 들어 `12/05/99` 문자열은 1999년 12월 5일을 나타냅니다. 버퍼의 길이는 9 자 이상 이어야 합니다.

**_wstrdate_s** 은 **_strdate_s**의 와이드 문자 버전입니다. **_wstrdate_s** 의 인수 및 반환 값은 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

*버퍼가* **NULL** 포인터 이거나 *크기가* 9 자 미만이 면 잘못 된 매개 변수 처리기가 호출 됩니다. [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 되어 있습니다. 계속 해 서 실행 하도록 허용한 경우 이러한 함수는-1을 반환 합니다. 버퍼가 **NULL** 이거나 *크기가* 0 보다 작거나 같은 경우 **errno** 를 **EINVAL** 로 설정 합니다. 또는 *크기가* 9 보다 작은 경우 **errno** 을 **ERANGE** 로 설정 합니다.

C + +에서는 템플릿 오버 로드로 이러한 함수를 사용 하는 것이 더 간단 합니다. 오버 로드는 버퍼 길이를 자동으로 유추할 수 있으므로 *크기* 인수를 지정할 필요가 없습니다. 또한 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

이러한 함수의 디버그 라이브러리 버전은 먼저 0xFE를 사용 하 여 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

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

## <a name="see-also"></a>참조

[시간 관리](../../c-runtime-library/time-management.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[시간, _time32, _time64](time-time32-time64.md)\
[_tzset](tzset.md)
