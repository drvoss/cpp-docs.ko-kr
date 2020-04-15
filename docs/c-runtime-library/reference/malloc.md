---
title: malloc
ms.date: 4/2/2020
api_name:
- malloc
- _o_malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- malloc
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
ms.openlocfilehash: afe9264351110bc062d6168ef803fa6fb796538a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341570"
---
# <a name="malloc"></a>malloc

메모리 블록을 할당합니다.

## <a name="syntax"></a>구문

```C
void *malloc(
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*크기*<br/>
할당할 바이트입니다.

## <a name="return-value"></a>Return Value

**malloc는** 할당된 공간에 void 포인터를 반환하거나 사용 가능한 메모리가 부족한 경우 **NULL을** 반환합니다. **void**이외의 형식에 포인터를 반환하려면 반환 값에 형식 캐스트를 사용합니다. 반환 값이 가리키는 스토리지 공간은 맞춤 요구 사항이 기본 맞춤보다 작거나 같은 모든 형식의 개체 스토리지에 적절하게 맞춰지도록 보장됩니다. Visual C++에서 기본 정렬은 **이중**또는 8바이트에 필요한 정렬입니다. 64비트 플랫폼을 대상으로 하는 코드에서는 16바이트입니다. [_aligned_malloc](aligned-malloc.md) 사용하여 정렬 요구 사항이 더 큰 개체(예: __m128 [및](../../cpp/m128.md) **__m256)** 및 `__declspec(align( n ))` **n이** 8보다 큰 위치를 사용하여 선언된 형식과 같은 정렬 요구 사항이 큰 개체에 저장소를 할당합니다. *크기가* 0이면 **malloc은** 힙에 길이가 0인 항목을 할당하고 해당 항목에 유효한 포인터를 반환합니다. 요청된 메모리 양이 적더라도 **항상 malloc에서**반환을 확인합니다.

## <a name="remarks"></a>설명

**malloc** 함수는 최소 *크기* 바이트의 메모리 블록을 할당합니다. 정렬 및 유지 관리 정보에 필요한 공간 때문에 블록이 *크기* 바이트보다 클 수 있습니다.

**malloc은** 메모리 할당이 실패하거나 요청된 메모리 양이 **_HEAP_MAXREQ**초과하는 경우 **errno를** **ENOMEM으로** 설정합니다. 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

시작 코드는 **malloc을** 사용하여 **_environ,** *envp*및 *argv* 변수에 대한 저장소를 할당합니다. 다음 기능과 넓은 문자 대응도 **malloc.**

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[_exec 함수](../../c-runtime-library/exec-wexec-functions.md)|[fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[_spawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[시스템](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[ungetc](ungetc-ungetwc.md)|
|[fputc](fputc-fputwc.md)|[Getchar](getc-getwc.md)|[puts](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[가져오기](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

C++ [_set_new_mode](set-new-mode.md) 함수는 **malloc**에 대한 새 처리기 모드를 설정합니다. 새 처리기 모드는 오류가 발생할 경우 **malloc이** [_set_new_handler](set-new-handler.md)설정된 대로 새 처리기 루틴을 호출할지 여부를 나타냅니다. 기본적으로 **malloc는** 메모리할당 실패시 새 처리기 루틴을 호출하지 않습니다. **malloc가** 메모리를 할당하지 못하면 **동일한** 이유로 **새** 연산자가 수행하는 것과 동일한 방식으로 새 처리기 루틴을 호출하도록 이 기본 동작을 재정의할 수 있습니다. 기본값을 재정의하려면 `_set_new_mode(1)` 프로그램 초기에 전화하거나 NEWMODE로 연결합니다. OBJ [(링크 옵션](../../c-runtime-library/link-options.md)참조).

응용 프로그램이 C 런타임 라이브러리의 디버그 버전과 연결되면 **malloc은** [_malloc_dbg.](malloc-dbg.md) 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

**malloc표시** `__declspec(noalias)` 및 `__declspec(restrict)`; 즉, 함수는 전역 변수를 수정하지 않으며 반환된 포인터는 별칭이 아닙니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**malloc**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_malloc.c
// This program allocates memory with
// malloc, then frees the memory with free.

#include <stdlib.h>   // For _MAX_PATH definition
#include <stdio.h>
#include <malloc.h>

int main( void )
{
   char *string;

   // Allocate space for a path name
   string = malloc( _MAX_PATH );

   // In a C++ file, explicitly cast malloc's return.  For example,
   // string = (char *)malloc( _MAX_PATH );

   if( string == NULL )
      printf( "Insufficient memory available\n" );
   else
   {
      printf( "Memory space allocated for path name\n" );
      free( string );
      printf( "Memory freed\n" );
   }
}
```

```Output
Memory space allocated for path name
Memory freed
```

## <a name="see-also"></a>참고 항목

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[무료](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
