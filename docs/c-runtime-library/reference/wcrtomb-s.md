---
title: wcrtomb_s
ms.date: 4/2/2020
api_name:
- wcrtomb_s
- _o_wcrtomb_s
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
- wcrtomb_s
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
ms.openlocfilehash: ee25b18bfbb86b34e46c8c6776e8ab83157613e8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328176"
---
# <a name="wcrtomb_s"></a>wcrtomb_s

와이드 문자를 멀티바이트 문자 표현으로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wcrtomb](wcrtomb.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char *mbchar,
   size_t sizeOfmbchar,
   wchar_t *wchar,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char (&mbchar)[size],
   wchar_t *wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
기록된 바이트 수를 반환하거나, 오류가 발생하면 -1을 반환합니다.

*mbc하르*<br/>
멀티바이트로 변환된 결과 문자입니다.

*크기Ofmbchar*<br/>
바이트로 *mbchar* 변수의 크기입니다.

*Wchar*<br/>
변환할 와이드 문자입니다.

*mbstate*<br/>
**mbstate_t** 개체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

오류가 발생하면 0 또는 **errno** 값을 반환합니다.

## <a name="remarks"></a>설명

**wcrtomb_s** 함수는 *mbstate에*포함된 지정된 변환 상태에서 시작하여 *wchar에*포함된 값에서 *mbchar로*표시되는 주소로 넓은 문자를 변환합니다. *pReturnValue* 값은 변환된 바이트 수이지만 **MB_CUR_MAX** 바이트 또는 오류가 발생한 경우 -1을 넘지 않습니다.

*mbstate가* null이면 내부 **mbstate_t** 변환 상태가 사용됩니다. *wchar에* 포함된 문자에 해당 다중 바이트 문자가 없는 경우 *pReturnValue* 값은 -1이 되고 함수는 **EILSEQ의** **errno** 값을 반환합니다.

**wcrtomb_s** 함수는 wctomb_s 다르며 재시작 가능성에 [_wctomb_s_l.](wctomb-s-wctomb-s-l.md) 변환 상태는 동일하거나 다른 다시 시작 가능한 함수에 대한 후속 호출에 대해 *mbstate에* 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어 응용 프로그램은 wcstombs_s 대신 **wcsrtombs_s** 대한 후속 호출이 사용된 경우 **wcslen 대신 wcsrlen을**사용합니다. **wcsrlen** **wcstombs_s**

C++에서는 템플릿 오버로드로 인해 이러한 함수를 간편하게 사용할 수 있습니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="exceptions"></a>예외

**wcrtomb_s** 함수는 이 함수가 실행되고 *mbstate가* null인 동안 현재 스레드에서 **setlocale를** 호출하는 함수가 없는 한 다중 스레드안전입니다.

## <a name="example"></a>예제

```C
// crt_wcrtomb_s.c
// This program converts a wide character
// to its corresponding multibyte character.
//

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    errno_t     returnValue;
    size_t      pReturnValue;
    mbstate_t   mbstate;
    size_t      sizeOfmbStr = 1;
    char        mbchar = 0;
    wchar_t*    wchar = L"Q\0";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),
                            *wchar, &mbstate);
    if (returnValue == 0) {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wchar);
        printf(" was converted to a the \"%c\" ", mbchar);
        printf("multibyte character.\n");
    }
    else
    {
        printf("No corresponding multibyte character "
               "was found.\n");
    }
}
```

```Output
The corresponding wide character "Q" was converted to a the "Q" multibyte character.
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wcrtomb_s**|\<wchar.h>|

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
