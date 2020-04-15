---
title: getc, getwc
ms.date: 4/2/2020
api_name:
- getwc
- getc
- _o_getc
- _o_getwc
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
- _gettc
- getwc
- _gettchar
- getc
helpviewer_keywords:
- characters, reading
- _gettc function
- getwchar function
- streams, reading characters from
- reading characters from streams
- getc function
- getwc function
- gettc function
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
ms.openlocfilehash: 5c05d7a2743cd0c1e843d6895e8f5574031ab098
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344842"
---
# <a name="getc-getwc"></a>getc, getwc

스트림에서 문자를 읽습니다.

## <a name="syntax"></a>구문

```C
int getc(
   FILE *stream
);
wint_t getwc(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
입력 스트림입니다.

## <a name="return-value"></a>Return Value

읽은 문자를 반환합니다. 읽기 오류 또는 파일 끝 조건을 나타내기 위해 **getc은** **EOF를**반환하고 **getwc는** **WEOF를**반환합니다. **getc의** **경우, 페러** 또는 **feof를** 사용하여 오류가 있는지 또는 파일의 끝을 확인하십시오. *스트림이* **NULL인**경우 **getc** 및 **getwc는** [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이러한 함수는 **EOF(또는** **getwc에** **대한 WEOF)를** 반환하고 **errno를** **EINVAL로**설정합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

각 루틴은 파일에서 현재 위치의 단일 문자를 읽고 다음 문자를 가리킬 연결된 파일 포인터(정의된 경우)를 늘립니다. 파일이 *스트림*과 연결됩니다.

이러한 함수는 호출 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않는 버전의 경우 [_getc_nolock, _getwc_nolock](getc-nolock-getwc-nolock.md)을 참조하세요.

이어서 루틴별 설명이 제공됩니다.

|루틴에서 반환된 값|설명|
|-------------|-------------|
|**getc**|**fgetc와**동일하지만 함수 및 매크로로 구현됩니다.|
|**getwc**|**getc의**와이드 문자 버전 . *스트림이* 텍스트 모드 또는 이진 모드에서 열리는지 여부에 따라 다중 바이트 문자 또는 넓은 문자를 읽습니다.|

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettc**|**getc**|**getc**|**getwc**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**getc**|\<stdio.h>|
|**getwc**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_getc.c
// Use getc to read a line from a file.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;
    FILE* fp;

    // Read a single line from the file "crt_getc.txt".

    fopen_s(&fp, "crt_getc.txt", "r");
    if (!fp)
    {
       printf("Failed to open file crt_getc.txt.\n");
       exit(1);
    }

    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);

    fclose(fp);
}
```

### <a name="input-crt_getctxt"></a>입력: crt_getc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>출력

```Output
Input was: Line one.
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
