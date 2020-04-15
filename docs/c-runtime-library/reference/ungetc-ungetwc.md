---
title: ungetc, ungetwc
ms.date: 4/2/2020
api_name:
- ungetwc
- ungetc
- _o_ungetc
- _o_ungetwc
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
- _ungettc
- ungetwc
- ungetc
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
ms.openlocfilehash: 484af7b72f860a8a9d12cf0b62444871caad4675
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361291"
---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc

스트림에 문자를 다시 푸시합니다.

## <a name="syntax"></a>구문

```C
int ungetc(
   int c,
   FILE *stream
);
wint_t ungetwc(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*C*<br/>
푸시할 문자 수입니다.

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

성공하면 이러한 각 함수는 문자 인수 *c를*반환합니다. *c를* 뒤로 밀수 없거나 문자를 읽지 않은 경우 입력 스트림이 변경되지 않고 **ungetc가** **EOF를**반환합니다. **ungetwc** 는 **WEOF를**반환합니다. *스트림이* **NULL인**경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있으면 **EOF** 또는 **WEOF가** 반환되고 **errno가** **EINVAL로**설정됩니다.

이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**ungetc** 함수는 문자 *c를* *다시 스트림으로* 밀어 내고 파일 끝 표시기를 지웁습니다. 이때 스트림이 읽기를 위해 열려 있어야 합니다. *스트림에서* 후속 읽기 작업은 *c로*시작됩니다. **ungetc를** 사용하여 **스트림에 EOF를** 푸시하려는 시도는 무시됩니다.

**스트림에** 배치된 문자는 스트림에서 문자를 읽기 전에 **fflush,** [fseek,](fseek-fseeki64.md) **fsetpos**또는 [되감기가](rewind.md) 호출되는 경우 지워질 수 있습니다. 파일 위치 표시기에는 문자가 다시 푸시되기 전의 값이 지정됩니다. 스트림에 해당하는 외부 스토리지는 변경되지 않습니다. 텍스트 스트림에 대해 성공적으로 **ungetc** 호출할 때 푸시백 문자를 모두 읽거나 삭제할 때까지 파일 위치 표시기를 지정하지 않습니다. 이진 스트림에 대해 성공적으로 **ungetc** 호출할 때마다 파일 위치 표시등이 감소됩니다. 호출 전에 값이 0이면 호출 후 값이 정의되지 않습니다.

두 호출 간에 읽기 또는 파일 위치 지정 작업 없이 **ungetc를** 두 번 호출하는 경우 결과를 예측할 수 없습니다. **fscanf에**대한 호출 후 다른 읽기 작업(예: **getc)이**수행되지 않는 한 **ungetc에** 대한 호출이 실패할 수 있습니다. **fscanf** 자체가 **ungetc를**호출하기 때문입니다.

**ungetwc는** **ungetc의**넓은 문자 버전입니다. 그러나 텍스트 또는 이진 스트림에 대해 **ungetwc** 호출이 성공할 때마다 푸시백 문자를 모두 읽거나 삭제할 때까지 파일 위치 표시기의 값이 지정되지 않습니다.

이러한 함수는 스레드로부터 안전하며, 실행 중에 중요한 데이터를 잠급니다. 데이터를 잠그지 않는 버전은 [_ungetc_nolock, _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md)을 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> 또는 \<wchar.h>|

콘솔은 UWP(유니버설 Windows 플랫폼) 앱에서 지원되지 않습니다. 콘솔, **stdin,** **stdout**및 **stderr와**연결된 표준 스트림 핸들은 C 런타임 함수가 UWP 앱에서 사용하기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_ungetc.c
// This program first converts a character
// representation of an unsigned integer to an integer. If
// the program encounters a character that is not a digit,
// the program uses ungetc to replace it in the  stream.
//

#include <stdio.h>
#include <ctype.h>

int main( void )
{
   int ch;
   int result = 0;

   // Read in and convert number:
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )
      result = result * 10 + ch - '0';    // Use digit.
   if( ch != EOF )
      ungetc( ch, stdin );                // Put nondigit back.
   printf( "Number = %d\nNext character in stream = '%c'",
            result, getchar() );
}
```

```Output

      521aNumber = 521
Next character in stream = 'a'
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
