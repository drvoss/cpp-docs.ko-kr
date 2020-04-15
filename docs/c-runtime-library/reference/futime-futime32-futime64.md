---
title: _futime, _futime32, _futime64
ms.date: 4/2/2020
api_name:
- _futime64
- _futime32
- _futime
- _o__futime32
- _o__futime64
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
- futime
- _futime
- futime64
- _futime64
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
ms.openlocfilehash: 1f60bb3b366c48e3d53368f81ebc2528694794f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345497"
---
# <a name="_futime-_futime32-_futime64"></a>_futime, _futime32, _futime64

열린 파일의 수정 시간을 설정합니다.

## <a name="syntax"></a>구문

```C
int _futime(
   int fd,
   struct _utimbuf *filetime
);
int _futime32(
   int fd,
   struct __utimbuf32 *filetime
);
int _futime64(
   int fd,
   struct __utimbuf64 *filetime
);
```

### <a name="parameters"></a>매개 변수

*Fd*<br/>
열린 파일에 대한 파일 설명자입니다.

*Filetime*<br/>
새 수정 날짜를 포함하는 구조체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

성공하면 0을 반환합니다. 오류가 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 함수는 -1을 반환하고 **errno는** 잘못된 파일 설명자 또는 잘못된 매개 변수를 나타내는 **EINVAL을**나타내는 **EBADF로**설정됩니다.

## <a name="remarks"></a>설명

**_futime** 루틴은 *fd와*연결된 열린 파일의 수정 날짜와 액세스 시간을 설정합니다. **_futime** [_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md)동일합니다. **_utimbuf** 구조에는 새 수정 날짜 및 액세스 시간에 대한 필드가 포함되어 있습니다. 두 필드 모두 유효한 값을 포함합니다. **_utimbuf32** **_utimbuf64** 각각 32비트 및 64비트 시간 유형을 사용하는 경우를 제외하고 **_utimbuf** 동일합니다. **_futime** 및 **_utimbuf** 64비트 시간 유형을 사용하며 **_futime** **동작에서 _futime64**동일합니다. 이전 동작을 강제로 수행해야 하는 경우 **_USE_32BIT_TIME_T**. 이렇게 하면 **_futime32** 동작이 **_futime** 동일하고 **_utimbuf** 구조가 32비트 시간 형식을 사용하게 되어 **__utimbuf32.**

**__utimbuf64** 구조를 사용하는 **_futime64**3000년 12월 31일 UTC 23:59:59를 통해 파일 날짜를 읽고 수정할 수 있습니다. 파일의 날짜가 UTC인 2038년 1월 18일 23:59:59 보다 늦은 경우 **_futime32** 호출이 실패합니다. 1970년 1월 1일 자정은 이러한 함수에 대한 날짜 범위의 하한입니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|선택적 헤더|
|--------------|---------------------|---------------------|
|**_futime**|\<sys/utime.h>|\<errno.h>|
|**_futime32**|\<sys/utime.h>|\<errno.h>|
|**_futime64**|\<sys/utime.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_futime.c
// This program uses _futime to set the
// file-modification time to the current time.

#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <io.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <sys/utime.h>
#include <share.h>

int main( void )
{
   int hFile;

   // Show file time before and after.
   system( "dir crt_futime.c_input" );

   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );

   if( _futime( hFile, NULL ) == -1 )
      perror( "_futime failed\n" );
   else
      printf( "File time modified\n" );

   _close (hFile);

   system( "dir crt_futime.c_input" );
}
```

### <a name="input-crt_futimec_input"></a>입력: crt_futime.c_input

```Input
Arbitrary file contents.
```

### <a name="sample-output"></a>샘플 출력

```Output
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:40 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:41 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
File time modified
```

## <a name="see-also"></a>참고 항목

[시간 관리](../../c-runtime-library/time-management.md)<br/>
