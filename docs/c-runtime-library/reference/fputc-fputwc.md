---
title: fputc, fputwc
ms.date: 4/2/2020
api_name:
- fputc
- fputwc
- _o_fputc
- _o_fputwc
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
- fputc
- fputwc
- _fputtc
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
ms.openlocfilehash: 289e1114a936bdaa41fc59a0526db006536461f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346264"
---
# <a name="fputc-fputwc"></a>fputc, fputwc

스트림에 문자를 씁니다.

## <a name="syntax"></a>구문

```C
int fputc(
   int c,
   FILE *stream
);
wint_t fputwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*C*<br/>
쓸 문자입니다.

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

이러한 각 함수는 기록된 문자를 반환합니다. **fputc의**경우 **EOF의** 반환 값은 오류를 나타냅니다. **fputwc의**경우 **WEOF의** 반환 값은 오류를 나타냅니다. *스트림이* **NULL인**경우 이러한 함수는 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 **EOF를** 반환하고 **errno를** **EINVAL로**설정합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

이러한 각 함수는 연결된 파일 위치 표시기(정의된 경우)로 표시된 위치에 단일 문자 *c를* 파일에 기록하고 적절한 표시기를 진행합니다. **fputc** 및 **fputwc의**경우 파일이 *스트림과*연결됩니다. 파일이 위치 지정 요청을 지원할 수 없거나 추가 모드에서 열린 경우에는 문자가 스트림의 끝에 추가됩니다.

스트림이 ANSI 모드에서 열리는 경우 두 함수는 동일하게 작동합니다. **fputc는** 현재 유니코드 스트림으로 출력을 지원하지 않습니다.

**_nolock** 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 점을 제외하면 동일합니다. 자세한 내용은 [_fputc_nolock, _fputwc_nolock](fputc-nolock-fputwc-nolock.md)를 참조하세요.

이어서 루틴별 설명이 제공됩니다.

|루틴에서 반환된 값|설명|
|-------------|-------------|
|**fputc**|**putc와**동일하지만 함수와 매크로가 아닌 함수로만 구현됩니다.|
|**fputwc**|**fputc의**와이드 문자 버전 . *스트림이* 텍스트 모드 또는 이진 모드에서 열리는지 여부에 따라 *c를* 다중 바이트 문자 또는 넓은 문자로 씁니다.|

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputtc**|**fputc**|**fputc**|**fputwc**|

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fputc**|\<stdio.h>|
|**fputwc**|\<stdio.h> 또는 \<wchar.h>|

콘솔은 UWP(유니버설 Windows 플랫폼) 앱에서 지원되지 않습니다. 콘솔과 연결된 표준 스트림**핸들(stdin,** **stdout**및 **stderr)은**C 런타임 함수가 UWP 앱에서 사용하기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fputc.c
// This program uses fputc
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
   char strptr1[] = "This is a test of fputc!!\n";
   char *p;

   // Print line to stream using fputc.
   p = strptr1;
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;

}
```

```Output
This is a test of fputc!!
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
