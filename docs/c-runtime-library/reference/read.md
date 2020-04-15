---
title: _read
ms.date: 4/2/2020
api_name:
- _read
- _o__read
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _read
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
ms.openlocfilehash: db3726b85bb4ba7c8e9a691bef3fb063ec5709c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338129"
---
# <a name="_read"></a>_read

파일에서 데이터를 읽습니다.

## <a name="syntax"></a>구문

```C
int _read(
   int const fd,
   void * const buffer,
   unsigned const buffer_size
);
```

### <a name="parameters"></a>매개 변수

*Fd*<br/>
열려 있는 파일을 참조하는 파일 설명자입니다.

*버퍼*<br/>
데이터의 스토리지 위치입니다.

*buffer_size*<br/>
읽을 수 있는 최대 바이트 수입니다.

## <a name="return-value"></a>Return Value

**_read** 파일에 남아 있는 *buffer_size* 바이트 미만이거나 파일이 텍스트 모드에서 열린 경우 *buffer_size* 미만일 수 있는 읽기 바이트 수를 반환합니다. 텍스트 모드에서는 각 캐리지 리턴 `\r\n` 라인 피드 쌍이 `\n`단일 줄 피드 문자로 바뀝습니다. 단일 줄 피드 문자만 반환 값에 계산됩니다. 이러한 바꾸기는 파일 포인터에 영향을 주지 않습니다.

함수는 파일의 끝에서 읽기를 시도하는 경우 0을 반환합니다. *fd가* 유효하지 않으면 파일을 읽기 위해 열리지 않거나 파일이 잠겨 있으면 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 함수는 -1을 반환하고 **errno를** **EBADF로**설정합니다.

*버퍼가* **NULL이거나****INT_MAX** *buffer_size* > 경우 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있으면 함수가 -1을 반환하고 **errno가** **EINVAL로**설정됩니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

**_read** 함수는 *fd와*연결된 파일에서 최대 *buffer_size* 바이트를 *버퍼로* 읽습니다. 읽기 작업은 지정된 파일과 연결된 파일 포인터의 현재 위치에서 시작됩니다. 읽기 작업 후 파일 포인터는 읽지 않은 다음 문자를 가리킵니다.

파일이 텍스트 모드에서 열린 경우 **_read** CTRL+Z 문자가 발생하면 읽기가 종료되며, 이 문자는 파일 끝 표시기로 처리됩니다. 파일 끝 표시기를 지우려면 [_lseek](lseek-lseeki64.md)를 사용합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_read**|\<io.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_read.c
/* This program opens a file named crt_read.txt
* and tries to read 60,000 bytes from
* that file using _read. It then displays the
* actual number of bytes read.
*/

#include <fcntl.h>      /* Needed only for _O_RDWR definition */
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <share.h>

char buffer[60000];

int main( void )
{
   int fh, bytesread;
   unsigned int nbytes = 60000;

   /* Open file for input: */
   if ( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ))
   {
      perror( "open failed on input file" );
      exit( 1 );
   }

   /* Read in input: */
   if (( bytesread = _read( fh, buffer, nbytes )) <= 0 )
      perror( "Problem reading file" );
   else
      printf( "Read %u bytes from file\n", bytesread );

   _close( fh );
}
```

### <a name="input-crt_readtxt"></a>입력: crt_read.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>출력

```Output
Read 19 bytes from file
```

## <a name="see-also"></a>참고 항목

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fread](fread.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_write](write.md)<br/>
