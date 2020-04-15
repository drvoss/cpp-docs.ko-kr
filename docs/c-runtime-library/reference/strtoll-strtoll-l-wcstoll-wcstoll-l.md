---
title: strtoll, _strtoll_l, wcstoll, _wcstoll_l
ms.date: 4/2/2020
api_name:
- strtoll
- wcstoll
- _strtoll_l
- _wcstoll_l
- _o__strtoll_l
- _o__wcstoll_l
- _o_strtoll
- _o_wcstoll
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _strtoll_l
- _tcstoll_l
- _tcstoll
- _wcstoll_l
- strtoll
- wcstoll
helpviewer_keywords:
- _tcstoll_l function
- _wcstoll_l function
- strtoll function
- wcstoll function
- _tcstoll function
- _strtoll_l function
ms.assetid: e2d05dcf-d3b2-4291-9e60-dee77e540fd7
ms.openlocfilehash: d5a0ce8cb2c1d5f88d5439b99047609b32c8d2ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365185"
---
# <a name="strtoll-_strtoll_l-wcstoll-_wcstoll_l"></a>strtoll, _strtoll_l, wcstoll, _wcstoll_l

문자열을 **긴** **long** 값으로 변환합니다.

## <a name="syntax"></a>구문

```C
long long strtoll(
   const char *strSource,
   char **endptr,
   int base
);
long long wcstoll(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
long long _strtoll_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
long long _wcstoll_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*스트소스 (것)스*<br/>
변환할 Null 종료 문자열입니다.

*엔드프트르*<br/>
검색을 중지하는 문자에 대한 포인터입니다.

*base*<br/>
사용할 기수입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**strtoll은** 문자열 *strSource에*표시되는 값을 반환 **LLONG_MIN** **LLONG_MAX합니다.** 변환을 수행할 수 없으면 이 함수는 0을 반환합니다. **wcstoll은** **strtoll과**유사하게 값을 반환합니다.

**LLONG_MAX** 및 **LLONG_MIN** 제한에 정의되어 있습니다. H.

*strSource가* **NULL이거나** *기준이* 0이 아니고 2 보다 크거나 36보다 큰 경우 **errno는** **EINVAL로**설정됩니다.

반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**strtoll** 함수는 *strSource를* **긴** **long**길이로 변환합니다. 두 함수 모두 숫자의 일부로 인식할 수 없는 첫 번째 문자에서 문자열 *strSource* 읽기를 중지합니다. null 문자를 종료하거나 *기본*문자보다 크거나 같은 첫 번째 숫자 문자일 수 있습니다. **wcstoll은** **스트톨의**넓은 문자 버전입니다. 해당 *strSource* 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoll**|**스트톨레고**|**스트톨레고**|**wcstoll**|
|**_tcstoll_l**|**_strtoll_l**|**_strtoll_l**|**_wcstoll_l**|

로캘의 **LC_NUMERIC** 범주 설정은 *strSource에서*radix 문자의 인식을 결정합니다. 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md)을 참조하십시오. **_l** 접미사가 없는 함수는 현재 로캘을 사용합니다. **_strtoll_l** **_wcstoll_l** 접미사가 없는 해당 함수와 동일하지만 전달된 로캘을 대신 사용합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

*endptr이* **NULL이**아닌 경우 검사를 중지한 문자에 대한 포인터는 *endptr로*가리키는 위치에 저장됩니다. 변환을 수행할 수 없는 경우(유효한 숫자를 찾지 않았거나 잘못된 베이스를 지정한 경우) *strSource* 값은 *endptr*.

**strtoll은** *strSource가* 다음 형식의 문자열을 가리킬 것으로 예상합니다.

> [*공백*] [{**+** **-**&#124; }] [**0** [{ **x** &#124; **x}]** [ *문자*&#124;*숫자]*

*공백은* 무시되는 공백 및 탭 문자로 구성될 수 있습니다. *숫자는* 하나 이상의 소수 자릿수입니다. *문자는* 'z'(또는 'Z'를 통해 'A')를 통해 'a'라는 글자 중 하나 이상입니다. 이 형식에 맞지 않는 첫 번째 문자가 발견되면 검색이 중지됩니다. *기준이* 2에서 36 사이이면 숫자의 베이스로 사용됩니다. *기준이* 0이면 *strSource가* 가리키는 문자열의 초기 문자가 베이스를 결정하는 데 사용됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'가 아니면 문자열은 8진수 정수로 해석됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'이면 문자열은 16진수 정수로 해석됩니다. 첫 번째 문자가 '1'~'9' 이면 문자열은 10진수 정수로 해석됩니다. 문자 'a'~'z' 또는 'A'~'Z'에는 값 10~35가 할당됩니다. 할당된 값이 *밑*보다 작은 문자만 사용할 수 있습니다. 밑의 범위를 벗어난 첫 번째 문자가 발견되면 검색이 중지됩니다. 예를 들어 *기준이* 0이고 첫 번째 문자가 '0'이면 팔각정이 가정되고 '8' 또는 '9' 문자가 스캔을 중지합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**스트톨레,** **_strtoll_l**|\<stdlib.h>|
|**wcstoll**, **_wcstoll_l**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
