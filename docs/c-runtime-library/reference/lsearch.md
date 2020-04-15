---
title: _lsearch
ms.date: 4/2/2020
api_name:
- _lsearch
- _o__lsearch
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
- _lsearch
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
ms.openlocfilehash: a6ef3d86ffe8f03da34d4a374bddda1452815672
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341641"
---
# <a name="_lsearch"></a>_lsearch

값에 대한 선형 검색을 수행합니다. 찾을 수 없는 경우 목록의 끝에 추가합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_lsearch_s](lsearch-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void *_lsearch(
   const void *key,
   void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>매개 변수

*키*<br/>
검색할 개체입니다.

*base*<br/>
검색할 배열의 기준에 대한 포인터입니다.

*number*<br/>
요소의 수입니다.

*width*<br/>
각 배열 요소의 너비입니다.

*비교*<br/>
비교 루틴에 대한 포인터입니다. 첫 번째 매개 변수는 검색할 키에 대한 포인터입니다. 두 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

키가 발견되면 **_lsearch** *키와*일치하는 *기본* 배열 요소에 대한 포인터를 반환합니다. 키를 찾을 수 없는 경우 **_lsearch** 배열 끝에 새로 추가된 항목에 대한 포인터를 반환합니다.

## <a name="remarks"></a>설명

**_lsearch** 함수는 각각 *너비* 바이트의 *숫자* 요소 배열에서 값 *키에* 대한 선형 검색을 수행합니다. **bsearch와**달리 **_lsearch** 배열을 정렬할 필요가 없습니다. *키를* 찾을 수 없는 경우 **_lsearch** 배열 및 증분 *수의*끝에 추가합니다.

*비교* 인수는 두 배열 요소를 비교하고 해당 관계를 지정하는 값을 반환하는 사용자 제공 루틴에 대한 포인터입니다. **_lsearch** 각 호출에 두 개의 배열 요소에 포인터를 전달, 검색 하는 동안 하나 이상의 *비교* 루틴을 호출 합니다. *compare는* 요소를 비교하고 0이 아닌 것(요소가 다르다는 의미) 또는 0(요소가 동일하다는 의미)을 반환해야 합니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. *compare*- *key* or *number가* **NULL이거나** *base가* **NULL이고** *숫자가* 0이 아닌 경우 또는 *너비가* 0보다 작은 경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 **errno는** **EINVAL로** 설정되고 함수는 **NULL을**반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_lsearch**|\<search.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_lsearch.c
#include <search.h>
#include <string.h>
#include <stdio.h>

int compare( const void *arg1, const void *arg2 );

int main(void)
{
   char * wordlist[4] = { "hello", "thanks", "bye" };
                            // leave room to grow...
   int n = 3;
   char **result;
   char *key = "extra";
   int i;

   printf( "wordlist before _lsearch:" );
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );
   printf( "\n" );

   result = (char **)_lsearch( &key, wordlist,
                      &n, sizeof(char *), compare );

   printf( "wordlist after _lsearch:" );
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );
   printf( "\n" );
}

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}
```

```Output
wordlist before _lsearch: hello thanks bye
wordlist after _lsearch: hello thanks bye extra
```

## <a name="see-also"></a>참고 항목

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lfind](lfind.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
