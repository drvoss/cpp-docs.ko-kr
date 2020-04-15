---
title: _fdopen, _wfdopen
ms.date: 4/2/2020
api_name:
- _fdopen
- _wfdopen
- _o__fdopen
- _o__wfdopen
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
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
ms.openlocfilehash: 82a7e891e8bd6031ebbf761534b6df7cd8488d36
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347383"
---
# <a name="_fdopen-_wfdopen"></a>_fdopen, _wfdopen

하위 수준 I/O를 위해 이전에 연 파일에 스트림을 연결합니다.

## <a name="syntax"></a>구문

```C
FILE *_fdopen(
   int fd,
   const char *mode
);
FILE *_wfdopen(
   int fd,
   const wchar_t *mode
);
```

### <a name="parameters"></a>매개 변수

*Fd*<br/>
열린 파일의 파일 설명자입니다.

*모드*<br/>
파일 액세스의 유형입니다.

## <a name="return-value"></a>Return Value

각 함수는 열린 스트림에 대한 포인터를 반환합니다. null 포인터 값은 오류를 나타냅니다. 오류가 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 **errno는** 잘못된 파일 설명자를 나타내는 **EBADF**또는 해당 *모드가* null 포인터임을 나타내는 **EINVAL로**설정됩니다.

이 오류 및 다른 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

**_fdopen** 함수는 I/O 스트림을 *fd로*식별된 파일과 연결하므로 하위 수준 I/O에 대해 열리는 파일을 버퍼링하고 서식을 지정할 수 있습니다. **_wfdopen** **_fdopen**와이드 문자 버전입니다. **_wfdopen** *모드* 인수는 와이드 문자 문자열입니다. **_wfdopen** **_fdopen** 그렇지 않으면 동일하게 행동합니다.

**_fdopen** 전달된 파일 설명자는 반환된 **FILE &#42;** 스트림에서 소유합니다. **_fdopen** 성공하면 파일 설명자에서 [ \_close를](close.md) 호출하지 마십시오. 반환된 **FILE &#42;** [fclose을](fclose-fcloseall.md) 호출하여 파일 설명자도 닫힙습니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|\_유니코드 \_및 MBCS가 정의되지 않음|\_MBCS 정의|\_유니코드 정의|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfdopen**|**_fdopen**|**_fdopen**|**_wfdopen**|

*모드* 문자열은 파일에 대해 요청된 파일 액세스 유형을 지정합니다.

| *모드* | 액세스 권한 |
|--------|--------|
| **"r"** | 읽기 위해 엽니다. 파일이 없거나 찾을 수 없는 경우 **fopen** 호출이 실패합니다. |
| **"w"** | 쓰기 위해 빈 파일을 엽니다. 지정한 파일이 있으면 이 파일의 내용은 삭제됩니다. |
| **"가성비 좋은"** | 파일 의 끝에 쓰기위해 열립니다(부속). 파일이 없는 경우 파일을 만듭니다. |
| **"r+"** | 읽고 쓰기 위해 엽니다. 파일이 있어야 합니다. |
| **"w+"** | 읽고 쓰기 위해 빈 파일을 엽니다. 파일이 있으면 이 파일의 내용은 삭제됩니다. |
| **"a+"** | 읽고 추가하기 위해 엽니다. 파일이 없는 경우 파일을 만듭니다. |

**"a"** 또는 **"a+"** 액세스 유형으로 파일을 열면 모든 쓰기 작업이 파일 끝에 발생합니다. 파일 포인터는 [fseek](fseek-fseeki64.md) 또는 [되감기를](rewind.md)사용하여 위치를 지정할 수 있지만 쓰기 작업이 수행되기 전에 항상 파일의 끝으로 다시 이동됩니다. 따라서 기존 데이터를 덮어쓸 수 없습니다. **"r+"**, **"w+"** 또는 **"a+"** 액세스 유형이 지정되면 읽기와 쓰기가 모두 허용됩니다(파일이 "업데이트"를 위해 열려 있다고 함). 그러나 읽기와 쓰기 사이를 전환할 때 중간 [fflush,](fflush.md) [fsetpos,](fsetpos.md) [fseek](fseek-fseeki64.md)또는 [되감기](rewind.md) 작업이 있어야 합니다. 원하는 경우 [fsetpos](fsetpos.md) 또는 [fseek](fseek-fseeki64.md) 작업에 대한 현재 위치를 지정할 수 있습니다.

위의 값 외에도 다음 문자를 *모드에* 포함하여 줄 바선 문자의 변환 모드를 지정할 수도 있습니다.

| *모드* 수정자 | 동작 |
|-----------------|----------|
| **T** | 텍스트(변환됨) 모드에서 엽니다. 이 모드에서는 CR-LF(캐리지 리턴 줄 바꿈) 조합은 입력 시 단일 LF(줄 바꿈)로 변환되고, LF 문자는 출력 시 CR-LF 조합으로 변환됩니다. 또한 CTRL+Z는 입력 시 파일 끝 문자로 변환됩니다. |
| **B** | 이진(변환되지 않음) 모드에서 엽니다. **t** 모드의 모든 변환은 억제됩니다. |
| **C** | **fflush** 또는 **_flushall** 호출되는 경우 파일 버퍼의 내용이 디스크에 직접 기록되도록 연결된 *파일 이름에* 대한 커밋 플래그를 활성화합니다. |
| **N** | 연결된 *파일 이름에* 대한 커밋 플래그를 "커밋 없음"으로 재설정합니다. 이것이 기본값입니다. 또한 Commode.obj와 프로그램을 연결하는 경우 전역 커밋 플래그를 재정의합니다. 프로그램을 Commode.obj와 명시적으로 연결하지 않는 한 전역 커밋 플래그 기본값은 "커밋 없음"입니다. |

**t**, **c**및 **n** *모드* 옵션은 **펜및** **_fdopen**대한 Microsoft 확장입니다. ANSI 이식성을 유지하려는 경우에는 사용하지 마세요.

**t** 또는 **b가** *모드로*제공되지 않으면 기본 변환 모드는 전역 변수 [ \_fmode에](../../c-runtime-library/fmode.md)의해 정의됩니다. **t** 또는 **b가** 인수에 접두사된 경우 함수가 실패하고 NULL을 반환합니다. 텍스트 모드와 이진 모드에 대한 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)를 참조하세요.

**fopen** 및 **_fdopen** 사용되는 *모드* 문자열에 대한 유효한 문자는 이 표에 표시된 것처럼 [ \_open](open-wopen.md) 및 [ \_sopen에](sopen-wsopen.md)사용되는 *oflag* 인수에 해당합니다.

|*모드* 문자열의 문자|**_open** 및 **_sopen** 대한 *등가값*|
|---------------------------------|---------------------------------------------------|
|**a.**|**\_O\_WRONLY \_\_&#124; O 부속** (보통 ** \_\_O WRONLY \_&#124; O\_creAT \_&#124; O\_부속)**|
|**a+**|**\_O\_RDWR \_\_&#124; O 부속** (보통 ** \_\_O RDWR \_&#124; O\_부화 \_&#124; O\_CREAT)**|
|**R**|**\_O\_RDONLY**|
|**r +**|**\_O\_RDWR**|
|**W**|**\_O\_WRONLY** (보통 ** \_\_O \_\_WRONLY \_&#124;\_O creAT &#124; O TRUNC)**|
|**w +**|**\_O\_RDWR** (보통 ** \_\_O \_\_RDWR \_&#124;\_O creAT &#124; O TRUNC)**|
|**B**|**\_오\_바이너리**|
|**T**|**\_O\_텍스트**|
|**C**|없음|
|**N**|없음|

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_fdopen**|\<stdio.h>|
|**_wfdopen**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```c
// crt_fdopen.c
// This program opens a file by using low-level
// I/O, then uses _fdopen to switch to stream
// access. It counts the lines in the file.

#include <stdlib.h>
#include <stdio.h>
#include <fcntl.h>
#include <io.h>
#include <share.h>

int main( void )
{
   FILE *stream;
   int  fd, count = 0;
   char inbuf[128];

   // Open a file.
   if( _sopen_s( &fd, "crt_fdopen.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
      exit( 1 );

   // Get stream from file descriptor.
   if( (stream = _fdopen( fd, "r" )) == NULL )
      exit( 1 );

   while( fgets( inbuf, 128, stream ) != NULL )
      count++;

   // After _fdopen, close by using fclose, not _close.
   fclose( stream );
   printf( "Lines in file: %d\n", count );
}
```

### <a name="input-crt_fdopentxt"></a>입력: crt_fdopen.txt

```Input
Line one
Line two
```

### <a name="output"></a>출력

```Output
Lines in file: 2
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[\_dup, \_dup2](dup-dup2.md)<br/>
[프램, \_클로즈올](fclose-fcloseall.md)<br/>
[펜, \_wfopen](fopen-wfopen.md)<br/>
[프레오픈, \_wfreopen](freopen-wfreopen.md)<br/>
[\_열기, \_오픈](open-wopen.md)<br/>
