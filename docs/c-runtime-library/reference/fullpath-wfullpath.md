---
title: _fullpath, _wfullpath
ms.date: 4/2/2020
api_name:
- _fullpath
- _wfullpath
- _o__fullpath
- _o__wfullpath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wfullpath
- fullpath
- _wfullpath
- _fullpath
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
ms.openlocfilehash: 0910cf4f39e00be84e683cd6f3b9afbeb3f2a749
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345494"
---
# <a name="_fullpath-_wfullpath"></a>_fullpath, _wfullpath

지정된 상대 경로 이름의 절대 또는 전체 경로 이름을 만듭니다.

## <a name="syntax"></a>구문

```C
char *_fullpath(
   char *absPath,
   const char *relPath,
   size_t maxLength
);
wchar_t *_wfullpath(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength
);
```

### <a name="parameters"></a>매개 변수

*abspath*<br/>
절대 또는 전체 경로 이름 또는 **NULL을**포함하는 버퍼에 대한 포인터 .

*릴 패스*<br/>
상대 경로 이름입니다.

*maxLength*<br/>
절대 경로 이름*버퍼(absPath)의*최대 길이입니다. 이 길이는 **_fullpath** 바이트이지만 **_wfullpath**경우 와이드 문자 **(wchar_t)입니다.**

## <a name="return-value"></a>Return Value

이러한 각 함수는 절대 경로*이름(absPath)을*포함하는 버퍼에 대한 포인터를 반환합니다. 오류가 있는 경우(예: *relPath에서* 전달된 값에 유효하지 않거나 찾을 수 없는 드라이브 문자가 포함되어 있거나 생성된 절대 경로*이름(absPath)의*길이가 *maxLength보다*큰 경우 함수는 **NULL을**반환합니다.

## <a name="remarks"></a>설명

**_fullpath** 함수는 *relPath의* 상대 경로 이름을 정규화 또는 절대 경로로 확장하고 이 이름을 *absPath에*저장합니다. *absPath가* **NULL인**경우 **malloc는** 경로 이름을 보유하기에 충분한 길이의 버퍼를 할당하는 데 사용됩니다. 호출자가 이 버퍼를 해제해야 합니다. 상대 경로 이름은 현재 위치에서 시작되는 또 다른 위치에 대한 경로를 지정합니다(예: 현재 작업 디렉터리: "."). 절대 경로 이름은 파일 시스템의 루트에서 원하는 위치에 도달하는 데 필요한 전체 경로를 설명하는 상태 경로 이름의 확장입니다. **_makepath**달리 **_fullpath** "./" 또는 "를 포함하는 상대*경로(relPath)에*대한 절대 경로 이름을 얻는 데 사용할 수 있습니다. /"를 자신의 이름으로

예를 들어 C 런타임 루틴을 사용하려면 루틴 선언이 들어 있는 헤더 파일을 애플리케이션에 포함해야 합니다. 각 헤더 파일의 include 문은 애플리케이션 작업 디렉터리를 기준으로 한 상대적 방식으로 파일 위치를 참조합니다.

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <stdlib.h>
```

파일의 절대 경로(실제 파일 시스템 위치)가 다음과 같을 경우:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** 현재 사용 중인 다중 바이트 코드 페이지에 따라 다중 바이트 문자 시퀀스를 인식하여 적절한 다중 바이트 문자열 인수를 자동으로 처리합니다. **_wfullpath** **_fullpath**와이드 문자 버전입니다. **_wfullpath** 문자열 인수는 와이드 문자 문자열입니다. **_wfullpath** 멀티바이트 문자 문자열을 **_wfullpath** 처리하지 않는다는 점을 제외하면 _wfullpath **_fullpath** 동일하게 작동합니다.

**_DEBUG** **_CRTDBG_MAP_ALLOC** 모두 정의된 경우 **_fullpath** **및 _wfullpath** 대한 호출은 **_fullpath_dbg** 호출로 대체되고 **메모리** 할당을 _wfullpath_dbg. 자세한 내용은 [_fullpath_dbg, _wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md)를 참조하세요.

*maxlen이* 0보다 크거나 같으면 이 함수는 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이 함수는 **errno를** **EINVAL로** 설정하고 **NULL**을 반환합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

*absPath* 버퍼가 **NULL인**경우 **_fullpath** [malloc을](malloc.md) 호출하여 버퍼를 할당하고 *maxLength* 인수를 무시합니다. 호출자는 [free](free.md)를 사용하여 이 버퍼를 적절하게 할당 해제해야 합니다. *relPath* 인수가 디스크 드라이브를 지정하면 이 드라이브의 현재 디렉터리가 경로와 결합됩니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h>|
|**_wfullpath**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fullpath.c
// This program demonstrates how _fullpath
// creates a full path from a partial path.

#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#include <direct.h>

void PrintFullPath( char * partialPath )
{
   char full[_MAX_PATH];
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )
      printf( "Full path is: %s\n", full );
   else
      printf( "Invalid path\n" );
}

int main( void )
{
   PrintFullPath( "test" );
   PrintFullPath( "\\test" );
   PrintFullPath( "..\\test" );
}
```

```Output
Full path is: C:\Documents and Settings\user\My Documents\test
Full path is: C:\test
Full path is: C:\Documents and Settings\user\test
```

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
