---
title: strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l
ms.date: 4/2/2020
api_name:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
- _o__mbspbrk
- _o__mbspbrk_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
helpviewer_keywords:
- fstrpbrk function
- _ftcspbrk function
- _mbspbrk_l function
- strpbrk function
- _fstrpbrk function
- mbspbrk function
- characters [C++], scanning strings
- _tcspbrk function
- wcspbrk function
- ftcspbrk function
- character sets [C++], scanning strings for characters
- strings [C++], scanning
- tcspbrk function
- _mbspbrk function
- mbspbrk_l function
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
ms.openlocfilehash: ecdf896587096f0370351aac07cbd6be57257305
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322163"
---
# <a name="strpbrk-wcspbrk-_mbspbrk-_mbspbrk_l"></a>strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l

문자열에서 지정된 문자 집합의 문자를 검색합니다.

> [!IMPORTANT]
> Windows 런타임에서 실행되는 애플리케이션에서는 `_mbspbrk` 및 `_mbspbrk_l`을 사용할 수는 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *strpbrk(
   const char *str,
   const char *strCharSet
); // C only
char *strpbrk(
   char *str,
   const char *strCharSet
); // C++ only
const char *strpbrk(
   const char *str,
   const char *strCharSet
); // C++ only
wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C only
wchar_t *wcspbrk(
   wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
const wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C only
unsigned char *_mbspbrk(
   unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
const unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C only
unsigned char *_mbspbrk_l(
   unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C++ only
const unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char* strCharSet,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
Null로 종료되는 검색 대상 문자열입니다.

*스트라셋*<br/>
Null 종료 문자 집합입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

*strcharSet에서* 문자의 첫 번째 발생에 대 한 포인터를 반환 *합니다.*

## <a name="remarks"></a>설명

함수는 `strpbrk` *strCharSet의*문자 집합에 속하는 *str에서* 문자의 첫 번째 발생에 대한 포인터를 반환합니다. 종료 null 문자는 검색에 포함되지 않습니다.

`wcspbrk` 및 `_mbspbrk` 는 `strpbrk`의 와이드 문자 및 멀티바이트 문자 버전입니다. `wcspbrk`의 인수 및 반환 값은 와이드 문자열이며 `_mbspbrk`의 인수와 반환 값은 멀티바이트 문자열입니다.

`_mbspbrk`는 매개 변수의 유효성을 검사합니다. *str* 또는 *strCharSet이* NULL인 경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 `_mbspbrk` 경우 NULL을 반환하고 EINVAL로 설정합니다. `errno` `strpbrk` 및 `wcspbrk`는 매개 변수의 유효성을 검사하지 않습니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

`_mbspbrk`는 [size_t](../../c-runtime-library/standard-types.md) 형식의 값이 아닌 포인터를 반환한다는 점을 제외하면 `_mbspbrk`는 `_mbscspn`과 유사합니다.

C에서 이러한 함수는 첫 번째 인수에 대한 **const** 포인터를 취합니다. C++에서는 두 오버로드를 모두 사용할 수 있습니다. **const에** 포인터를 취하는 오버로드는 **const에**대한 포인터를 반환합니다. 비**const에** 포인터를 소요 하는 버전은 비**const에**대 한 포인터를 반환 합니다. 매크로 _CRT_CONST_CORRECT_OVERLOADS 이러한 함수의 **const** 및**non-const** 버전을 모두 사용할 수 있는 경우 정의 됩니다. C++ 오버로드 모두에 대해**const가** 아닌 동작이 필요한 경우 _CONST_RETURN 기호를 정의합니다.

출력 값은 로캘의 LC_CTYPE 범주 설정설정의 영향을 받습니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하십시오. **_l** 접미사가 없는 이러한 함수의 버전은 이 로캘 종속 동작에 대해 현재 로캘을 사용합니다. **_l** 접미사가 있는 버전은 대신 전달된 로캘 매개 변수를 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|
|**해당 /a**|**해당 /a**|`_mbspbrk_l`|**해당 /a**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`strpbrk`|\<string.h>|
|`wcspbrk`|\<string.h> 또는 \<wchar.h>|
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strpbrk.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";
   char *result = NULL;

   // Return pointer to first digit in "string".
   printf( "1: %s\n", string );
   result = strpbrk( string, "0123456789" );
   printf( "2: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "3: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "4: %s\n", result );
}
```

```Output
1: The 3 men and 2 boys ate 5 pigs

2: 3 men and 2 boys ate 5 pigs

3: 2 boys ate 5 pigs

4: 5 pigs
```

## <a name="see-also"></a>참고 항목

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
