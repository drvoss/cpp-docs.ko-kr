---
title: _aligned_offset_realloc
ms.date: 4/2/2020
api_name:
- _aligned_offset_realloc
- _o__aligned_offset_realloc
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
- aligned_offset_realloc
- _aligned_offset_realloc
helpviewer_keywords:
- aligned_offset_realloc function
- _aligned_offset_realloc function
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
ms.openlocfilehash: b27f5000a48ec3aafe37c6bd59e9b9acddd5bec5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350573"
---
# <a name="_aligned_offset_realloc"></a>_aligned_offset_realloc

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다.

## <a name="syntax"></a>구문

```C
void * _aligned_offset_realloc(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
현재 메모리 블록 포인터입니다.

*크기*<br/>
메모리 할당의 크기입니다.

*정렬(alignment)*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

*offset*<br/>
맞춤을 강제하는 메모리 할당으로의 오프셋입니다.

## <a name="return-value"></a>Return Value

**_aligned_offset_realloc** void 포인터를 재할당된(및 이동된) 메모리 블록으로 반환합니다. 반환 **값은** 크기가 0이고 버퍼 인수가 **NULL이**아니거나 블록을 지정된 크기로 확장할 수 있는 사용 가능한 메모리가 충분하지 않은 경우 NULL입니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 스토리지를 위해 적절하게 맞도록 보장되어 있는 스토리지 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.

**_aligned_offset_realloc** `__declspec(noalias)` 표시되어 `__declspec(restrict)`있으며, 함수가 전역 변수를 수정하지 않도록 보장되고 반환된 포인터가 별칭이 아님을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

## <a name="remarks"></a>설명

[_aligned_offset_malloc](aligned-offset-malloc.md) **_aligned_offset_realloc** 구조 내의 간격띄우기에서 구조를 정렬할 수 있습니다.

**_aligned_offset_realloc** **malloc을**기반으로 합니다. **_aligned_offset_malloc**사용에 대한 자세한 내용은 [malloc](malloc.md)을 참조하십시오. *memblock이* **NULL이면**함수는 내부적으로 **_aligned_offset_malloc** 호출합니다.

이 함수는 메모리 할당이 실패했거나 요청된 크기가 **_HEAP_MAXREQ**보다 큰 경우 **errno를** **ENOMEM으로** 설정합니다. **errno에**대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하십시오. 또한 **_aligned_offset_realloc** 매개 변수의 유효성을 검사합니다. *정렬이* 2의 힘이 아니거나 *오프셋이* *크기* 및 0이 아닌 크기보다 크거나 같으면 이 함수는 매개 변수 [유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이 함수는 **NULL을** 반환하고 **errno를** **EINVAL로**설정합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_aligned_offset_realloc**|\<malloc.h>|

## <a name="example"></a>예제

자세한 내용은 [_aligned_malloc](aligned-malloc.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

[데이터 정렬](../../c-runtime-library/data-alignment.md)<br/>
