---
title: _mktemp_s, _wmktemp_s
ms.date: 4/2/2020
api_name:
- _mktemp_s
- _wmktemp_s
- _o__mktemp_s
- _o__wmktemp_s
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
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
ms.openlocfilehash: 061c5647b2c5a5e79b017cf93989f62ad19cfc0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338762"
---
# <a name="_mktemp_s-_wmktemp_s"></a>_mktemp_s, _wmktemp_s

고유한 파일 이름을 만듭니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_mktemp, _wmktemp](mktemp-wmktemp.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _mktemp_s(
   char *nameTemplate,
   size_t sizeInChars
);
errno_t _wmktemp_s(
   wchar_t *nameTemplate,
   size_t sizeInChars
);
template <size_t size>
errno_t _mktemp_s(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
errno_t _wmktemp_s(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*네임 템플릿*<br/>
파일 이름 패턴입니다.

*크기인차스*<br/>
**_mktemp_s**단일 바이트 문자의 버퍼 크기; null 터미네이터를 포함하여 **_wmktemp_s**와이드 문자입니다.

## <a name="return-value"></a>Return Value

이 두 함수는 모두 정상적으로 실행되면 0을 반환하고 실행 시 오류가 발생하면 오류 코드를 반환합니다.

### <a name="error-conditions"></a>오류 조건

|*네임 템플릿*|*크기인차스*|반환 값|*이름* 템플릿의 새 값|
|----------------|-------------------|----------------------|-------------------------------|
|**Null**|any|**아인발 ()에인발 (것)**|**Null**|
|잘못된 형식(올바른 형식의 비고 섹션 참조)|any|**아인발 ()에인발 (것)**|빈 문자열|
|any|<= X의 수|**아인발 ()에인발 (것)**|빈 문자열|

위의 오류 조건 중 하나라도 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 **errno는** **EINVAL로** 설정되고 함수는 **EINVAL을**반환합니다.

## <a name="remarks"></a>설명

**_mktemp_s** 함수는 *nameTemplate* 인수를 수정하여 고유한 파일 이름을 만듭니다. *nameTemplate* **_mktemp_s** 런타임 시스템에서 현재 사용 중인 다중 바이트 코드 페이지에 따라 다중 바이트 문자 시퀀스를 인식하여 적절한 다중 바이트 문자 문자열 인수를 자동으로 처리합니다. **_wmktemp_s** **_mktemp_s**와이드 문자 버전입니다. **_wmktemp_s** 인수는 와이드 문자 문자열입니다. **_wmktemp_s** **_mktemp_s** **_wmktemp_s** 다중 바이트 문자 문자열을 처리하지 않는다는 점을 제외하고는 다르게 다르게 작동합니다.

이러한 함수의 디버그 라이브러리 버전은 먼저 버퍼를 0xFE로 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

*nameTemplate* 인수에는 **baseXXXXXX**형식이 있으며, *여기서 기본은* 제공하는 새 파일 이름의 일부이고 각 X는 **_mktemp_s**제공된 문자의 자리 표시자입니다. *nameTemplate의* 각 자리 표시자 문자는 대문자 X여야 **_mktemp_s** *기본을* 보존하고 첫 번째 후행 X를 알파벳 문자로 대체합니다. **_mktemp_s** 다음 후행 X를 5자리 값으로 대체합니다. 이 값은 호출 프로세스 또는 다중 스레드 프로그램에서 호출 스레드를 식별하는 고유 번호입니다.

**_mktemp_s** 대한 각 성공적인 호출은 *nameTemplate*. 동일한 *이름인* 동일한 프로세스 또는 스레드에서 후속 호출에서 **_mktemp_s** 이전 호출에서 **_mktemp_s** 반환된 이름과 일치하는 파일 이름을 확인합니다. 지정된 이름에 대한 파일이 없으면 **_mktemp_s** 해당 이름을 반환합니다. 이전에 반환된 모든 이름에 대해 파일이 있는 경우 **_mktemp_s** 이전에 반환된 이름에 사용된 알파벳 문자를 'a'에서 'z'까지 순서대로 사용 가능한 다음 소문자로 대체하여 새 이름을 만듭니다. 예를 *들어, 기준이* 다음과 같은 경우:

> **Fn**

**_mktemp_s** 제공하는 5자리 값은 12345이며 반환되는 이름은 다음과 입니다.

> **fna12345**

이 이름이 FNA12345 파일을 만드는 데 사용되고 이 파일이 여전히 존재하는 경우 동일한 프로세스 또는 *nameTemplate에* 대한 동일한 *기준을* 가진 스레드에서 호출시 반환된 다음 이름은 다음과 같습니다.

> **fnb12345**

FNA12345가 존재하지 않는 경우 반환된 다음 이름은 다시 아래와 같습니다.

> **fna12345**

**_mktemp_s** *기본* 및 *nameTemplate* 값의 지정된 조합에 대해 최대 26개의 고유 파일 이름을 만들 수 있습니다. 따라서 FNZ12345는 이 예제에서 사용되는 *기본* 및 *nameTemplate* 값에 대해 만들 수 **_mktemp_s** 마지막 고유한 파일 이름입니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mktemp_s**|\<io.h>|
|**_wmktemp_s**|\<io.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// crt_mktemp_s.cpp
/* The program uses _mktemp to create
* five unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>

char *fnTemplate = "fnXXXXXX";
char names[5][9];

int main()
{
   int i, err, sizeInChars;
   FILE *fp;

   for( i = 0; i < 5; i++ )
   {
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );
      /* Get the size of the string and add one for the null terminator.*/
      sizeInChars = strnlen(names[i], 9) + 1;
      /* Attempt to find a unique filename: */
      err = _mktemp_s( names[i], sizeInChars );
      if( err != 0 )
         printf( "Problem creating the template" );
      else
      {
         if( fopen_s( &fp, names[i], "w" ) == 0 )
            printf( "Unique filename is %s\n", names[i] );
         else
            printf( "Cannot open %s\n", names[i] );
         fclose( fp );
      }
   }

   return 0;
}
```

### <a name="sample-output"></a>샘플 출력

```Output
Unique filename is fna03188
Unique filename is fnb03188
Unique filename is fnc03188
Unique filename is fnd03188
Unique filename is fne03188
```

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
