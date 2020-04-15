---
title: _mktemp, _wmktemp
ms.date: 4/2/2020
api_name:
- _wmktemp
- _mktemp
- _o__mktemp
- _o__wmktemp
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
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
ms.openlocfilehash: 8affd20ca7826f0d383f749567c9625d61dacd48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338715"
---
# <a name="_mktemp-_wmktemp"></a>_mktemp, _wmktemp

고유한 파일 이름을 만듭니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_mktemp_s, _wmktemp_s](mktemp-s-wmktemp-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_mktemp(
   char *nameTemplate
);
wchar_t *_wmktemp(
   wchar_t *nameTemplate
);
template <size_t size>
char *_mktemp(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
wchar_t *_wmktemp(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*네임 템플릿*<br/>
파일 이름 패턴입니다.

## <a name="return-value"></a>Return Value

이러한 각 함수는 수정된 nameTemplate에 대한 포인터를 반환합니다. *nameTemplate잘못* 형성 되 거나 주어진된 nameTemplate에서 더 이상 고유 한 이름을 만들 수 없습니다 경우 **함수NULL을** 반환 합니다.

## <a name="remarks"></a>설명

**_mktemp** 함수는 *nameTemplate* 인수를 수정하여 고유한 파일 이름을 만듭니다. **_mktemp** 런타임 시스템에서 현재 사용 중인 다중 바이트 코드 페이지에 따라 다중 바이트 문자 시퀀스를 인식하여 적절한 다중 바이트 문자열 인수를 자동으로 처리합니다. **_wmktemp** **_mktemp**와이드 문자 버전입니다. **_wmktemp** 인수 및 반환 값은 와이드 문자 문자열입니다. **_wmktemp** 멀티바이트 문자 문자열을 처리하지 않는다는 점을 제외하면 **_wmktemp** **_mktemp** 다르게 다르게 작동합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

*nameTemplate* 인수에는 기본 *XXXXXX형식이*있으며, 여기서 *기본은* 제공하는 새 파일 이름의 일부이고 각 X는 **_mktemp**제공된 문자의 자리 표시자입니다. *nameTemplate의* 각 자리 표시자 문자는 대문자 **X여야** _mktemp *기본을* 보존하고 첫 번째 후행 X를 알파벳 문자로 대체합니다. **_mktemp** 다음 후행 X를 5자리 값으로 바꿉습니다. 이 값은 호출 프로세스 또는 다중 스레드 프로그램에서 호출 스레드를 식별하는 고유 번호입니다.

**_mktemp** 대한 각 성공적인 호출은 *nameTemplate*. 동일한 *이름인* 동일한 프로세스 또는 스레드에서 후속 호출에서 **_mktemp** 이전 호출에서 **_mktemp** 반환된 이름과 일치하는 파일 이름을 확인합니다. 지정된 이름에 대한 파일이 없는 경우 **_mktemp** 해당 이름을 반환합니다. 이전에 반환된 모든 이름에 대해 파일이 있는 경우 **_mktemp** 이전에 반환된 이름에 사용된 알파벳 문자를 'a'에서 'z'까지 순서대로 사용 가능한 다음 소문자로 대체하여 새 이름을 만듭니다. 예를 *들어, 기준이* 다음과 같은 경우:

> **Fn**

**_mktemp** 의해 제공되는 다섯 자리 값은 12345이며 반환된 첫 번째 이름은 다음과 입니다.

> **fna12345**

이 이름이 FNA12345 파일을 만드는 데 사용되고 이 파일이 여전히 존재하는 경우 동일한 프로세스 또는 *nameTemplate에* 대한 동일한 *기준을* 가진 스레드에서 호출시 반환된 다음 이름은 다음과 같습니다.

> **fnb12345**

FNA12345가 존재하지 않는 경우 반환된 다음 이름은 다시 아래와 같습니다.

> **fna12345**

**_mktemp** *기본* 및 *nameTemplate* 값의 지정된 조합에 대해 최대 26개의 고유 파일 이름을 만들 수 있습니다. 따라서 FNZ12345는 이 예제에서 사용되는 *기본* 및 *nameTemplate* 값에 대해 만들 수 **_mktemp** 마지막 고유한 파일 이름입니다.

오류가 발생할 경우 **errno가** 설정됩니다. *nameTemplate* 형식이 잘못된 형식(예: 6X 미만)인 경우 **errno는** **EINVAL로**설정됩니다. **_mktemp** 가능한 모든 26개의 파일 이름이 이미 있기 때문에 고유한 이름을 만들 수 없는 경우 **_mktemp** nameTemplate를 빈 문자열로 설정하고 **EEXIST**를 반환합니다.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mktemp**|\<io.h>|
|**_wmktemp**|\<io.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_mktemp.c
// compile with: /W3
/* The program uses _mktemp to create
* unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>
#include <errno.h>

char *template = "fnXXXXXX";
char *result;
char names[27][9];

int main( void )
{
   int i;
   FILE *fp;

   for( i = 0; i < 27; i++ )
   {
      strcpy_s( names[i], sizeof( names[i] ), template );
      /* Attempt to find a unique filename: */
      result = _mktemp( names[i] );  // C4996
      // Note: _mktemp is deprecated; consider using _mktemp_s instead
      if( result == NULL )
      {
         printf( "Problem creating the template\n" );
         if (errno == EINVAL)
         {
             printf( "Bad parameter\n");
         }
         else if (errno == EEXIST)
         {
             printf( "Out of unique filenames\n");
         }
      }
      else
      {
         fopen_s( &fp, result, "w" );
         if( fp != NULL )
            printf( "Unique filename is %s\n", result );
         else
            printf( "Cannot open %s\n", result );
         fclose( fp );
      }
   }
}
```

```Output
Unique filename is fna03912
Unique filename is fnb03912
Unique filename is fnc03912
Unique filename is fnd03912
Unique filename is fne03912
Unique filename is fnf03912
Unique filename is fng03912
Unique filename is fnh03912
Unique filename is fni03912
Unique filename is fnj03912
Unique filename is fnk03912
Unique filename is fnl03912
Unique filename is fnm03912
Unique filename is fnn03912
Unique filename is fno03912
Unique filename is fnp03912
Unique filename is fnq03912
Unique filename is fnr03912
Unique filename is fns03912
Unique filename is fnt03912
Unique filename is fnu03912
Unique filename is fnv03912
Unique filename is fnw03912
Unique filename is fnx03912
Unique filename is fny03912
Unique filename is fnz03912
Problem creating the template.
Out of unique filenames.
```

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>
