---
title: _mbclen, mblen, _mblen_l, _mbclen_l
description: Microsoft CRT (C 런타임 라이브러리) _mbclen, mblen, _mblen_l 및 _mbclen_l 함수에 대해 설명 합니다.
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b004babc9e7c82d25cd52ec036c3061c99b5f367
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914364"
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

*c*\
멀티바이트 문자입니다.

*mbstr*\
멀티바이트 문자 바이트 시퀀스의 주소입니다.

*수*\
검사할 바이트 수입니다.

*로캘을*\
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**_mbclen** 및 **_mbclen_l** 는 멀티 바이트 문자 *c*의 길이에 따라 1 또는 2를 반환 합니다. *C* 가 멀티 바이트 인지 여부에 관계 없이 함수는 항상 u t f-8에 대해 1을 반환 합니다. **_Mbclen**에 대 한 오류 반환은 없습니다.

*Mbstr* 이 **NULL**이 아닌 경우 **mblen** 및 **_mblen_l** 는 멀티 바이트 문자의 길이 (바이트)를 반환 합니다. **Mblen** 및 **_mblen_l** 함수는 u t f-8에서 올바르게 작동 하며 1에서 3 사이의 값을 반환할 수 있습니다. *Mbstr* 이 **NULL** 이거나 와이드 문자 null 문자를 가리키는 경우 **mblen** 및 **_mblen_l** 는 0을 반환 합니다. *Mbstr* 가 가리키는 개체는 첫 번째 *카운트* 문자 내에서 유효한 멀티 바이트 문자를 형성 하거나 **mblen** 및 **_mblen_l** -1을 반환 합니다.

## <a name="remarks"></a>설명

**_Mbclen** 함수는 멀티 바이트 문자 *c*의 길이 (바이트)를 반환 합니다. *C* 가 [_ismbblead](ismbblead-ismbblead-l.md)에 대 한 암시적 호출에 의해 결정 된 멀티 바이트 문자의 선행 바이트를 가리키지 않는 경우 **_mbclen** 의 결과를 예측할 수 없습니다.

**mblen** 은 유효한 멀티 바이트 문자인 경우 *mbstr* 의 길이 (바이트)를 반환 합니다. 또한 코드 페이지와 관련 된 멀티 바이트 문자 유효성을 결정 합니다. **mblen** 은 *mbstr*에 포함 된 바이트 *수* 를 검사 하지만 **MB_CUR_MAX** 바이트를 초과 하지 않습니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정에 영향을 받습니다. **_L** 접미사가 없는 이러한 함수 버전은이 로캘 종속 동작에 현재 로캘을 사용 합니다. **_L** 접미사로 사용 하는 버전은 동일 하 게 작동 하지만 대신 전달 된 로캘 매개 변수를 사용 합니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md) 및 [Locale](../../c-runtime-library/locale.md)을 참조 하세요.

**_mbclen**, **_mblen_l**및 **_Mbclen_l** 은 Microsoft 전용 이며 표준 C 라이브러리의 일부가 아닙니다. 이식 가능한 코드를 원하는 위치에 사용 하지 않는 것이 좋습니다. 표준 C 호환성의 경우 대신 **mblen** 또는 **mbrlen** 을 사용 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

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

## <a name="see-also"></a>참조

[문자 분류](../../c-runtime-library/character-classification.md)\
[로캘을](../../c-runtime-library/locale.md)\
[멀티 바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)\
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)\
[mbrlen](mbrlen.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
