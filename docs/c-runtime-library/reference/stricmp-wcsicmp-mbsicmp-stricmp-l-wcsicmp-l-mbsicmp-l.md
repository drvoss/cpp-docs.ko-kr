---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
ms.date: 4/2/2020
api_name:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
- _o__mbsicmp
- _o__mbsicmp_l
- _o__stricmp
- _o__stricmp_l
- _o__wcsicmp
- _o__wcsicmp_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ftcsicmp
- _stricmp
- wcsicmp_l
- _wcsicmp
- _tcsicmp
- _strcmpi
- stricmp_l
- _mbsicmp
- _fstricmp
- mbsicmp_l
- mbsicmp
helpviewer_keywords:
- _wcsicmp function
- _stricmp_l function
- fstricmp function
- _tcsicmp function
- ftcsicmp function
- string comparison [C++], lowercase
- _wcsicmp_l function
- _fstricmp function
- strings [C++], comparing
- mbsicmp function
- _ftcsicmp function
- _mbsicmp_l function
- wcsicmp_l function
- _stricmp function
- _mbsicmp function
- tcsicmp function
- stricmp_l function
- mbsicmp_l function
- _strcmpi function
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
ms.openlocfilehash: 315a86c5cf7e58219bad25f2b6633dd91275c09f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320464"
---
# <a name="_stricmp-_wcsicmp-_mbsicmp-_stricmp_l-_wcsicmp_l-_mbsicmp_l"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

대소문자를 구분하지 않는 문자열 비교를 수행합니다.

> [!IMPORTANT]
> **_mbsicmp** 및 **_mbsicmp_l** Windows 런타임에서 실행되는 응용 프로그램에서사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _stricmp(
   const char *string1,
   const char *string2
);
int _wcsicmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbsicmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _stricmp_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int _wcsicmp_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbsicmp_l(
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

반환 값은 다음과 같이 *string1과* *string2의* 관계를 나타냅니다.

|반환 값|Description|
|------------------|-----------------|
|< 0|*문자열1보다* *문자열2*|
|0|*문자열1과* *문자열2*|
|> 0|*문자열1이* *문자열2보다* 큽|

오류가 발생하면 **_mbsicmp** **_NLSCMPERROR** \<string.h> mbstring.h \<> 정의된 _NLSCMPERROR 반환합니다.

## <a name="remarks"></a>설명

**_stricmp** 함수는 각 문자를 소문자로 변환한 후 *string1과* *string2를* 정상적으로 비교하고 관계를 나타내는 값을 반환합니다. **_stricoll** **_stricmp** **_stricmp** 비교는 대문자와 소문자를 결정하는 **LC_CTYPE**영향을 받습니다. **_stricoll** 함수는 대/소문자 및 데이터 정렬 순서를 모두 포함하는 로캘의 **LC_CTYPE** **및 LC_COLLATE** 범주에 따라 문자열을 비교합니다. **LC_COLLATE** 범주에 대한 자세한 내용은 [setlocale](setlocale-wsetlocale.md) 및 [로캘 범주를](../../c-runtime-library/locale-categories.md)참조하십시오. **_l** 접미사가 없는 이러한 함수의 버전은 로캘 종속 동작에 대해 현재 로캘을 사용합니다. 접미사가 있는 버전은 전달된 로캘을 사용한다는 점만 제외하면 동일합니다. 로캘이 설정되지 않은 경우에는 C 로캘이 사용됩니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

> [!NOTE]
> **_stricmp** **_strcmpi**같습니다. 서로 교환하여 사용할 수 있지만 **_stricmp** 기본 표준입니다.

**_strcmpi** 함수는 **_stricmp** 동일하며 이전 버전과의 호환성을 위해서만 제공됩니다.

**_stricmp** 소문자 비교를 수행하므로 예기치 않은 동작이 발생할 수 있습니다.

**_stricmp** 의 대/소문자 변환이 비교 결과에 영향을 미치는 경우를 설명하기 위해 JOHNSTON과 JOHN_HENRY 두 문자열이 있다고 가정합니다. JOHN_HENRY 문자열은 "_"의 ASCII 값이 소문자 S보다 작기 때문에 JOHNSTON보다 작은 것으로 간주됩니다. 실제로 ASCII 값이 91~96인 문자는 모든 문자보다 작은 것으로 간주됩니다.

[strcmp](strcmp-wcscmp-mbscmp.md) 함수를 **_stricmp**대신 사용하는 경우 JOHN_HENRY JOHNSTON보다 큽합니다.

**_wcsicmp** **_mbsicmp** **_stricmp**와이드 문자 및 멀티 바이트 문자 버전입니다. **_wcsicmp** 인수 및 반환 값은 와이드 문자 문자열입니다. **_mbsicmp** 그 문자열은 멀티 바이트 문자 문자열입니다. **_mbsicmp** 현재 다중 바이트 코드 페이지에 따라 다중 바이트 문자 시퀀스를 인식하고 오류에 **_NLSCMPERROR** 반환합니다. 자세한 내용은 [코드 페이지](../../c-runtime-library/code-pages.md) 참조하세요. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

**_wcsicmp** **wcscmp는** **wcscmp가** 비교하기 전에 인수를 소문자로 변환하지 않는다는 점을 제외하고는 동일하게 작동합니다. **_mbsicmp** **_mbscmp** **_mbscmp** 인수를 비교하기 전에 소문자로 변환하지 않는다는 점을 제외하고는 동일하게 행동합니다.

라틴어 1 문자로 작업하려면 **_wcsicmp** [setlocale를](setlocale-wsetlocale.md) 호출해야 합니다. 기본적으로는 C 로캘이 적용되므로 예를 들어 ä와 Ä는 비교 시 같은 항목으로 간주되지 않습니다. **_wcsicmp**호출하기 전에 C 로캘 이외의 로캘을 사용하여 **setlocale를** 호출합니다. 다음 샘플에서는 **_wcsicmp** 로캘에 얼마나 민감한지 보여 줍니다.

```C
// crt_stricmp_locale.c
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <string.h>
#include <stdio.h>
#include <locale.h>

int main() {
   setlocale(LC_ALL,"C");   // in effect by default
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails
   setlocale(LC_ALL,"");
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds
}
```

다른 방법은 _create_locale 호출하여 [_wcreate_locale](create-locale-wcreate-locale.md) 반환된 로캘 개체를 **_wcsicmp_l**매개 변수로 전달하는 것입니다.

이러한 모든 함수는 해당 함수 매개 변수의 유효성을 검사합니다. *string1* 또는 *string2가* null 포인터인 경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md) 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 이러한 함수는 **_NLSCMPERROR** 반환하고 **errno를** **EINVAL로**설정합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicmp**|**_stricmp**|**_mbsicmp**|**_wcsicmp**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_stricmp**, **_stricmp_l**|\<string.h>|
|**_wcsicmp**, **_wcsicmp_l**|\<string.h> 또는 \<wchar.h>|
|**_mbsicmp**, **_mbsicmp_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_stricmp.c

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
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
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
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[스트콜 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
