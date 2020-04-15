---
title: strstr, wcsstr, _mbsstr, _mbsstr_l
ms.date: 4/2/2020
api_name:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
- _o__mbsstr
- _o__mbsstr_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
helpviewer_keywords:
- strings [C++], searching
- mbsstr function
- _ftcsstr function
- ftcsstr function
- fstrstr function
- _tcsstr function
- substrings, finding
- mbsstr_l function
- tcsstr function
- _mbsstr function
- wcsstr function
- _fstrstr function
- _mbsstr_l function
- strstr function
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
ms.openlocfilehash: 06fb79ac050f4e1c357a76a782730cd72cbdadec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316934"
---
# <a name="strstr-wcsstr-_mbsstr-_mbsstr_l"></a>strstr, wcsstr, _mbsstr, _mbsstr_l

문자열에서 처음 나오는 검색 문자열에 대한 포인터를 반환합니다.

> [!IMPORTANT]
> Windows 런타임에서 실행되는 애플리케이션에서는 `_mbsstr` 및 `_mbsstr_l`을 사용할 수는 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *strstr(
   const char *str,
   const char *strSearch
); // C only
char *strstr(
   char *str,
   const char *strSearch
); // C++ only
const char *strstr(
   const char *str,
   const char *strSearch
); // C++ only
wchar_t *wcsstr(
   const wchar_t *str,
   const wchar_t *strSearch
); // C only
wchar_t *wcsstr(
   wchar_t *str,
   const wchar_t *strSearch
); // C++ only
const wchar_t *wcsstr(
   const wchar_t *str,
   const wchar_t *strSearch
); // C++ only
unsigned char *_mbsstr(
   const unsigned char *str,
   const unsigned char *strSearch
); // C only
unsigned char *_mbsstr(
   unsigned char *str,
   const unsigned char *strSearch
); // C++ only
const unsigned char *_mbsstr(
   const unsigned char *str,
   const unsigned char *strSearch
); // C++ only
unsigned char *_mbsstr_l(
   const unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C only
unsigned char *_mbsstr_l(
   unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C++ only
const unsigned char *_mbsstr_l(
   const unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
검색할 Null 종료 문자열입니다.

*스트라이치*<br/>
검색할 Null 종료 문자열입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

*strSearchstr에* 나타나지 않는 경우 *strSearch*에서 *strSearch* 또는 NULL의 첫 번째 *발생에*대한 포인터를 반환합니다. *strSearch가* 0 길이의 문자열을 가리키면 함수는 *str*을 반환합니다.

## <a name="remarks"></a>설명

함수는 `strstr` *str에서* *strSearch의* 첫 번째 발생에 대한 포인터를 반환합니다. 종료 null 문자는 검색에 포함되지 않습니다. `wcsstr`은 `strstr`의 와이드 문자 버전이고 `_mbsstr`은 멀티바이트 버전입니다. `wcsstr`의 인수 및 반환 값은 와이드 문자열이며 `_mbsstr`의 인수와 반환 값은 멀티바이트 문자열입니다. `_mbsstr`는 매개 변수의 유효성을 검사합니다. *str* 또는 *strSearch가* NULL이면 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md) 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 `_mbsstr` `errno` 경우 EINVAL로 설정하고 0을 반환합니다. `strstr` 및 `wcsstr`는 매개 변수의 유효성을 검사하지 않습니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

> [!IMPORTANT]
> 이러한 함수에서는 버퍼 오버런 문제로 인한 위협이 발생할 수 있습니다. 버퍼 오버런은 시스템 공격에 이용될 수 있습니다. 버퍼 오버런 문제가 발생하면 임의 코드를 실행할 수 있게 되어 보증하지 않은 방식으로 권한이 상승할 수 있기 때문입니다. 자세한 내용은 [버퍼 오버런 방지](/windows/win32/SecBP/avoiding-buffer-overruns)를 참조하세요.

C에서 이러한 함수는 첫 번째 인수에 대한 **const** 포인터를 취합니다. C++에서는 두 오버로드를 모두 사용할 수 있습니다. **const에** 포인터를 소요 하는 오버 로드 **const에**대 한 포인터를 반환 합니다. 비**const에** 포인터를 소요 하는 버전은 비**const에**대 한 포인터를 반환 합니다. 매크로 _CRT_CONST_CORRECT_OVERLOADS 이러한 함수의 **const** 및**non-const** 버전을 모두 사용할 수 있는 경우 정의 됩니다. C++ 오버로드 모두에 대해**const가** 아닌 동작이 필요한 경우 _CONST_RETURN 기호를 정의합니다.

출력 값은 LC_CTYPE 로캘 범주 설정의 영향을 받습니다. 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md)을 참조하십시오. **_l** 접미사가 없는 이러한 함수의 버전은 이 로캘 종속 동작에 대해 현재 로캘을 사용합니다. **_l** 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|
|**해당 /a**|**해당 /a**|`_mbsstr_l`|**해당 /a**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`strstr`|\<string.h>|
|`wcsstr`|\<string.h> 또는 \<wchar.h>|
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strstr.c

#include <string.h>
#include <stdio.h>

char str[] =    "lazy";
char string[] = "The quick brown dog jumps over the lazy fox";
char fmt1[] =   "         1         2         3         4         5";
char fmt2[] =   "12345678901234567890123456789012345678901234567890";

int main( void )
{
   char *pdest;
   int  result;
   printf( "String to be searched:\n   %s\n", string );
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );
   pdest = strstr( string, str );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf( "%s found at position %d\n", str, result );
   else
      printf( "%s not found\n", str );
}
```

```Output
String to be searched:
   The quick brown dog jumps over the lazy fox
            1         2         3         4         5
   12345678901234567890123456789012345678901234567890

lazy found at position 36
```

## <a name="see-also"></a>참고 항목

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[basic_string::찾기](../../standard-library/basic-string-class.md#find)<br/>
