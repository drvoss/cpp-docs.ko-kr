---
title: _aligned_offset_malloc
ms.date: 4/2/2020
api_name:
- _aligned_offset_malloc
- _o__aligned_offset_malloc
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
- _aligned_offset_malloc
- aligned_offset_malloc
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
ms.openlocfilehash: 1f13afbab75d2926d1c642c1430a3ffe5ecbac8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350586"
---
# <a name="_aligned_offset_malloc"></a>_aligned_offset_malloc

지정된 맞춤 경계에 메모리를 할당합니다.

## <a name="syntax"></a>구문

```C
void * _aligned_offset_malloc(
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>매개 변수

*크기*<br/>
요청된 메모리 할당 크기입니다.

*정렬(alignment)*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

*offset*<br/>
맞춤을 강제하는 메모리 할당으로의 오프셋입니다.

## <a name="return-value"></a>Return Value

작업이 실패한 경우 할당된 메모리 블록 또는 **NULL에** 대한 포인터입니다.

## <a name="remarks"></a>설명

**_aligned_offset_malloc** 중첩 된 요소에 정렬이 필요한 경우에 유용합니다. 예를 들어 중첩 된 클래스에 정렬이 필요한 경우.

**_aligned_offset_malloc** **malloc을**기반으로합니다. 자세한 내용은 [malloc](malloc.md)을 참조하십시오.

**_aligned_offset_malloc** `__declspec(noalias)` 표시되어 `__declspec(restrict)`있으며, 함수가 전역 변수를 수정하지 않도록 보장되고 반환된 포인터가 별칭이 아님을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

이 함수는 메모리 할당이 실패했거나 요청된 크기가 **_HEAP_MAXREQ**보다 큰 경우 **errno를** **ENOMEM으로** 설정합니다. **errno에**대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하십시오. 또한 **_aligned_offset_malloc** 매개 변수의 유효성을 검사합니다. *정렬이* 2의 힘이 아니거나 *오프셋이* *크기* 및 0이 아닌 크기보다 크거나 같으면 이 함수는 매개 변수 [유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이 함수는 **NULL을** 반환하고 **errno를** **EINVAL로**설정합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>예제

자세한 내용은 [_aligned_malloc](aligned-malloc.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

[데이터 정렬](../../c-runtime-library/data-alignment.md)<br/>
