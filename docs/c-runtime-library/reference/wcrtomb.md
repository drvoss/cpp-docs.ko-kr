---
title: wcrtomb
ms.date: 4/2/2020
api_name:
- wcrtomb
- _o_wcrtomb
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
- wcrtomb
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
ms.openlocfilehash: eda857b80404aebe46b090741e0b56d4fe692f34
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328092"
---
# <a name="wcrtomb"></a>wcrtomb

와이드 문자를 멀티바이트 문자 표현으로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [wcrtomb_s](wcrtomb-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t wcrtomb(
   char *mbchar,
   wchar_t wchar,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcrtomb(
   char (&mbchar)[size],
   wchar_t wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*mbc하르*<br/>
멀티바이트로 변환된 결과 문자입니다.

*Wchar*<br/>
변환할 와이드 문자입니다.

*mbstate*<br/>
**mbstate_t** 개체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

변환된 멀티바이트 문자를 표시하는 데 필요한 바이트 수를 반환하고, 오류가 발생하면 -1을 반환합니다.

## <a name="remarks"></a>설명

**wcrtomb** 함수는 *mbstate에*포함된 지정된 변환 상태에서 시작하여 *wchar에*포함된 값에서 *mbchar로*표시되는 주소로 넓은 문자를 변환합니다. 반환 값은 해당 다바이트 문자를 나타내는 데 필요한 바이트 수이지만 **MB_CUR_MAX** 바이트 이상을 반환하지 는 않습니다.

*mbstate가* null이면 *mbchar의* 변환 상태를 포함하는 내부 **mbstate_t** 개체가 사용됩니다. 문자 시퀀스 *wchar에* 해당 다중 바이트 문자 표현이 없는 경우 -1이 반환되고 **errno가** **EILSEQ로**설정됩니다.

**wcrtomb** 함수는 다시 시작 가능성에 [의해 _wctomb_l wctomb과](wctomb-wctomb-l.md) 다릅니다. 변환 상태는 동일하거나 다른 다시 시작 가능한 함수에 대한 후속 호출에 대해 *mbstate에* 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어, 응용 프로그램은 **wcsnlen**대신 **wcsnlen을** **사용합니다.** **wcsrtombs**

C++에서 이 함수는 해당 최신 보안 버전을 호출하는 템플릿 오버로드를 포함합니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="exceptions"></a>예외

**wcrtomb** 함수는 이 함수가 실행되는 동안 현재 스레드에서 **setlocale를** 호출하는 함수가 없고 *mbstate가* null인 동안 멀티 스레드안전입니다.

## <a name="example"></a>예제

```C
// crt_wcrtomb.c
// compile with: /W3
// This program converts a wide character
// to its corresponding multibyte character.

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    size_t      sizeOfCovertion = 0;
    mbstate_t   mbstate;
    char        mbStr = 0;
    wchar_t*    wcStr = L"Q";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead
    if (sizeOfCovertion > 0)
    {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wcStr);
        printf(" was converted to the \"%c\" ", mbStr);
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
The corresponding wide character "Q" was converted to the "Q" multibyte character.
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wcrtomb**|\<wchar.h>|

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
