---
title: freopen, _wfreopen
ms.date: 4/2/2020
api_name:
- freopen
- _wfreopen
- _o__wfreopen
- _o_freopen
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
- _wfreopen
- _tfreopen
- freopen
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
ms.openlocfilehash: 635775469ed6545abd6da43ba27d496d439f80ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345864"
---
# <a name="freopen-_wfreopen"></a>freopen, _wfreopen

파일 포인터를 다시 할당합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
FILE *freopen(
   const char *path,
   const char *mode,
   FILE *stream
);
FILE *_wfreopen(
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*경로*<br/>
새 파일의 경로입니다.

*모드*<br/>
허용되는 액세스 형식입니다.

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

각 함수는 새로 열린 파일에 대한 포인터를 반환합니다. 오류가 발생하면 원본 파일이 닫히고 함수가 **NULL** 포인터 값을 반환합니다. *path*, *mode*또는 *stream이* null 포인터이거나 *파일 이름이* 빈 문자열인 경우 이러한 함수는 매개 변수 [유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이러한 함수는 **errno를** **EINVAL로** 설정하고 **NULL을**반환합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

이러한 함수의 더 안전한 버전이 있습니다. [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md)를 참조하세요.

**freopen** 함수는 현재 *스트림과* 연결된 파일을 닫고 *경로로*지정된 파일에 *스트림을* 다시 할당합니다. **_wfreopen** **_freopen**와이드 문자 버전입니다. **_wfreopen** *경로* 및 *모드* 인수는 와이드 문자 문자열입니다. **_wfreopen** **_freopen** 달리 동일하게 행동합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen**|**freopen**|**freopen**|**_wfreopen**|

**freopen은** 일반적으로 미리 열린 파일을 **stdin,** **stdout**및 **stderr를** 사용자가 지정한 파일로 리디렉션하는 데 사용됩니다. *스트림과* 연결된 새 파일은 다음과 같이 파일에 대해 요청된 액세스 유형을 지정하는 문자 문자열인 *모드로*열립니다.

|*모드*|액세스 권한|
|-|-|
| **"r"** | 읽기 위해 엽니다. 파일이 없거나 찾을 수 없는 경우 **freopen** 호출이 실패합니다. |
| **"w"** | 쓰기 위해 빈 파일을 엽니다. 지정한 파일이 있으면 이 파일의 내용은 삭제됩니다. |
| **"가성비 좋은"** | 새 데이터를 파일에 쓰기 전에 EOF(파일 끝) 표식을 제거하지 않고 파일의 끝에 쓰기(추가)하기 위해 엽니다. 파일이 없는 경우 파일을 만듭니다. |
| **"r+"** | 읽고 쓰기 위해 엽니다. 파일이 있어야 합니다. |
| **"w+"** | 읽고 쓰기 위해 빈 파일을 엽니다. 파일이 있으면 이 파일의 내용은 삭제됩니다. |
| **"a+"** | 읽고 추가하기 위해 엽니다. 추가 작업에는 새 데이터를 파일에 쓰기 전에 EOF 표식을 제거하는 작업이 포함됩니다. 쓰기 완료 후 EOF 표식이 복원되지 않습니다. 파일이 없는 경우 파일을 만듭니다. |

기존 파일을 파괴할 수 있기 때문에 **"w"** 및 **"w+"** 형식을 주의하여 사용하십시오.

**"a"** 또는 **"a+"** 액세스 유형으로 파일을 열면 모든 쓰기 작업이 파일 끝에 수행됩니다. 파일 포인터는 [fseek](fseek-fseeki64.md) 또는 [되감기를](rewind.md)사용하여 재배치할 수 있지만 쓰기 작업이 수행되기 전에 파일 포인터는 항상 파일 의 끝으로 다시 이동됩니다. 따라서 기존 데이터를 덮어쓸 수 없습니다.

**"a"** 모드는 파일에 적용하기 전에 EOF 마커를 제거하지 않습니다. 추가 작업이 수행된 이후에는 MS-DOS TYPE 명령은 원래 EOF 표식까지만 데이터를 표시하고 파일에 추가된 데이터는 표시하지 않습니다. **"a+"** 모드는 파일에 부가하기 전에 EOF 마커를 제거합니다. 추가 후에는 MS-DOS TYPE 명령으로 파일의 모든 데이터를 표시합니다. CTRL+Z EOF 마커로 종료되는 스트림 파일에 "a+" 모드를 적용하려면 **"a+"** 모드가 필요합니다.

**"r+"**, **"w+"** 또는 **"a+"** 액세스 유형이 지정되면 읽기와 쓰기가 모두 허용됩니다(파일이 "업데이트"를 위해 열려 있다고 함). 그러나 읽기와 쓰기를 전환할 때는 먼저 [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md) 또는 [rewind](rewind.md) 작업이 있어야 합니다. 원하는 경우 [fsetpos](fsetpos.md) 또는 [fseek](fseek-fseeki64.md) 작업에 대해 현재 위치를 지정할 수 있습니다. 위의 값 외에도 다음 문자 중 하나가 *모드* 문자열에 포함되어 새 줄의 변환 모드를 지정할 수 있습니다.

|*모드* 수정자|번역 모드|
|-|-|
| **T** | 텍스트(변환됨) 모드에서 엽니다. |
| **B** | 바이너리 (번역되지 않은) 모드에서 열립니다. 캐리지 리턴 및 라인 이송 문자와 관련된 변환이 억제됩니다. |

텍스트(번역) 모드에서 캐리지 리턴 라인 피드(CR-LF) 조합은 입력시 단일 줄 피드(LF) 문자로 변환됩니다. LF 문자는 출력시 CR-LF 조합으로 변환됩니다. 또한 CTRL+Z는 입력 시 파일 끝 문자로 변환됩니다. 읽기 또는 **"a+"로**읽기 및 읽기를 위해 열린 파일에서 런타임 라이브러리는 파일 끝에 있는 CTRL+Z를 확인하고 가능하면 제거합니다. 이는 [fseek](fseek-fseeki64.md) 및 [ftell을](ftell-ftelli64.md) 사용하여 파일 내에서 이동하면 파일 끝 근처에서 [fseek가](fseek-fseeki64.md) 부적절하게 동작할 수 있기 때문에 수행됩니다. **t** 옵션은 ANSI 이식성이 필요한 곳에서 는 사용하지 않아야 하는 Microsoft 확장입니다.

**t** 또는 **b가** *모드로*제공되지 않으면 기본 변환 모드는 전역 변수 [_fmode](../../c-runtime-library/fmode.md)의해 정의됩니다. **t** 또는 **b가** 인수에 접두사된 경우 함수가 실패하고 **NULL을**반환합니다.

텍스트 모드와 이진 모드에 대한 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**freopen**|\<stdio.h>|
|**_wfreopen**|\<stdio.h> 또는 \<wchar.h>|

콘솔은 UWP(유니버설 Windows 플랫폼) 앱에서 지원되지 않습니다. 콘솔, **stdin,** **stdout**및 **stderr와**연결된 표준 스트림 핸들은 C 런타임 함수가 UWP 앱에서 사용하기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_freopen.c
// compile with: /W3
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.
#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   // Reassign "stderr" to "freopen.out":
   stream = freopen( "freopen.out", "w", stderr ); // C4996
   // Note: freopen is deprecated; consider using freopen_s instead

   if( stream == NULL )
      fprintf( stdout, "error on freopen\n" );
   else
   {
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );
      fprintf( stream, "This will go to the file 'freopen.out'\n" );
      fclose( stream );
   }
   system( "type freopen.out" );
}
```

```Output
successfully reassigned
This will go to the file 'freopen.out'
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
