---
title: _recalloc
ms.date: 4/2/2020
api_name:
- _recalloc
- _o__recalloc
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
- _recalloc
- recalloc
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
ms.openlocfilehash: 57972a48336d8dd362b5da7513c854703134921b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338117"
---
# <a name="_recalloc"></a>_recalloc

**realloc와** **calloc의**조합 . 메모리에 배열을 다시 할당하고 해당 요소를 0으로 초기화합니다.

## <a name="syntax"></a>구문

```C
void *_recalloc(
   void *memblock
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
이전에 할당된 메모리 블록에 대한 포인터입니다.

*number*<br/>
요소의 수입니다.

*크기*<br/>
각 요소의 길이입니다(바이트).

## <a name="return-value"></a>Return Value

**_recalloc** void **포인터를** 재할당된(및 이동된) 메모리 블록으로 반환합니다.

블록을 지정된 크기로 확장할 수 있는 사용 가능한 메모리가 충분하지 않으면 원래 블록은 변경되지 않고 **NULL이** 반환됩니다.

요청된 크기가 0이면 *memblock이* 가리키는 블록이 해제됩니다. 반환 값은 **NULL이고** *memblock은* 해제된 블록을 가리킵니다.

반환 값은 모든 형식의 개체 스토리지를 위해 적절하게 맞도록 보장되어 있는 스토리지 공간을 가리킵니다. **void**이외의 형식에 대한 포인터를 얻으려면 반환 값에 형식 캐스트를 사용합니다.

## <a name="remarks"></a>설명

**_recalloc** 함수는 할당된 메모리 블록의 크기를 변경합니다. *memblock* 인수는 메모리 블록의 시작을 가리킵니다. *memblock이* **NULL인**경우 **_recalloc** [calloc과](calloc.md) 동일한 방식으로 행동하고 새 *숫자* * *크기* 바이트 블록을 할당합니다. 각 요소는 0으로 초기화됩니다. *memblock이* **NULL이**아닌 경우 **calloc,** [malloc](malloc.md)또는 [realloc에](realloc.md)대한 이전 호출에 의해 반환된 포인터여야 합니다.

새 블록이 새 메모리 위치에 있을 수 있으므로 **_recalloc** 반환되는 포인터는 *memblock* 인수를 통해 전달되는 포인터가 아닐 수 있습니다.

**_recalloc** 메모리 할당이 실패하거나 요청된 메모리 양이 **_HEAP_MAXREQ**초과하는 경우 **errno를** **ENOMEM으로** 설정합니다. 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

**recalloc은** C++ [_set_new_mode](set-new-mode.md) 함수를 사용하여 새 처리기 모드를 설정하기 위해 **realloc을** 호출합니다. 새 처리기 모드는 오류가 발생할 경우 **realloc이** [_set_new_handler](set-new-handler.md)대해 설정한 대로 새 처리기 루틴을 호출할지 여부를 나타냅니다. 기본적으로 **realloc는** 메모리할당 실패시 새 처리기 루틴을 호출하지 않습니다. **_recalloc** 메모리를 할당하지 못하면 새 처리기 루틴을 **같은** 이유로 실패할 때와 동일한 방식으로 새 처리기 **루틴을** 호출하도록 이 기본 동작을 재정의할 수 있습니다. 기본값을 재정의하려면 다음 코드를

```C
_set_new_mode(1);
```

프로그램에서 초기에 호출하거나, NEWMODE.OBJ를 사용하여 연결합니다.

응용 프로그램이 C 런타임 라이브러리의 디버그 버전과 연결되면 **_recalloc** [_recalloc_dbg.](recalloc-dbg.md) 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**_recalloc** `__declspec(noalias)` 표시되어 `__declspec(restrict)`있으며, 함수가 전역 변수를 수정하지 않도록 보장되고 반환된 포인터가 별칭이 아님을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_recalloc**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[무료](free.md)<br/>
[링크 옵션](../../c-runtime-library/link-options.md)<br/>
