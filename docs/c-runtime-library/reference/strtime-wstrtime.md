---
title: _strtime, _wstrtime
ms.date: 4/2/2020
api_name:
- _wstrtime
- _strtime
- _o__strtime
- _o__wstrtime
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
- _wstrtime
- _strtime
- wstrtime
- strtime
- _tstrtime
helpviewer_keywords:
- strtime function
- _strtime function
- _wstrtime function
- copying time to buffers
- wstrtime function
- tstrtime function
- _tstrtime function
- time, copying
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
ms.openlocfilehash: 827e5a579d801c12b932440fcbbaa18343ad7ece
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316876"
---
# <a name="_strtime-_wstrtime"></a>_strtime, _wstrtime

버퍼에 시간을 복사합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_strtime_s, _wstrtime_s](strtime-s-wstrtime-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_strtime(
   char *timestr
);
wchar_t *_wstrtime(
   wchar_t *timestr
);
template <size_t size>
char *_strtime(
   char (&timestr)[size]
); // C++ only
template <size_t size>
wchar_t *_wstrtime(
   wchar_t (&timestr)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*타임스트*<br/>
시간 문자열입니다.

## <a name="return-value"></a>Return Value

결과 문자 문자열 *timestr에*대한 포인터를 반환합니다.

## <a name="remarks"></a>설명

**_strtime** 함수는 현재 현지 시간을 *timestr로*가리키는 버퍼에 복사합니다. 시간은 **hh:mm:ss로** 서식이 지정되며 **hh는** 24시간 표기의 시간을 나타내는 두 자리이고, **mm은** 시간 지난 분을 나타내는 두 자리숫자이고, **ss는** 초를 나타내는 두 자리숫자입니다. 예를 들어 문자열 **18:23:44는** 오후 6시 이후 23분 44초를 나타냅니다. 버퍼는 9바이트 이상이어야 합니다.

**_wstrtime** **_strtime**와이드 문자 버전입니다. **_wstrtime** 인수 및 반환 값은 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다. *timestr이* **NULL** 포인터이거나 *timestr이* 잘못 서식이 지정된 경우 [매개 변수 유효성 검사기에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 예외가 계속 될 수 있는 경우 이러한 함수는 **NULL을** 반환하고 *timestr이* **NULL인** 경우 **errno를** **EINVAL로** 설정하거나 *timestr이* 잘못 서식이 지정된 경우 **Errno를** **ERANGE로** 설정합니다.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime**|**_strtime**|**_strtime**|**_wstrtime**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_strtime**|\<time.h>|
|**_wstrtime**|\<time.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strtime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
   char tbuffer [9];
   _strtime( tbuffer ); // C4996
   // Note: _strtime is deprecated; consider using _strtime_s instead
   printf( "The current time is %s \n", tbuffer );
}
```

```Output
The current time is 14:21:44
```

## <a name="see-also"></a>참고 항목

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
