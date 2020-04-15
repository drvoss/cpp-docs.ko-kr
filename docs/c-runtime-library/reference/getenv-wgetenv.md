---
title: getenv, _wgetenv
description: Microsoft C 런타임 라이브러리 getenv _wgetenv 및 함수에 대해 설명합니다.
ms.date: 4/2/2020
api_name:
- getenv
- _wgetenv
- _o__wgetenv
- _o_getenv
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wgetenv
- getenv
- _tgetenv
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
no-loc:
- getenv
- _wgetenv
- getenv_s
- _wgetenv_s
- _putenv_s
- main
- wmain
- errno
- EINVAL
- ERANGE
- _environ
- _wenviron
- _putenv
- _wputenv
- _tgetenv_s
- _tzset
- _dupenv_s
- _wdupenv_s
ms.openlocfilehash: c9d7f7e1a2c5d6b15aee2f7f972a30cc0c90115c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344248"
---
# <a name="getenv-_wgetenv"></a>getenv, _wgetenv

현재 환경에서 값을 가져옵니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)를 참조하세요.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *getenv(
   const char *varname
);
wchar_t *_wgetenv(
   const wchar_t *varname
);
```

### <a name="parameters"></a>매개 변수

*바르나메*<br/>
환경 변수 이름입니다.

## <a name="return-value"></a>반환 값

*varname을*포함 하는 환경 테이블 항목에 대 한 포인터를 반환 합니다. 반환된 포인터를 사용하여 환경 변수의 값을 수정하는 것은 안전하지 않습니다. [_putenv](putenv-wputenv.md) 함수를 사용하여 환경 변수의 값을 수정합니다. 환경 테이블에서 *varname을* 찾을 수 없는 경우 반환 값은 **NULL입니다.**

## <a name="remarks"></a>설명

**getenv** 함수는 *varname에*대한 환경 변수 목록을 검색합니다. **getenv는** Windows 운영 체제에서 대소문자를 구분하지 않습니다. **getenv** 및 **_putenv** 환경에 액세스하기 위해 **_environ** 전역 변수가 가리키는 환경의 복사본을 사용합니다. **getenv는** 운영 체제에서 프로세스에 대해 생성된 환경 "세그먼트"가 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조에서만 작동합니다. 따라서 *envp* 인수를 [main](../../cpp/main-function-command-line-args.md) 또는 [wmain에](../../cpp/main-function-command-line-args.md) 사용하는 프로그램은 잘못된 정보를 검색할 수 있습니다.

*varname이* **NULL인**경우 이 함수는 매개 변수 유효성 [검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이 함수는 **errno를** **EINVAL로** 설정하고 **NULL**을 반환합니다.

**_wgetenv** **getenv의**넓은 문자 버전입니다; **_wgetenv** 인수 및 반환 값은 와이드 문자 문자열입니다. **_wenviron** 전역 변수는 **_environ**의 와이드 문자 버전입니다.

MBCS 프로그램(예: SBCS ASCII 프로그램에서)에서 **환경이** 다중 바이트 문자 문자열로 구성되므로 _wenviron 처음에는 **NULL입니다.** 그런 다음 [_wputenv](putenv-wputenv.md)첫 번째 호출에서 또는 (MBCS) 환경이 이미 있는 경우 **_wgetenv** 첫 번째 호출에서 해당 와이드 문자 문자열 환경이 만들어지고 **_wenviron**의해 가리켜요.

마찬가지로 유니코드 **(_wmain)** 프로그램에서 환경은 와이드 문자 문자열로 구성되어 있기 때문에 **_environ** 처음에는 **NULL입니다.** 그런 다음 **_putenv**첫 번째 호출에서 또는 (유니코드) 환경이 이미 존재하는 경우 **getenv에** 대한 첫 번째 호출에서 해당 MBCS 환경이 만들어지고 **_environ**의해 가리켜요.

환경의 두 개의 복사본(MBCS 및 유니코드)이 프로그램에 동시에 존재하는 경우 런타임 시스템은 두 복사본을 모두 유지해야 하며 이에 따라 실행 시간이 늦어집니다. 예를 들어 **_putenv**호출할 때마다 두 환경 문자열이 일치하도록 **_wputenv** 호출도 자동으로 실행됩니다.

> [!CAUTION]
> 드문 경우지만, 런타임 시스템이 유니코드 버전과 멀티바이트 버전의 환경을 모두 유지할 때 이러한 두 환경 버전이 정확히 일치하지 않을 수도 있습니다. 이는 고유한 멀티바이트 문자열이 고유한 유지코드 문자열에 매핑되지만 고유 유니코드 문자열에서 멀티바이트 문자열로 매핑이 반드시 고유하지는 않기 때문입니다. 자세한 내용은 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)을 참조하세요.

> [!NOTE]
> **함수의 _putenv** 및 **_getenv** 패밀리는 스레드에서 안전하지 않습니다. **_getenv** **_putenv** 문자열을 수정하는 동안 문자열 포인터를 반환하여 임의의 오류가 발생할 수 있습니다. 이러한 함수에 대한 호출은 동기화해야 합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

**TZ** 환경 변수의 값을 확인하거나 변경하려면 **getenv**, **_putenv** 사용하고 필요에 따라 **_tzset.** **TZ에**대한 자세한 내용은 [_tzset](tzset.md) 및 [_daylight, 시간대 및 _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)를 참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**getenv**|\<stdlib.h>|
|**_wgetenv**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_getenv.c
// compile with: /W3
// This program uses getenv to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *libvar;

   // Get the value of the LIB environment variable.
   libvar = getenv( "LIB" ); // C4996
   // Note: getenv is deprecated; consider using getenv_s instead

   if( libvar != NULL )
      printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects the environment
   // variable of the current process. The command processor's
   // environment is not changed.
   _putenv( "LIB=c:\\mylib;c:\\yourlib" ); // C4996
   // Note: _putenv is deprecated; consider using putenv_s instead

   // Get new value.
   libvar = getenv( "LIB" ); // C4996

   if( libvar != NULL )
      printf( "New LIB variable is: %s\n", libvar );
}
```

```Output
Original LIB variable is: C:\progra~1\devstu~1\vc\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>참고 항목

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[환경 상수](../../c-runtime-library/environmental-constants.md)<br/>
