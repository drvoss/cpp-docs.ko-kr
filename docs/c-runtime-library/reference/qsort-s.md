---
title: qsort_s
ms.date: 4/2/2020
api_name:
- qsort_s
- _o_qsort_s
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
- qsort_s
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
ms.openlocfilehash: 6013098199e1b69d03dc9cf2780cbf4376abcc0d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332969"
---
# <a name="qsort_s"></a>qsort_s

빠른 정렬을 수행합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안이 향상된 [qsort](qsort.md) 버전입니다.

## <a name="syntax"></a>구문

```C
void qsort_s(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>매개 변수

*base*<br/>
대상 배열의 시작 부분입니다.

*number*<br/>
요소의 배열 크기입니다.

*width*<br/>
요소 크기(바이트)입니다.

*비교*<br/>
비교 함수입니다. 첫 번째 인수는 *컨텍스트* 포인터입니다. 두 번째 인수는 *검색키에* 대한 포인터입니다. 세 번째 인수는 *키와*비교할 배열 요소에 대한 포인터입니다.

*context*<br/>
*비교* 루틴이 액세스해야 하는 모든 개체일 수 있는 컨텍스트에 대한 포인터입니다.

## <a name="remarks"></a>설명

**qsort_s** 함수는 빠른 정렬 알고리즘을 구현하여 각 *너비* 바이트의 *숫자* 요소 배열을 정렬합니다. 인수 *베이스는* 정렬할 배열의 기본에 대한 포인터입니다. **qsort_s** 정렬된 요소로 이 배열을 덮어씁니다. 인수 *비교는* 두 배열 요소를 비교하고 해당 관계를 지정하는 값을 반환하는 사용자 제공 루틴에 대한 포인터입니다. **qsort_s** 정렬 하는 동안 *비교* 루틴을 하나 이상 호출 하 여 각 호출에 두 개의 배열 요소에 포인터를 전달 합니다.

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

루틴은 요소를 비교한 후에 다음 값 중 하나를 반환해야 합니다.

|반환 값|Description|
|------------------|-----------------|
|< 0|**elem1** **elem2** 미만|
|0|**elem2에** 해당하는 **elem1**|
|> 0|**elem1** **elem2보다** 큰|

비교 함수에 정의된 대로 배열은 오름차순으로 정렬됩니다. 배열을 내림차순으로 정렬하려면 비교 함수에서 "보다 큼"과 "보다 작음"의 의미를 반전하면 됩니다.

함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있으면 함수가 반환되고 **errno가** **EINVAL로**설정됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="error-conditions"></a>오류 조건

|key|base|compare|num|width|errno|
|---------|----------|-------------|---------|-----------|-----------|
|**Null**|any|any|any|any|**아인발 ()에인발 (것)**|
|any|**Null**|any|!= 0|any|**아인발 ()에인발 (것)**|
|any|any|any|any|<= 0|**아인발 ()에인발 (것)**|
|any|any|**Null**|any|any|**아인발 ()에인발 (것)**|

**qsort_s** **qsort와** 동일한 동작을 가지고 있지만 *컨텍스트* 매개 변수를 가지고 **errno를**설정합니다. 비교 함수는 *컨텍스트* 매개 변수를 전달하여 개체 포인터를 사용하여 요소 포인터를 통해 액세스할 수 없는 개체 기능 또는 기타 정보에 액세스할 수 있습니다. *컨텍스트* 매개 변수를 추가하면 정적 변수를 사용하여 *비교* 함수에서 공유 정보를 사용할 수 있도록 컨텍스트가 다시 발생버그를 방지하는 데 사용할 수 있으므로 *컨텍스트를* **qsort_s** 더 안전합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h> 및 \<search.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 모든 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

다음 예제에서는 **qsort_s** 함수에서 *컨텍스트* 매개 변수를 사용 하는 방법을 보여 줍니다. *컨텍스트* 매개 변수를 사용하면 스레드 안전 정렬을 더 쉽게 수행할 수 있습니다. 스레드 안전을 보장하기 위해 동기화해야 하는 정적 변수를 사용하는 대신 각 정렬에서 다른 *컨텍스트* 매개 변수를 전달합니다. 이 예제에서는 로캘 개체가 *컨텍스트* 매개 변수로 사용됩니다.

```cpp
// crt_qsort_s.cpp
// compile with: /EHsc /MT
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
// so \x00e1 is the German Sharp S in that codepage and \x00a4
// is the n tilde.

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.850"
#define SPANISH_LOCALE "Spanish_Spain.850"
#define ENGLISH_LOCALE "English_US.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S and \x001f for the n tilde.
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.1252"
#define SPANISH_LOCALE "Spanish_Spain.1252"
#define ENGLISH_LOCALE "English_US.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making sort_array vulnerable to thread
// conflicts.

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char s1[256];
    char s2[256];
    strcpy_s(s1, 256, *(char**)str1);
    strcpy_s(s2, 256, *(char**)str2);
    _strlwr_s( s1, sizeof(s1) );
    _strlwr_s( s2, sizeof(s2) );

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(s1,
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);

}

void sort_array(char *array[], int num, locale &loc)
{
    qsort_s(array, num, sizeof(char*), compare, &loc);
}

void print_array(char *a[], int c)
{
   for (int i = 0; i < c; i++)
      printf("%s ", a[i]);
   printf("\n");

}

void sort_german(void * Dummy)
{
   sort_array(array1, 6, locale(GERMAN_LOCALE));
}

void sort_spanish(void * Dummy)
{
   sort_array(array2, 3, locale(SPANISH_LOCALE));
}

void sort_english(void * Dummy)
{
   sort_array(array3, 3, locale(ENGLISH_LOCALE));
}

int main( )
{
   int i;
   HANDLE threads[3];

   printf("Unsorted input:\n");
   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);

   // Create several threads that perform sorts in different
   // languages at the same time.

   threads[0] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_german , 0, NULL));
   threads[1] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_spanish, 0, NULL));
   threads[2] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_english, 0, NULL));

   for (i = 0; i < 3; i++)
   {
      if (threads[i] == reinterpret_cast<HANDLE>(-1))
      {
         printf("Error creating threads.\n");
         exit(1);
      }
   }

   // Wait until all threads have terminated.
   WaitForMultipleObjects(3, threads, true, INFINITE);

   printf("Sorted output: \n");

   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);
}
```

### <a name="sample-output"></a>샘플 출력

```Output
Unsorted input:
weiß weis annehmen weizen Zeit weit
Español España espantado
table tableux tablet
Sorted output:
annehmen weiß weis weit weizen Zeit
España Español espantado
table tablet tableux
```

## <a name="see-also"></a>참고 항목

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort](qsort.md)<br/>
