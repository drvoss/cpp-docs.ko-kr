---
title: setbuf
ms.date: 4/2/2020
api_name:
- setbuf
- _o_setbuf
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
- setbuf
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
ms.openlocfilehash: f96cffb8770cda78ebff8d873b441ddc288bc41f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332072"
---
# <a name="setbuf"></a>setbuf

스트림 버퍼링을 제어합니다. 이 함수는 사용되지 않습니다. 대신 [setvbuf](setvbuf.md)를 사용하세요.

## <a name="syntax"></a>구문

```C
void setbuf(
   FILE *stream,
   char *buffer
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

*버퍼*<br/>
사용자가 할당한 버퍼입니다.

## <a name="remarks"></a>설명

**setbuf** 함수는 스트림에 대한 버퍼링을 *제어합니다.* *스트림* 인수는 읽거나 쓰지 않은 열린 파일을 참조해야 합니다. *버퍼* 인수가 **NULL이면**스트림이 버퍼링되지 않습니다. 그렇지 않은 경우 버퍼는 **BUFSIZ가** STDIO에 정의된 버퍼 크기인 길이 **BUFSIZ의**문자 배열을 가리키야 합니다. H. 지정된 스트림에 대한 기본 시스템 할당 버퍼 대신 사용자 지정 버퍼가 I/O 버퍼링에 사용됩니다. **stderr** 스트림은 기본적으로 버퍼링되지 않지만 **setbuf를** 사용하여 **stderr**에 버퍼를 할당할 수 있습니다.

**setbuf는** 새 코드에 대 한 기본 [루틴setvbuf로](setvbuf.md)대체 되었습니다. **setvbuf와**달리 **setbuf는** 오류를 보고할 방법이 없습니다. **setvbuf를** 사용하면 버퍼링 모드와 버퍼 크기를 모두 제어할 수 있습니다. **setbuf는** 기존 코드와의 호환성을 위해 존재합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**setbuf**|\<stdio.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_setbuf.c
// compile with: /W3
// This program first opens files named DATA1 and
// DATA2. Then it uses setbuf to give DATA1 a user-assigned
// buffer and to change DATA2 so that it has no buffer.

#include <stdio.h>

int main( void )
{
   char buf[BUFSIZ];
   FILE *stream1, *stream2;

   fopen_s( &stream1, "data1", "a" );
   fopen_s( &stream2, "data2", "w" );

   if( (stream1 != NULL) && (stream2 != NULL) )
   {
      // "stream1" uses user-assigned buffer:
      setbuf( stream1, buf ); // C4996
      // Note: setbuf is deprecated; consider using setvbuf instead
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );

      // "stream2" is unbuffered
      setbuf( stream2, NULL ); // C4996
      printf( "stream2 buffering disabled\n" );
      _fcloseall();
   }
}
```

```Output
stream1 set to user-defined buffer at: 0012FCDC
stream2 buffering disabled
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setvbuf](setvbuf.md)<br/>
