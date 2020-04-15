---
title: fopen_s, _wfopen_s
ms.date: 4/2/2020
api_name:
- _wfopen_s
- fopen_s
- _o__wfopen_s
- _o_fopen_s
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
- fopen_s
- _tfopen_s
- _wfopen_s
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
ms.openlocfilehash: 80d04e75637cfab9795bf5dfb9da9786cf4ebd71
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346484"
---
# <a name="fopen_s-_wfopen_s"></a>fopen_s, _wfopen_s

파일을 엽니다. 이러한 버전의 [fopen, _wfopen](fopen-wfopen.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

## <a name="syntax"></a>구문

```C
errno_t fopen_s(
   FILE** pFile,
   const char *filename,
   const char *mode
);
errno_t _wfopen_s(
   FILE** pFile,
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>매개 변수

*pFile*<br/>
열린 파일에 대한 포인터를 수신할 파일 포인터에 대한 포인터입니다.

*파일*<br/>
파일 이름입니다.

*모드*<br/>
허용되는 액세스 형식입니다.

## <a name="return-value"></a>Return Value

성공 시 0이고, 실패 시 오류 코드입니다. 이러한 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

### <a name="error-conditions"></a>오류 조건

|*pFile*|*파일*|*모드*|Return Value|*pFile의* 내용|
|-------------|----------------|------------|------------------|------------------------|
|**Null**|any|any|**아인발 ()에인발 (것)**|변경 안 됨|
|any|**Null**|any|**아인발 ()에인발 (것)**|변경 안 됨|
|any|any|**Null**|**아인발 ()에인발 (것)**|변경 안 됨|

## <a name="remarks"></a>설명

**fopen_s** **_wfopen_s** 의해 열리는 파일은 할 수 없습니다. 파일을 공유할 수 있어야 하는 경우 읽기/쓰기 공유에 **_SH_DENYNO** 같은 적절한 공유 모드 상수와 함께 [_wfsopen _fsopen](fsopen-wfsopen.md) 사용합니다.

**fopen_s** 함수는 *파일 이름으로*지정된 파일을 엽니다. **_wfopen_s** **fopen_s**와이드 문자 버전입니다. **_wfopen_s** 인수는 와이드 문자 문자열입니다. **_wfopen_s** **fopen_s** 달리 동일하게 행동합니다.

**fopen_s** 실행 지점에서 파일 시스템에서 유효한 경로를 허용합니다. 매핑된 네트워크 드라이브와 관련된 UNC 경로 및 경로는 코드를 실행하는 시스템이 실행 시 공유 또는 매핑된 네트워크 드라이브에 액세스할 수 있는 한 **fopen_s** 허용됩니다. **fopen_s**대한 경로를 생성할 때 실행 환경에서 드라이브, 경로 또는 네트워크 공유의 가용성에 대해 가정하지 마십시오. 슬래시(/) 또는 백슬래시(\\)를 경로의 디렉터리 구분 기호로 사용할 수 있습니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. *pFile*, *파일 이름*또는 *모드가* null 포인터인 경우 이러한 함수는 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 예외를 생성합니다.

파일에서 다른 작업을 수행하기 전에 항상 반환 값을 검사하여 함수가 성공했는지를 확인하세요. 오류가 발생하면 오류 코드가 반환되고 전역 변수 **errno가** 설정됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="unicode-support"></a>유니코드 지원

**fopen_s** 유니코드 파일 스트림을 지원합니다. 새 유니코드 또는 기존 유니코드 파일을 열려면 원하는 인코딩을 지정하는 *ccs* 플래그를 전달하여 **fopen_s.**

**fopen_s(&fp, "newfile.txt", "rw, ccs=**_인코딩");_**");**

*인코딩허용* 값은 **유니코드,** **UTF-8**및 **UTF-16LE입니다.** *인코딩에*값이 지정되지 않은 경우 **fopen_s** ANSI 인코딩을 사용합니다.

파일이 이미 있고 읽기 또는 추가용으로 열려 있는 경우 BOM(바이트 순서 표시)(파일에 있는 경우)에 따라 인코딩이 결정됩니다. BOM 인코딩은 *ccs* 플래그에 의해 지정된 인코딩보다 우선합니다. *ccs* 인코딩은 BOM이 없거나 파일이 새 파일인 경우에만 사용됩니다.

> [!NOTE]
> BOM 검색은 유니코드 모드에서 열린 파일에만 적용됩니다. 즉, *ccs* 플래그를 전달하여 입니다.

다음 표에서는 **fopen_s** 제공되는 다양한 *ccs* 플래그와 파일의 바이트 순서 표시에 대한 모드를 요약합니다.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>ccs 플래그 및 BOM을 기반으로 사용되는 인코딩

|ccs 플래그|BOM이 없거나 새 파일|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**유니코드**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

유니코드 모드에서 쓰도록 파일을 열면 BOM이 파일에 자동으로 기록됩니다.

*모드가* **"a, ccs=**_인코딩"인_**"** 경우 **먼저** 읽기 액세스 및 쓰기 액세스 가 모두 있는 파일을 열려고 fopen_s. 성공하면 함수가 BOM을 읽어서 파일에 대한 인코딩을 결정하고, 실패하면 함수가 파일에 대한 기본 인코딩을 사용합니다. 두 경우 모두 **fopen_s** 쓰기 전용 액세스 권한을 가진 파일을 다시 엽니다. (이 **모드에만** 적용, 하지 **+**.)

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen_s**|**fopen_s**|**fopen_s**|**_wfopen_s**|

문자열 *모드는* 다음과 같이 파일에 대해 요청된 액세스 의 종류를 지정합니다.

|*모드*|액세스 권한|
|-|-|
| **"r"** | 읽기 위해 엽니다. 파일이 없거나 찾을 수 없는 경우 **fopen_s** 호출이 실패합니다. |
| **"w"** | 쓰기 위해 빈 파일을 엽니다. 지정한 파일이 있으면 이 파일의 내용은 삭제됩니다. |
| **"가성비 좋은"** | 새 데이터를 파일에 쓰기 전에 EOF(파일 끝) 표식을 제거하지 않고 파일의 끝에 쓰기(추가)하기 위해 엽니다. 파일이 없는 경우 파일을 만듭니다. |
| **"r+"** | 읽고 쓰기 위해 엽니다. 파일이 있어야 합니다. |
| **"w+"** | 읽고 쓰기 위해 빈 파일을 엽니다. 파일이 있으면 이 파일의 내용은 삭제됩니다. |
| **"a+"** | 읽고 추가하기 위해 엽니다. 추가 작업에는 새 데이터를 파일에 쓰기 전에 EOF 표식을 제거하는 작업이 포함됩니다. 쓰기 완료 후 EOF 표식이 복원되지 않습니다. 파일이 없는 경우 파일을 만듭니다. |

**"a"** 또는 **"a+"** 액세스 유형을 사용하여 파일을 열면 모든 쓰기 작업이 파일 끝에 발생합니다. 파일 포인터는 [fseek](fseek-fseeki64.md) 또는 [되감기를](rewind.md)사용하여 재배치할 수 있지만 기존 데이터를 덮어쓸 수 없도록 쓰기 작업이 수행되기 전에 항상 파일의 끝으로 다시 이동됩니다.

**"a"** 모드는 파일에 적용하기 전에 EOF 마커를 제거하지 않습니다. 추가 작업이 수행된 이후에는 MS-DOS TYPE 명령은 원래 EOF 표식까지만 데이터를 표시하고 파일에 추가된 데이터는 표시하지 않습니다. **"a+"** 모드는 파일에 부가하기 전에 EOF 마커를 제거합니다. 추가 후에는 MS-DOS TYPE 명령으로 파일의 모든 데이터를 표시합니다. CTRL+Z EOF 마커를 사용하여 종료되는 스트림 파일에 "a+" 모드를 적용하려면 **"a+"** 모드가 필요합니다.

**"r+"**, **"w+"** 또는 **"a+"** 액세스 유형을 지정하면 읽기와 쓰기가 모두 허용됩니다. (이 파일은 "업데이트"를 위해 열려 있다고합니다.) 그러나 읽기에서 쓰기로 전환할 때 입력 작업에 EOF 마커가 발생해야 합니다. EOF가 없는 경우 사이에 파일 위치 지정 함수를 호출해야 합니다. 파일 위치 지정 함수는 **fsetpos,** [fseek](fseek-fseeki64.md)및 [되감기입니다.](rewind.md) 쓰기에서 읽기로 전환할 때 **fflush** 또는 파일 위치 지정 함수에 대한 중간 호출을 사용해야 합니다.

위의 값 외에도 다음 문자를 *모드에* 포함하여 줄 바선 문자의 변환 모드를 지정할 수 있습니다.

|*모드* 수정자|번역 모드|
|-|-|
| **T** | 텍스트(변환됨) 모드에서 엽니다. |
| **B** | 바이너리 (번역되지 않은) 모드에서 열립니다. 캐리지 리턴 및 라인 이송 문자와 관련된 변환이 억제됩니다. |

텍스트(번역) 모드에서 CTRL+Z는 입력시 파일 끝 문자로 해석됩니다. **"a+"로**읽기/쓰기를 위해 열린 파일에서 **fopen_s** 파일 끝에 있는 CTRL+Z를 확인하고 가능하면 제거합니다. 이는 [fseek](fseek-fseeki64.md) 및 **ftell을** 사용하여 CTRL+Z로 끝나는 파일 내에서 이동하면 [fseek가](fseek-fseeki64.md) 파일 끝 근처에서 부적절하게 동작할 수 있기 때문에 수행됩니다.

또한 텍스트 모드에서는 캐리지 리턴 라인 피드 조합이 입력시 단일 줄 피드로 변환되고 라인 피드 문자는 출력시 캐리지 리턴 라인 피드 조합으로 변환됩니다. 유니코드 스트림 I/O 함수가 텍스트 모드에서 작동할 경우(기본값) 소스 또는 대상 스트림은 멀티바이트 문자 시퀀스로 간주됩니다. 따라서 유니코드 스트림 입력 함수는 **mbtowc** 함수 호출과 마찬가지로 멀티바이트 문자를 와이드 문자로 변환합니다. 동일한 이유로 유니코드 스트림 출력 함수는 **wctomb** 함수 호출과 마찬가지로 와이드 문자를 멀티바이트 문자로 변환합니다.

**t** 또는 **b가** *모드로*제공되지 않으면 기본 변환 모드는 전역 변수 [_fmode](../../c-runtime-library/fmode.md)의해 정의됩니다. **t** 또는 **b가** 인수에 접두사된 경우 함수가 실패하고 **NULL을**반환합니다.

텍스트 및 이진 모드를 유니코드 및 멀티바이트 스트림 I/O에서 사용하는 방법에 대한 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [텍스트 및 이진 모드의 유니코드 스트림 I/O](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)를 참조하세요.

|*모드* 수정자|동작|
|-|-|
| **C** | **fflush** 또는 **_flushall** 호출되는 경우 파일 버퍼의 내용이 디스크에 직접 기록되도록 연결된 *파일 이름에* 대한 커밋 플래그를 활성화합니다. |
| **N** | 연결된 *파일 이름에* 대한 커밋 플래그를 "커밋 없음"으로 재설정합니다. 이것이 기본값입니다. 또한 프로그램을 COMMODE.OBJ와 연결할 경우 전역 커밋 플래그를 재정의합니다. 프로그램을 COMMODE.OBJ와 명시적으로 연결하지 않을 경우 전역 커밋 플래그 기본값은 "커밋 안 함"입니다( [Link Options](../../c-runtime-library/link-options.md)참조). |
| **N** | 자식 프로세스에서 파일을 상속하지 않도록 지정합니다. |
| **S** | 캐싱이 디스크에서 순차적 액세스를 위해 최적화되며 이에 제한되지 않습니다. |
| **R** | 캐싱이 디스크에서 임의 액세스를 위해 최적화되며 이에 제한되지 않습니다. |
| **T** | 파일을 임시 파일로 지정합니다. 가능하면 디스크에 플러시되지 않습니다. |
| **D** | 파일을 임시 파일로 지정합니다. 마지막 파일 포인터를 닫을 때 삭제됩니다. |
| **ccs=**_인코딩_ | 이 파일에 사용할 인코딩된 문자 **집합(UTF-8,** **UTF-16LE**또는 **UNICODE**중 하나)을 지정합니다. ANSI 인코딩을 원할 경우 지정되지 않은 상태로 둡니다. |

**fopen_s** 사용된 *모드* 문자열에 대한 유효한 문자와 [_fdopen](fdopen-wfdopen.md) 다음과 같이 [_open](open-wopen.md) [및 _sopen](sopen-wsopen.md)사용되는 *oflag* 인수에 해당합니다.

|*모드* 문자열의 문자|_open/_sopen 대한 *등가값*|
|-------------------------------|----------------------------------------------------|
|**a.**|**_O_WRONLY** &#124; **_O_APPEND** (일반적으로 **_O_CREAT _O_CREAT** &#124;** _O_APPEND**에 **_O_WRONLY &#124;****|
|**a+**|**_O_RDWR** **_O_APPEND** &#124; **(_O_RDWR** 일반적으로 &#124; _O_APPEND &#124; **_O_CREAT** **&#124;)**|
|**R**|**_O_RDONLY**|
|**r +**|**_O_RDWR**|
|**W**|**_O_WRONLY** (일반적으로 **&#124; _O_CREAT &#124;**** _O_TRUNC**에 **_O_WRONLY)**|
|**w +**|**_O_RDWR** **(일반적으로** _O_RDWR **_O_CREAT &#124;** **_O_TRUNC**&#124;)|
|**B**|**_O_BINARY**|
|**T**|**_O_TEXT**|
|**C**|없음|
|**N**|없음|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**ccs=유니코드**|**_O_WTEXT**|
|**ccs=UTF-8**|**_O_UTF8**|
|**ccs=UTF-16LE**|**_O_UTF16**|

**rb** 모드를 사용하는 경우 코드를 이식할 필요가 없으며 많은 파일을 읽거나 네트워크 성능에 신경 쓰지 않는 경우 매핑된 Win32 파일도 옵션이 될 수 있습니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fopen_s**|\<stdio.h>|
|**_wfopen_s**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

**c**, **n**및 **t** *모드* 옵션은 **fopen_s** 및 [_fdopen](fdopen-wfdopen.md) 위한 Microsoft 확장이며 ANSI 이식성이 필요한 곳에 는 사용하지 않아야 합니다.

## <a name="example"></a>예제

```C
// crt_fopen_s.c
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   errno_t err;

   // Open for read (will fail if file "crt_fopen_s.c" does not exist)
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );
   if( err == 0 )
   {
      printf( "The file 'crt_fopen_s.c' was opened\n" );
   }
   else
   {
      printf( "The file 'crt_fopen_s.c' was not opened\n" );
   }

   // Open for write
   err = fopen_s( &stream2, "data2", "w+" );
   if( err == 0 )
   {
      printf( "The file 'data2' was opened\n" );
   }
   else
   {
      printf( "The file 'data2' was not opened\n" );
   }

   // Close stream if it is not NULL
   if( stream )
   {
      err = fclose( stream );
      if ( err == 0 )
      {
         printf( "The file 'crt_fopen_s.c' was closed\n" );
      }
      else
      {
         printf( "The file 'crt_fopen_s.c' was not closed\n" );
      }
   }

   // All other files are closed:
   int numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen_s.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
