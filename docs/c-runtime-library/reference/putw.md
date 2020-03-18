---
title: _putw
ms.date: 11/04/2016
api_name:
- _putw
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _putw
helpviewer_keywords:
- integers, writing to streams
- putw function
- streams, writing integers to
- _putw function
ms.assetid: 83d63644-249d-4a39-87e5-3b7aa313968d
ms.openlocfilehash: be2ee5c1b3706b1f2a0847415ab4a82a6a4bbe4f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443730"
---
# <a name="_putw"></a>_putw

정수를 스트림에 씁니다.

## <a name="syntax"></a>구문

```C
int _putw(
   int binint,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*binint*<br/>
출력할 이진 정수입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

작성된 값을 반환합니다. **EOF** 의 반환 값은 오류를 나타낼 수 있습니다. **EOF** 도 올바른 정수 값 이므로 **ferror** 를 사용 하 여 오류를 확인 합니다. *Stream* 이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 **errno** 를 **EINVAL** 로 설정 하 고 **EOF**를 반환 합니다.

이러한 오류 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**_Putw** 함수는 **int** 형식의 이진 값을 스트림의 현재 위치에 씁니다 *.* **_putw** 은 스트림의 항목 맞춤에 영향을 주지 않으며 특수 한 맞춤을 가정 하지도 않습니다. **_putw** 는 주로 이전 라이브러리와의 호환성을 위해 사용 됩니다. **Int** 의 크기와 **int** 내 바이트의 순서가 시스템 마다 다르기 때문에 **_putw** 에서 이식성 문제가 발생할 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_putw**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_putw.c
/* This program uses _putw to write a
* word to a stream, then performs an error check.
*/

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   unsigned u;
   if( fopen_s( &stream, "data.out", "wb" ) )
      exit( 1 );
   for( u = 0; u < 10; u++ )
   {
      _putw( u + 0x2132, stream );   /* Write word to stream. */
      if( ferror( stream ) )         /* Make error check. */
      {
         printf( "_putw failed" );
         clearerr_s( stream );
         exit( 1 );
      }
   }
   printf( "Wrote ten words\n" );
   fclose( stream );
}
```

### <a name="output"></a>출력

```Output
Wrote ten words
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_getw](getw.md)<br/>
