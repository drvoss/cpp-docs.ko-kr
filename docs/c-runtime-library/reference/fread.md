---
title: fread
ms.date: 4/2/2020
api_name:
- fread
- _o_fread
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
- fread
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
ms.openlocfilehash: 26ffd56072f1a5fddc3131a42cd47c145e437b60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346060"
---
# <a name="fread"></a>fread

스트림에서 데이터를 읽습니다.

## <a name="syntax"></a>구문

```C
size_t fread(
   void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*버퍼*<br/>
데이터의 스토리지 위치입니다.

*크기*<br/>
항목 크기(바이트)입니다.

*count*<br/>
읽힐 항목의 최대 수입니다.

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

**fread는** 실제로 읽은 전체 항목의 수를 반환하며, 오류가 발생하거나 파일의 끝이 *개수에*도달하기 전에 발생한 경우 *개수보다* 적을 수 있습니다. **feof** 또는 **ferror** 함수를 사용하여 읽기 오류를 파일 끝 조건과 구별합니다. *크기* 또는 *개수가* 0이면 **fread가** 0을 반환하고 버퍼 내용은 변경되지 않습니다. *스트림* 또는 *버퍼가* null 포인터인 경우 **fread는** [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이 함수는 **errno를** **EINVAL로** 설정하고 0을 반환합니다.

이러한 오류 코드에 대한 자세한 내용은 [ \_doserno, errno, \_sys\_errlist 및 \_sys\_nerr를](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 참조하십시오.

## <a name="remarks"></a>설명

**fread** 함수는 입력 *스트림에서* *크기* 바이트 항목을 *계산하고* *버퍼에*저장합니다. *스트림과* 연결된 파일 포인터(있는 경우)는 실제로 읽은 바이트 수에 따라 증가합니다. 지정된 스트림이 텍스트 [모드에서](../../c-runtime-library/text-and-binary-mode-file-i-o.md)열리면 Windows 스타일 줄 바선이 유닉스 스타일의 줄 바이라고 변환됩니다. 즉, 캐리지 리턴 라인 피드(CRLF) 쌍은 단일 라인 피드(LF) 문자로 대체됩니다. 이렇게 바뀌더라도 파일 포인터 또는 반환 값에는 영향을 미치지 않습니다. 오류가 발생할 경우 파일 포인터 위치는 비활성화 상태입니다. 부분적으로 읽은 항목의 값은 확인할 수 없습니다.

텍스트 모드 스트림에서 사용할 때 요청된 데이터 양(즉, *크기* \* *수)이*내부 **FILE** \* 버퍼 크기보다 크거나 같으면(기본적으로 [setvbuf를](../../c-runtime-library/reference/setvbuf.md)사용하여 구성할 수 있는 4096바이트), 스트림 데이터는 사용자 제공 버퍼에 직접 복사되고 해당 버퍼에서 줄 바꿈 변환이 수행됩니다. 변환된 데이터는 버퍼에 복사된 스트림 데이터보다 짧을 수 있기 때문에 *버퍼*\[*return_value* \* *크기(return_value* **fread에서**반환 값인 경우) 파일에서 변환되지 않은 데이터가 포함될 수 있습니다. *return_value* 따라서 *버퍼의*\[의도가 C 스타일 문자열로 작동하려면 버퍼*return_value* \* *크기]에서*문자 데이터를 null-terminate하는 것이 좋습니다. 텍스트 모드와 바이너리 모드의 효과에 대한 자세한 내용은 [fopen을](fopen-wfopen.md) 참조하십시오.

이 함수는 다른 스레드를 잠급니다. 비잠금 버전이 필요한 경우 **_fread_nolock.**

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fread**|\<stdio.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fread.c
// This program opens a file named FREAD.OUT and
// writes 25 characters to the file. It then tries to open
// FREAD.OUT and read in 25 characters. If the attempt succeeds,
// the program displays the number of actual items read.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char list[30];
   int  i, numread, numwritten;

   // Open file in text mode:
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )
   {
      for ( i = 0; i < 25; i++ )
         list[i] = (char)('z' - i);
      // Write 25 characters to stream
      numwritten = fwrite( list, sizeof( char ), 25, stream );
      printf( "Wrote %d items\n", numwritten );
      fclose( stream );

   }
   else
      printf( "Problem opening the file\n" );

   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )
   {
      // Attempt to read in 25 characters
      numread = fread( list, sizeof( char ), 25, stream );
      printf( "Number of items read = %d\n", numread );
      printf( "Contents of buffer = %.25s\n", list );
      fclose( stream );
   }
   else
      printf( "File could not be opened\n" );
}
```

```Output
Wrote 25 items
Number of items read = 25
Contents of buffer = zyxwvutsrqponmlkjihgfedcb
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[텍스트 및 이진 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
[fopen](fopen-wfopen.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
