---
title: setlocale, _wsetlocale
description: CRT (Microsoft C 런타임) 라이브러리 함수 setlocale 및 _wsetlocale에 대해 설명 합니다.
ms.date: 4/2/2020
api_name:
- _wsetlocale
- setlocale
- _o__wsetlocale
- _o_setlocale
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wsetlocale
- _tsetlocale
- setlocale
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
no-loc:
- setlocale
- _wsetlocale
ms.openlocfilehash: 312fd8e9f794368d334ea353e2c92241d701ab0b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918846"
---
# <a name="setlocale-_wsetlocale"></a>setlocale, _wsetlocale

런타임 로캘을 설정하거나 가져옵니다.

## <a name="syntax"></a>구문

```C
char *setlocale(
   int category,
   const char *locale
);
wchar_t *_wsetlocale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>매개 변수

*범주*\
로캘의 영향을 받는 범주입니다.

*로캘을*\
로캘 지정자입니다.

## <a name="return-value"></a>반환 값

유효한 *로캘* 및 *범주가* 지정 된 경우 지정 된 *로캘* 및 *범주*와 연결 된 문자열에 대 한 포인터를 반환 합니다. *로캘* 또는 *범주가* 유효 하지 않으면은 null 포인터를 반환 하 고 프로그램의 현재 로캘 설정은 변경 되지 않습니다.

예: 호출

```C
setlocale( LC_ALL, "en-US" );
```

문자열만 반환하는 모든 범주를 설정합니다.

```Output
en-US
```

**Setlocale** 에서 반환 된 문자열을 복사 하 여 프로그램의 로캘 정보 부분을 복원할 수 있습니다. **Setlocale**에서 반환 하는 문자열에 대해 전역 또는 스레드 로컬 저장소가 사용 됩니다. 나중에 **setlocale** 을 호출 하면 문자열을 덮어쓰므로 이전 호출에서 반환 된 문자열 포인터가 무효화 됩니다.

## <a name="remarks"></a>설명

**Setlocale** 함수를 사용 하 여 *로캘* 및 *범주*에 지정 된 현재 프로그램 로캘 정보의 일부 또는 모두를 설정, 변경 또는 쿼리 합니다. *로캘은* 프로그램의 특정 측면을 사용자 지정할 수 있는 집약성 (국가/지역 및 언어)을 나타냅니다. 일부 로캘 종속 범주에는 날짜 형식 지정 및 통화 값의 형식 표시가 포함됩니다. 컴퓨터에서 여러 양식이 지원 되는 언어의 기본 문자열로 *로캘을* 설정 하는 경우에는 **setlocale** 반환 값을 확인 하 여 적용 되는 언어를 확인 해야 합니다. 예를 들어 *로캘을* "중국어"로 설정 하면 반환 값이 "중국어 간체" 또는 "중국어 번체" 일 수 있습니다.

**_wsetlocale** 은 **setlocale**의 와이드 문자 버전입니다. **_wsetlocale** 의 *로캘* 인수 및 반환 값은 와이드 문자열입니다. **_wsetlocale** 와 **setlocale** 은 동일 하 게 작동 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsetlocale**|**setlocale**|**setlocale**|**_wsetlocale**|

*Category* 인수는 영향을 받는 프로그램 로캘 정보의 일부를 지정 합니다. *범주* 에 사용 되는 매크로 및 영향을 받는 프로그램의 일부는 다음과 같습니다.

|*범주* 플래그|영향|
|-|-|
| **LC_ALL** | 아래에 나열된 모든 범주입니다. |
| **LC_COLLATE** | **Strcoll**, **_stricoll**, **wcscoll**, **_wcsicoll**, **strxfrm**, **_strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**및 **wcsxfrm** 함수를 말합니다. |
| **LC_CTYPE** | 문자 처리 함수 ( **isdigit**, **isxdigit**, **mbstowcs**및 **mbtowc**는 영향을 받지 않음)입니다. |
| **LC_MONETARY** | **Localeconv** 함수에서 반환 된 통화 형식 정보입니다. |
| **LC_NUMERIC** | 형식이 지정 된 출력 루틴 (예: **printf**), 데이터 변환 루틴 및 **localeconv**에서 반환 하는 비 통화 서식 지정 정보에 대 한 소수점 문자입니다. 소수점 문자 외에도 **LC_NUMERIC** 는 천 단위 구분 기호와 [localeconv](localeconv.md)에서 반환 하는 grouping 컨트롤 문자열을 설정 합니다. |
| **LC_TIME** | **Strftime** 및 **wcsftime** 함수 |

이 함수는 범주 매개 변수의 유효성을 검사합니다. 범주 매개 변수가 이전 표에 지정 된 값 중 하나가 아닌 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 **errno** 를 **EINVAL** 로 설정 하 고 **NULL**을 반환 합니다.

*Locale* 인수는 로캘을 지정 하는 문자열에 대 한 포인터입니다. *로캘* 인수의 형식에 대 한 자세한 내용은 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)을 참조 하세요. *locale*에서 빈 문자열을 가리키면 로캘은 구현에서 정의된 네이티브 환경입니다. C 값은 C 번역에 대 한 최소 ANSI 규격 **환경을 지정 합니다** . **C** 로캘에서는 모든 **char** 데이터 형식이 1 바이트이 고 해당 값이 항상 256 보다 작은 것으로 가정 합니다.

프로그램을 시작할 때 다음 문을 실행합니다.

`setlocale( LC_ALL, "C" );`

*로캘* 인수는 로캘 이름, 언어 문자열, 언어 문자열 및 국가/지역 코드, 코드 페이지, 언어 문자열, 국가/지역 코드 및 코드 페이지를 사용할 수 있습니다. 사용 가능한 로캘 이름, 언어, 국가/지역 코드 및 코드 페이지의 집합에는 Windows NLS API에서 지 원하는 모든 항목이 포함 됩니다. **Setlocale** 에서 지 원하는 로캘 이름 집합은 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)에 설명 되어 있습니다. **Setlocale** 에서 지 원하는 언어 및 국가/지역 문자열 집합은 [언어 문자열](../../c-runtime-library/language-strings.md) 및 [국가/지역 문자열](../../c-runtime-library/country-region-strings.md)에 나열 됩니다. 코드에 포함되거나 스토리지에 직렬화된 로캘 문자열의 성능과 유지 관리를 위해 로캘 이름 형식을 사용하는 것이 좋습니다. 로캘 이름 문자열은 언어와 국가/지역 이름 형식보다 운영 체제 업데이트에 의해 변경될 가능성이 적습니다.

*로캘* 인수로 전달 되는 null 포인터는에 국제 환경을 설정 하는 대신 **setlocale** 을 쿼리하도록 지시 합니다. *로캘* 인수가 null 포인터인 경우 프로그램의 현재 로캘 설정은 변경 되지 않습니다. 대신 **setlocale** 은 스레드의 현재 로캘 *범주* 와 연결 된 문자열에 대 한 포인터를 반환 합니다. *Category* 인수가 **LC_ALL**경우 함수는 세미콜론으로 구분 된 각 범주의 현재 설정을 나타내는 문자열을 반환 합니다. 예: 호출 시퀀스

```C
// Set all categories and return "en-US"
setlocale(LC_ALL, "en-US");
// Set only the LC_MONETARY category and return "fr-FR"
setlocale(LC_MONETARY, "fr-FR");
printf("%s\n", setlocale(LC_ALL, NULL));
```

다음을 반환합니다.

```Output
LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US
```

**LC_ALL** 범주와 연결 된 문자열입니다.

다음 예는 **LC_ALL** 범주와 관련이 있습니다. 문자열 중 하나입니다. OCP "and"입니다. 해당 로캘 이름에 대 한 사용자 기본 OEM 코드 페이지 및 사용자 기본 ANSI 코드 페이지의 사용을 지정 하기 위해 코드 페이지 번호 대신 ACP "를 사용할 수 있습니다.

- `setlocale( LC_ALL, "" );`

   로캘을 운영 체제에서 가져온 사용자 기본 ANSI 코드 페이지인 기본값으로 설정합니다. 로캘 이름은 [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)에서 반환 하는 값으로 설정 됩니다. 코드 페이지는 [Getacp](/windows/win32/api/winnls/nf-winnls-getacp)에서 반환 된 값으로 설정 됩니다.

- `setlocale( LC_ALL, ".OCP" );`

   로캘을 운영 체제에서 얻은 현재 OEM 코드 페이지로 설정 합니다. 로캘 이름은 [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)에서 반환 하는 값으로 설정 됩니다. 코드 페이지는 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)의 사용자 기본 로캘 이름에 대 한 [LOCALE_IDEFAULTCODEPAGE](/windows/win32/intl/locale-idefault-constants) 값으로 설정 됩니다.

- `setlocale( LC_ALL, ".ACP" );`

   로캘을 운영 체제에서 얻은 ANSI 코드 페이지로 설정합니다. 로캘 이름은 [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)에서 반환 하는 값으로 설정 됩니다. 코드 페이지는 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)의 사용자 기본 로캘 이름에 대 한 [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) 값으로 설정 됩니다.

- `setlocale( LC_ALL, "<localename>" );`

   * \<Localename>* 에 의해 표시 되는 로캘 이름으로 로캘을 설정 합니다. 코드 페이지는 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)에 의해 지정 된 로캘 이름에 대 한 [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) 값으로 설정 됩니다.

- `setlocale( LC_ALL, "<language>_<country>" );`

   * \<언어>* 및 * \<국가>* 에서 표시 한 언어 및 국가/지역에 대 한 로캘을 호스트 운영 체제에서 가져온 기본 코드 페이지와 함께 설정 합니다. 코드 페이지는 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)에 의해 지정 된 로캘 이름에 대 한 [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) 값으로 설정 됩니다.

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   언어>* \<>*, 국가/지역 및 * \<code_page>* 문자열로 표시 되는 언어, 국가/지역 및 코드 페이지로 로캘을 설정 합니다. * \< * 언어, 국가/지역 및 코드 페이지의 다양한 조합을 사용할 수 있습니다. 예를 들어, 이 호출은 코드 페이지 1252에 따라 로캘을 프랑스어(캐나다)로 설정합니다.

   `setlocale( LC_ALL, "French_Canada.1252" );`

   이 호출은 기본 ANSI 코드 페이지에 따라 로캘을 프랑스어(캐나다)로 설정합니다.

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   이 호출은 기본 OEM 코드 페이지에 따라 로캘을 프랑스어(캐나다)로 설정합니다.

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   로캘을 * \<언어>* 로 표시 되는 언어로 설정 하 고, 호스트 운영 체제에서 가져온 대로 지정 된 언어에 대 한 기본 국가/지역 및 해당 국가/지역에 대 한 사용자 기본 ANSI 코드 페이지를 사용 합니다. 예를 들어 **setlocale** 에 대 한 다음 호출은 기능적으로 동일 합니다.

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   성능 및 유지 관리에 첫 번째 폼을 사용하는 것이 좋습니다.

- `setlocale( LC_ALL, ".<code_page>" );`

   지정한 코드 페이지에 대한 기본 국가/지역 및 언어(호스트 운영 체제에 의해 정의됨)와 함께 *<code_page>* 에 의해 표시되는 값으로 코드 페이지를 설정합니다.

코드 페이지의 변경 내용을 적용 하려면 범주가 **LC_ALL** 또는 **LC_CTYPE** 여야 합니다. 예를 들어, 기본 국가/지역 및 호스트 운영 체제의 언어가 "미국" 및 "영어" 인 경우 다음 두 번의 **setlocale** 호출은 기능적으로 동일 합니다.

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

자세한 내용은 [C/C++ 전처리기 참조](../../preprocessor/c-cpp-preprocessor-reference.md)에서 [setlocale](../../preprocessor/setlocale.md) pragma 지시문을 참조하세요.

함수 [_configthreadlocale](configthreadlocale.md) 은 **setlocale** 이 프로그램의 모든 스레드 로캘 또는 호출 스레드의 로캘로 영향을 주는지 여부를 제어 하는 데 사용 됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**setlocale**|\<locale.h>|
|**_wsetlocale**|\<locale.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_setlocale.c
//
// This program demonstrates the use of setlocale when
// using two independent threads.
//

#include <locale.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date in the current
// locale's format.
int get_date(unsigned char* str)
{
    __time64_t ltime;
    struct tm  thetime;

    // Retrieve the current time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // "%#x" is the long date representation in the
    // current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm *)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to the argument
// and prints the date.
uintptr_t __stdcall SecondThreadFunc( void* pArguments )
{
    unsigned char str[BUFF_SIZE];
    char * locale = (char *)pArguments;

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, locale));

    // Retrieve the date string from the helper function
    if (get_date(str) == 0)
    {
        printf("The date in %s locale is: '%s'\n", locale, str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread sets the locale to English
// and then spawns a second thread (above) and prints the date.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the locale of the main thread to US English.
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "en-US"));

    // Create the second thread with a German locale.
    // Our thread function takes an argument of the locale to use.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      "de-DE", 0, &threadID );

    if (get_date(str) == 0)
    {
        // Retrieve the date string from the helper function
        printf("The date in en-US locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to en-US.
The time in en-US locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to de-DE.
The time in de-DE locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>참조

[로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[_configthreadlocale](configthreadlocale.md)\
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)\
[로캘을](../../c-runtime-library/locale.md)\
[localeconv](localeconv.md)\
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)\
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)\
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)\
[_setmbcp](setmbcp.md)\
[strcoll 함수](../../c-runtime-library/strcoll-functions.md)\
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)\
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)\
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)\
[wctomb, _wctomb_l](wctomb-wctomb-l.md)
