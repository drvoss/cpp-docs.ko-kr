---
title: setvbuf
ms.date: 4/2/2020
api_name:
- setvbuf
- _o_setvbuf
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setvbuf
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
ms.openlocfilehash: 203265a8dd85854bcedd737359b856fdc4cce04d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316260"
---
# <a name="setvbuf"></a>setvbuf

스트림 버퍼링 및 버퍼 크기를 제어합니다.

## <a name="syntax"></a>구문

```C
int setvbuf(
   FILE *stream,
   char *buffer,
   int mode,
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

*버퍼*<br/>
사용자가 할당한 버퍼입니다.

*모드*<br/>
버퍼링 모드입니다.

*크기*<br/>
버퍼 크기(바이트)입니다. 허용 범위: 2 <= *크기* <= INT_MAX (2147483647). 내부적으로 *크기에* 대해 제공된 값은 가장 가까운 배수 인 2로 반올림됩니다.

## <a name="return-value"></a>Return Value

정상적으로 실행되는 경우 0을 반환합니다.

*스트림이* **NULL인**경우 모드 *또는* *크기가* 유효한 변경 내에 있지 않으면 매개 변수 [유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이 함수는 -1을 반환하고 **errno**를 **EINVAL**로 설정합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**setvbuf** 함수를 사용하면 프로그램이 스트림에 대한 버퍼링 및 버퍼 크기를 모두 제어할 수 *있습니다.* *스트림은* I/O 연산을 거치지 않은 열린 파일을 참조해야 합니다. *버퍼로* 가리키는 배열은 **NULL이**아니라면 버퍼로 사용되며, 이 경우 **setvbuf는** 길이 *크기*/2 \* 2 바이트의 자동으로 할당된 버퍼를 사용합니다.

모드는 **_IOFBF,** **_IOLBF**또는 **_IONBF**이어야합니다. *모드가* **_IOFBF** **_IOLBF**경우 *크기는* 버퍼의 크기로 사용됩니다. *모드가* **_IONBF**스트림이 버퍼링되지 않고 *크기* 및 *버퍼가* 무시됩니다. *모드및* 그 의미에 대한 값은 다음과 같습니다.

|*모드* 값|의미|
|-|-|
| **_IOFBF** | 전체 버퍼링; 즉, *버퍼는* 버퍼로 사용되고 *크기는* 버퍼의 크기로 사용됩니다. *버퍼가* **NULL인**경우 자동으로 할당된 버퍼 *크기* 바이트가 깁니다. |
| **_IOLBF** | 이 값을 사용하는 경우 라인 버퍼링이 제공되는 시스템도 있습니다. 그러나 Win32의 경우 비헤이비어는 전체 버퍼링인 **_IOFBF** 동일합니다. |
| **_IONBF** | 버퍼 또는 *크기에*관계없이 *버퍼가* 사용되지 않습니다. |

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**setvbuf**|\<stdio.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_setvbuf.c
// This program opens two streams: stream1
// and stream2. It then uses setvbuf to give stream1 a
// user-defined buffer of 1024 bytes and stream2 no buffer.
//

#include <stdio.h>

int main( void )
{
   char buf[1024];
   FILE *stream1, *stream2;

   if( fopen_s( &stream1, "data1", "a" ) == 0 &&
       fopen_s( &stream2, "data2", "w" ) == 0 )
   {
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )
         printf( "Incorrect type or size of buffer for stream1\n" );
      else
         printf( "'stream1' now has a buffer of 1024 bytes\n" );
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )
         printf( "Incorrect type or size of buffer for stream2\n" );
      else
         printf( "'stream2' now has no buffer\n" );
      _fcloseall();
   }
}
```

```Output
'stream1' now has a buffer of 1024 bytes
'stream2' now has no buffer
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setbuf](setbuf.md)<br/>
