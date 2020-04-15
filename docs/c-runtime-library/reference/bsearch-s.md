---
title: bsearch_s
ms.date: 4/2/2020
api_name:
- bsearch_s
- _o_bsearch_s
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- bsearch_s
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch_s function
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
ms.openlocfilehash: ef8a68f0db45e718af6b17fe0d08c33a6fd61d6c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333841"
---
# <a name="bsearch_s"></a>bsearch_s

정렬된 배열의 이진 검색을 수행합니다. 이 함수는 [CRT의 보안 기능에](../../c-runtime-library/security-features-in-the-crt.md)설명된 대로 보안 기능이 향상된 [bsearch](bsearch.md) 버전입니다.

## <a name="syntax"></a>구문

```C
void *bsearch_s(
   const void *key,
   const void *base,
   size_t number,
   size_t width,
   int ( __cdecl *compare ) ( void *, const void *key, const void *datum),
   void * context
);
```

### <a name="parameters"></a>매개 변수

*키*\
검색할 키에 대한 포인터입니다.

*기본*\
검색 데이터의 기본에 대한 포인터입니다.

*수*\
요소의 수입니다.

*너비*\
요소의 너비입니다.

*비교*\
두 요소를 비교하는 콜백 함수입니다. 첫 번째 인수는 *컨텍스트* 포인터입니다. 두 번째 인수는 *검색키에* 대한 포인터입니다. 세 번째 인수는 *키와*비교할 배열 요소에 대한 포인터입니다.

*컨텍스트*\
비교 함수에서 액세스할 수 있는 개체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**bsearch_s** *base를*가리키는 배열에서 *키발생에* 대한 포인터를 반환합니다. *키가* 없는 경우 함수는 **NULL**을 반환합니다. 배열이 오름차순 정렬이 아니거나 동일한 키를 가진 중복 레코드를 포함하는 경우에는 결과를 예측할 수 없습니다.

잘못된 매개 변수가 함수에 전달되면 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 **errno는** **EINVAL로** 설정되고 함수는 **NULL을**반환합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

### <a name="error-conditions"></a>오류 조건

|||||||
|-|-|-|-|-|-|
|*키*|*base*|*비교*|*number*|*width*|**errno**|
|**Null**|any|any|any|any|**아인발 ()에인발 (것)**|
|any|**Null**|any|!= 0|any|**아인발 ()에인발 (것)**|
|any|any|any|any|= 0|**아인발 ()에인발 (것)**|
|any|any|**Null**|an|any|**아인발 ()에인발 (것)**|

## <a name="remarks"></a>설명

**bsearch_s** 함수는 *각각의 너비* 바이트 크기의 *정렬된 숫자* 요소 배열의 이진 검색을 수행합니다. *기준* 값은 검색할 배열의 기본에 대한 포인터이며 *키는* 검색중인 값입니다. *compare* 매개 변수는 요청된 키를 배열 요소와 비교하고 관계를 지정하는 다음 값 중 하나를 반환하는 사용자 제공 루틴에 대한 포인터입니다.

|*비교* 루틴에 의해 반환된 값|Description|
|-----------------------------------------|-----------------|
|\< 0|키가 배열 요소보다 작습니다.|
|0|키가 배열 요소와 같습니다.|
|> 0|키가 배열 요소보다 큽니다.|

*컨텍스트* 포인터는 검색된 데이터 구조가 개체의 일부이고 비교 함수가 개체의 멤버에 액세스해야 하는 경우에 유용할 수 있습니다. *compare* 함수는 void 포인터를 해당 개체 유형및 해당 개체의 액세스 멤버로 캐스팅할 수 있습니다. *컨텍스트* 매개 변수를 추가하면 정적 변수를 사용하여 *비교* 함수에서 데이터를 사용할 수 있도록 하는 것과 관련된 재진입 버그를 피하기 위해 추가 컨텍스트를 사용할 수 있기 때문에 **bsearch_s** 더 안전합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**bsearch_s**|\<stdlib.h> 및 \<search.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램은 [qsort_s](qsort-s.md)를 사용하여 문자열 배열을 정렬한 다음 bsearch_s를 사용하여 "cat" 단어를 찾습니다.

```cpp
// crt_bsearch_s.cpp
// This program uses bsearch_s to search a string array,
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
#define ENGLISH_LOCALE "English_US.850"
#endif

#ifdef CODEPAGE_1252
#define ENGLISH_LOCALE "English_US.1252"
#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making it vulnerable to thread conflicts
// (if this were a multithreaded program).

int compare( void *pvlocale, char **str1, char **str2)
{
    char *s1 = *str1;
    char *s2 = *str2;

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(
       s1, s1+strlen(s1),
       s2, s2+strlen(s2) );
}

int main( void )
{
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};

   char *key = "cat";
   char **result;
   int i;

   /* Sort using Quicksort algorithm: */
   qsort_s( arr,
            sizeof(arr)/sizeof(arr[0]),
            sizeof( char * ),
            (int (*)(void*, const void*, const void*))compare,
            &locale(ENGLISH_LOCALE) );

   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */
      printf( "%s ", arr[i] );

   /* Find the word "cat" using a binary search algorithm: */
   result = (char **)bsearch_s( &key,
                                arr,
                                sizeof(arr)/sizeof(arr[0]),
                                sizeof( char * ),
                                (int (*)(void*, const void*, const void*))compare,
                                &locale(ENGLISH_LOCALE) );
   if( result )
      printf( "\n%s found at %Fp\n", *result, result );
   else
      printf( "\nCat not found!\n" );
}
```

```Output
cat cow dog goat horse human pig rat
cat found at 002F0F04
```

## <a name="see-also"></a>참고 항목

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)\
[_lfind](lfind.md)\
[_lsearch](lsearch.md)\
[qsort](qsort.md)
