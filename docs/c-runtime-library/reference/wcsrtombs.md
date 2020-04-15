---
title: wcsrtombs
ms.date: 4/2/2020
api_name:
- wcsrtombs
- _o_wcsrtombs
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
- wcsrtombs
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
ms.openlocfilehash: af22a7d55c5f4958db6962e98f212fb5bb89e61e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328054"
---
# <a name="wcsrtombs"></a>wcsrtombs

와이드 문자열을 멀티바이트 문자열 표현으로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [wcsrtombs_s](wcsrtombs-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t wcsrtombs(
   char *mbstr,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcsrtombs(
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*mbstr*<br/>
변환된 결과 멀티바이트 문자열의 주소 위치입니다.

*wcstr*<br/>
변환할 와이드 문자열의 위치를 간접적으로 가리킵니다.

*count*<br/>
변환할 문자의 수입니다.

*mbstate*<br/>
변환 상태 개체에 **대한 mbstate_t** 포인터입니다.

## <a name="return-value"></a>Return Value

정상적으로 변환된 바이트의 수를 반환합니다. null 종결 null 바이트(있는 경우)는 포함되지 않습니다. 오류가 발생하면 -1을 반환합니다.

## <a name="remarks"></a>설명

**wcsrtombs** 함수는 *mbstate에*포함된 지정된 변환 상태에서 시작하여 *wcstr에서*간접적으로 가리키는 값에서 *mbstr의*주소로 넓은 문자의 문자열을 변환합니다. 변환은 각 문자에 대해 계속됩니다: null 종신 넓은 문자가 발생한 후, 해당되지 않는 문자가 발생하거나 다음 문자가 *개수에*포함된 제한을 초과하는 경우. **wcsrtombs가** 카운트가 발생하기 전이나 *카운트가* 발생하기 전에 또는 있을 때 와이드 문자 null 문자(L'\0')가 발생하면 8비트 0으로 변환하고 중지합니다.

따라서 *mbstr의* 멀티바이트 문자 문자열은 **wcsrtombs가** 변환 중에 넓은 문자 null 문자를 만나는 경우에만 null-종료됩니다. *wcstr* 및 *mbstr에* 의해 가리키는 시퀀스가 겹치는 경우 **wcsrtombs의** 동작은 정의되지 않습니다. **wcsrtombs는** 현재 로캘의 LC_TYPE 범주의 영향을 받습니다.

**wcsrtombs** 기능은 [wcstombs와 다르며, 재시작](wcstombs-wcstombs-l.md) 가능성에 의해 _wcstombs_l. 변환 상태는 동일하거나 다른 다시 시작 가능한 함수에 대한 후속 호출에 대해 *mbstate에* 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어, 응용 프로그램은 **wcsnlen**대신 **wcsnlen을** **사용합니다.** **wcsrtombs**

*mbstr* 인수가 **NULL이면** **wcsrtombs는** 대상 문자열의 바이트로 필요한 크기를 반환합니다. *mbstate가* null이면 내부 **mbstate_t** 변환 상태가 사용됩니다. 문자 시퀀스 *wchar에* 해당 다중 바이트 문자 표현이 없는 경우 -1이 반환되고 **errno가** **EILSEQ로**설정됩니다.

C++에서 이 함수는 해당 최신 보안 버전을 호출하는 템플릿 오버로드를 포함합니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="exceptions"></a>예외

**wcsrtombs** 함수는 이 함수가 실행되고 *mbstate가* null이 아닌 동안 현재 스레드에서 **setlocale를** 호출하는 함수가 없는 한 다중 스레드안전입니다.

## <a name="example"></a>예제

```cpp
// crt_wcsrtombs.cpp
// compile with: /W3
// This code example converts a wide
// character string into a multibyte
// character string.

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

int main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    countConverted = wcsrtombs(mbString, &wcsIndirectString,
                               MB_BUFFER_SIZE, &mbstate); // C4996
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s
    if (errno == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfuly converted.\n" );
    }
}
```

```Output
The string was successfuly converted.
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wcsrtombs**|\<wchar.h>|

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
