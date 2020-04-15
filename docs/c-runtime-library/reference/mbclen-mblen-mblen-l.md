---
title: _mbclen, mblen, _mblen_l, _mbclen_l
description: Microsoft C 런타임 라이브러리(CRT) _mbclen, mblen, _mblen_l 및 _mbclen_l 함수에 대해 설명합니다.
ms.date: 4/2/2020
api_name:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
- _o__mbclen
- _o__mbclen_l
- _o__mblen_l
- _o_mblen
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mblen
- ftclen
- _mbclen
- _mbclen_l
- tclen
- _ftclen
- _tclen
- mbclen
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- _mbclen_l function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
ms.openlocfilehash: 76e8771898d8baa65f275304a9aefdcaeeb5b3bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341116"
---
# <a name="_mbclen-mblen-_mblen_l-_mbclen_l"></a>_mbclen, mblen, _mblen_l, _mbclen_l

멀티바이트 문자의 길이를 가져오고 유효성을 확인합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t _mbclen(
   const unsigned char *c
);
size_t _mbclen_l(
   unsigned char const* c,
   _locale_t locale
);
int mblen(
   const char *mbstr,
   size_t count
);
int _mblen_l(
   const char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*C*\
멀티바이트 문자입니다.

*mbstr*\
멀티바이트 문자 바이트 시퀀스의 주소입니다.

*횟수*\
검사할 바이트 수입니다.

*로캘*\
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**_mbclen** **및 _mbclen_l** 멀티바이트 문자 *c의*길이에 따라 1 또는 2를 반환합니다. 함수는 *c가* 멀티바이트인지 여부에 관계없이 UTF-8에 대해 항상 1을 반환합니다. **_mbclen**.

*mbstr이* **NULL이**아닌 경우 **mblen** 및 **_mblen_l** 길이를 바이트로 곱바이트로 반환합니다. **mblen** 및 **_mblen_l** 함수는 UTF-8에서 올바르게 작동하며 1과 3 사이의 값을 반환할 수 있습니다. *mbstr이* **NULL(또는** 와이드 문자 null 문자를 가리키는 경우)이면 **mblen과** **_mblen_l** 반환 0입니다. *mbstr가* 가리키는 개체는 첫 번째 *카운트* 문자 내에서 유효한 다중 바이트 문자를 형성해야 하거나 **mblen** 및 **_mblen_l** 반환 -1을 반환해야 합니다.

## <a name="remarks"></a>설명

**_mbclen** 함수는 다중 바이트 문자 *c의*길이를 바이트로 반환합니다. *c가* 다중 바이트 문자의 리드 바이트를 가리키지 않는 [경우(_ismbblead](ismbblead-ismbblead-l.md)대한 암시적 호출에 의해 결정된 경우 **_mbclen** 결과는 예측할 수 없습니다.

**mblen은** 유효한 다중 바이트 문자인 경우 *mbstr의* 바이트로 길이를 반환합니다. 또한 코드 페이지와 연결된 다중 바이트 문자 유효성도 결정합니다. **mblen은** *mbstr에*포함된 *바이트* 수를 수 또는 더 적게 검사하지만 **MB_CUR_MAX** 바이트를 초과하지는 않습니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정의 영향을 받습니다. **_l** 접미사가 없는 이러한 함수의 버전은 이 로캘 종속 동작에 대해 현재 로캘을 사용합니다. **_l** 접미사 버전은 동일하게 행동하지만 대신 전달된 로캘 매개 변수를 사용합니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md) 및 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.

**_mbclen** **_mblen_l**및 **_mbclen_l** 표준 C 라이브러리의 일부가 아닌 Microsoft 관련 입니다. 휴대용 코드를 원하는 곳에 사용하지 않는 것이 좋습니다. 표준 C 호환성을 위해 **mblen** 또는 **mbrlen** 대신 사용하십시오.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|매크로 또는 인라인 함수에 매핑|**_mbclen**|매크로 또는 인라인 함수에 매핑|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbclen**|\<mbstring.h>|
|**mblen**|\<stdlib.h>|
|**_mblen_l**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_mblen.c
/* illustrates the behavior of the mblen function
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    int      i;
    char    *pmbc = (char *)malloc( sizeof( char ) );
    wchar_t  wc   = L'a';

    printf( "Convert wide character to multibyte character:\n" );
    wctomb_s( &i, pmbc, sizeof(char), wc );
    printf( "   Characters converted: %u\n", i );
    printf( "   Multibyte character: %x\n\n", *pmbc );

    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );

    pmbc = NULL;
    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );
}
```

```Output
Convert wide character to multibyte character:
   Characters converted: 1
   Multibyte character: 61

Length in bytes of multibyte character 61: 1
Length in bytes of NULL multibyte character 0: 0
```

## <a name="see-also"></a>참고 항목

[문자 분류](../../c-runtime-library/character-classification.md)\
[로캘](../../c-runtime-library/locale.md)\
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)\
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)\
[mbrlen](mbrlen.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
