---
title: calloc
description: C 런타임 함수 calloc은 초기화되지 는 제로 초기화된 메모리를 할당합니다.
ms.date: 4/2/2020
api_name:
- calloc
- _o_calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: fb4f7d6dc059023d34cb0b811edf5dfb48cb7a34
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333646"
---
# <a name="calloc"></a>calloc

0으로 초기화된 요소가 있는 메모리에 배열을 할당합니다.

## <a name="syntax"></a>구문

```C
void *calloc(
   size_t number,
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*number*<br/>
요소의 수입니다.

*크기*<br/>
각 요소의 길이입니다(바이트).

## <a name="return-value"></a>Return Value

**calloc할당된** 공간에 대한 포인터를 반환합니다. 반환 값이 가리킨 스토리지 공간은 모든 형식의 개체 스토리지를 위해 적절하게 정렬되도록 보장됩니다. **void**이외의 형식에 대한 포인터를 얻으려면 반환 값에 형식 캐스트를 사용합니다.

## <a name="remarks"></a>설명

**calloc** 함수는 각 길이 *크기* 바이트의 *숫자* 요소 배열에 대 한 저장소 공간을 할당 합니다. 각 요소는 0으로 초기화됩니다.

**calloc는** 메모리 할당이 실패하거나 요청된 메모리 양이 **_HEAP_MAXREQ**초과하는 경우 **errno를** **ENOMEM으로** 설정합니다. 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

Microsoft 구현에서 *숫자* 또는 *크기가* 0이면 **calloc은** 0이 아닌 크기의 할당된 블록에 대한 포인터를 반환합니다. 반환된 포인터를 읽거나 쓰려고 하면 정의되지 않은 동작이 발생합니다.

**calloc는** C++ [_set_new_mode](set-new-mode.md) 함수를 사용하여 *새 처리기 모드를*설정합니다. 새 처리기 모드는 실패시 **calloc이** [_set_new_handler](set-new-handler.md)대해 설정한 대로 새 처리기 루틴을 호출할지 여부를 나타냅니다. 기본적으로 **calloc는** 메모리를 할당하지 못하면 새 처리기 루틴을 호출하지 않습니다. **calloc가** 메모리를 할당하지 못하면 새 **연산자가** 같은 이유로 실패할 때와 동일한 방식으로 새 처리기 루틴을 호출하도록 이 기본 동작을 재정의할 수 있습니다. 기본값을 재정의하려면 다음 코드를

```C
_set_new_mode(1);
```

프로그램 초기에 또는 *NEWMODE와 연결합니다. OBJ* [(링크 옵션](../../c-runtime-library/link-options.md)참조).

응용 프로그램이 C 런타임 라이브러리의 디버그 버전과 연결되면 **calloc는** [_calloc_dbg.](calloc-dbg.md) 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**calloc가** `__declspec(noalias)` 표시되고 `__declspec(restrict)`, 함수가 전역 변수를 수정하지 않도록 보장되고 반환된 포인터가 별칭이 아님을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**calloc**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_calloc.c
// This program uses calloc to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>

int main( void )
{
   long *buffer;

   buffer = (long *)calloc( 40, sizeof( long ) );
   if( buffer != NULL )
      printf( "Allocated 40 long integers\n" );
   else
      printf( "Can't allocate memory\n" );
   free( buffer );
}
```

```Output
Allocated 40 long integers
```

## <a name="see-also"></a>참고 항목

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[무료](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
