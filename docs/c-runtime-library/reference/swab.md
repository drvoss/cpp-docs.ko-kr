---
title: _swab
ms.date: 4/2/2020
api_name:
- _swab
- stdlib/_swab
- _o__swab
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
- api-ms-win-crt-utility-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _swab
- stdlib/_swab
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
ms.openlocfilehash: f7fe23cd9c1b2eab52ebe50904d0bb18fe16cea6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362964"
---
# <a name="_swab"></a>_swab

바이트를 교환합니다.

## <a name="syntax"></a>구문

```C
void _swab(
   char *src,
   char *dest,
   int n
);
```

## <a name="parameters"></a>매개 변수

*Src*<br/>
복사하고 교환할 데이터입니다.

*dest*<br/>
교환된 데이터에 대한 스토리지 위치입니다.

*N*<br/>
복사되고 교환될 바이트 수입니다.

## <a name="return-value"></a>반환 값

**면봉** 함수는 값을 반환하지 않습니다. 함수는 *src* 또는 *dest* 포인터가 null이거나 *n이* 0보다 크고 매개 [변수 유효성 검사기에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출되는 경우 **errno를** **EINVAL로** 설정합니다.

이 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 참조하십시오.

## <a name="remarks"></a>설명

*n이* 짝수이면 **_swab** 함수는 *src에서* *n* 바이트를 복사하고 인접 바이트의 각 쌍을 교환하고 결과를 *dest에*저장합니다. *n이* 홀수이면 **_swab** *src의*첫 번째 *n-1*바이트를 복사하고 교환하고 최종 바이트는 복사되지 않습니다. **_swab** 함수는 일반적으로 다른 바이트 순서를 사용하는 컴퓨터로 전송하기 위해 이진 데이터를 준비하는 데 사용됩니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h> C++: \<cstdlib> 또는 \<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_swab.c

#include <stdlib.h>
#include <stdio.h>

char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";
char to[] =   "...........................";

int main()
{
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);
    _swab(from, to, sizeof(from));
    printf("After:  %s\n        %s\n\n", from, to);
}
```

```Output
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes
        ...........................

After:  BADCFEHGJILKNMPORQTSVUXWZY
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.
```

## <a name="see-also"></a>참고 항목

[버퍼 조작](../../c-runtime-library/buffer-manipulation.md)<br/>
