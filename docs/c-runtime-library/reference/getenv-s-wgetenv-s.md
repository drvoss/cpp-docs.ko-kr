---
title: getenv_s, _wgetenv_s
description: Microsoft C 런타임 라이브러리 getenv_s 및 _wgetenv_s 함수에 대해 설명 합니다.
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 0713ed5735916c31edaab1a178a5e9b1b7cf5377
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913675"
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

*이면 numberofelements 이벤트가*<br/>
*버퍼*의 크기입니다.

*varname*<br/>
환경 변수 이름입니다.

## <a name="return-value"></a>Return Value

성공하면 0이고, 그렇지 않으면 실패 시 오류 코드입니다.

### <a name="error-conditions"></a>오류 조건

|*pReturnValue*|*버퍼*|*이면 numberofelements 이벤트가*|*varname*|Return Value|
|--------------------|--------------|------------------------|---------------|------------------|
|**N**|any|any|any|**EINVAL**|
|any|**N**|>0|any|**EINVAL**|
|any|any|any|**N**|**EINVAL**|

이들 오류 조건은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 **errno** 를 **EINVAL** 로 설정 하 고 **EINVAL**를 반환 합니다.

또한 버퍼가 너무 작으면이 함수는 **ERANGE**를 반환 합니다. 잘못된 매개 변수 처리기를 호출하지 않습니다. *PReturnValue*에서 필요한 버퍼 크기를 작성 하므로 프로그램이 더 큰 버퍼를 사용 하 여 함수를 다시 호출할 수 있습니다.

## <a name="remarks"></a>설명

**Getenv_s** 함수는 *varname*에 대 한 환경 변수 목록을 검색 합니다. **getenv_s** 은 Windows 운영 체제에서 대/소문자를 구분 하지 않습니다. **getenv_s** 및 [_putenv_s](putenv-s-wputenv-s.md) 전역 변수 **_environ** 에서 가리키는 환경의 복사본을 사용 하 여 환경에 액세스 합니다. **getenv_s** 는 운영 체제에서 프로세스에 대해 만드는 환경 "세그먼트"가 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조 에서만 작동 합니다. 따라서 [main](../../cpp/main-function-command-line-args.md) 또는 [wmain](../../cpp/main-function-command-line-args.md) 에 *envp* 인수를 사용 하는 프로그램은 잘못 된 정보를 검색할 수 있습니다.

**_wgetenv_s** 은 **getenv_s**의 와이드 문자 버전입니다. **_wgetenv_s** 의 인수 및 반환 값은 와이드 문자 문자열입니다. **_Wenviron** 전역 변수는 **_environ**의 와이드 문자 버전입니다.

MBCS 프로그램 (예: SBCS ASCII 프로그램)에서 환경은 멀티 바이트 문자열로 구성 되기 때문에 **_wenviron** 처음에는 **NULL** 입니다. 그런 다음 [_wputenv](putenv-wputenv.md)에 대 한 첫 번째 호출 또는 **_wgetenv_s**에 대 한 첫 번째 호출에서 (MBCS) 환경이 이미 있는 경우 해당 와이드 문자 문자열 환경이 만들어지고 **_wenviron**에서 가리킵니다.

마찬가지로 유니코드 (**_wmain**) 프로그램에서 환경이 와이드 문자열로 구성 되기 때문에 **_environ** 는 처음에 **NULL** 입니다. 그런 다음 [_putenv](putenv-wputenv.md)에 대 한 첫 번째 호출 또는 **getenv_s** 에 대 한 첫 번째 호출에서 (유니코드) 환경이 이미 있는 경우 해당 MBCS 환경이 만들어지고 **_environ**에서이를 가리킵니다.

환경의 두 개의 복사본(MBCS 및 유니코드)이 프로그램에 동시에 존재하는 경우 런타임 시스템은 두 복사본을 모두 유지해야 하며 이로 인해 실행 시간이 늦어집니다. 예를 들어 **_putenv**를 호출 하는 경우에는 **_wputenv** 에 대 한 호출도 자동으로 실행 되어 두 환경 문자열이 일치 하 게 됩니다.

> [!CAUTION]
> 드문 경우지만, 런타임 시스템이 유니코드 버전과 멀티바이트 버전의 환경을 모두 유지할 때 두 환경 버전이 정확히 일치하지 않을 수도 있습니다. 이는 고유한 멀티바이트 문자열이 고유한 유지코드 문자열에 매핑되지만 고유 유니코드 문자열에서 멀티바이트 문자열로 매핑이 반드시 고유하지는 않기 때문에 발생합니다. 자세한 내용은 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)을 참조하세요.

> [!NOTE]
> **_Putenv_s** 및 **_getenv_s** 함수 패밀리는 스레드로부터 안전 하지 않습니다. **_putenv_s** 문자열을 수정 하는 동안 **_getenv_s** 는 문자열 포인터를 반환할 수 있으므로 임의 오류가 발생 합니다. 이러한 함수에 대한 호출은 동기화해야 합니다.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 보다 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

**TZ** 환경 변수의 값을 확인 하거나 변경 하려면 필요에 따라 **getenv_s**, **_putenv**및 **_tzset**를 사용 합니다. **TZ**에 대 한 자세한 내용은 [_tzset](tzset.md) 및 [_daylight, _dstbias, _timezone 및 _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)을 참조 하세요.

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

## <a name="see-also"></a>참조

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[환경 상수](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
