---
title: getenv_s, _wgetenv_s
description: Microsoft C 런타임 라이브러리 getenv_s _wgetenv_s 및 함수에 대해 설명합니다.
ms.date: 4/2/2020
api_name:
- getenv_s
- _wgetenv_s
- _o__wgetenv_s
- _o_getenv_s
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
- getenv_s
- _tgetenv_s
- _wgetenv_s
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
no-loc:
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
ms.openlocfilehash: 17c4e001f7f4637f6f66f218c94378368976901f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344285"
---
# <a name="getenv_s-_wgetenv_s"></a>getenv_s, _wgetenv_s

현재 환경에서 값을 가져옵니다. 이러한 버전의 [getenv, _wgetenv](getenv-wgetenv.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t getenv_s(
   size_t *pReturnValue,
   char* buffer,
   size_t numberOfElements,
   const char *varname
);
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *varname
);
template <size_t size>
errno_t getenv_s(
   size_t *pReturnValue,
   char (&buffer)[size],
   const char *varname
); // C++ only
template <size_t size>
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t (&buffer)[size],
   const wchar_t *varname
); // C++ only
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
필요한 버퍼 크기이거나, 변수가 없으면 0입니다.

*버퍼*<br/>
환경 변수의 값을 저장할 버퍼입니다.

*숫자오브엘리먼트*<br/>
*버퍼의*크기 .

*바르나메*<br/>
환경 변수 이름입니다.

## <a name="return-value"></a>Return Value

성공하면 0이고, 그렇지 않으면 실패 시 오류 코드입니다.

### <a name="error-conditions"></a>오류 조건

|*pReturnValue*|*버퍼*|*숫자오브엘리먼트*|*바르나메*|Return Value|
|--------------------|--------------|------------------------|---------------|------------------|
|**Null**|any|any|any|**아인발 ()에인발 (것)**|
|any|**Null**|>0|any|**아인발 ()에인발 (것)**|
|any|any|any|**Null**|**아인발 ()에인발 (것)**|

이들 오류 조건은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 함수는 **errno를** **EINVAL로** 설정하고 **EINVAL을**반환합니다.

또한 버퍼가 너무 작으면 이러한 함수가 **ERANGE**를 반환합니다. 잘못된 매개 변수 처리기를 호출하지 않습니다. *그들은 pReturnValue에*필요한 버퍼 크기를 기록 하 고 따라서 더 큰 버퍼와 함수를 다시 호출 하는 프로그램을 사용 합니다.

## <a name="remarks"></a>설명

**getenv_s** 함수는 *varname에*대한 환경 변수 목록을 검색합니다. **getenv_s** Windows 운영 체제에서 대소문자를 구분하지 않습니다. **getenv_s** 및 [_putenv_s](putenv-s-wputenv-s.md) _environ 전역 **변수가** 가리키는 환경의 복사본을 사용하여 환경에 액세스합니다. **getenv_s** 운영 체제에서 프로세스에 대해 생성된 환경 "세그먼트"가 아닌 런타임 라이브러리에 액세스할 수 있는 데이터 구조에서만 작동합니다. 따라서 *envp* 인수를 [main](../../cpp/main-function-command-line-args.md) 또는 [wmain에](../../cpp/main-function-command-line-args.md) 사용하는 프로그램은 잘못된 정보를 검색할 수 있습니다.

**_wgetenv_s** **getenv_s**와이드 문자 버전입니다. **_wgetenv_s** 인수 및 반환 값은 와이드 문자 문자열입니다. **_wenviron** 전역 변수는 **_environ**의 와이드 문자 버전입니다.

MBCS 프로그램(예: SBCS ASCII 프로그램에서)에서 **환경이** 다중 바이트 문자 문자열로 구성되므로 _wenviron 처음에는 **NULL입니다.** 그런 다음 [_wputenv](putenv-wputenv.md)첫 번째 호출에서 또는 **_wgetenv_s**대한 첫 번째 호출에서 (MBCS) 환경이 이미 있는 경우 해당 와이드 문자 문자열 환경이 만들어지고 **_wenviron**의해 가리켜요.

마찬가지로 유니코드 **(_wmain)** 프로그램에서 환경은 와이드 문자 문자열로 구성되어 있기 때문에 **_environ** 처음에는 **NULL입니다.** 그런 다음 [_putenv](putenv-wputenv.md)첫 번째 호출에서 또는 (유니코드) 환경이 이미 있는 경우 **getenv_s** 첫 번째 호출에서 해당 MBCS 환경이 만들어지고 **_environ**의해 가리켜요.

환경의 두 개의 복사본(MBCS 및 유니코드)이 프로그램에 동시에 존재하는 경우 런타임 시스템은 두 복사본을 모두 유지해야 하며 이로 인해 실행 시간이 늦어집니다. 예를 들어 **_putenv**호출할 때 두 환경 문자열이 일치하도록 **_wputenv** 호출도 자동으로 실행됩니다.

> [!CAUTION]
> 드문 경우지만, 런타임 시스템이 유니코드 버전과 멀티바이트 버전의 환경을 모두 유지할 때 두 환경 버전이 정확히 일치하지 않을 수도 있습니다. 이는 고유한 멀티바이트 문자열이 고유한 유지코드 문자열에 매핑되지만 고유 유니코드 문자열에서 멀티바이트 문자열로 매핑이 반드시 고유하지는 않기 때문에 발생합니다. 자세한 내용은 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)을 참조하세요.

> [!NOTE]
> **함수의 _putenv_s** 및 **_getenv_s** 패밀리는 스레드에서 안전하지 않습니다. **_getenv_s** _putenv_s 문자열을 **_putenv_s** 수정하는 동안 문자열 포인터를 반환하여 임의 의 실패를 일으킬 수 있습니다. 이러한 함수에 대한 호출은 동기화해야 합니다.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 보다 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

**TZ** 환경 변수의 값을 확인하거나 변경하려면 필요에 따라 **getenv_s** **_putenv**및 **_tzset**사용합니다. **TZ에**대한 자세한 내용은 [_tzset](tzset.md) 및 [_daylight, _dstbias, _timezone 및 _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)를 참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**getenv_s**|\<stdlib.h>|
|**_wgetenv_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_getenv_s.c
// This program uses getenv_s to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* libvar;
   size_t requiredSize;

   getenv_s( &requiredSize, NULL, 0, "LIB");
   if (requiredSize == 0)
   {
      printf("LIB doesn't exist!\n");
      exit(1);
   }

   libvar = (char*) malloc(requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects
   // the environment variable of the current process. The command
   // processor's environment is not changed.
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );

   getenv_s( &requiredSize, NULL, 0, "LIB");

   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the new value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "New LIB variable is: %s\n", libvar );

   free(libvar);
}
```

```Output
Original LIB variable is: c:\vctools\lib;c:\vctools\atlmfc\lib;c:\vctools\PlatformSDK\lib;c:\vctools\Visual Studio SDKs\DIA Sdk\lib;c:\vctools\Visual Studio SDKs\BSC Sdk\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>참고 항목

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[환경 상수](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
