---
title: isalpha, iswalpha, _isalpha_l, _iswalpha_l
ms.date: 4/2/2020
api_name:
- iswalpha
- _iswalpha_l
- isalpha
- _isalpha_l
- _o_isalpha
- _o_iswalpha
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
- _istalpha
- _ismbcalpha_l
- isalpha
- _isalpha_l
- iswalpha
- _istalpha_l
- _iswalpha_l
helpviewer_keywords:
- _iswalpha_l function
- _isalpha_l function
- _ismbcalpha_l function
- _istalpha_l function
- _ismbcalpha function
- isalpha function
- iswalpha function
- istalpha function
- _istalpha function
ms.assetid: ed6cc2be-c4b0-4475-87ac-bc06d8c23064
ms.openlocfilehash: 187031adc0b22aff2c5418cd7e0f3e64075f1745
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343925"
---
# <a name="isalpha-iswalpha-_isalpha_l-_iswalpha_l"></a>isalpha, iswalpha, _isalpha_l, _iswalpha_l

정수가 영문자를 나타내는지 여부를 확인합니다.

## <a name="syntax"></a>구문

```C
int isalpha(
   int c
);
int iswalpha(
   wint_t c
);
int _isalpha_l(
   int c,
   _locale_t locale
);
int _iswalpha_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*C*<br/>
테스트할 정수입니다.

*로캘*<br/>
현재 로캘 대신 사용할 로캘입니다.

## <a name="return-value"></a>Return Value

*c가* 알파벳 문자의 특정 표현인 경우 이러한 각 루틴은 0이 아닌 것을 반환합니다. **isalpha는** *c가* A - Z 또는 - z 범위 내에 있는 경우 비영도 값을 반환합니다. **iswalpha는** [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) 또는 **iswlower가** 영하가 아닌 와이드 문자에 대해서만 비영값을 반환합니다. 즉, **iswcntrl,** **iswdigit**, **iswunct,** 또는 **iswspace가** 영하지 않은 구현 정의 집합 중 하나인 와이드 문자에 대해 의미합니다. *c가* 테스트 조건을 충족하지 않는 경우 이러한 각 루틴은 0을 반환합니다.

**_l** 접미사가 있는 이러한 함수의 버전은 현재 로캘 대신 전달되는 로캘 매개 변수를 사용합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

**isalpha** 및 **_isalpha_l** 동작은 *c가* EOF가 아니거나 0에서 0xFF 범위(포함)가 아닌 경우 정의되지 않습니다. 디버그 CRT 라이브러리가 사용되고 *c가* 이러한 값 중 하나가 아닌 경우 함수는 어설션을 발생시게 됩니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istalpha**|**isalpha**|**_ismbcalpha**|**iswalpha**|
|**_istalpha_l**|**_isalpha_l**|**_ismbcalpha_l**|**_iswalpha_l**|

## <a name="remarks"></a>설명

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**isalpha**|\<ctype.h>|
|**iswalpha**|\<ctype.h> 또는 \<wchar.h>|
|**_isalpha_l**|\<ctype.h>|
|**_iswalpha_l**|\<ctype.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
