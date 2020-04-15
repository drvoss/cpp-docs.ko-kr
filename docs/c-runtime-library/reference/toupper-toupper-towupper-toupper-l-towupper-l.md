---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l
ms.date: 4/2/2020
api_name:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
- _o__toupper
- _o__toupper_l
- _o__towupper_l
- _o_toupper
- _o_towupper
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- towupper
- _toupper
- _totupper
- toupper
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
ms.openlocfilehash: 85c218fdb3f5153e572e434bffbdb64510554d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362317"
---
# <a name="toupper-_toupper-towupper-_toupper_l-_towupper_l"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l

문자를 대문자로 변환합니다.

## <a name="syntax"></a>구문

```C
int toupper(
   int c
);
int _toupper(
   int c
);
int towupper(
   wint_t c
);
int _toupper_l(
   int c ,
   _locale_t locale
);
int _towupper_l(
   wint_t c ,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*C*<br/>
변환할 문자입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

이러한 각 루틴은 가능하면 *c의*복사본을 변환하고 결과를 반환합니다.

*c가* **iswlower가** 영하지 않은 와이드 문자이고 [iswupper가](isupper-isupper-l-iswupper-iswupper-l.md) 영하지 않은 해당 와이드 문자가 있는 경우 **towupper는** 해당 와이드 문자를 반환합니다. 그렇지 않으면 **towupper는** 변경되지 않은 *c를* 반환합니다.

오류를 나타내기 위해 예약된 반환 값은 없습니다.

**토퍼가** 예상된 결과를 제공하기 위해서는 [__isascii](isascii-isascii-iswascii.md) 더 [낮게](islower-iswlower-islower-l-iswlower-l.md) 비영을 반환해야 합니다.

## <a name="remarks"></a>설명

이러한 각 루틴은 가능하며 적절한 경우 지정된 소문자를 대문자로 변환합니다. **토우어의** 대/소문자 변환은 로캘에 따라 다릅니다. 현재 로캘에서 유효한 문자의 대/소문자만 변경됩니다. **_l** 접미사가 없는 함수는 현재 설정된 로캘을 사용합니다. **_l** 접미사가 있는 이러한 함수의 버전은 로캘을 매개 변수로 사용하고 현재 설정된 로캘 대신 해당 함수를 사용합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

예상 된 결과를 제공하기 위해 **토퍼를** [위해, __isascii](isascii-isascii-iswascii.md) 및 [isupper](isupper-isupper-l-iswupper-iswupper-l.md) 모두 비 제로를 반환해야합니다.

[데이터 변환 루틴](../../c-runtime-library/data-conversion.md)

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**Toupper**|**_mbctoupper**|**towupper**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l** **_towupper_l** 로캘 에 대한 종속성은 없으며 직접 호출할 수 없습니다. _totupper_l 내부 용으로 **제공됩니다.**

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**Toupper**|\<ctype.h>|
|**_toupper**|\<ctype.h>|
|**towupper**|\<ctype.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[to 함수](../../c-runtime-library/to-functions.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
[to 함수](../../c-runtime-library/to-functions.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
