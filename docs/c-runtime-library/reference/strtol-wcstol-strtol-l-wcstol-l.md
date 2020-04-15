---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 4/2/2020
api_name:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- _o__strtol_l
- _o__wcstol_l
- _o_strtol
- _o_wcstol
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
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
no-loc:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- LONG_MAX
- LONG_MIN
- errno
- ERANGE
- EINVAL
- LC_NUMERIC
- _tcstol
- _tcstol_l
- localeconv
- setlocale
- _wsetlocale
- strtod
- _strtod_l
- wcstod
- _wcstod_l
- strtoll
- _strtoll_l
- wcstoll
- _wcstoll_l
- strtoul
- _strtoul_l
- wcstoul
- _wcstoul_l
- atof
- _atof_l
- _wtof
- _wtof_l
ms.openlocfilehash: dbeaf04d34aa20e15de48e99082ed07edb6129ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320485"
---
# <a name="strtol-wcstol-_strtol_l-_wcstol_l"></a>strtol, wcstol, _strtol_l, _wcstol_l

문자열을 **긴** 정수 값으로 변환합니다.

## <a name="syntax"></a>구문

```C
long strtol(
   const char *string,
   char **end_ptr,
   int base
);
long wcstol(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base
);
long _strtol_l(
   const char *string,
   char **end_ptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*문자열*\
변환할 Null 종료 문자열입니다.

*end_ptr*\
마지막으로 해석된 문자 다음의 문자를 가리키도록 설정된 출력 매개 변수입니다. **NULL**인 경우 무시됩니다.

*기본*\
사용할 기수입니다.

*로캘*\
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**strtol**, **wcstol**, **_strtol_l**및 **_wcstol_l** *문자열에*표시된 값을 반환합니다. 변환이 불가능한 경우 0을 반환합니다. 표현이 오버플로를 일으킬 때 LONG_MAX **반환하거나** **LONG_MIN.**

오버플로우 또는 언더플로우가 발생하는 경우 **errno가** **ERANGE로** 설정됩니다. *문자열이* **NULL인**경우 **EINVAL로** 설정됩니다. 또는 *기준이* 0이 아닌 경우 2 보다 크거나 36보다 큽니다. **ERANGE,** **EINVAL**및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, 에르노, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하십시오.

## <a name="remarks"></a>설명

**스트톨,** **wcstol,** **_strtol_l**및 **_wcstol_l** 함수는 *문자열을* **긴**으로 변환합니다. 숫자의 일부로 인식되지 않는 첫 번째 문자에서 *문자열* 읽기를 중지합니다. 종료-null 문자, 또는 첫 번째 영숫자 문자보다 크거나 *기본과*같을 수 있습니다.

**wcstol** 및 **_wcstol_l** **스트톨과** **_strtol_l**와이드 문자 버전입니다. 문자열 *string* 인수는 와이드 문자 문자열입니다. 이러한 함수는 **스트톨과** 동일하게 작동하며 그렇지 **않으면 _strtol_l.** 로캘의 **LC_NUMERIC** 범주 설정은 *문자열의*radix 문자(소수표 또는 소수점)의 인식을 결정합니다. 함수 **스트톨** 및 **wcstol은** 현재 로캘을 사용합니다. **_strtol_l** **_wcstol_l** 대신 전달된 로캘을 사용합니다. 자세한 내용은 [setlocale] 및 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.

*end_ptr* **NULL이면**무시됩니다. 그렇지 않으면 스캔을 중지한 문자에 대한 포인터가 *end_ptr*가리키는 위치에 저장됩니다. 유효한 숫자가 없거나 잘못된 기준을 지정하면 변환이 불가능합니다. *문자열* 값은 *end_ptr*가리키는 위치에 저장됩니다.

**strtol은** *문자열이* 다음 형식의 문자열을 가리킬 것으로 예상합니다.

> [*공백*] [{**+** **-**&#124; }] [**0** [{ **x** &#124; **X** }] [*[[[[[[[[[]]*

대괄호`[ ]`() 서라운드 옵션 요소. 곱슬 받침대와 세로 막대`{ | }`() 단일 요소에 대한 대안. *공백은* 무시되는 공백 및 탭 문자로 구성될 수 있습니다. *숫자는* 소수 자릿수 또는 'z'(또는 'Z'를 통해 'A')를 통해 문자 'a'입니다. 이 양식에 맞지 않는 첫 번째 문자는 검사를 중지합니다. *기준이* 2에서 36 사이이면 숫자의 기준으로 사용됩니다. *기준이* 0이면 *문자열로* 가리키는 문자열의 초기 문자가 기본을 결정하는 데 사용됩니다. 첫 번째 문자가 0이고 두 번째 문자가 'x' 또는 'X'가 아닌 경우 문자열은 팔각형 정수로 해석됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'이면 문자열은 16진수 정수로 해석됩니다. 첫 번째 문자가 '1'~'9' 이면 문자열은 10진수 정수로 해석됩니다. 'z'를 통해 문자 'a'(또는 'Z'를 통해 'A')는 값 10에서 35까지 할당됩니다. 검색은 값이 *기준보다*적은 문자만 허용합니다. 밑의 범위를 벗어난 첫 번째 문자가 발견되면 검색이 중지됩니다. 예를 들어 문자열이 "01"으로 시작한다고 *가정합니다.* *기준이* 0이면 스캐너는 팔각형 정수라고 가정합니다. '8' 또는 '9' 문자는 스캔을 중지합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> 또는 \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|
|**_wcstol_l**|\<stdlib.h> 또는 \<wchar.h>|

**_strtol_l** 및 **_wcstol_l** 기능은 표준 C 라이브러리의 일부가 아닌 Microsoft에 특정합니다. 호환성에 대한 자세한 내용은 [Compatibility](../compatibility.md)을 참조하세요.

## <a name="example"></a>예제

에 대한 [strtod](strtod-strtod-l-wcstod-wcstod-l.md)예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[데이터 변환](../data-conversion.md)\
[로캘](../locale.md)\
[localeconv](localeconv.md)\
[setlocale, _wsetlocale](setlocale-wsetlocale.md)\
[숫자 값 함수에 문자열](../string-to-numeric-value-functions.md)\
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)\
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)\
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)\
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)
