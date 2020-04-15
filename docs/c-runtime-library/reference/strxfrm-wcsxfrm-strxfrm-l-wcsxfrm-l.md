---
title: strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
ms.date: 4/2/2020
api_name:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
- _o__strxfrm_l
- _o__wcsxfrm_l
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strxfrm
- _tcsxfrm
- wcsxfrm
helpviewer_keywords:
- strxfrm_l function
- _tcsxfrm function
- _strxfrm_l function
- strxfrm function
- wcsxfrm_l function
- wcsxfrm function
- string comparison [C++], transforming strings
- tcsxfrm function
- strings [C++], comparing locale
- _wcsxfrm_l function
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
ms.openlocfilehash: aabe7e7c2e44f558b936e0fd4c6fa4a85dc582f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362965"
---
# <a name="strxfrm-wcsxfrm-_strxfrm_l-_wcsxfrm_l"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l

로캘별 정보를 기반으로 문자열을 변형합니다.

## <a name="syntax"></a>구문

```C
size_t strxfrm(
   char *strDest,
   const char *strSource,
   size_t count
);
size_t wcsxfrm(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count
);
size_t _strxfrm_l(
   char *strDest,
   const char *strSource,
   size_t count,
   _locale_t locale
);
size_t wcsxfrm_l(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*스트레스트*<br/>
대상 문자열입니다.

*스트소스 (것)스*<br/>
원본 문자열입니다.

*count*<br/>
*스트레스트에*배치할 최대 문자 수입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

종료 null 문자를 세지 않고 변형된 문자열의 길이를 반환합니다. 반환 값이 *개수보다*크거나 같으면 *strDest의* 내용을 예측할 수 없습니다. 오류가 발생하면 각 함수는 **errno를** 설정하고 **INT_MAX**반환합니다. 잘못된 문자의 경우 **errno가** **EILSEQ로**설정됩니다.

## <a name="remarks"></a>설명

**strxfrm** 함수는 *strSource가* 가리키는 문자열을 *strDest에*저장된 새 대조 된 형식으로 변환합니다. null 문자를 포함한 *카운트* 문자는 변환되어 결과 문자열에 배치되지 않습니다. 변환은 로캘의 **LC_COLLATE** 범주 설정을 사용하여 이루어집니다. **LC_COLLATE**대한 자세한 내용은 [setlocale](setlocale-wsetlocale.md)를 참조하십시오. **strxfrm은** 현재 로캘을 로캘 종속 동작에 사용합니다. **_strxfrm_l** 현재 로캘 대신에 전달된 로캘을 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

변환 후 변환된 두 문자열을 사용하여 **strcmp를** 호출하면 원래 두 문자열에 적용된 **strcoll** 호출과 동일한 결과가 생성됩니다. **strcoll** 및 **stricoll과**마찬가지로 **strxfrm은** 자동으로 다중 바이트 문자 문자열을 적절하게 처리합니다.

**wcsxfrm은** **strxfrm의**넓은 문자 버전입니다. **wcsxfrm의** 문자열 인수는 와이드 문자 포인터입니다. **wcsxfrm의**경우 문자열 변환 후 두 개의 변환된 문자열을 사용하여 **wcscmp를** 호출하면 원래 두 문자열에 적용된 **wcscoll** 호출과 동일한 결과가 생성됩니다. **wcsxfrm** 및 **strxfrm은** 달리 동일하게 작동합니다. **wcsxfrm은** 로캘 종속 동작에 대해 현재 로캘을 사용합니다. **_wcsxfrm_l** 현재 로캘 대신 전달된 로캘을 사용합니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. *strSource가* null 포인터이거나 *strDest가* **NULL** 포인터인 경우(수가 0이 아닌 경우), *개수가* **INT_MAX**큰 경우 매개 [변수 유효성 검사에](../../c-runtime-library/parameter-validation.md) 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 이러한 함수는 **errno를** **EINVAL로** 설정하고 **INT_MAX**반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

"C" 로캘에서 문자 집합(ASCII 문자 집합)의 순서는 사전적 문자 순서와 같습니다. 그러나 다른 로캘에서 문자 집합의 문자 순서는 사전적 문자 순서와 다를 수 있습니다. 예를 들어 특정 유럽 로캘의 문자 집합에서 문자 'a'(값 0x61)는 문자 '&\#x00E4;'(값 0xE4) 앞에 오지만 사전적으로는 문자 'ä'가 'a' 앞에 옵니다.

문자 집합과 사전 문자 순서가 다른 로캘에서는 원래 문자열에 **strxfrm을** 사용한 다음 결과 문자열에 **strcmp를** 사용하여 현재 로캘의 **LC_COLLATE** 범주 설정에 따라 사전 그래픽 문자열 비교를 생성합니다. 따라서 위의 로캘에서 두 문자열을 사전문자로 비교하려면 원래 문자열에 **strxfrm을** 사용한 다음 결과 문자열에 **strcmp를** 사용합니다. 또는 원래 문자열에서 **strcmp** 대신 **strcoll을** 사용할 수 있습니다.

**strxfrm은** 기본적으로 **LCMAP_SORTKEY** [LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw) 주위래퍼입니다.

다음 식의 값은 소스 문자열의 **strxfrm** 변환을 보유하는 데 필요한 배열의 크기입니다.

`1 + strxfrm( NULL, string, 0 )`

"C" 로캘에서만 **strxfrm은** 다음과 같습니다.

```C
strncpy( _string1, _string2, _count );
return( strlen( _string1 ) );
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strxfrm**|\<string.h>|
|**wcsxfrm**|\<string.h> 또는 \<wchar.h>|
|**_strxfrm_l**|\<string.h>|
|**_wcsxfrm_l**|\<string.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[스트콜 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
