---
title: _strnset_s, _strnset_s_l, _wcsnset_s, _wcsnset_s_l, _mbsnset_s, _mbsnset_s_l
ms.date: 4/2/2020
api_name:
- _mbsnset_s_l
- _strnset_s
- _mbsnset_s
- _strnset_s_l
- _wcsnset_s_l
- _wcsnset_s
- _o__mbsnset_s
- _o__mbsnset_s_l
- _o__strnset_s
- _o__wcsnset_s
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnset_s_l
- wcsnset_s
- _tcsnset_s_l
- _wcsnset_s
- _mbsnset_s
- _wcsnset_s_l
- _strnset_s_l
- strnset_s_l
- _tcsnset_s
- _strnset_s
- strnset_s
- mbsnset_s_l
- mbsnset_s
- wcsnset_s_l
helpviewer_keywords:
- tcsnset_s function
- mbsnset_s_l function
- initializing characters
- wcsnset_s function
- mbsnset_s function
- _tcsnset_s_l function
- _strnset_s_l function
- _mbsnset_s function
- strnset_s_l function
- _tcsnset_s function
- _strnset_s function
- tcsnset_s_l function
- _mbsnset_s_l function
- strnset_s function
- _wcsnset_s function
ms.assetid: 9cf1b321-b5cb-4469-b285-4c07cfbd8813
ms.openlocfilehash: 62b0ecdc7d9e1afb93c4b15c37016ac687dc80d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364449"
---
# <a name="_strnset_s-_strnset_s_l-_wcsnset_s-_wcsnset_s_l-_mbsnset_s-_mbsnset_s_l"></a>_strnset_s, _strnset_s_l, _wcsnset_s, _wcsnset_s_l, _mbsnset_s, _mbsnset_s_l

문자열의 문자를 지정된 문자로 초기화합니다. 이러한 버전의 [_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 향상된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> **_mbsnset_s** 및 **_mbsnset_s_l** Windows 런타임에서 실행되는 응용 프로그램에서사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t _strnset_s(
   char *str,
   size_t numberOfElements,
   int c,
   size_t count
);
errno_t _strnset_s_l(
   char *str,
   size_t numberOfElements,
   int c,
   size_t count,
   locale_t locale
);
errno_t _wcsnset_s(
   wchar_t *str,
   size_t numberOfElements,
   wchar_t c,
   size_t count
);
errno_t _wcsnset_s_l(
   wchar_t *str,
   size_t numberOfElements,
   wchar_t c,
   size_t count,
   _locale_t locale
);
errno_t _mbsnset_s(
   unsigned char *str,
   size_t numberOfElements,
   unsigned int c,
   size_t count
);
errno_t _mbsnset_s_l(
   unsigned char *str,
   size_t numberOfElements,
   unsigned int c,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
변경할 문자열입니다.

*숫자오브엘리먼트*<br/>
*str* 버퍼의 크기입니다.

*C*<br/>
문자 설정입니다.

*count*<br/>
설정할 문자의 수입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

정상적으로 실행되는 경우 0이고 그렇지 않으면 오류 코드입니다.

이러한 함수는 해당 인수의 유효성을 검사합니다. *str이* 유효한 null-terminated 문자열이 아니거나 크기 인수가 0보다 작거나 같으면 매개 변수 유효성 [검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 이러한 함수는 오류 코드를 반환하고 **errno를** 해당 오류 코드로 설정합니다. 보다 구체적인 값이 적용되지 않는 경우 기본 오류 코드는 **EINVAL입니다.**

## <a name="remarks"></a>설명

이러한 함수는 최대 *c에* *str의* 첫 번째 *카운트* 문자를 설정합니다. *개수가* *str*크기보다 크면 *str* 의 크기가 *개수*대신 사용됩니다. *카운트가* *numberOfElements보다* 크고 두 매개 변수가 *str의*크기보다 큰 경우 오류가 발생합니다.

**_wcsnset_s** **_mbsnset_s** **_strnset_s**와이드 문자 및 멀티 바이트 문자 버전입니다. **_wcsnset_s** 문자열 인수는 와이드 문자 문자열입니다. **_mbsnset_s** 다중 바이트 문자 문자열입니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정에 따른 영향을 받습니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요. **_l** 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, **_l** 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

이러한 함수의 디버그 라이브러리 버전은 먼저 버퍼를 0xFE로 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnset_s**|**_strnset_s**|**_mbsnbset_s**|**_wcsnset_s**|
|**_tcsnset_s_l**|**_strnset_s_l**|**_mbsnbset_s_l**|**_wcsnset_s_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_strnset_s**|\<string.h>|
|**_strnset_s_l**|\<tchar.h>|
|**_wcsnset_s**|\<string.h> 또는 \<wchar.h>|
|**_wcsnset_s_l**|\<tchar.h>|
|**_mbsnset_s**, **_mbsnset_s_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strnset_s.c
#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[15] = "This is a test";
   /* Set not more than 4 characters of string to be *'s */
   printf( "Before: %s\n", string );
   _strnset_s( string, sizeof(string), '*', 4 );
   printf( "After:  %s\n", string );
}
```

```Output
Before: This is a test
After:  **** is a test
```

## <a name="see-also"></a>참고 항목

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
