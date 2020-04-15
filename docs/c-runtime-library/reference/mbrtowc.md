---
title: mbrtowc
ms.date: 4/2/2020
api_name:
- mbrtowc
- _o_mbrtowc
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
- mbrtowc
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
ms.openlocfilehash: be46c3f3c728b70c7cbf060572acc24662637a81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340925"
---
# <a name="mbrtowc"></a>mbrtowc

현재 로캘의 멀티바이트 문자를 해당하는 와이드 문자로 변환합니다. 이때 멀티바이트 문자의 중간에서 변환을 다시 시작할 수 있습니다.

## <a name="syntax"></a>구문

```C
size_t mbrtowc(
   wchar_t *wchar,
   const char *mbchar,
   size_t count,
   mbstate_t *mbstate
);
```

### <a name="parameters"></a>매개 변수

*Wchar*<br/>
변환된 와이드 문자 문자열(wchar_t 입력)을 **wchar_t**수신하는 와이드 문자의 주소입니다. 반환 와이드 문자가 필요하지 않으면 이 값은 null 포인터일 수 있습니다.

*mbc하르*<br/>
바이트 시퀀스(멀티바이트 문자)의 주소입니다.

*count*<br/>
검사할 바이트 수입니다.

*mbstate*<br/>
변환 상태 개체에 대한 포인터입니다. 이 값이 null 포인터이면 함수는 정적 내부 변환 상태 개체를 사용합니다. 내부 **mbstate_t** 개체는 스레드에서 안전하지 않으므로 항상 고유한 *mbstate* 인수를 전달하는 것이 좋습니다.

## <a name="return-value"></a>Return Value

해당 값은

0 다음 *개수* 또는 그 이하의 바이트는 *wchar에*저장되는 널 와이드 문자를 *wchar* 나타내는 다바이트 문자를 완료합니다.

1을 *계산하고*포함다음 *개수* 또는 더 적은 바이트가 유효한 다중 바이트 문자를 완료합니다. 반환되는 값은 멀티바이트 문자를 완성하는 바이트 수입니다. 와이드 문자 등가 *wchar,* *wchar* null 포인터가 아닌 경우 에 저장 됩니다.

(size_t) (-1) 인코딩 오류가 발생했습니다. 다음 *개수* 또는 그 이하의 바이트는 완전하고 유효한 다중 바이트 문자에 기여하지 않습니다. 이 경우 **errno는** EILSEQ로 설정되고 *mbstate의* 변환 시프트 상태는 지정되지 않습니다.

(size_t) (-2) 다음 *바이트* 수는 불완전하지만 잠재적으로 유효한 다바이트 문자에 기여하며 모든 *개수* 바이트가 처리되었습니다. 값은 *wchar에*저장되지 않지만 *mbstate는* 함수를 다시 시작하도록 업데이트됩니다.

## <a name="remarks"></a>설명

*mbchar가* null 포인터인 경우 함수는 호출과 동일합니다.

`mbrtowc(NULL, "", 1, &mbstate)`

이 경우 *인수 wchar* 및 *개수의* 값은 무시됩니다.

*mbchar가* null 포인터가 아닌 경우 함수는 *mbchar의* *바이트 수를* 검사하여 다음 다바이트 문자를 완료하는 데 필요한 바이트 수를 결정합니다. 다음 문자가 유효한 경우 해당 멀티바이트 문자는 null 포인터가 아닌 경우 *wchar에* 저장됩니다. 문자가 해당 와이드 null 문자인 경우 *mbstate의* 결과 상태는 초기 변환 상태입니다.

**mbrtowc** 기능은 [mbtowc와 다르며, 재시동가능성에 _mbtowc_l.](mbtowc-mbtowc-l.md) 변환 상태는 동일하거나 다른 다시 시작 가능한 함수에 대한 후속 호출에 대해 *mbstate에* 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어, **wcsrtombs 대신 wcsrtombs에** 대한 후속 호출이 사용되는 경우 응용 프로그램은 **wcsrlen** 대신 wcsrlen을 사용해야 **합니다.** **wcsrlen**

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="example"></a>예제

멀티바이트 문자를 해당하는 와이드 문자로 변환합니다.

```cpp
// crt_mbrtowc.cpp

#include <stdio.h>
#include <mbctype.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

#define BUF_SIZE 100

int Sample(char* szIn, wchar_t* wcOut, int nMax)
{
    mbstate_t   state = {0}; // Initial state
    size_t      nConvResult,
                nmbLen = 0,
                nwcLen = 0;
    wchar_t*    wcCur = wcOut;
    wchar_t*    wcEnd = wcCur + nMax;
    const char* mbCur = szIn;
    const char* mbEnd = mbCur + strlen(mbCur) + 1;
    char*       szLocal;

    // Sets all locale to French_Canada.1252
    szLocal = setlocale(LC_ALL, "French_Canada.1252");
    if (!szLocal)
    {
        printf("The fuction setlocale(LC_ALL, \"French_Canada.1252\") failed!\n");
        return 1;
    }

    printf("Locale set to: \"%s\"\n", szLocal);

    // Sets the code page associated current locale's code page
    // from a previous call to setlocale.
    if (_setmbcp(_MB_CP_SBCS) == -1)
    {
        printf("The fuction _setmbcp(_MB_CP_SBCS) failed!");
        return 1;
    }

    while ((mbCur < mbEnd) && (wcCur < wcEnd))
    {
        //
        nConvResult = mbrtowc(wcCur, mbCur, 1, &state);
        switch (nConvResult)
        {
            case 0:
            {  // done
                printf("Conversion succeeded!\nMultibyte String: ");
                printf(szIn);
                printf("\nWC String: ");
                wprintf(wcOut);
                printf("\n");
                mbCur = mbEnd;
                break;
            }

            case -1:
            {  // encoding error
                printf("The call to mbrtowc has detected an encoding error.\n");
                mbCur = mbEnd;
                break;
            }

            case -2:
            {  // incomplete character
                if   (!mbsinit(&state))
                {
                    printf("Currently in middle of mb conversion, state = %x\n", state);
                    // state will contain data regarding lead byte of mb character
                }

                ++nmbLen;
                ++mbCur;
                break;
            }

            default:
            {
                if   (nConvResult > 2) // The multibyte should never be larger than 2
                {
                    printf("Error: The size of the converted multibyte is %d.\n", nConvResult);
                }

                ++nmbLen;
                ++nwcLen;
                ++wcCur;
                ++mbCur;
            break;
            }
        }
    }

   return 0;
}

int main(int argc, char* argv[])
{
    char    mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";
    wchar_t wcBuf[BUF_SIZE] = {L''};

    return Sample(mbBuf, wcBuf, BUF_SIZE);
}
```

### <a name="sample-output"></a>샘플 출력

```Output
Locale set to: "French_Canada.1252"
Conversion succeeded!
Multibyte String: AaBbCcÜïα∩≡xXyYzZ
WC String: AaBbCcÜïα∩≡xXyYzZ
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**mbrtowc**|\<wchar.h>|

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
