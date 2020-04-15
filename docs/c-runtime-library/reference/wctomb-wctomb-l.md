---
title: wctomb, _wctomb_l
ms.date: 4/2/2020
api_name:
- _wctomb_l
- wctomb
- _o__wctomb_l
- _o_wctomb
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctomb
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
ms.openlocfilehash: 162585ea866b4fb26cfaae3bc94345dadaba0baa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367410"
---
# <a name="wctomb-_wctomb_l"></a>wctomb, _wctomb_l

와이드 문자를 해당 멀티바이트 문자로 변환합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int wctomb(
   char *mbchar,
   wchar_t wchar
);
int _wctomb_l(
   char *mbchar,
   wchar_t wchar,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*mbc하르*<br/>
멀티바이트 문자의 주소입니다.

*Wchar*<br/>
와이드 문자입니다.

## <a name="return-value"></a>Return Value

**wctomb이** 와이드 문자를 다바이트 문자로 변환하는 경우 와이드 문자에서 바이트 **수(MB_CUR_MAX**보다 크지 않습니다)를 반환합니다. *wchar가* 와이드 문자 null 문자(L'\0')인 경우 **wctomb은** 1을 반환합니다. 대상 포인터 *mbchar가* **NULL이면** **wctomb은** 0을 반환합니다. 현재 로캘에서 변환이 불가능한 경우 **wctomb은** -1을 반환하고 **errno는** **EILSEQ로**설정됩니다.

## <a name="remarks"></a>설명

**wctomb** 함수는 *해당 다중* 바이트 문자로 wchar 인수를 변환하고 결과를 *mbchar에*저장합니다. 모든 프로그램에서 언제든지 이 함수를 호출할 수 있습니다. **wctomb는** 모든 로캘 종속 동작에 대해 현재 로캘을 사용합니다. **_wctomb_l** 대신 전달된 로캘을 사용한다는 점을 제외하면 **wctomb과** 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

**wctomb는** 매개 변수의 유효성을 검사합니다. *mbchar가* **NULL인**경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 **errno는** **EINVAL로** 설정되고 함수는 -1을 반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wctomb**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램은 wctomb 함수의 동작을 보여 줍니다.

```cpp
// crt_wctomb.cpp
// compile with: /W3
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int i;
   wchar_t wc = L'a';
   char *pmb = (char *)malloc( MB_CUR_MAX );

   printf( "Convert a wide character:\n" );
   i = wctomb( pmb, wc ); // C4996
   // Note: wctomb is deprecated; consider using wctomb_s
   printf( "   Characters converted: %u\n", i );
   printf( "   Multibyte character: %.1s\n\n", pmb );
}
```

```Output
Convert a wide character:
   Characters converted: 1
   Multibyte character: a
```

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
