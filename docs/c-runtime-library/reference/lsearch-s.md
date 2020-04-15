---
title: _lsearch_s
ms.date: 4/2/2020
api_name:
- _lsearch_s
- _o__lsearch_s
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
- _lsearch_s
- lsearch_s
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
ms.openlocfilehash: 720b83dd48b42d77f35bce12f16e8ac79eb3b4d3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341657"
---
# <a name="_lsearch_s"></a>_lsearch_s

값에 대한 선형 검색을 수행합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_lsearch](lsearch.md) 버전입니다.

## <a name="syntax"></a>구문

```C
void *_lsearch_s(
   const void *key,
   void *base,
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
검색할 배열의 기준에 대한 포인터입니다.

*number*<br/>
요소의 수입니다.

*크기*<br/>
각 배열 요소의 크기(바이트)입니다.

*비교*<br/>
비교 루틴에 대한 포인터입니다. 두 번째 매개 변수는 검색할 키에 대한 포인터입니다. 세 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.

*context*<br/>
비교 함수에서 액세스할 수 있는 개체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

*키가* 발견되면 **_lsearch_s** *키와*일치하는 *기본* 배열 요소에 대한 포인터를 반환합니다. *키를* 찾을 수 없는 경우 **_lsearch_s** 배열 끝에 새로 추가된 항목에 대한 포인터를 반환합니다.

함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 **errno가** **EINVAL로** 설정되고 함수가 **NULL을**반환합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

### <a name="error-conditions"></a>오류 조건

|*키*|*base*|*비교*|*number*|*크기*|**errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**Null**|any|any|any|any|**아인발 ()에인발 (것)**|
|any|**Null**|any|!= 0|any|**아인발 ()에인발 (것)**|
|any|any|any|any|0|**아인발 ()에인발 (것)**|
|any|any|**Null**|an|any|**아인발 ()에인발 (것)**|

## <a name="remarks"></a>설명

**_lsearch_s** 함수는 각각 *너비* 바이트의 *숫자* 요소 배열에서 값 *키에* 대한 선형 검색을 수행합니다. **bsearch_s**달리 배열을 정렬할 필요가 **_lsearch_s.** *키를* 찾을 수 없는 경우 **_lsearch_s** 배열 및 증분 *수의*끝에 추가합니다.

*비교* 함수는 두 배열 요소를 비교하고 해당 관계를 지정하는 값을 반환하는 사용자 제공 루틴에 대한 포인터입니다. *비교* 함수는 컨텍스트에 대한 포인터를 첫 번째 인수로 합니다. **_lsearch_s** 호출은 검색 중에 하나 이상의 시간을 *비교하여* 각 호출의 두 배열 요소에 포인터를 전달합니다. *compare는* 요소를 비교한 다음 0이 아닌(요소가 다르다는 의미) 또는 0(요소가 동일하다는 의미)을 반환해야 합니다.

*컨텍스트* 포인터는 검색된 데이터 구조가 개체의 일부이고 *비교* 함수가 개체의 멤버에 액세스해야 하는 경우에 유용할 수 있습니다. 예를 들어 *compare* 함수의 코드는 void 포인터를 해당 개체 유형으로 캐스팅하고 해당 개체의 멤버에 액세스할 수 있습니다. *컨텍스트* 포인터를 추가하면 정적 변수를 사용하여 *비교* 함수에서 데이터를 사용할 수 있도록 하는 것과 관련된 재진입 버그를 피하기 위해 추가 컨텍스트를 사용할 수 있으므로 **_lsearch_s** 더 안전합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_lsearch_s**|\<search.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>
