---
title: _atoi64, _atoi64_l, _wtoi64, _wtoi64_l
ms.date: 4/2/2020
api_name:
- _atoi64_l
- _wtoi64
- _atoi64
- _wtoi64_l
- _o__atoi64
- _o__atoi64_l
- _o__wtoi64
- _o__wtoi64_l
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
- _atoi64
- _tstoi64
- _ttoi64
- wtoi64
- _tstoi64_l
- atoi64
- _wtoi64_l
- _wtoi64
- wtoi64_l
- _atoi64_l
- atoi64_l
helpviewer_keywords:
- tstoi64 function
- wtoi64 function
- atoi64_l function
- _ttoi64 function
- string conversion, to integers
- wtoi64_l function
- atoi64 function
- _tstoi64 function
- _atoi64_l function
- _wtoi64_l function
- ttoi64 function
- _wtoi64 function
- _atoi64 function
ms.assetid: 2c3e30fd-545d-4222-8364-0c5905df9526
ms.openlocfilehash: 103b100b293ff183dd89f3e7c2f291f9d49519e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348826"
---
# <a name="_atoi64-_atoi64_l-_wtoi64-_wtoi64_l"></a>_atoi64, _atoi64_l, _wtoi64, _wtoi64_l

문자열을 64비트 정수로 변환합니다.

## <a name="syntax"></a>구문

```C
__int64 _atoi64(
   const char *str
);
__int64 _wtoi64(
   const wchar_t *str
);
__int64 _atoi64_l(
   const char *str,
   _locale_t locale
);
__int64 _wtoi64_l(
   const wchar_t *str,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
변환할 문자열입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

각 함수는 입력 문자를 숫자로 해석하여 생성된 **__int64** 값을 반환합니다. 입력을 해당 형식의 값으로 변환할 수 없는 경우 **_atoi64** 반환 값은 0입니다.

큰 양수 적분 값을 가진 오버플로의 경우 **_atoi64** 큰 음수 적분 값을 가진 오버플로의 경우 **I64_MAX** 반환하고 **I64_MIN** 반환합니다.

모든 범위를 벗어난 경우 **errno는** **ERANGE로**설정됩니다. 전달된 매개 변수가 **NULL인**경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 이러한 함수는 **errno를** **EINVAL로** 설정하고 0을 반환합니다.

## <a name="remarks"></a>설명

이러한 함수는 문자열을 64비트 정수 값으로 변환합니다.

입력 문자열은 지정된 형식의 숫자 값으로 해석될 수 있는 문자 시퀀스입니다. 함수는 숫자의 일부로 인식할 수 없는 첫 번째 문자에서 입력 문자열 읽기를 중지합니다. 이 문자는 문자열을 종결하는 null 문자('\0' 또는 L'\0')일 수 있습니다.

**_atoi64** *str* 인수에는 다음과 같은 양식이 있습니다.

> [*공백*] [*기호*] [*숫자*]

*공백은* 무시되는 공백 또는 탭 문자로 구성됩니다. *기호는* 플러스 (+) 또는 마이너스 (-); *자릿수는* 하나 이상의 숫자입니다.

**_wtoi64** 매개 변수로 넓은 문자 문자열을 사용 한다는 점을 제외 하 고 **_atoi64** 동일 합니다.

**_l** 접미사가 있는 이러한 함수의 버전은 현재 로캘 대신 전달된 로캘 매개 변수를 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tstoi64**|**_atoi64**|**_atoi64**|**_wtoi64**|
|**_ttoi64**|**_atoi64**|**_atoi64**|**_wtoi64**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|--------------|---------------------|
|**_atoi64**, **_atoi64_l**|\<stdlib.h>|
|**_wtoi64**, **_wtoi64_l**|\<stdlib.h> 또는 \<wchar.h>|

## <a name="example"></a>예제

이 프로그램은 문자열로 저장된 숫자를 **_atoi64** 함수를 사용하여 숫자 값으로 변환하는 방법을 보여줍니다.

```C
// crt_atoi64.c
// This program shows how numbers stored as
// strings can be converted to numeric values
// using the _atoi64 functions.
#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
    char    *str = NULL;
    __int64 value = 0;

    // An example of the _atoi64 function
    // with leading and trailing white spaces.
    str = "  -2309 ";
    value = _atoi64( str );
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );

    // Another example of the _atoi64 function
    // with an arbitrary decimal point.
    str = "314127.64";
    value = _atoi64( str );
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );

    // Another example of the _atoi64 function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = _atoi64( str );
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: _atoi64( "  -2309 " ) = -2309
Function: _atoi64( "314127.64" ) = 314127
Function: _atoi64( "3336402735171707160320" ) = -1
Overflow condition occurred.
```

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>
