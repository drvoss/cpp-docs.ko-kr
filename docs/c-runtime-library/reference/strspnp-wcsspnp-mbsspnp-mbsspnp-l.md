---
title: _strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l
ms.date: 4/2/2020
api_name:
- _mbsspnp
- _wcsspnp
- _mbsspnp_l
- _strspnp
- _o__mbsspnp
- _o__mbsspnp_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcsspnp
- _mbsspnp
- strspnp
- _ftcsspnp
- _mbsspnp_l
- wcsspnp
- mbsspnp_l
- _wcsspnp
- _strspnp
- mbsspnp
helpviewer_keywords:
- _strspnp function
- _wcsspnp function
- _mbsspnp_l function
- strspnp function
- mbsspnp function
- wcsspnp function
- _mbsspnp function
- mbsspnp_l function
- _tcsspnp function
- tcsspnp function
ms.assetid: 1ce18100-2edd-4c3b-af8b-53f204d80233
ms.openlocfilehash: c45fc42fb9edce1b82b0910f8aae81d4058d5974
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317016"
---
# <a name="_strspnp-_wcsspnp-_mbsspnp-_mbsspnp_l"></a>_strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l

지정된 다른 문자열에 없는 지정된 문자열의 첫 번째 문자에 대한 포인터를 반환합니다.

> [!IMPORTANT]
> **_mbsspnp** 및 **_mbsspnp_l** Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_strspnp(
   const char *str,
   const char *charset
);
wchar_t *_wcsspnp(
   const unsigned wchar_t *str,
   const unsigned wchar_t *charset
);
unsigned char *_mbsspnp(
   const unsigned char *str,
   const unsigned char *charset
);
unsigned char *_mbsspnp_l(
   const unsigned char *str,
   const unsigned char *charset,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
검색할 Null 종료 문자열입니다.

*문자 집합*<br/>
Null 종료 문자 집합입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**_strspnp** **_wcsspnp**및 *charset의*문자 집합에 속하지 않는 *str의* 첫 번째 문자에 대한 포인터를 반환할 **_mbsspnp** 있습니다. 이러한 각 함수는 *str이* *charset의*문자로 만 구성된 경우 **NULL을** 반환합니다. 각 이러한 루틴에 대해 오류를 나타내기 위한 반환 값은 예약되지 않습니다.

## <a name="remarks"></a>설명

**_mbsspnp** 함수는 *charset의*문자 집합에 속하지 않는 *str의* 첫 번째 문자인 다중 바이트 문자에 대한 포인터를 반환합니다. **_mbsspnp** 현재 사용 중인 다중 바이트 코드 페이지에 따라 [다중 바이트](../../c-runtime-library/code-pages.md) 문자 시퀀스를 인식합니다. 종료 null 문자는 검색에 포함되지 않습니다.

*str* 또는 *charset이* null 포인터인 경우 이 함수는 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 함수는 **NULL을** 반환하고 **errno를** **EINVAL로**설정합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsspnp**|**_strspnp**|**_mbsspnp**|**_wcsspnp**|

**_strspnp** **_wcsspnp** _mbsspnp 단일 바이트 문자 및 와이드 **_mbsspnp**문자 버전입니다. **_strspnp** **_wcsspnp** 달리 **_mbsspnp** 동일하게 행동합니다. 이 매핑에 대해서만 제공되며 다른 이유로 사용해서는 안 됩니다. 자세한 내용은 [일반 텍스트 매핑 사용](../../c-runtime-library/using-generic-text-mappings.md) 및 [일반 텍스트 매핑](../../c-runtime-library/generic-text-mappings.md)을 참조하세요.

**_mbsspnp_l** 대신 전달된 로캘 매개 변수를 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbsspnp**|\<mbstring.h>|
|**_strspnp**|\<tchar.h>|
|**_wcsspnp**|\<tchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_mbsspnp.c
#include <mbstring.h>
#include <stdio.h>

int main( void ) {
   const unsigned char string1[] = "cabbage";
   const unsigned char string2[] = "c";
   unsigned char *ptr = 0;
   ptr = _mbsspnp( string1, string2 );
   printf( "%s\n", ptr);
}
```

### <a name="output"></a>출력

```Output
abbage
```

## <a name="see-also"></a>참고 항목

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
