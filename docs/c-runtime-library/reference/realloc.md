---
title: realloc
ms.date: 4/2/2020
api_name:
- realloc
- _o_realloc
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
- _brealloc
- _nrealloc
- realloc
- _frealloc
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
ms.openlocfilehash: 964c465a95d44de9d8a4d399f23ec43f8a3a6692
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332938"
---
# <a name="realloc"></a>realloc

메모리 블록을 다시 할당합니다.

## <a name="syntax"></a>구문

```C
void *realloc(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
이전에 할당된 메모리 블록에 대한 포인터입니다.

*크기*<br/>
새 크기(바이트)입니다.

## <a name="return-value"></a>Return Value

**realloc는** void **포인터를** 재할당된(및 이동된) 메모리 블록으로 반환합니다.

블록을 지정된 크기로 확장할 수 있는 사용 가능한 메모리가 충분하지 않으면 원래 블록은 변경되지 않고 **NULL이** 반환됩니다.

*크기가* 0이면 *memblock이* 가리키는 블록이 해제됩니다. 반환 값은 **NULL이고** *memblock은* 해제된 블록을 가리킵니다.

반환 값은 모든 형식의 개체 스토리지를 위해 적절하게 맞도록 보장되어 있는 스토리지 공간을 가리킵니다. **void**이외의 형식에 대한 포인터를 얻으려면 반환 값에 형식 캐스트를 사용합니다.

## <a name="remarks"></a>설명

**realloc** 함수는 할당된 메모리 블록의 크기를 변경합니다. *memblock* 인수는 메모리 블록의 시작을 가리킵니다. *memblock이* **NULL인**경우 **realloc은** **malloc과** 동일한 방식으로 행동하고 새 *크기* 바이트 블록을 할당합니다. *memblock이* **NULL이**아닌 경우 **calloc,** **malloc**또는 **realloc에**대한 이전 호출에 의해 반환된 포인터여야 합니다.

*크기* 인수는 블록의 새 크기를 바이트로 제공합니다. 블록의 내용은 새 크기와 이전 크기 중 더 짧은 쪽까지는 변경되지 않습니다. 그러나 새 블록은 다른 위치에 있을 수 있습니다. 새 블록이 새 메모리 위치에 있을 수 있으므로 **realloc에서** 반환하는 포인터는 *memblock* 인수를 통해 전달되는 포인터라고 보장할 수 없습니다. **realloc** 버퍼 성장의 경우 새로 할당 된 메모리를 0 하지 않습니다.

**realloc는** 메모리 할당이 실패하거나 요청된 메모리 양이 **_HEAP_MAXREQ**초과하는 경우 **errno를** **ENOMEM으로** 설정합니다. 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

**realloc은** C++ [_set_new_mode](set-new-mode.md) 함수를 사용하여 새 처리기 모드를 설정하기 위해 **malloc을** 호출합니다. 새 처리기 모드는 오류가 발생할 경우 **malloc이** [_set_new_handler](set-new-handler.md)설정된 대로 새 처리기 루틴을 호출할지 여부를 나타냅니다. 기본적으로 **malloc는** 메모리할당 실패시 새 처리기 루틴을 호출하지 않습니다. **realloc메모리** 할당에 실패할 때 **malloc이** 동일한 이유로 실패할 때 **새** 연산자가 수행하는 것과 동일한 방식으로 새 처리기 루틴을 호출하도록 이 기본 동작을 재정의할 수 있습니다. 기본값을 재정의하려면 다음 코드를

```C
_set_new_mode(1);
```

프로그램에서 초기에 호출하거나, NEWMODE.OBJ를 사용하여 연결합니다([링크 옵션](../../c-runtime-library/link-options.md) 참조).

응용 프로그램이 C 런타임 라이브러리의 디버그 버전과 연결되면 **realloc는** [_realloc_dbg.](realloc-dbg.md) 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**realloc가** `__declspec(noalias)` 표시되고 `__declspec(restrict)`, 함수가 전역 변수를 수정하지 않도록 보장되고 반환된 포인터가 별칭이 아님을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**realloc**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_realloc.c
// This program allocates a block of memory for
// buffer and then uses _msize to display the size of that
// block. Next, it uses realloc to expand the amount of
// memory used by buffer and then calls _msize again to
// display the new amount of memory allocated to buffer.

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   long *buffer, *oldbuffer;
   size_t size;

   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )
      exit( 1 );

   size = _msize( buffer );
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );

   // Reallocate and show new size:
   oldbuffer = buffer;     // save pointer in case realloc fails
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))
        ==  NULL )
   {
      free( oldbuffer );  // free original block
      exit( 1 );
   }
   size = _msize( buffer );
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",
            size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after malloc of 1000 longs: 4000
Size of block after realloc of 1000 more longs: 8000
```

## <a name="see-also"></a>참고 항목

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[무료](free.md)<br/>
[malloc](malloc.md)<br/>
