---
title: _create_locale, _wcreate_locale
ms.date: 4/2/2020
api_name:
- _create_locale
- __create_locale
- _wcreate_locale
- _o__create_locale
- _o__wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- create_locale
- _create_locale
- __create_locale
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
ms.openlocfilehash: 611eaf342776b9a0f57c4f55c52a841c3fd13fb5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348261"
---
# <a name="_create_locale-_wcreate_locale"></a>_create_locale, _wcreate_locale

로캘 개체를 만듭니다.

## <a name="syntax"></a>구문

```C
_locale_t _create_locale(
   int category,
   const char *locale
);
_locale_t _wcreate_locale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>매개 변수

*범주*<br/>
범주입니다.

*로캘*<br/>
로캘 지정자입니다.

## <a name="return-value"></a>Return Value

유효한 *로캘* 및 *범주가* 지정되면 지정된 로캘 설정을 **_locale_t** 개체로 반환합니다. 프로그램의 현재 로캘 설정은 변경되지 않습니다.

## <a name="remarks"></a>설명

**_create_locale** 함수를 사용하면 많은 CRT **함수(_l** 접미사가 있는 함수)의 로캘별 버전에서 사용하기 위해 특정 영역별 설정을 나타내는 개체를 만들 수 있습니다. 이 동작은 **setlocale와**유사하지만 지정된 로캘 설정을 현재 환경에 적용하는 대신 설정이 반환되는 **_locale_t** 구조에 저장됩니다. **_locale_t** 구조는 더 이상 필요하지 않을 때 [_free_locale](free-locale.md) 사용하여 해제되어야 합니다.

**_wcreate_locale** **_create_locale**와이드 문자 버전입니다. **_wcreate_locale** *로캘* 인수는 와이드 문자 문자열입니다. **_wcreate_locale** **_create_locale** 다르게 동일하게 행동합니다.

*범주* 인수는 영향을 받는 로캘 별 동작의 부분을 지정합니다. *범주에* 사용되는 플래그와 영향을 받는 프로그램의 일부는 이 표에 나와 있습니다.

| *범주* 플래그 | 영향 |
|-----------------|---------|
| **Lc_all** |아래에 나열된 모든 범주입니다. |
| **LC_COLLATE** |**스트콜,** **_stricoll,** **wcscoll,** **_wcsicoll,** **strxfrm , strxfrm**, _strncoll , **_strnicoll**, **_wcsncoll**, **_wcsnicoll**, 및 **wcsxfrm** 기능 . **_strnicoll** |
| **LC_CTYPE** | 문자 처리 **함수(는**영향을 받지 않는 숫자, **isxdigit,** **mbstowcs**및 **mbtowc)** |
| **LC_MONETARY** | **localeconv** 함수에서 반환되는 통화 식 서식 정보입니다. |
| **LC_NUMERIC** | 서식이 지정된 출력 루틴(예: **printf)** 및 데이터 변환 루틴 및 **localeconv에서**반환하는 비금전적 서식 정보의 소수점 문자입니다. LC_NUMERIC 소수점 문자 외에도 수천 **LC_NUMERIC** 개의 구분 기호와 [localeconv에서](localeconv.md)반환되는 그룹화 컨트롤 문자열을 설정합니다. |
| **LC_TIME** | **스트프타임** 및 **wcsftime** 함수입니다. |

이 함수는 *범주* 및 *로캘* 매개 변수의 유효성을 검사합니다. 범주 매개 변수가 이전 테이블에 제공된 값 중 하나가 아니거나 *로캘이* **NULL인**경우 함수는 **NULL을**반환합니다.

*로캘* 인수는 로캘을 지정하는 문자열에 대한 포인터입니다. *로캘* 인수의 형식에 대한 자세한 내용은 [로캘 이름, 언어 및 국가/지역 문자열을](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)참조하십시오.

*로캘* 인수는 로캘 이름, 언어 문자열, 언어 문자열 및 국가/지역 코드, 코드 페이지 또는 언어 문자열, 국가/지역 코드 및 코드 페이지를 취할 수 있습니다. 사용 가능한 로캘 이름, 언어, 국가/지역 코드 및 코드 페이지 집합에는 Windows NLS API에서 지원하는 모든 것이 포함됩니다. **_create_locale** 지원하는 로캘 이름 집합은 [로캘 이름, 언어 및 국가/지역 문자열에 설명되어 있습니다.](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) **_create_locale** 지원하는 언어 및 국가/지역 문자열 집합은 [언어 문자열](../../c-runtime-library/language-strings.md) 및 [국가/지역 문자열에 나열됩니다.](../../c-runtime-library/country-region-strings.md)

로캘 설정에 대한 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md)을 참조하세요.

이 함수의 이전 이름인 **__create_locale(두** 개의 선행 밑줄이 있음)은 더 이상 사용되지 않습니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_create_locale**|\<locale.h>|
|**_wcreate_locale**|\<locale.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_create_locale.c
// Sets the current locale to "de-CH" using the
// setlocale function and demonstrates its effect on the strftime
// function.

#include <stdio.h>
#include <locale.h>
#include <time.h>

int main(void)
{
    time_t ltime;
    struct tm thetime;
    unsigned char str[100];
    _locale_t locale;

    // Create a locale object representing the German (Switzerland) locale
    locale = _create_locale(LC_ALL, "de-CH");
    time (&ltime);
    _gmtime64_s(&thetime, &ltime);

    // %#x is the long date representation, appropriate to
    // the current locale
    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In de-CH locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);

    // Create a locale object representing the default C locale
    locale = _create_locale(LC_ALL, "C");
    time(&ltime);
    _gmtime64_s(&thetime, &ltime);

    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In 'C' locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);
}
```

```Output
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'
```

## <a name="see-also"></a>참고 항목

[로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Language Strings](../../c-runtime-library/language-strings.md)<br/>
[국가/지역 문자열](../../c-runtime-library/country-region-strings.md)<br/>
[_free_locale](free-locale.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[스트콜 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
