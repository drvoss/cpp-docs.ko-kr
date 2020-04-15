---
title: fgetpos
ms.date: 4/2/2020
api_name:
- fgetpos
- _o_fgetpos
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
- fgetpos
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
ms.openlocfilehash: 0c16150a6240068e1453ec90b396c87ab9ece5a4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346918"
---
# <a name="fgetpos"></a>fgetpos

스트림의 파일 위치 표시기를 가져옵니다.

## <a name="syntax"></a>구문

```C
int fgetpos(
   FILE *stream,
   fpos_t *pos
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
대상 스트림입니다.

*Pos*<br/>
위치 표시기 스토리지입니다.

## <a name="return-value"></a>Return Value

성공하면 **fgetpos는 0을** 반환합니다. 오류가 발생할 경우 영하지 않은 값을 반환하고 **errno를** 다음 매니페스트 상수 중 하나로 설정합니다(STDIO에 정의). H): 지정된 스트림이 유효한 파일 포인터가 아니거나 액세스할 수 없음을 의미하는 **EBADF**또는 **eINVAL은** *스트림* 값 또는 *pos* 값이 null 포인터인 경우와 같이 유효하지 않음을 의미합니다. *stream* 또는 *pos가* **NULL** 포인터인 경우 함수는 매개 변수 유효성 검사에 설명된 대로 잘못된 매개 변수 처리기를 [호출합니다.](../../c-runtime-library/parameter-validation.md)

## <a name="remarks"></a>설명

**fgetpos** 함수는 *스트림* 인수의 파일 위치 표시기의 현재 값을 가져옵니다 및 *pos에*의해 가리키는 개체에 저장 합니다. **fsetpos** 함수는 나중에 *pos에* 저장된 정보를 사용하여 **fgetpos가** 호출되었을 때 *스트림* 인수의 포인터를 해당 위치로 재설정할 수 있습니다. *pos* 값은 내부 형식으로 저장되며 **fgetpos** 및 **fsetpos에서만**사용하기 위한 것입니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fgetpos**|\<stdio.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fgetpos.c
// This program uses fgetpos and fsetpos to
// return to a location in a file.

#include <stdio.h>

int main( void )
{
   FILE   *stream;
   fpos_t pos;
   char   buffer[20];

   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {
      perror( "Trouble opening file" );
      return -1;
   }

   // Read some data and then save the position.
   fread( buffer, sizeof( char ), 8, stream );
   if( fgetpos( stream, &pos ) != 0 ) {
      perror( "fgetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fgetpos: %.13s\n", buffer );

   // Restore to old position and read data
   if( fsetpos( stream, &pos ) != 0 ) {
      perror( "fsetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fsetpos: %.13s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crt_fgetpostxt"></a>입력: crt_fgetpos.txt

```Input
fgetpos gets a stream's file-position indicator.
```

### <a name="output-crt_fgetpostxt"></a>출력 crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
