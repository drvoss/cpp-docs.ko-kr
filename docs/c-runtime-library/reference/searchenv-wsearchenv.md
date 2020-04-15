---
title: _searchenv, _wsearchenv
ms.date: 4/2/2020
api_name:
- _searchenv
- _wsearchenv
- _o__searchenv
- _o__wsearchenv
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
- _wsearchenv
- _tsearchenv
- wsearchenv
- _searchenv
- searchenv
helpviewer_keywords:
- _wsearchenv function
- files [C++], finding
- _searchenv function
- tsearchenv function
- environment paths, searching for files
- _tsearchenv function
- wsearchenv function
- searchenv function
- environment paths
ms.assetid: 9c944a27-d326-409b-aee6-410e8762d9d3
ms.openlocfilehash: 22a8ca8fa7e56a84289d7e90ffb519073f006b5c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332386"
---
# <a name="_searchenv-_wsearchenv"></a>_searchenv, _wsearchenv

환경 경로를 사용하여 파일을 검색합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md)를 참조하세요.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void _searchenv(
   const char *filename,
   const char *varname,
   char *pathname
);
void _wsearchenv(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname
);
template <size_t size>
void _searchenv(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
void _wsearchenv(
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

## <a name="remarks"></a>설명

**_searchenv** 루틴은 지정된 도메인의 대상 파일을 검색합니다. *varname* 변수는 디렉터리 경로 목록을 지정하는 환경 또는 사용자 정의 변수(예: **PATH,** **LIB**또는 **INCLUDE)일**수 있습니다. **_searchenv** 대/소문자를 구분하기 때문에 *varname은* 환경 변수의 대/소문자와 일치해야 합니다.

루틴은 먼저 현재 작업 디렉터리에서 파일을 검색합니다. 파일을 찾을 수 없는 경우 환경 변수에 지정된 디렉터리에서 찾습니다. 대상 파일이 해당 디렉터리 중 하나에 있으면 새로 만든 경로가 *pathname로*복사됩니다. 파일 *이름* 파일을 찾을 수 없는 경우 *pathname빈* null-종료 된 문자열을 포함 합니다.

*경로 이름* 버퍼는 생성된 경로 이름의 전체 길이를 수용하기 위해 적어도 **_MAX_PATH** 문자여야 합니다. 그렇지 않으면 **_searchenv** *경로 이름* 버퍼를 오버런하고 예기치 않은 동작이 발생할 수 있습니다.

**_wsearchenv** **_searchenv**와이드 문자 버전이며 **_wsearchenv** 인수는 와이드 문자 문자열입니다. **_wsearchenv** **_searchenv** 달리 동일하게 행동합니다.

*파일 이름이* 빈 문자열인 경우 이러한 함수는 **ENOENT**를 반환합니다.

*파일 이름* 또는 *pathname이* **NULL** 포인터인 경우 매개 변수 유효성 [검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 이러한 함수는 -1을 반환하고 **errno를** **EINVAL로**설정합니다.

**errno** 및 오류 코드에 대한 자세한 내용은 [errno 상수](../../c-runtime-library/errno-constants.md)를 참조하십시오.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv**|**_searchenv**|**_searchenv**|**_wsearchenv**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_searchenv**|\<stdlib.h>|
|**_wsearchenv**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_searchenv.c
// compile with: /W3
// This program searches for a file in
// a directory that's specified by an environment variable.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";

   // Search for file in PATH environment variable:
   _searchenv( searchfile, envvar, pathbuffer ); // C4996
   // Note: _searchenv is deprecated; consider using _searchenv_s
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 8\VC\BIN\CL.EXE
```

## <a name="see-also"></a>참고 항목

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md)<br/>
