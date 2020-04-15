---
title: strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
ms.date: 4/2/2020
api_name:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
- _o__mbsnlen
- _o__mbsnlen_l
- _o__mbstrnlen
- _o__mbstrnlen_l
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
- wcsnlen
- strnlen_s
- _mbsnlen
- _mbsnlen_l
- _tcsnlen
- _tcscnlen
- _mbstrnlen_l
- wcsnlen_s
- _mbstrnlen
- strnlen
- _tcscnlen_l
helpviewer_keywords:
- _tcscnlen function
- _mbstrnlen function
- _mbsnlen_l function
- lengths, strings
- mbstrnlen function
- mbsnlen_l function
- _mbstrnlen_l function
- _tcscnlen_l function
- wcsnlen_l function
- _tcsnlen function
- _mbsnlen function
- strnlen function
- mbsnlen function
- wcsnlen_s function
- strnlen_s function
- mbstrnlen_l function
- wcsnlen function
- string length
- strnlen_l function
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
ms.openlocfilehash: db4fa65fa47dfe11d7ab56ffc5feee06f2634e2a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364465"
---
# <a name="strnlen-strnlen_s-wcsnlen-wcsnlen_s-_mbsnlen-_mbsnlen_l-_mbstrnlen-_mbstrnlen_l"></a>strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l

현재 로캘이나 전달된 로캘을 사용하여 문자열 길이를 가져옵니다. 이러한 함수는 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)의 더 안전한 버전입니다.

> [!IMPORTANT]
> **_mbsnlen**, **_mbsnlen_l** **_mbstrnlen**및 **_mbstrnlen_l** Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t strnlen(
   const char *str,
   size_t numberOfElements
);
size_t strnlen_s(
   const char *str,
   size_t numberOfElements
);
size_t wcsnlen(
   const wchar_t *str,
   size_t numberOfElements
);
size_t wcsnlen_s(
   const wchar_t *str,
   size_t numberOfElements
);
size_t _mbsnlen(
   const unsigned char *str,
   size_t numberOfElements
);
size_t _mbsnlen_l(
   const unsigned char *str,
   size_t numberOfElements,
   _locale_t locale
);
size_t _mbstrnlen(
   const char *str,
   size_t numberOfElements
);
size_t _mbstrnlen_l(
   const char *str,
   size_t numberOfElements,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
Null 종료 문자열입니다.

*숫자오브엘리먼트*<br/>
문자열 버퍼의 크기입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

이러한 함수는 null 종결 문자를 제외하고 문자열에 있는 문자의 수를 반환합니다. 첫 번째 번호 내에 null 종단기가 없는 *경우OfElements* 문자열의 바이트(또는 **wcsnlen의**넓은 문자)가 *반환되어* 오류 조건을 나타냅니다. null-terminated 문자열에는 *numberOfElements*보다 엄격하게 적은 길이가 있습니다.

**문자열에** 잘못된 다중 바이트 문자가 포함된 경우 _mbstrnlen **_mbstrnlen_l** 반환 -1입니다.

## <a name="remarks"></a>설명

> [!NOTE]
> **스트렌은** **스트렌을**대체하지 않습니다. **strnlen은** 네트워크 패킷과 같은 알려진 크기의 버퍼에서 수신되지 않은 데이터의 크기를 계산하는 데만 사용됩니다. **strnlen은** 길이를 계산하지만 문자열이 종료되지 않은 경우 버퍼의 끝을 지나가지 않습니다. 다른 상황에서는 **strlen**. **(wcsnlen,** **_mbsnlen**및 **_mbstrnlen**마찬가지입니다.)

이러한 각 함수는 null 문자 종료를 포함하지 않고 *str의*문자 수를 반환합니다. 그러나 **strnlen** 및 **strnlen_s** 문자열을 단일 바이트 문자열로 해석하므로 반환 값은 문자열에 다바이트 문자가 포함되어 있더라도 항상 바이트 수와 같습니다. **wcsnlen과** **wcsnlen_s** 각각 **스트렌렌과** **strnlen_s** 와이드 문자 버전입니다. **wcsnlen** 및 **wcsnlen_s** 대한 인수는 와이드 문자 문자열이며 문자 수는 와이드 문자 단위입니다. 그렇지 **않으면, wcsnlen** 및 **strnlen은** **strnlen_s** **wcsnlen_s**마찬가지로 동일하게 행동합니다.

**strnlen**, **wcsnlen**및 **_mbsnlen** 매개 변수의 유효성을 검사하지 않습니다. *str이* **NULL인**경우 액세스 위반이 발생합니다.

**strnlen_s** **wcsnlen_s** 매개 변수의 유효성을 검사합니다. *str이* **NULL이면**함수는 0을 반환합니다.

**_mbstrnlen** 매개 변수도 확인합니다. *str이* **NULL이거나** *numberOfElements가* **INT_MAX**큰 경우 **_mbstrnlen** 매개 변수 [유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 예외를 생성합니다. 실행을 계속할 수 있는 경우 **_mbstrnlen** **errno를** **EINVAL로** 설정하고 -1을 반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnlen**|**strnlen**|**strnlen**|**wcsnlen**|
|**_tcscnlen**|**strnlen**|**_mbsnlen**|**wcsnlen**|
|**_tcscnlen_l**|**strnlen**|**_mbsnlen_l**|**wcsnlen**|

**_mbsnlen _mbstrnlen** 다중 바이트 문자 문자열에서 다중 바이트 문자 의 수를 **반환합니다.** **_mbsnlen** 현재 사용 중인 다중바이트 코드 페이지 또는 전달되는 로캘에 따라 다중 바이트 문자 시퀀스를 인식합니다. 다중 바이트 문자 유효성을 테스트하지 않습니다. **_mbstrnlen** 멀티바이트 문자 유효성에 대한 테스트를 하고 다중 바이트 문자 시퀀스를 인식합니다. **_mbstrnlen** 전달된 문자열에 잘못된 다중 바이트 문자가 포함된 경우 **errno는** **EILSEQ로**설정됩니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정설정의 영향을 받습니다. 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md) 를 참조하십시오. 이러한 함수의 버전은 _l 접미사가 없는 함수가 이 **_l** 로캘 종속 동작에 대해 현재 로캘을 사용하고 **_l** 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**스트렌렌**, **strnlen_s**|\<string.h>|
|**wcsnlen**, **wcsnlen_s**|\<string.h> 또는 \<wchar.h>|
|**_mbsnlen**, **_mbsnlen_l**|\<mbstring.h>|
|**_mbstrnlen**, **_mbstrnlen_l**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strnlen.c

#include <string.h>

int main()
{
   // str1 is 82 characters long. str2 is 159 characters long

   char* str1 = "The length of a string is the number of characters\n"
               "excluding the terminating null.";
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"
                "than the maximum size specified, the maximum size is\n"
                "returned rather than the actual size of the string.";
   size_t len;
   size_t maxsize = 100;

   len = strnlen(str1, maxsize);
   printf("%s\n Length: %d \n\n", str1, len);

   len = strnlen(str2, maxsize);
   printf("%s\n Length: %d \n", str2, len);
}
```

```Output
The length of a string is the number of characters
excluding the terminating null.
Length: 82

strnlen takes a maximum size. If the string is longer
than the maximum size specified, the maximum size is
returned rather than the actual size of the string.
Length: 100
```

## <a name="see-also"></a>참고 항목

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[스트콜 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
