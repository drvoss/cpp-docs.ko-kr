---
title: bsearch
ms.date: 4/2/2020
api_name:
- bsearch
- _o_bsearch
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
- bsearch
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
ms.openlocfilehash: efad391eb2512cfa59cc3597430a84727676f27e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333808"
---
# <a name="bsearch"></a>bsearch

정렬된 배열의 이진 검색을 수행합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [bsearch_s](bsearch-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void *bsearch(
   const void *key,
   const void *base,
   size_t num,
   size_t width,
   int ( __cdecl *compare ) (const void *key, const void *datum)
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
두 요소를 비교하는 콜백 함수입니다. 첫 번째는 검색에 대한 키에 대한 포인터이고 두 번째는 키와 비교할 배열 요소에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**bsearch는** *base를*가리키는 배열의 *키* 발생에 대한 포인터를 반환합니다. *키가* 없는 경우 함수는 **NULL**을 반환합니다. 배열이 오름차순 정렬이 아니거나 동일한 키를 가진 중복 레코드를 포함하는 경우에는 결과를 예측할 수 없습니다.

## <a name="remarks"></a>설명

**bsearch** 함수는 *각각의 너비* 바이트 크기의 *정렬된 숫자* 요소 배열의 이진 검색을 수행합니다. *기준* 값은 검색할 배열의 기본에 대한 포인터이며 *키는* 검색중인 값입니다. *비교* 매개 변수는 요청된 키를 배열 요소와 비교하는 사용자 제공 루틴에 대한 포인터입니다. 관계를 지정하는 다음 값 중 하나를 반환합니다.

|*비교* 루틴에 의해 반환된 값|Description|
|-----------------------------------------|-----------------|
|\< 0|키가 배열 요소보다 작습니다.|
|0|키가 배열 요소와 같습니다.|
|> 0|키가 배열 요소보다 큽니다.|

이 함수는 해당 매개 변수의 유효성을 검사합니다. *compare*- *key* or *number가* **NULL이거나** *base가* **NULL이고** *숫자가* 0이 아닌 경우 또는 *너비가* 0인 경우 함수는 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 **errno가** `EINVAL` 로 설정되고 함수가 **NULL을**반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**bsearch**|\<stdlib.h> 및 \<search.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램은 qsort를 사용하여 문자열 배열을 정렬한 다음 bsearch를 사용하여 "cat" 단어를 찾습니다.

```C
// crt_bsearch.c
#include <search.h>
#include <string.h>
#include <stdio.h>

int compare( char **arg1, char **arg2 )
{
   /* Compare all of both strings: */
   return _strcmpi( *arg1, *arg2 );
}

int main( void )
{
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};
   char **result;
   char *key = "cat";
   int i;

   /* Sort using Quicksort algorithm: */
   qsort( (void *)arr, sizeof(arr)/sizeof(arr[0]), sizeof( char * ), (int (*)(const
   void*, const void*))compare );

   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */
      printf( "%s ", arr[i] );

   /* Find the word "cat" using a binary search algorithm: */
   result = (char **)bsearch( (char *) &key, (char *)arr, sizeof(arr)/sizeof(arr[0]),
                              sizeof( char * ), (int (*)(const void*, const void*))compare );
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
