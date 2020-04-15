---
title: strtod, _strtod_l, wcstod, _wcstod_l
ms.date: 4/2/2020
api_name:
- wcstod
- _wcstod_l
- _strtod_l
- strtod
- _o__strtod_l
- _o__wcstod_l
- _o_strtod
- _o_wcstod
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
- _tcstod
- strtod
- wcstod
- _strtod_l
- _wcstod_l
- stdlib/strtod
- corecrt_wstdlib/wcstod
- stdlib/_strtod_l
- corecrt_wstdlib/_wcstod_l
helpviewer_keywords:
- wcstod_l function
- tcstod_l function
- _tcstod_l function
- strtod function
- _wcstod_l function
- wcstod function
- strtod_l function
- tcstod function
- _tcstod function
- _strtod_l function
- string conversion, to floating point values
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
ms.openlocfilehash: a688846d5db4d508327745728f8933c91bfd54e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337660"
---
# <a name="strtod-_strtod_l-wcstod-_wcstod_l"></a>strtod, _strtod_l, wcstod, _wcstod_l

문자열을 배정밀도 값으로 변환합니다.

## <a name="syntax"></a>구문

```C
double strtod(
   const char *strSource,
   char **endptr
);
double _strtod_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
double wcstod(
   const wchar_t *strSource,
   wchar_t **endptr
);
double wcstod_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*스트소스 (것)스*<br/>
변환할 Null 종료 문자열입니다.

*엔드프트르*<br/>
검색을 중지하는 문자에 대한 포인터입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**strtod는** 표현이 오버플로를 일으키는 경우를 제외하고 부동 소수점 번호의 값을 반환하며, 이 경우 함수는 +/-**HUGE_VAL**반환합니다. **HUGE_VAL** 부호는 나타낼 수 없는 값의 부호와 일치합니다. 변환을 수행할 수 없거나 언더플로우가 발생하는 경우 **strtod는** 0을 반환합니다.

**wcstod는 strtod와** 유사하게 값을 **반환합니다.** 두 함수 모두 오버플로 또는 언더플로우가 발생하고 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출되면 **errno가** **ERANGE로** 설정됩니다. 이 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 참조하십시오.

## <a name="remarks"></a>설명

각 함수는 입력 문자열 *strSource를* **double로**변환합니다. **strtod** 함수는 *strSource를* 이중 정밀도 값으로 변환합니다. **strtod는** 숫자의 일부로 인식할 수 없는 첫 번째 문자에서 문자열 *strSource를* 읽는 것을 중지합니다. 이 문자는 종료 null 문자일 수 있습니다. **wcstod는** **스트롱의**넓은 문자 버전입니다; 해당 *strSource* 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

현재 로캘의 **LC_NUMERIC** 범주 설정은 *strSource에서*radix 포인트 문자의 인식을 결정합니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요. **_l** 접미사가 없는 함수는 현재 로캘을 사용합니다. **_strtod_l** 대신 전달된 *로캘을* 사용한다는 점을 제외하면 **_strtod_l** 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

*endptr이* **NULL이**아닌 경우 검사를 중지한 문자에 대한 포인터는 *endptr로*가리키는 위치에 저장됩니다. 변환을 수행할 수 없는 경우(유효한 숫자를 찾지 않았거나 잘못된 베이스를 지정한 경우) *strSource* 값은 *endptr*이 가리키는 위치에 저장됩니다.

**strtod는** *strSource가* 다음 양식 중 하나의 문자열을 가리키기를 기대합니다.

[*공백*] [*기호*] {*숫자* [*방사형* *숫자]*&#124; *방사형* *자릿수*} [{e &#124; **E**} *digits*[*기호*] [*공백*] [*sequence**기호*] { 0x &#124;**e** **0X**} {*육신자리* [*radix"}* *hexdigits*&#124;**0x** *radixs* *hexdigits*} [ {**p** &#124; **P**} [*기호* *]*[ 화이트 스페이스 ]*[* 화이트 스페이스 ] [*기호*] {**INF** &#124; **인피니티**} [*화이트 스페이스*] **[** *기호*]

선택적 선행 *공백은* 무시되는 공백 및 탭 문자로 구성될 수 있습니다. *기호는* 플러스 (+) 또는 마이너스 (-); *숫자는* 하나 이상의 소수 자릿수입니다. *육각숫자는* 하나 이상의 육각형 숫자입니다. *radix는* 기본 "C" 로캘의 마침표(.) 또는 현재 로캘이 다르거나 *로캘이* 지정된 경우 로캘별 값인 radix 포인트 문자입니다. *시퀀스는* 숫자 또는 밑줄 문자의 시퀀스입니다. 소수점과 육각형 숫자 형식 모두에서 radix 점 문자 앞에 숫자가 나타나지 않으면 radix 점 문자 앞에 하나 이상 나타나야 합니다. 소수점 이하의 숫자 뒤에는 소개**문자(e** 또는 **E)와**선택적으로 서명된 정수로 구성된 지수가 뒤따를 수 있습니다. 육각형 형식에서 육각형 자릿수 뒤에는 소개**문자(p** 또는 **P)와**2의 힘으로 지수를 나타내는 선택적으로 서명된 헥사데피mal 정수로 구성된 지수가 뒤따를 수 있습니다. 어느 형태에서든 지수 부분이나 radix 포인트 문자가 나타나지 않으면 radix 포인트 문자가 문자열의 마지막 숫자를 따르는 것으로 가정합니다. **케이스는 INF** 및 **NAN** 양식 모두에서 무시됩니다. 이러한 양식 중 하나에 맞지 않는 첫 번째 문자는 검사를 중지합니다.

이러한 함수의 UCRT 버전은 포트란**스타일(d** 또는 **D)** 지수 문자의 변환을 지원하지 않습니다. 이러한 비표준 확장은 CRT의 이전 버전에서 지원되었으므로 코드에 대한 중요한 변경 사항일 수 있습니다. UCRT 버전은 이전 버전에서는 지원되지 않은 HEXadecimal 문자열 및 INF 및 NAN 값의 라운드 트립을 지원합니다. 이로 인해 코드가 주요 변경 사항이 발생할 수도 있습니다. 예를 들어 문자열 "0x1a"는 이전 **strtod** 버전에서는 0.0으로 해석되지만 UCRT 버전에서는 26.0으로 해석됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**스트롱**, **_strtod_l**|C: &lt;stdlib.h> C++: &lt;cstdlib> 또는 &lt;stdlib.h> |
|**wcstod**, **_wcstod_l**|C: &lt;stdlib.h> 또는 &lt;wchar.h> C++: &lt;cstdlib>, &lt;stdlib.h> 또는 &lt;wchar.h> |

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strtod.c
// This program uses strtod to convert a
// string to a double-precision value; strtol to
// convert a string to long integer values; and strtoul
// to convert a string to unsigned long-integer values.
//

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char   *string, *stopstring;
   double x;
   long   l;
   int    base;
   unsigned long ul;

   string = "3.1415926This stopped it";
   x = strtod( string, &stopstring );
   printf( "string = %s\n", string );
   printf("   strtod = %f\n", x );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "-10110134932This stopped it";
   l = strtol( string, &stopstring, 10 );
   printf( "string = %s\n", string );
   printf("   strtol = %ld\n", l );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "10110134932";
   printf( "string = %s\n", string );

   // Convert string using base 2, 4, and 8:
   for( base = 2; base <= 8; base *= 2 )
   {
      // Convert the string:
      ul = strtoul( string, &stopstring, base );
      printf( "   strtol = %ld (base %d)\n", ul, base );
      printf( "   Stopped scan at: %s\n", stopstring );
   }
}
```

```Output
string = 3.1415926This stopped it
   strtod = 3.141593
   Stopped scan at: This stopped it

string = -10110134932This stopped it
   strtol = -2147483648
   Stopped scan at: This stopped it

string = 10110134932
   strtol = 45 (base 2)
   Stopped scan at: 34932
   strtol = 4423 (base 4)
   Stopped scan at: 4932
   strtol = 2134108 (base 8)
   Stopped scan at: 932
```

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
