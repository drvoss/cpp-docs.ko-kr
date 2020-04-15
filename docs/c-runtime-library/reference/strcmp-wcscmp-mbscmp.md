---
title: strcmp, wcscmp, _mbscmp, _mbscmp_l
ms.date: 4/2/2020
api_name:
- wcscmp
- _mbscmp
- _mbscmp_l
- strcmp
- _o__mbscmp
- _o__mbscmp_l
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbscmp
- _mbscmp_l
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- _mbscmp_l function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
ms.openlocfilehash: 16bb294f7bbdc0b95b59b845d7b714f823f9d962
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357281"
---
# <a name="strcmp-wcscmp-_mbscmp-_mbscmp_l"></a>strcmp, wcscmp, _mbscmp, _mbscmp_l

비교 문자열입니다.

> [!IMPORTANT]
> **_mbscmp** 및 **_mbscmp_l** Windows 런타임에서 실행되는 응용 프로그램에서사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int strcmp(
   const char *string1,
   const char *string2
);
int wcscmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbscmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _mbscmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*문자열1,* *문자열2*<br/>
비교할 Null 종료 문자열입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

이러한 각 함수에 대한 반환 값은 *string1과* *string2의*서수 관계를 나타냅니다.

|값|문자열 1과 문자열 2의 관계|
|-----------|----------------------------------------|
|< 0|*문자열 1이* *문자열2보다* 낮습니다.|
|0|*문자열1은* *문자열2와* 동일합니다.|
|> 0|*문자열1이* *문자열2보다* 큽|

매개 변수 유효성 검사 오류에서 **_mbscmp** 및 **_mbscmp_l**>> \< \<_NLSCMPERROR **반환합니다.**

## <a name="remarks"></a>설명

**strcmp** 함수는 *string1과* *string2의* 서수 비교를 수행하고 해당 관계를 나타내는 값을 반환합니다. **wcscmp와** **_mbscmp** 각각 넓은 문자 및 다중 바이트 문자 버전의 **strcmp입니다.** **_mbscmp** 현재 다중 바이트 코드 페이지에 따라 다중 바이트 문자 시퀀스를 인식하고 오류에 **_NLSCMPERROR** 반환합니다. **_mbscmp_l** 동일한 동작을 가지고 있지만 현재 로캘 대신 전달되는 로캘 매개 변수를 사용합니다. 자세한 내용은 [코드 페이지](../../c-runtime-library/code-pages.md) 참조하세요. 또한 *string1* 또는 *string2가* null 포인터인 경우 **_mbscmp** 매개 변수 유효성 [검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 **_mbscmp** _NLSCMPERROR **반환하고** **errno를** **EINVAL로** **설정하지 _mbscmp_l.** **strcmp** 및 **wcscmp는** 매개 변수의 유효성을 검사하지 않습니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscmp**|**Strcmp**|**_mbscmp**|**wcscmp**|

**strcmp** 함수는 **strcmp** 비교가 서수이며 로캘의 영향을 받지 않는다는 점에서 **strcoll** 함수와 다릅니다. **strcoll은** 현재 로캘의 **LC_COLLATE** 범주를 사용하여 문자열을 사전적으로 비교합니다. **LC_COLLATE** 범주에 대한 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md)를 참조하십시오.

"C" 로캘에서 문자 집합(ASCII 문자 집합)의 순서는 사전적 문자 순서와 같습니다. 그러나 다른 로캘에서 문자 집합의 순서는 사전적 순서와 다를 수 있습니다. 예를 들어 특정 유럽 로캘의 문자 집합에서 문자 'a'(값 0x61)는 문자 'ä'(값 0xE4) 앞에 오지만 사전적으로는 문자 'ä'가 'a' 앞에 옵니다.

문자 집합과 사전 문자 순서가 다른 로캘에서는 문자열의 사전 비교를 위해 **strcmp** 대신 **strcoll을** 사용할 수 있습니다. 또는 원래 문자열에서 **strxfrm을** 사용한 다음 결과 문자열에 **strcmp를** 사용할 수 있습니다.

**strcmp** 함수는 대/소문자를 구분합니다. stricmp, ** \_wcsicmp**및 ** \_mbsicmp는** 먼저 소문자 형태로 변환하여 문자열을 비교합니다. ** \_** ASCII 테이블의 'Z'와 'a' 사이에 있는 문자를 포함하는 두 개의\\문자열('[',',''',''','',',',',',',',',',',',',')과 '',')는\`대/소문자에 따라 다르게 비교됩니다. 예를 들어 두 문자열 "ABCDE" 및 "ABCD^"는 비교가 소문자("abcde" > "abcd^")인 경우 한 가지 방법을 비교하고 다른 방법("ABCDE" < "ABCD^")을 비교하는 경우 대문자입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**Strcmp**|\<string.h>|
|**wcscmp**|\<string.h> 또는 \<wchar.h>|
|**_mbscmp**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_strcmp.c

#include <string.h>
#include <stdio.h>
#include <stdlib.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown dog jumps over the lazy fox";

int main( void )
{
   char tmp[20];
   int result;

   // Case sensitive
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );
   result = strcmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof (tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
   The quick brown dog jumps over the lazy fox
   The QUICK brown dog jumps over the lazy fox

   strcmp:   String 1 is greater than string 2
   _stricmp:  String 1 is equal to string 2
```

## <a name="see-also"></a>참고 항목

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[스트콜 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
