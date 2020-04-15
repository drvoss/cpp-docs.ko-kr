---
title: _expand
ms.date: 4/2/2020
api_name:
- _expand
- _o__expand
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
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
ms.openlocfilehash: 7f2a789bc5f475411808bc00a4280b7573b67cf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347538"
---
# <a name="_expand"></a>_expand

메모리 블록의 크기를 변경합니다.

## <a name="syntax"></a>구문

```C
void *_expand(
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

**_expand** void 포인터를 재할당된 메모리 블록에 반환합니다. **_expand** **realloc과**달리 블록을 이동하여 크기를 변경할 수 없습니다. 따라서 블록을 이동하지 않고 확장할 수 있는 충분한 메모리가 있는 경우 **_expand** *memblock* 매개 변수는 반환 값과 동일합니다.

**_expand** 작업 중에 오류가 감지되면 **NULL을** 반환합니다. 예를 들어 **_expand** 메모리 블록을 축소하는 데 사용되는 경우 작은 블록 힙 또는 잘못된 블록 포인터의 손상이 감지되어 **NULL을**반환할 수 있습니다.

블록을 이동하지 않고 지정된 크기로 확장할 수 있는 메모리가 부족하면 함수가 **NULL**을 반환합니다. **_expand** 요청된 크기보다 작은 크기로 확장된 블록을 반환하지 않습니다. 오류가 발생하면 **errno는** 오류의 특성을 나타냅니다. **errno에**대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하십시오.

반환 값은 모든 형식의 개체 스토리지를 위해 적절하게 맞도록 보장되어 있는 스토리지 공간을 가리킵니다. 항목의 새 크기를 확인하려면 **_msize.** **void**이외의 형식에 대한 포인터를 얻으려면 반환 값에 형식 캐스트를 사용합니다.

## <a name="remarks"></a>설명

**_expand** 함수는 힙에서 위치를 이동하지 않고 블록을 확장하거나 축소하려고 시도하여 이전에 할당된 메모리 블록의 크기를 변경합니다. *memblock* 매개 변수는 블록의 시작 부분을 가리킵니다. *크기* 매개 변수는 블록의 새 크기를 바이트로 제공합니다. 블록의 콘텐츠는 새 크기와 이전 크기 중 더 짧은 크기까지 변경 사항이 없습니다. *memblock해제된* 블록이 되어서는 안 됩니다.

> [!NOTE]
> 64비트 플랫폼에서 **_expand** 새 크기가 현재 크기보다 작으면 블록을 계약하지 않을 수 있습니다. 특히 블록의 크기가 16K 미만이어서 낮은 조각화 힙에 할당된 경우 **_expand** 블록을 변경하지 않고 *memblock을*반환합니다.

응용 프로그램이 C 런타임 라이브러리의 디버그 버전과 연결되면 **_expand** [_expand_dbg.](expand-dbg.md) 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

이 함수는 해당 매개 변수의 유효성을 검사합니다. *memblock이* null 포인터인 경우 이 함수는 매개 변수 유효성 [검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 **errno는** **EINVAL로** 설정되고 함수는 **NULL을**반환합니다. *크기가* **_HEAP_MAXREQ**보다 큰 경우 **errno는** **ENOMEM으로** 설정되고 함수는 **NULL을**반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_expand**|\<malloc.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_expand.c

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   char *bufchar;
   printf( "Allocate a 512 element buffer\n" );
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )
      exit( 1 );
   printf( "Allocated %d bytes at %Fp\n",
         _msize( bufchar ), (void *)bufchar );
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )
      printf( "Can't expand" );
   else
      printf( "Expanded block to %d bytes at %Fp\n",
            _msize( bufchar ), (void *)bufchar );
   // Free memory
   free( bufchar );
   exit( 0 );
}
```

```Output
Allocate a 512 element buffer
Allocated 512 bytes at 002C12BC
Expanded block to 1024 bytes at 002C12BC
```

## <a name="see-also"></a>참고 항목

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[무료](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
