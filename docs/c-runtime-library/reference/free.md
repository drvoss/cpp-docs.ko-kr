---
title: 제한 없음
ms.date: 4/2/2020
api_name:
- free
- _o_free
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
- free
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
ms.openlocfilehash: eefbe957ce5057b5038f98bc8da8fb2f0bdd3d1c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345988"
---
# <a name="free"></a>제한 없음

메모리 블록을 할당 해제하거나 해제합니다.

## <a name="syntax"></a>구문

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
해제할 이전에 할당된 메모리 블록입니다.

## <a name="remarks"></a>설명

**사용 권은** **호출,** **malloc**또는 **realloc에**의해 이전에 할당 된 메모리 블록 *(memblock)을*할당합니다. 해제된 바이트 수는 블록이 할당될 때 요청된 바이트 수(또는 **realloc의**경우 재할당)와 같습니다. *memblock이* **NULL이면**포인터가 무시되고 **즉시 무료반환됩니다.** 잘못된 **포인터(calloc,** **malloc**또는 **realloc에**의해 할당되지 않은 메모리 블록에 대한 포인터)를 해제하려고 하면 후속 할당 요청에 영향을 미치고 오류가 발생할 수 있습니다.

메모리를 해제하는 과정에서 오류가 발생하면 **errno는** 오류의 특성에 대한 운영 체제의 정보로 설정됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

메모리 블록이 해제된 후 [_heapmin](heapmin.md)은 사용되지 않은 영역을 결합하고 다시 운영 체제로 릴리스하여 힙에 있는 사용 가능한 메모리 양을 최소화합니다. 운영 체제로 릴리스되지 않은 해제된 메모리는 사용 가능한 풀로 복원되고 다시 할당할 수 있습니다.

응용 프로그램이 C 런타임 라이브러리의 디버그 버전과 연결되면 **free** 는 [_free_dbg.](free-dbg.md) 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**free는** `__declspec(noalias)`표시되어 있으므로 함수가 전역 변수를 수정하지 않도록 보장됩니다. 자세한 내용은 [noalias](../../cpp/noalias.md)를 참조하세요.

[_malloca](malloca.md)를 사용하여 할당된 메모리를 해제하려면 [_freea](freea.md)를 사용합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**무료**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[malloc](malloc.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
