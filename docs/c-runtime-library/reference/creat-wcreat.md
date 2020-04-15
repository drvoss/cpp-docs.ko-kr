---
title: _creat, _wcreat
ms.date: 4/2/2020
api_name:
- _creat
- _wcreat
- _o__creat
- _o__wcreat
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
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
ms.openlocfilehash: 18ecf78d2cbff3647eae912a1bb1b17d5340f185
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348332"
---
# <a name="_creat-_wcreat"></a>_creat, _wcreat

새 파일을 만듭니다. **_creat** **_wcreat** 더 이상 사용되지 않았습니다. 대신 [_sopen_s _wsopen_s](sopen-s-wsopen-s.md) 사용합니다.

## <a name="syntax"></a>구문

```C
int _creat(
   const char *filename,
   int pmode
);
int _wcreat(
   const wchar_t *filename,
   int pmode
);
```

### <a name="parameters"></a>매개 변수

*파일*<br/>
새 파일의 이름입니다.

*Pmode*<br/>
권한 설정

## <a name="return-value"></a>Return Value

이러한 함수는 성공하는 경우 생성된 파일에 파일 설명자를 반환합니다. 그렇지 않으면 함수는 다음 표에 표시된 대로 -1을 반환하고 **errno를** 설정합니다.

|**에르노** 설정|Description|
|---------------------|-----------------|
|**EACCES**|*파일 이름은* 기존 읽기 전용 파일을 지정하거나 파일 대신 디렉터리를 지정합니다.|
|**EMFILE**|사용 가능한 추가 파일 설명자가 없습니다.|
|**이노엔트 (이노엔트 주)**|지정된 파일을 찾을 수 없습니다.|

*파일 이름이* **NULL인**경우 이러한 함수는 매개 변수 [유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이러한 함수는 **errno를** **EINVAL로** 설정하고 -1을 반환합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

**_creat** 함수는 새 파일을 만들거나 기존 파일을 열고 자를 합니다. **_wcreat** **_creat**와이드 문자 버전입니다. **_wcreat** *파일 이름* 인수는 와이드 문자 문자열입니다. **_wcreat** **_creat** 달리 동일하게 행동합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

*filename으로* 지정된 파일이 없으면 지정된 사용 권한 설정으로 새 파일이 만들어지고 쓰기 위해 열립니다. 파일이 이미 있고 사용 권한 설정을 사용하면 쓰기가 허용되는 **경우 _creat** 파일을 길이 0으로 트렁크하여 이전 내용을 파기하고 작성을 위해 엽니다. 권한 *설정인 pmode*는 새로 만든 파일에만 적용됩니다. 새 파일은 처음으로 닫힌 이후 지정된 권한 설정을 받습니다. 정수 식 *pmode는* SYS\Stat.h에 정의된 매니페스트 상 **_S_IWRITE** 및 **_S_IREAD**중 하나 또는 둘 다를 포함합니다. 두 상수가 모두 부여되면 비트(bitwise) 또는 **&#124;** 연산자(&#124;)와 결합됩니다. *pmode* 매개 변수는 다음 값 중 하나로 설정됩니다.

|값|정의|
|-----------|----------------|
|**_S_IWRITE**|쓰기를 허용합니다.|
|**_S_IREAD**|읽기를 허용합니다.|
|**_S_IREAD** &#124; **_S_IWRITE**|읽기 및 쓰기를 허용합니다.|

쓰기 권한이 부여되지 않은 경우 파일은 읽기 전용입니다. 모든 파일을 항상 읽을 수 있으므로 쓰기 전용 권한을 부여할 수 없습니다. 그런 다음 **_S_IWRITE** **모드와 _S_IREAD** | **_S_IWRITE** 동일합니다. **_creat** 사용하여 열린 파일은 항상 **_SH_DENYNO**함께 호환성 [모드(_sopen](sopen-wsopen.md)참조)에서 열립니다.

**_creat** 권한을 설정하기 전에 현재 파일 권한 마스크를 *pmode에* [적용합니다(_umask](umask.md)참조). **_creat** 주로 이전 라이브러리와의 호환성을 위해 제공됩니다. *oflag* 매개 변수에 **_O_CREAT** **및 _O_TRUNC** **_open** 호출하는 것은 **_creat** 동일하며 새 코드에 적합합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|
|**_wcreat**|\<io.h> 또는 \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_creat.c
// compile with: /W3
// This program uses _creat to create
// the file (or truncate the existing file)
// named data and open it for writing.

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int fh;

   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996
   // Note: _creat is deprecated; use _sopen_s instead
   if( fh == -1 )
      perror( "Couldn't create data file" );
   else
   {
      printf( "Created data file.\n" );
      _close( fh );
   }
}
```

```Output
Created data file.
```

## <a name="see-also"></a>참고 항목

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>
