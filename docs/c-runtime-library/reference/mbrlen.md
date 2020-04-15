---
title: mbrlen
ms.date: 4/2/2020
api_name:
- mbrlen
- _o_mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrlen
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
ms.openlocfilehash: 7503de22a8310335ddd678335916d3e74dab6e70
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340985"
---
# <a name="mbrlen"></a>mbrlen

현재 로캘에서 멀티바이트 문자열을 완성하는 데 필요한 바이트 수를 결정합니다. 이때 멀티바이트 문자의 중간에서 다시 시작할 수 있습니다.

## <a name="syntax"></a>구문

```C
size_t mbrlen(
   const char * str,
   size_t count,
   mbstate_t * mbstate
);
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
멀티바이트 문자열에서 검사할 다음 바이트에 대한 포인터입니다.

*count*<br/>
검사할 최대 바이트 수입니다.

*mbstate*<br/>
*str의*초기 바이트의 현재 시프트 상태에 대한 포인터.

## <a name="return-value"></a>Return Value

해당 값은

|||
|-|-|
0|다음 *개수* 또는 그 이하의 바이트는 넓은 null 문자를 나타내는 다바이트 문자를 완료합니다.
1 *카운트,* 포함|다음 *개수* 또는 그 이하의 바이트가 유효한 다중 바이트 문자를 완료합니다. 반환되는 값은 멀티바이트 문자를 완성하는 바이트 수입니다.
(size_t)(-2)|다음 *바이트* 수는 불완전하지만 잠재적으로 유효한 다바이트 문자에 기여하며 모든 *카운트* 바이트가 처리되었습니다.
(size_t)(-1)|인코딩 오류가 발생했습니다. 다음 *개수* 또는 그 이하의 바이트는 완전하고 유효한 다중 바이트 문자에 기여하지 않습니다. 이 경우 **errno는** EILSEQ로 설정되고 *mbstate의* 변환 상태가 지정되지 않습니다.

## <a name="remarks"></a>설명

**mbrlen** 함수는 *str이* 가리키는 바이트로 시작하여 최대 *바이트를* 검사하여 시프트 시퀀스를 포함하여 다음 멀티바이트 문자를 완료하는 데 필요한 바이트 수를 결정합니다. *mbstate가* 사용자가 `mbrtowc(NULL, str, count, &mbstate)` 제공한 **mbstate_t** 개체 또는 라이브러리에서 제공하는 정적 내부 개체인 호출과 동일합니다.

**mbrlen** 함수는 *mbstate* 매개 변수에서 불완전한 다중 바이트 문자의 시프트 상태를 저장하고 사용합니다. 이렇게 하면 **mbrlen이** 필요한 경우 멀티바이트 문자 의 중간에 다시 시작하여 대부분의 *카운트* 바이트를 검사할 수 있습니다. *mbstate가* null 포인터인 경우 **mbrlen은** 내부정적 **mbstate_t** 개체를 사용하여 shift 상태를 저장합니다. 내부 **mbstate_t** 개체는 스레드에서 안전하지 않으므로 항상 고유한 *mbstate* 매개 변수를 할당하고 전달하는 것이 좋습니다.

**mbrlen** 함수는 [_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md) 재시작 가능성에 의해 다릅니다. shift 상태는 동일하거나 다른 다시 시작 가능한 함수에 대한 후속 호출에 대해 *mbstate에* 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어, **wcsrtombs 대신 wcsrtombs에** 대한 후속 호출이 사용되는 경우 응용 프로그램은 **wcsrlen** 대신 wcsrlen을 사용해야 **합니다.** **wcsrlen**

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|적용할 수 없음|적용할 수 없음|**mbrlen**|적용할 수 없음|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 예제에서는 다중 바이트 문자의 해석이 현재 코드 페이지에 따라 달라지는 방법을 보여 주며 **mbrlen의**다시 시작 기능을 보여 줍니다.

```C
// crt_mbrlen.c
// Compile by using: cl crt_mbrlen.c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

size_t Example(const char * pStr)
{
    size_t      charLen = 0;
    size_t      charCount = 0;
    mbstate_t   mbState = {0};

    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&
            charLen != (size_t)-1)
    {
        if (charLen != (size_t)-2) // if complete mbcs char,
        {
            charCount++;
        }
    }
    return (charCount);
}

int main( void )
{
    int         cp;
    size_t      charCount = 0;
    const char  *pSample =
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";

    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);

    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale
    _setmbcp(932); // and Japanese multibyte code page
    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);
}
```

```Output

Code page: 0
é╨éτé¬é╚: Shift-jis hiragana.
Character count: 29

Code page: 932
????: Shift-jis hiragana.
Character count: 25
```

## <a name="see-also"></a>참고 항목

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
