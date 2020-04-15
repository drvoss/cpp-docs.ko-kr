---
title: _searchenv_s, _wsearchenv_s
ms.date: 4/2/2020
api_name:
- _wsearchenv_s
- _searchenv_s
- _o__searchenv_s
- _o__wsearchenv_s
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
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
ms.openlocfilehash: 3d526c546e1496b3b13b14a12c9025cbd0347cd2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332396"
---
# <a name="_searchenv_s-_wsearchenv_s"></a>_searchenv_s, _wsearchenv_s

환경 경로를 사용하여 파일을 검색합니다. 이러한 버전의 [_searchenv, _wsearchenv](searchenv-wsearchenv.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char *pathname,
   size_t numberOfElements
);
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname,
   size_t numberOfElements
);
template <size_t size>
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t (&pathname)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*파일*<br/>
검색할 파일의 이름입니다.

*바르나메*<br/>
검색할 환경입니다.

*경로*<br/>
전체 경로를 저장할 버퍼입니다.

*숫자오브엘리먼트*<br/>
*경로 이름* 버퍼의 크기입니다.

## <a name="return-value"></a>Return Value

성공 시 0이고, 실패 시 오류 코드입니다.

*파일 이름이* 빈 문자열인 경우 반환 값은 **ENOENT**입니다.

### <a name="error-conditions"></a>오류 조건

|*파일*|*바르나메*|*경로*|*숫자오브엘리먼트*|반환 값|*경로 이름의* 내용|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|any|any|**Null**|any|**아인발 ()에인발 (것)**|해당 없음|
|**Null**|any|any|any|**아인발 ()에인발 (것)**|변경되지 않음|
|any|any|any|<= 0|**아인발 ()에인발 (것)**|변경되지 않음|

이러한 조건 중 하나라도 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 발생합니다. 실행을 계속할 수 있는 경우 이러한 함수는 **errno를** **EINVAL로** 설정하고 **EINVAL을**반환합니다.

## <a name="remarks"></a>설명

**_searchenv_s** 루틴은 지정된 도메인의 대상 파일을 검색합니다. *varname* 변수는 **PATH,** **LIB**및 **INCLUDE와**같은 디렉터리 경로 목록을 지정하는 모든 환경 또는 사용자 정의 변수일 수 있습니다. **_searchenv_s** 대/소문자를 구분하기 때문에 *varname은* 환경 변수의 대/소문자와 일치해야 합니다. *varname이* 프로세스 환경에 정의된 환경 변수의 이름과 일치하지 않으면 함수가 0을 반환하고 *pathname* 변수는 변경되지 않습니다.

루틴은 먼저 현재 작업 디렉터리에서 파일을 검색합니다. 파일을 찾을 수 없는 경우 다음 위치로 환경 변수에 지정된 디렉터리를 확인합니다. 대상 파일이 해당 디렉터리 중 하나에 있으면 새로 만든 경로가 *pathname로*복사됩니다. 파일 *이름* 파일을 찾을 수 없는 경우 *pathname빈* null-종료 된 문자열을 포함 합니다.

*경로 이름* 버퍼는 생성된 경로 이름의 전체 길이를 수용하기 위해 적어도 **_MAX_PATH** 문자여야 합니다. 그렇지 않으면 **_searchenv_s** *경로 이름* 버퍼를 오버런하여 예기치 않은 동작이 발생할 수 있습니다.

**_wsearchenv_s** **_searchenv_s**와이드 문자 버전입니다. **_wsearchenv_s** 인수는 와이드 문자 문자열입니다. **_wsearchenv_s** **_searchenv_s** 달리 동일하게 행동합니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv_s**|**_searchenv_s**|**_searchenv_s**|**_wsearchenv_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_searchenv_s**|\<stdlib.h>|
|**_wsearchenv_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_searchenv_s.c
/* This program searches for a file in
* a directory specified by an environment variable.
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";
   errno_t err;

   /* Search for file in PATH environment variable: */
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );
   if (err != 0)
   {
      printf("Error searching the path. Error code: %d\n", err);
   }
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE
```

## <a name="see-also"></a>참고 항목

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
