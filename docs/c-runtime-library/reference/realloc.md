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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 72c38021452940553bad770160ecc5db7ea546d0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216819"
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

*size*<br/>
새 크기(바이트)입니다.

## <a name="return-value"></a>Return Value

**realloc** **`void`** 는 다시 할당 된 (그리고 이동 가능한) 메모리 블록에 대 한 포인터를 반환 합니다.

블록을 지정 된 크기로 확장 하는 데 사용할 수 있는 메모리가 충분 하지 않은 경우 원래 블록은 변경 되지 않은 상태로 유지 되 고 **NULL** 이 반환 됩니다.

*Size* 가 0 이면 *memblock* 이 가리키는 블록이 해제 됩니다. 반환 값은 **NULL**이 고 *memblock* 은 해제 된 블록을 가리키는 상태로 유지 됩니다.

반환 값은 모든 형식의 개체 스토리지를 위해 적절하게 맞도록 보장되어 있는 스토리지 공간을 가리킵니다. 이외의 형식에 대 한 포인터를 가져오려면 **`void`** 반환 값에 형식 캐스팅을 사용 합니다.

## <a name="remarks"></a>설명

**Realloc** 함수는 할당 된 메모리 블록의 크기를 변경 합니다. *Memblock* 인수는 메모리 블록의 시작 부분을 가리킵니다. *Memblock* 이 **NULL**인 경우 **realloc** 는 **malloc** 와 동일한 방식으로 동작 하며 *크기* 바이트의 새 블록을 할당 합니다. *Memblock* 이 **NULL**이 아닌 경우 **calloc**, **malloc**또는 **realloc**에 대 한 이전 호출에서 반환 된 포인터 여야 합니다.

*Size* 인수는 블록의 새 크기 (바이트)를 제공 합니다. 블록의 내용은 새 크기와 이전 크기 중 더 짧은 쪽까지는 변경되지 않습니다. 그러나 새 블록은 다른 위치에 있을 수 있습니다. 새 블록은 새 메모리 위치에 있을 수 있으므로 **realloc** 에서 반환 되는 포인터는 *memblock* 인수를 통해 전달 되는 포인터가 보장 되지 않습니다. 버퍼가 증가 하는 경우 **realloc** 은 새로 할당 된 메모리를 0으로 만들지 않습니다.

**realloc** 는 메모리 할당이 실패 하거나 요청 된 메모리 양이 **_HEAP_MAXREQ**을 초과 하는 경우 **errno** 을 **enomem** 으로 설정 합니다. 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

**realloc** 는 c + + [_set_new_mode](set-new-mode.md) 함수를 사용 하 여 새 처리기 모드를 설정 하기 위해 **malloc** 를 호출 합니다. 새 처리기 모드는 실패 시 **malloc** 가 [_set_new_handler](set-new-handler.md)에 의해 설정 된 대로 새 처리기 루틴을 호출 하는지 여부를 나타냅니다. 기본적으로 **malloc** 은 메모리 할당 실패 시 새 처리기 루틴을 호출 하지 않습니다. 이 기본 동작을 재정의 하 여 **realloc** 에서 메모리를 할당 하지 못할 때 **malloc** 이 **`new`** 연산자가 같은 이유로 실패 했을 때와 동일한 방식으로 새 처리기 루틴을 호출 하도록 할 수 있습니다. 기본값을 재정의하려면 다음 코드를

```C
_set_new_mode(1);
```

프로그램에서 초기에 호출하거나, NEWMODE.OBJ를 사용하여 연결합니다([링크 옵션](../../c-runtime-library/link-options.md) 참조).

응용 프로그램이 C 런타임 라이브러리의 디버그 버전에 연결 된 경우 **realloc** 은 [_realloc_dbg](realloc-dbg.md)를 확인 합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**realloc** 는 및로 표시 됩니다 `__declspec(noalias)` `__declspec(restrict)` . 즉, 함수가 전역 변수를 수정 하지 않도록 보장 하 고 반환 된 포인터에 별칭이 지정 되지 않습니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

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
[늘릴](free.md)<br/>
[malloc](malloc.md)<br/>
