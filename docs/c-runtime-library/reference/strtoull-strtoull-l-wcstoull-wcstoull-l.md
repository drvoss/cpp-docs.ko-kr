---
title: strtoull, _strtoull_l, wcstoull, _wcstoull_l
ms.date: 4/2/2020
api_name:
- _strtoull_l
- _wcstoull_l
- strtoull
- wcstoull
- _o__strtoull_l
- _o__wcstoull_l
- _o_strtoull
- _o_wcstoull
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
- _wcstoull_l
- _tcstoull
- _tcstoull_l
- wcstoull
- _strtoull_l
- strtoull
helpviewer_keywords:
- strtoull function
- _tcstoull_l function
- _tcstoull function
- _wcstoull_l function
- _strtoull_l function
- wcstoull function
ms.assetid: 36dac1cc-e901-40a0-8802-63562d6d01df
ms.openlocfilehash: 5a27218b9d83314f995df30fbe21d97031d371af
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354058"
---
# <a name="strtoull-_strtoull_l-wcstoull-_wcstoull_l"></a>strtoull, _strtoull_l, wcstoull, _wcstoull_l

문자열을 부호 없는 long long 정수값으로 변환합니다.

## <a name="syntax"></a>구문

```C
unsigned long long strtoull(
   const char *strSource,
   char **endptr,
   int base
);
unsigned long long _strtoull_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned long long wcstoull(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned long long _wcstoull_l(
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

**strtoull은** 오버플로에서 변환된 값(있는 경우) 또는 **ULLONG_MAX** 반환합니다. 변환을 수행할 수 없는 경우 **strtoull은** 0을 반환합니다. **wcstoull은** **strtoull과**유사하게 값을 반환합니다. 두 함수 모두 오버플로 또는 언더플로우가 발생하는 경우 **errno가** **ERANGE로** 설정됩니다.

반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

이러한 각 함수는 입력 문자열 *strSource를* **서명되지 않은** **긴** **long** 긴 정수 값으로 변환합니다.

**strtoull은** 숫자의 일부로 인식할 수 없는 첫 번째 문자에서 문자열 *strSource읽기를* 중지합니다. null 문자를 종료하거나 *기본*문자보다 크거나 같은 첫 번째 숫자 문자일 수 있습니다. 로캘의 **LC_NUMERIC** 범주설정은 *strSource에서*radix 문자의 인식을 결정합니다. 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md)을 참조하십시오. **strtoull** 및 **wcstoull은** 현재 로캘을 사용합니다. **_strtoull_l** **_wcstoull_l** 대신 전달되었지만 그렇지 않으면 동일한 로캘을 사용합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

*endptr이* **NULL이**아닌 경우 검사를 중지한 문자에 대한 포인터는 *endptr로*가리키는 위치에 저장됩니다. 변환을 수행할 수 없는 경우(유효한 숫자를 찾지 않았거나 잘못된 베이스를 지정한 경우) *strSource* 값은 *endptr*.

**wcstoull은** **스트툴의** 와이드 문자 버전이며 *strSource* 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoull**|**strtoull**|**strtoull**|**wcstoull**|
|**_tcstoull_l**|**strtoull_l**|**_strtoull_l**|**_wcstoull_l**|

**strtoull은** *strSource가* 다음 형식의 문자열을 가리키기를 기대합니다.

> [*공백*] [{**+** **-**&#124; }] [**0** [{ **x** &#124; **x}]** [ *문자*&#124;*숫자]*

*공백은* 무시되는 공백 및 탭 문자로 구성될 수 있습니다. *숫자는* 하나 이상의 소수 자릿수입니다. *문자는* 'z'(또는 'Z'를 통해 'A')를 통해 'a'라는 글자 중 하나 이상입니다. 이 형식에 맞지 않는 첫 번째 문자가 발견되면 검색이 중지됩니다. *기준이* 2에서 36 사이이면 숫자의 베이스로 사용됩니다. *기준이* 0이면 *strSource가* 가리키는 문자열의 초기 문자가 베이스를 결정하는 데 사용됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'가 아니면 문자열은 8진수 정수로 해석됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'이면 문자열은 16진수 정수로 해석됩니다. 첫 번째 문자가 '1'~'9' 이면 문자열은 10진수 정수로 해석됩니다. 문자 'a'~'z' 또는 'A'~'Z'에는 값 10~35가 할당됩니다. 할당된 값이 *밑*보다 작은 문자만 사용할 수 있습니다. 밑의 범위를 벗어난 첫 번째 문자가 발견되면 검색이 중지됩니다. 예를 들어 *기준이* 0이고 첫 번째 문자가 '0'이면 팔각정이 가정되고 '8' 또는 '9' 문자가 스캔을 중지합니다. **strtoull은** 더하기**+** 기호 ()**-** 또는 마이너스 기호 () 접두사를 허용합니다. 선행 마이너스 부호는 반환 값이 부정되어 있음을 나타냅니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strtoull**|\<stdlib.h>|
|**wcstoull**|\<stdlib.h> 또는 \<wchar.h>|
|**_strtoull_l**|\<stdlib.h>|
|**_wcstoull_l**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[strtod](strtod-strtod-l-wcstod-wcstod-l.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
