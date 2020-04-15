---
title: fgetc, fgetwc
ms.date: 4/2/2020
api_name:
- fgetwc
- fgetc
- _o_fgetc
- _o_fgetwc
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
- _fgettc
- fgetwc
- fgetc
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
ms.openlocfilehash: c1589c64127b47f4dd2a1147f2b4d549601db4fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347005"
---
# <a name="fgetc-fgetwc"></a>fgetc, fgetwc

스트림에서 문자를 읽습니다.

## <a name="syntax"></a>구문

```C
int fgetc(
   FILE *stream
);
wint_t fgetwc(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

**fgetc는** **int로** 읽은 문자를 반환하거나 오류 또는 파일 끝을 나타내기 위해 **EOF를** 반환합니다. **fgetwc는** [wint_t](../../c-runtime-library/standard-types.md)문자 읽기 또는 반환 **WEOF에** 해당하는 와이드 문자를 반환하여 오류 또는 파일의 끝을 나타냅니다. 두 함수 모두 **feof** 또는 **ferror를** 사용하여 오류와 파일 끝 조건을 구분합니다. 읽기 오류가 발생하는 경우 스트림에 대한 오류 표시기가 설정됩니다. *스트림이* **NULL인**경우 **fgetc** 및 **fgetwc는** [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이러한 함수는 **errno를** **EINVAL로** 설정하고 **EOF를**반환합니다.

## <a name="remarks"></a>설명

이러한 각 함수는 *스트림과*연결된 파일의 현재 위치에서 단일 문자를 읽습니다. 그러고 나서 다음 문자를 가리킬 연결된 파일 포인터(정의된 경우)를 늘립니다. 스트림이 파일 끝에 있는 경우 스트림에 대한 파일 끝 표시기가 설정됩니다.

**fgetc은** **getc와**동일하지만 함수와 매크로가 아닌 함수로만 구현됩니다.

**fgetwc는** **fgetc의**넓은 문자 버전입니다; *스트림이* 텍스트 모드 또는 이진 모드에서 열리는지 여부에 따라 **c를** 다중 바이트 문자 또는 넓은 문자로 읽습니다.

**_nolock** 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 점을 제외하면 동일합니다.

와이드 문자 및 멀티바이트 문자를 텍스트 모드 및 이진 모드에서 처리하는 방법에 대한 자세한 내용은 [텍스트 및 이진 모드에서 유니코드 스트림 I/O](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgettc**|**fgetc**|**fgetc**|**fgetwc**|

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fgetc**|\<stdio.h>|
|**fgetwc**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fgetc.c
// This program uses getc to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   char buffer[81];
   int  i, ch;

   // Open file to read line from:
   fopen_s( &stream, "crt_fgetc.txt", "r" );
   if( stream == NULL )
      exit( 0 );

   // Read in first 80 characters and place them in "buffer":
   ch = fgetc( stream );
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = fgetc( stream );
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crt_fgetctxt"></a>입력: crt_fgetc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>출력

```Output
Line one.
Line two.
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
