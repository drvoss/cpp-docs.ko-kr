---
title: wcstombs_s, _wcstombs_s_l
ms.date: 4/2/2020
api_name:
- _wcstombs_s_l
- wcstombs_s
- _o__wcstombs_s_l
- _o_wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
ms.openlocfilehash: c20066cddb3f28d31d2964ec720b64ed49836f65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328043"
---
# <a name="wcstombs_s-_wcstombs_s_l"></a>wcstombs_s, _wcstombs_s_l

와이드 문자의 시퀀스를 멀티바이트 문자의 해당 시퀀스로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t wcstombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count
);

errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);

template <size_t size>
errno_t wcstombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only

template <size_t size>
errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
null 종단을 포함하여 변환된 문자열의 바이트 크기입니다.

*mbstr*<br/>
결과 변환된 멀티바이트 문자열에 대한 버퍼 주소입니다.

*sizeInBytes*<br/>
*mbstr* 버퍼의 바이트 크기입니다.

*wcstr*<br/>
변환할 와이드 문자열을 가리킵니다.

*count*<br/>
mbstr 버퍼에 저장할 최대 *mbstr* 바이트 수(null 문자 종료 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)포함 하지 않음)

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

성공시 0, 실패시 오류 코드.

|오류 조건|반환 값 및 **errno**|
|---------------------|------------------------------|
|*mbstr은* **NULL이며** *크기인 바이트* > 0|**아인발 ()에인발 (것)**|
|*wcstr은* **NULL입니다.**|**아인발 ()에인발 (것)**|
|대상 버퍼가 너무 작아 변환된 문자열을 포함하지 **_TRUNCATE.** 아래 설명 참조) *count*|**ERANGE**|

이러한 조건 중 하나라도 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 실행을 계속할 수 있는 경우 함수는 오류 코드를 반환하고 **errno를** 테이블에 표시된 대로 설정합니다.

## <a name="remarks"></a>설명

**wcstombs_s** 함수는 *wcstr이* 가리키는 넓은 문자의 문자열을 *mbstr가*가리키는 버퍼에 저장된 멀티 바이트 문자로 변환합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.

- null 와이드 문자가 있는 경우

- 변환할 수 없는 와이드 문자가 있는 경우

- *mbstr* 버퍼에 저장된 바이트 수는 *카운트와*같습니다.

대상 문자열은 항상 null로 끝납니다(오류 발생 시도 포함).

*count가* [_TRUNCATE](../../c-runtime-library/truncate.md)특수 값인 경우 **wcstombs_s** 문자열을 대상 버퍼에 맞게 변환하는 동시에 null 종사에 대한 공간을 남겨 둡니까 합니다. 문자열이 잘린 경우 반환 값은 **STRUNCATE이며**변환은 성공한 것으로 간주됩니다.

**wcstombs_s** 소스 문자열을 성공적으로 변환하는 경우 null 종단을 포함한 변환된 문자열의 바이트 에 크기를 *&#42;pReturnValue(제공된* *pReturnValue는* **NULL이**아님)로 넣습니다. 이는 *mbstr* 인수가 **NULL이고** 필요한 버퍼 크기를 결정하는 방법을 제공하는 경우에도 발생합니다. *mbstr이* **NULL인**경우 *개수는* 무시됩니다.

**wcstombs_s** 멀티 바이트 문자로 변환 할 수없는 넓은 문자를 만나는 경우 *pReturnValue&#42;에*0을 넣고 대상 버퍼를 빈 문자열로 설정하고 **errno를** **EILSEQ로**설정하고 **EILSEQ를**반환합니다.

*wcstr* 및 *mbstr가* 가리키는 시퀀스가 겹치면 **wcstombs_s** 동작이 정의되지 않습니다.

> [!IMPORTANT]
> *wcstr* 및 *mbstr이* 겹치지 않도록 하고 그 *개수가* 변환할 와이드 문자 의 수를 올바르게 반영합니다.

**wcstombs_s** 모든 로캘 종속 동작에 현재 로캘을 사용합니다. **_wcstombs_s_l** 대신 전달된 로캘을 사용한다는 점을 제외하면 **wcstombs와** 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**wcstombs_s**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램은 **wcstombs_s** 함수의 동작을 보여 줍니다.

```C
// crt_wcstombs_s.c
// This example converts a wide character
// string to a multibyte character string.
#include <stdio.h>
#include <stdlib.h>
#include <assert.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t   i;
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t*pWCBuffer = L"Hello, world.";

    printf( "Convert wide-character string:\n" );

    // Conversion
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,
               pWCBuffer, (size_t)BUFFER_SIZE );

    // Output
    printf("   Characters converted: %u\n", i);
    printf("    Multibyte character: %s\n\n",
     pMBBuffer );

    // Free multibyte character buffer
    if (pMBBuffer)
    {
    free(pMBBuffer);
    }
}
```

```Output
Convert wide-character string:
   Characters converted: 14
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
