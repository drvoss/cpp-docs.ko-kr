---
title: _write
ms.date: 4/2/2020
api_name:
- _write
- _o__write
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
- _write
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
ms.openlocfilehash: a616df570d266c335337d897da59a2a0ec69b40e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367385"
---
# <a name="_write"></a>_write

파일에 데이터를 씁니다.

## <a name="syntax"></a>구문

```C
int _write(
   int fd,
   const void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>매개 변수

*Fd*<br/>
데이터를 쓸 파일의 파일 설명자입니다.

*버퍼*<br/>
쓸 데이터입니다.

*count*<br/>
바이트 수입니다.

## <a name="return-value"></a>Return Value

성공하면 **_write** 기록된 바이트 수를 반환합니다. 디스크에 남아 있는 실제 공간이 함수가 디스크에 쓰려고 하는 버퍼 크기보다 작으면 **_write** 실패하고 버퍼의 내용을 디스크로 플러시하지 않습니다. 반환 값 -1은 오류를 나타냅니다. 잘못된 매개 변수가 전달되면 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 함수는 -1을 반환하고 **errno는** 파일 설명자가 유효하지 않거나 파일을 작성하기 위해 열리지 않음을 의미하는 **EBADF**중 하나로 설정됩니다. **ENOSPC는**작동을 위해 장치에 충분한 공간이 남아 있지 않음을 의미합니다. 또는 **EINVAL은** *버퍼가* null 포인터이거나 유니코드 모드의 파일에 기록되도록 바이트의 홀수 *개수가* 전달되었다는 것을 의미합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

파일이 텍스트 모드에서 열리면 각 줄 바급식 문자가 출력의 캐리지 리턴 라인 피드 쌍으로 바뀝습니다. 교체는 반환 값에 영향을 주지 않습니다.

유니코드 변환 모드에서 파일이 열리는 **wchar_t** 경우(예: *fd가* **_open** 또는 **_sopen** 사용하여 열리거나 **_O_WTEXT,** **_O_U16TEXT**또는 **_O_U8TEXT**포함하는 모드 매개 변수를 사용하거나 **fopen** 및 **ccs=UNICODE,** **ccs=UTF-16LE**또는 **ccs=UTF-8을**포함하는 모드 매개변수를 사용하여 열거나 **_setmode**사용하여 모드가 유니코드 변환 모드로 변경된 경우*버퍼가* **wchar_t** wchar_t. 이 모드에서 홀수 바이트를 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다.

## <a name="remarks"></a>설명

**_write** 함수는 *버퍼에서* *fd와*연결된 파일로 *바이트* 수를 기록합니다. 쓰기 작업은 지정된 파일과 연결된 파일 포인터(있는 경우)의 현재 위치에서 시작됩니다. 추가의 목적으로 파일을 연 경우 쓰기 작업은 파일의 현재 끝에서 시작됩니다. 쓰기 작업 후 파일 포인터는 기록된 바이트 수에 따라 증가합니다.

텍스트 모드에서 열린 파일에 쓸 때 **_write** CTRL+Z 문자를 파일의 논리적 끝으로 처리합니다. 장치에 쓸 때 **_write** 버퍼의 CTRL+Z 문자를 출력 터미네이터로 처리합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_write**|\<io.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt__write.c
//
// This program opens a file for output and uses _write to write
// some bytes to the file.

#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <errno.h>
#include <share.h>

char buffer[] = "This is a test of '_write' function";

int main( void )
{
   int         fileHandle = 0;
   unsigned    bytesWritten = 0;

   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )
      return -1;

   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )
   {
      switch(errno)
      {
         case EBADF:
            perror("Bad file descriptor!");
            break;
         case ENOSPC:
            perror("No space left on device!");
            break;
         case EINVAL:
            perror("Invalid parameter: buffer was NULL!");
            break;
         default:
            // An unrelated error occurred
            perror("Unexpected error!");
      }
   }
   else
   {
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );
   }
   _close( fileHandle );
}
```

```Output
Wrote 36 bytes to file.
```

## <a name="see-also"></a>참고 항목

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
