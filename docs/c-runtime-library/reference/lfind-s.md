---
title: _lfind_s
ms.date: 4/2/2020
api_name:
- _lfind_s
- _o__lfind_s
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
- api-ms-win-crt-utility-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lfind_s
- _lfind_s
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
ms.openlocfilehash: 8f2983bee93c623eb936ed12422134281418076b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342182"
---
# <a name="_lfind_s"></a>_lfind_s

지정된 키에 대해 선형 검색을 수행합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_lfind](lfind.md) 버전입니다.

## <a name="syntax"></a>구문

```C
void *_lfind_s(
   const void *key,
   const void *base,
   unsigned int *num,
   size_t size,
   int (__cdecl *compare)(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>매개 변수

*키*<br/>
검색할 개체입니다.

*base*<br/>
검색 데이터의 기준에 대한 포인터입니다.

*number*<br/>
배열 요소의 수입니다.

*크기*<br/>
배열 요소의 크기(바이트)입니다.

*비교*<br/>
비교 루틴에 대한 포인터입니다. 첫 번째 매개 변수는 *컨텍스트* 포인터입니다. 두 번째 매개 변수는 검색할 키에 대한 포인터입니다. 세 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.

*context*<br/>
비교 함수에서 액세스할 수 있는 개체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

키가 발견되면 **_lfind_s** *키와*일치하는 *기본* 배열 요소에 대한 포인터를 반환합니다. 키가 없는 경우 **_lfind_s** **NULL**을 반환합니다.

함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 **errno는** **EINVAL로** 설정되고 함수는 **NULL을**반환합니다.

### <a name="error-conditions"></a>오류 조건

|key|base|compare|num|크기|errno|
|---------|----------|-------------|---------|----------|-----------|
|**Null**|any|any|any|any|**아인발 ()에인발 (것)**|
|any|**Null**|any|!= 0|any|**아인발 ()에인발 (것)**|
|any|any|any|any|0|**아인발 ()에인발 (것)**|
|any|any|**Null**|an|any|**아인발 ()에인발 (것)**|

## <a name="remarks"></a>설명

**_lfind_s** 함수는 각각 *너비* 바이트의 *숫자* 요소 배열에서 값 *키에* 대한 선형 검색을 수행합니다. **bsearch_s**달리 **_lfind_s** 배열을 정렬할 필요가 없습니다. *기본* 인수는 검색할 배열의 기본에 대한 포인터입니다. *비교* 인수는 두 배열 요소를 비교한 다음 해당 관계를 지정하는 값을 반환하는 사용자 제공 루틴에 대한 포인터입니다. **_lfind_s** 각 호출에 두 개의 배열 요소에 *컨텍스트* 포인터와 포인터를 전달, 검색 하는 동안 하나 이상의 *비교* 루틴을 호출 합니다. *비교* 루틴은 요소를 비교한 다음 비영도(요소가 다른 의미) 또는 0(요소가 동일하다는 의미)을 반환해야 합니다.

**_lfind_s** 비교 함수의 인수와 함수의 매개 변수 목록에 *컨텍스트* 포인터를 추가하는 것을 제외하고는 **_lfind** 비슷합니다. *컨텍스트* 포인터는 검색된 데이터 구조가 개체의 일부이고 *비교* 함수가 개체의 멤버에 액세스해야 하는 경우에 유용할 수 있습니다. *compare* 함수는 void 포인터를 해당 개체 유형으로 캐스팅하고 해당 개체의 멤버에 액세스할 수 있습니다. *컨텍스트* 매개 변수를 추가하면 정적 변수를 사용하여 *비교* 함수에서 데이터를 사용할 수 있도록 하는 것과 관련된 재진입 버그를 피하기 위해 추가 컨텍스트를 사용할 수 있으므로 **_lfind_s** 더 안전합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_lfind_s**|\<search.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// crt_lfind_s.cpp
// This program uses _lfind_s to search a string array,
// passing a locale as the context.
// compile with: /EHsc
#include <stdlib.h>
#include <stdio.h>
#include <search.h>
#include <process.h>
#include <locale.h>
#include <locale>
#include <windows.h>
using namespace std;

// The sort order is dependent on the code page.  Use 'chcp' at the
// command line to change the codepage.  When executing this application,
// the command prompt codepage must match the codepage used here:

#define CODEPAGE_850

#ifdef CODEPAGE_850
// Codepage 850 is the OEM codepage used by the command line,
// so \x00e1 is the German Sharp S

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };

#define GERMAN_LOCALE "German_Germany.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };

#define GERMAN_LOCALE "German_Germany.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making it vulnerable to thread conflicts
// (if this were a multithreaded program).

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char *s1 = *(char**)str1;
    char *s2 = *(char**)str2;

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(
       s1, s1+strlen(s1),
       s2, s2+strlen(s2) );
}

void find_it( char *key, char *array[], unsigned int num, locale &loc )
{
   char **result = (char **)_lfind_s( &key, array,
                      &num, sizeof(char *), compare, &loc );
   if( result )
      printf( "%s found\n", *result );
   else
      printf( "%s not found\n", key );
}

int main( )
{
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );
}
```

```Output
weit found
```

## <a name="see-also"></a>참고 항목

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort_s](qsort-s.md)<br/>
[_lfind](lfind.md)<br/>
