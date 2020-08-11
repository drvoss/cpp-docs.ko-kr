---
title: setlocale, _wsetlocale
description: CRT (Microsoft C 런타임) 라이브러리 함수 및에 대해 설명 합니다 setlocale _wsetlocale .
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
ms.openlocfilehash: 812aab43667416a5892d8e24d03d0e67cad8d0ac
ms.sourcegitcommit: b51703a96ee35ee2376d5f0775b70f03ccbe6d9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88086996"
---
# <a name="no-locsetlocale-no-loc_wsetlocale"></a>setlocale, _wsetlocale

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

프로그램 로캘 정보의 일부를 복원할 수 있도록 `setlocale`에서 반환된 문자열을 복사할 수 있습니다. 글로벌 또는 스레드 로컬 스토리지는 `setlocale`에서 반환된 문자열에 사용됩니다. `setlocale`에 대한 이후 호출이 문자열을 덮어쓰므로, 이전 호출에서 반환된 문자열 포인터가 무효화됩니다.

## <a name="remarks"></a>설명

`setlocale` *로캘* 및 *범주*에 지정 된 현재 프로그램 로캘 정보의 일부 또는 모두를 설정, 변경 또는 쿼리 하는 함수를 사용 합니다. *로캘은* 프로그램의 특정 측면을 사용자 지정할 수 있는 집약성 (국가/지역 및 언어)을 나타냅니다. 일부 로캘 종속 범주에는 날짜 형식 지정 및 통화 값의 형식 표시가 포함됩니다. 컴퓨터에서 여러 양식이 지원 되는 언어의 기본 문자열로 *로캘을* 설정 하는 경우 `setlocale` 반환 값을 확인 하 여 적용 되는 언어를 확인 해야 합니다. 예를 들어 *로캘을* "중국어"로 설정 하면 반환 값이 "중국어 간체" 또는 "중국어 번체" 일 수 있습니다.

`_wsetlocale`는의 와이드 문자 버전 이며 `setlocale` ,의 *로캘* 인수와 반환 값은 `_wsetlocale` 와이드 문자 문자열입니다. 그렇지 않으면`_wsetlocale` 과 `setlocale` 이 동일하게 작동합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tsetlocale`|`setlocale`|`setlocale`|`_wsetlocale`|

*Category* 인수는 영향을 받는 프로그램 로캘 정보의 일부를 지정 합니다. *범주* 에 사용 되는 매크로 및 영향을 받는 프로그램의 일부는 다음과 같습니다.

|*범주* 플래그|영향|
|-|-|
| `LC_ALL` | 아래에 나열된 모든 범주입니다. |
| `LC_COLLATE` | `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` 및 `wcsxfrm` 함수입니다. |
| `LC_CTYPE` | 문자 처리 함수(영향을 받지 않는 `isdigit`, `isxdigit`, `mbstowcs` 및 `mbtowc` 제외)입니다. |
| `LC_MONETARY` | `localeconv` 함수에 의해 반환되는 통화 서식 정보입니다. |
| `LC_NUMERIC` | 서식이 지정된 출력 루틴(예: `printf`), 데이터 변환 루틴 및 `localeconv`에 의해 반환된 비통화 서식 정보에 대한 소수점 문자입니다. 소수점 문자 이외에도 `LC_NUMERIC`은 1,000단위 구분 기호와 [localeconv](localeconv.md)에 의해 반환된 그룹화 제어 문자열을 설정합니다. |
| `LC_TIME` | `strftime` 및 `wcsftime` 함수입니다. |

이 함수는 범주 매개 변수의 유효성을 검사합니다. 범주 매개 변수가 이전 표에 지정 된 값 중 하나가 아닌 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다. 계속해서 실행하도록 허용된 경우 함수가`errno`를 `EINVAL`로 설정하고 `NULL`을 반환합니다.

*Locale* 인수는 로캘을 지정 하는 문자열에 대 한 포인터입니다. *로캘* 인수의 형식에 대 한 자세한 내용은 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)을 참조 하세요. *locale*에서 빈 문자열을 가리키면 로캘은 구현에서 정의된 네이티브 환경입니다. `C`의 값은 C 번역에 대한 최소 ANSI 표준에 맞는 환경을 지정합니다. `C`로캘은 ``char`` 데이터 형식이 1바이트이고 해당 값이 항상 256보다 작은 것으로 가정합니다.

프로그램을 시작할 때 다음 문을 실행합니다.

`setlocale( LC_ALL, "C" );`

*로캘* 인수는 로캘 이름, 언어 문자열, 언어 문자열 및 국가/지역 코드, 코드 페이지, 언어 문자열, 국가/지역 코드 및 코드 페이지를 사용할 수 있습니다. 사용 가능한 로캘 이름, 언어, 국가/지역 코드 및 코드 페이지의 집합에는 Windows NLS API에서 지 원하는 모든 항목이 포함 됩니다. `setlocale`에서 지원하는 로캘 이름 집합은 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)에 설명되어 있습니다. `setlocale`에서 지원하는 언어 및 국가/지역 문자열 집합은 [언어 문자열](../../c-runtime-library/language-strings.md) 및 [국가/지역 문자열](../../c-runtime-library/country-region-strings.md)에 나열되어 있습니다. 코드에 포함되거나 스토리지에 직렬화된 로캘 문자열의 성능과 유지 관리를 위해 로캘 이름 형식을 사용하는 것이 좋습니다. 로캘 이름 문자열은 언어와 국가/지역 이름 형식보다 운영 체제 업데이트에 의해 변경될 가능성이 적습니다.

*로캘* 인수로 전달 되는 null 포인터는가 `setlocale` 국제 환경을 설정 하는 대신 쿼리에 지시 합니다. *로캘* 인수가 null 포인터인 경우 프로그램의 현재 로캘 설정은 변경 되지 않습니다. 대신는 `setlocale` 스레드의 현재 로캘 *범주* 와 연결 된 문자열에 대 한 포인터를 반환 합니다. *Category* 인수가 이면 `LC_ALL` 함수는 세미콜론으로 구분 된 각 범주의 현재 설정을 나타내는 문자열을 반환 합니다. 예: 호출 시퀀스

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

`LC_ALL` 범주와 연결된 문자열입니다.

다음 예제는 `LC_ALL` 범주와 관련이 있습니다. 문자열 중 하나입니다. OCP "and"입니다. 해당 로캘 이름에 대 한 사용자 기본 OEM 코드 페이지 및 사용자 기본 ANSI 코드 페이지의 사용을 지정 하기 위해 코드 페이지 번호 대신 ACP "를 사용할 수 있습니다.

- `setlocale( LC_ALL, "" );`

   로캘을 운영 체제에서 가져온 사용자 기본 ANSI 코드 페이지인 기본값으로 설정합니다. 로캘 이름은 [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)에서 반환 하는 값으로 설정 됩니다. 코드 페이지는 [Getacp](/windows/win32/api/winnls/nf-winnls-getacp)에서 반환 된 값으로 설정 됩니다.

- `setlocale( LC_ALL, ".OCP" );`

   로캘을 운영 체제에서 얻은 현재 OEM 코드 페이지로 설정 합니다. 로캘 이름은 [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)에서 반환 하는 값으로 설정 됩니다. 코드 페이지는 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)의 사용자 기본 로캘 이름에 대 한 [LOCALE_IDEFAULTCODEPAGE](/windows/win32/intl/locale-idefault-constants) 값으로 설정 됩니다.

- `setlocale( LC_ALL, ".ACP" );`

   로캘을 운영 체제에서 얻은 ANSI 코드 페이지로 설정합니다. 로캘 이름은 [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)에서 반환 하는 값으로 설정 됩니다. 코드 페이지는 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)의 사용자 기본 로캘 이름에 대 한 [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) 값으로 설정 됩니다.

- `setlocale( LC_ALL, "<localename>" );`

   로캘을에 의해 표시 되는 로캘 이름으로 설정 *\<localename>* 합니다. 코드 페이지는 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)에 의해 지정 된 로캘 이름에 대 한 [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) 값으로 설정 됩니다.

- `setlocale( LC_ALL, "<language>_<country>" );`

   로캘을 *\<language>* *\<country>* 호스트 운영 체제에서 가져온 기본 코드 페이지와 함께 및에 표시 되는 언어 및 국가/지역으로 설정 합니다. 코드 페이지는 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)에 의해 지정 된 로캘 이름에 대 한 [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) 값으로 설정 됩니다.

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   로캘을, 및 문자열로 표시 되는 언어, 국가/지역 및 코드 페이지로 설정 합니다 *\<language>* *\<country>* *\<code_page>* . 언어, 국가/지역 및 코드 페이지의 다양한 조합을 사용할 수 있습니다. 예를 들어, 이 호출은 코드 페이지 1252에 따라 로캘을 프랑스어(캐나다)로 설정합니다.

   `setlocale( LC_ALL, "French_Canada.1252" );`

   이 호출은 기본 ANSI 코드 페이지에 따라 로캘을 프랑스어(캐나다)로 설정합니다.

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   이 호출은 기본 OEM 코드 페이지에 따라 로캘을 프랑스어(캐나다)로 설정합니다.

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   로캘을에 표시 되는 언어로 설정 하 *\<language>* 고, 호스트 운영 체제에서 가져온 대로 지정 된 언어에 대 한 기본 국가/지역 및 해당 국가/지역에 대 한 사용자 기본 ANSI 코드 페이지를 사용 합니다. 예를 들어, `setlocale`에 대한 다음 호출은 기능적으로 동일합니다.

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   성능 및 유지 관리에 첫 번째 폼을 사용하는 것이 좋습니다.

- `setlocale( LC_ALL, ".<code_page>" );`

   지정한 코드 페이지에 대한 기본 국가/지역 및 언어(호스트 운영 체제에 의해 정의됨)와 함께 *<code_page>* 에 의해 표시되는 값으로 코드 페이지를 설정합니다.

코드 페이지에 변경 내용을 적용하려면 범주가 `LC_ALL` 또는 `LC_CTYPE`이어야 합니다. 예를 들어, 기본 국가/지역 및 호스트 운영 체제의 언어가 "미국" 및 "영어"인 경우 `setlocale`에 대한 다음 두 호출이 기능적으로 동일합니다.

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

자세한 내용은 [setlocale](../../preprocessor/setlocale.md) [C/c + + 전처리기 참조](../../preprocessor/c-cpp-preprocessor-reference.md)의 pragma 지시문을 참조 하십시오.

[_configthreadlocale](configthreadlocale.md) 함수는 `setlocale`가 프로그램의 모든 스레드 로캘 또는 호출 스레드의 로캘에 영향을 주는지 아닌지를 제어하기 위해 사용됩니다.

## <a name="utf-8-support"></a>UTF-8 지원

Windows 10 빌드 17134 (4 월 2018 업데이트)부터 유니버설 C 런타임은 UTF-8 코드 페이지를 사용 하도록 지원 합니다. 즉, `char` C 런타임 함수에 전달 되는 문자열은 utf-8 인코딩의 문자열을 필요로 합니다. UTF-8 모드를 사용 하도록 설정 하려면를 사용 하는 경우 코드 페이지로 "UTF-8"을 사용 `setlocale` 합니다. 예를 들어 `setlocale(LC_ALL, ".utf8")` 는 로캘의 경우 현재 기본 WINDOWS ANSI 코드 페이지 (ACP)를 사용 하 고 코드 페이지에는 u t f-8을 사용 합니다.

를 호출한 후 `setlocale(LC_ALL, ".UTF8")` 에는 " 😊 "를에 전달할 수 있으며, `mbtowcs` `wchar_t` 이전에는이 작업을 수행 하는 데 사용할 수 있는 로캘 설정이 없었습니다.

UTF-8 모드는 `char` 기본 ACP (WINDOWS ANSI 코드 페이지)를 사용 하 여 이전에 번역 된 문자열이 있는 함수에도 사용할 수 있습니다. 예를 들어 [`_mkdir("😊")`](../reference/mkdir-wmkdir.md) utf-8 코드 페이지를 사용 하는 동안를 호출 하면 프로그램을 실행 하기 전에 ACP를 u t f-8로 변경 하도록 요구 하는 대신 해당 사용자를 폴더 이름으로 사용 하 여 디렉터리가 올바르게 생성 됩니다. 마찬가지로 해당 폴더 내에서를 호출 하면 [`_getcwd()`](../reference/getcwd-wgetcwd.md) u t f-8로 인코딩된 문자열을 반환 합니다. 호환성을 위해 C 로캘 코드 페이지가 u t f-8로 설정 되지 않은 경우에도 ACP가 사용 됩니다.

U t f-8은 프로그램 시작 중에 설정 되어 있으며 기본 Windows ACP (ANSI 코드 페이지)를 사용 해야 하는 C 런타임의 다음과 같은 측면에서 [`__argv`](../argc-argv-wargv.md) , 및를 사용 해야 [`_acmdln`](../acmdln-tcmdln-wcmdln.md) [`_pgmptr`](../pgmptr-wpgmptr.md) 합니다.

이 지원 [ `mbrtoc16` `mbrtoc32` 의 이전에는, ](../reference/mbrtoc16-mbrtoc323.md), [ `c16rtomb` 및 `c32rtomb` ](../reference/c16rtomb-c32rtomb1.md) 는 utf-8 좁은 문자열 ( `wchar_t` Windows 플랫폼과 동일한 인코딩)과 u t f-32 간을 변환 하는 데 있었습니다. 호환성을 위해 이러한 Api는를 통해 코드 페이지를 설정 하는 것이 아니라 u t f-8로만 변환 `setlocale` 됩니다.

Windows 7과 같은 Windows 10 이전의 OS에서이 기능을 사용 하려면 Windows SDK 이상의 버전 17134을 사용 하 여 정적으로 [앱 로컬 배포](../../windows/universal-crt-deployment.md#local-deployment) 또는 링크를 사용 해야 합니다. 17134 이전의 Windows 10 운영 체제의 경우 정적 연결만 지원 됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`setlocale`|\<locale.h>|
|`_wsetlocale`|\<locale.h> 또는 \<wchar.h>|

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

## <a name="see-also"></a>참고 항목

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
