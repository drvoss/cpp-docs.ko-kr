---
title: _mbccpy_s, _mbccpy_s_l
ms.date: 4/2/2020
api_name:
- _mbccpy_s
- _mbccpy_s_l
- _o__mbccpy_s
- _o__mbccpy_s_l
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
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
ms.openlocfilehash: 08df395c6978c84b3f53ed0b07ce988afd0249f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341240"
---
# <a name="_mbccpy_s-_mbccpy_s_l"></a>_mbccpy_s, _mbccpy_s_l

한 문자열에서 다른 문자열로 멀티바이트 문자를 복사합니다. 이러한 버전의 [_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t _mbccpy_s(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src
);
errno_t _mbccpy_s_l(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src,
   locale_t locale
);
template <size_t size>
errno_t _mbccpy_s(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src
); // C++ only
template <size_t size>
errno_t _mbccpy_s_l(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src,
   locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*dest*<br/>
복사 대상입니다.

*버프크기인바이트*<br/>
대상 버퍼의 크기입니다.

*p복사*<br/>
복사된 바이트 수로 채워집니다(성공할 경우 1 또는 2). 숫자에 신경 쓰지 않으면 **NULL을** 통과하십시오.

*Src*<br/>
복사할 멀티바이트 문자입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

성공 시 0이고, 실패 시 오류 코드입니다. *src* 또는 *dest가* **NULL이거나** **buffSizeinBytes** 바이트 이상이 *dest에*복사되는 경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 함수는 **EINVAL을** 반환하고 **errno는** **EINVAL로**설정됩니다.

## <a name="remarks"></a>설명

**_mbccpy_s** 함수는 *src에서* *dest까지*하나의 멀티바이트 문자를 복사합니다. *src가* [_ismbblead](ismbblead-ismbblead-l.md)대한 암시적 호출에 의해 결정된 다중 바이트 문자의 리드 바이트를 가리키지 않으면 *src가* 가리키는 단일 바이트가 복사됩니다. *src가* 리드 바이트를 가리키지만 다음 바이트가 0이므로 유효하지 않은 경우 0이 *dest로*복사되고 **errno가** **EILSEQ로**설정되고 함수가 **EILSEQ를**반환합니다.

**_mbccpy_s** null 종결자도 부속하지 않습니다. 그러나 *src가* null 문자를 가리키면 null이 *dest에* 복사됩니다 (이것은 일반 단일 바이트 복사본일 뿐입니다).

*pCopyd의* 값은 복사된 바이트 수로 채워져 있습니다. 연산이 성공할 경우 가능한 값은 1과 2입니다. **NULL이** 전달되면 이 매개 변수는 무시됩니다.

|*Src*|*dest에* 복사|*p복사*|반환 값|
|-----------|----------------------|---------------|------------------|
|비선행 바이트|비선행 바이트|1|0|
|0|0|1|0|
|선행 바이트와 그 뒤의 0이 아닌 값|선행 바이트와 그 뒤의 0이 아닌 값|2|0|
|선행 바이트와 그 뒤의 0|0|1|**EILSEQ**|

두 번째 행은 첫 번째 행의 특수 사례일 뿐입니다. 또한 표는 *버프SizeInBytes가* >= 복사된 것으로*가정합니다.*

**_mbccpy_s** 모든 로캘 종속 동작에 현재 로캘을 사용합니다. **_mbccpy_s_l** **_mbccpy_s_l** 모든 로캘 종속 동작에 전달된 로캘을 사용하는 것을 제외하고는 **_mbccpy_s** 동일합니다.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|매크로 또는 인라인 함수에 매핑됩니다.|**_mbccpy_s**|매크로 또는 인라인 함수에 매핑됩니다.|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring.h>|
|**_mbccpy_s_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
