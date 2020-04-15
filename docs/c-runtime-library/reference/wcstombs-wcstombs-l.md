---
title: wcstombs, _wcstombs_l
ms.date: 4/2/2020
api_name:
- wcstombs
- _wcstombs_l
- _o__wcstombs_l
- _o_wcstombs
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
- wcstombs
- _wcstombs_l
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
ms.openlocfilehash: fb95c6d73a3979a39995b9104a76fc42ca9e8535
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366716"
---
# <a name="wcstombs-_wcstombs_l"></a>wcstombs, _wcstombs_l

와이드 문자의 시퀀스를 멀티바이트 문자의 해당 시퀀스로 변환합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t wcstombs(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count
);
size_t _wcstombs_l(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
size_t wcstombs(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only
template <size_t size>
size_t _wcstombs_l(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*mbstr*<br/>
멀티바이트 문자 시퀀스의 주소입니다.

*wcstr*<br/>
와이드 문자 시퀀스의 주소입니다.

*count*<br/>
멀티바이트 출력 문자열에 저장할 수 있는 최대 바이트 수입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**wcstombs가** 성공적으로 다바이트 문자열을 변환하는 경우 종료 null(있는 경우)을 제외하고 다중 바이트 출력 문자열에 기록된 바이트 수를 반환합니다. *mbstr* 인수가 **NULL인**경우 **wcstombs는** 대상 문자열의 바이트로 필요한 크기를 반환합니다. **wcstombs가** 다양한 문자로 변환할 수 없는 넓은 문자를 만나면 size_t **입력하기** 위해 -1 캐스트를 반환하고 **errno를** **EILSEQ로**설정합니다.

## <a name="remarks"></a>설명

**wcstombs** 함수는 *wcstr이* 가리키는 와이드 문자 문자열을 해당 멀티 바이트 문자로 변환하고 결과를 *mbstr* 배열에 저장합니다. *count* 매개 변수는 멀티바이트 출력 문자열(즉, *mbstr*크기)에 저장할 수 있는 최대 바이트 수를 나타냅니다. 일반적으로는 와이드 문자열을 변환할 때 필요한 바이트의 수를 알 수 없습니다. 출력 문자열에서 1바이트만 사용하면 되면 되는 와이드 문자도 있고 2바이트를 사용해야 하는 문자도 있습니다. 입력 문자열의 모든 와이드 문자(와이드 문자 null 포함)에 대해 다바이트 출력 문자열에 두 바이트가 있는 경우 결과가 적합하도록 보장됩니다.

**wcstombs가** 카운트가 발생하기 전이나 *카운트가* 발생하기 전에 또는 있을 때 와이드 문자 null 문자(L'\0')가 발생하면 8비트 0으로 변환하고 중지합니다. 따라서 *mbstr의* 멀티바이트 문자 문자열은 **wcstombs가** 변환 중에 와이드 문자 null 문자를 만나는 경우에만 null-종료됩니다. *wcstr* 및 *mbstr가* 가리키는 시퀀스가 겹치는 경우 **wcstombs의** 동작은 정의되지 않습니다.

*mbstr* 인수가 **NULL인**경우 **wcstombs는** 대상 문자열의 바이트로 필요한 크기를 반환합니다.

**wcstombs는** 매개 변수의 유효성을 검사합니다. *wcstr이* **NULL이거나** *수가* **INT_MAX**큰 경우 이 함수는 매개 변수 [유효성 검사에](../../c-runtime-library/parameter-validation.md) 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 함수는 **errno를** **EINVAL로** 설정하고 -1을 반환합니다.

**wcstombs는** 로캘 종속 동작에 대해 현재 로캘을 사용합니다. **_wcstombs_l** 대신 전달된 로캘을 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h>|
|**_wcstombs_l**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램은 **wcstombs** 함수의 동작을 보여 줍니다.

```C
// crt_wcstombs.c
// compile with: /W3
// This example demonstrates the use
// of wcstombs, which converts a string
// of wide characters to a string of
// multibyte characters.

#include <stdlib.h>
#include <stdio.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t  count;
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t *pWCBuffer = L"Hello, world.";

    printf("Convert wide-character string:\n" );

    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996
    // Note: wcstombs is deprecated; consider using wcstombs_s instead
    printf("   Characters converted: %u\n",
            count );
    printf("    Multibyte character: %s\n\n",
           pMBBuffer );

    free(pMBBuffer);
}
```

```Output
Convert wide-character string:
   Characters converted: 13
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
