---
title: _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l
ms.date: 4/2/2020
api_name:
- _ismbcalpha
- _ismbcalnum
- _ismbcdigit
- _ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha_l
- _o__ismbcalnum
- _o__ismbcalnum_l
- _o__ismbcalpha
- _o__ismbcalpha_l
- _o__ismbcdigit
- _o__ismbcdigit_l
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
- _ismbcdigit
- ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha
- ismbcalnum
- ismbcdigit
- ismbcalpha
- _ismbcalnum_l
- _ismbcalnum
- ismbcdigit_l
helpviewer_keywords:
- ismbcalpha function
- _ismbcalnum function
- ismbcdigit_l function
- _ismbcalnum_l function
- _ismbcdigit function
- ismbcalnum function
- _ismbcalpha_l function
- ismbcdigit function
- _ismbcalpha function
- _ismbcdigit_l function
- ismbcalnum_l function
- ismbcalpha_l function
ms.assetid: 12d57925-aebe-46e0-80b0-82b84c4c31ec
ms.openlocfilehash: 828c8b68855197f0c17202739f98a45e0abb929c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343300"
---
# <a name="_ismbcalnum-_ismbcalnum_l-_ismbcalpha-_ismbcalpha_l-_ismbcdigit-_ismbcdigit_l"></a>_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l

멀티바이트 문자가 영숫자, 영문자 또는 숫자인지 검사합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _ismbcalnum
(
   unsigned int c
);
int _ismbcalnum_l
(
   unsigned int c,
   _locale_t locale
);
int _ismbcalpha
(
   unsigned int c
);
int _ismbcalpha_l
(
   unsigned int c,
   _locale_t locale
);
int _ismbcdigit
(
   unsigned int c
);
int _ismbcdigit_l
(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*C*<br/>
테스트할 문자입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

이러한 각 루틴은 이 문자가 테스트 조건을 만족하는 경우 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다. *c*<= 255이고 해당 **_ismbb** 루틴이 있는 경우(예: **_ismbcalnum** **_ismbbalnum**해당 _ismbb **루틴의** 반환 값입니다.

## <a name="remarks"></a>설명

이러한 각 루틴은 지정된 멀티바이트 문자를 지정된 조건에 대해 테스트합니다.

**_l** 접미사가 있는 이러한 함수의 버전은 로캘 종속 동작에 대해 현재 로캘 대신 전달된 로캘을 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

|루틴에서 반환된 값|테스트 조건|932 코드 페이지 예제|
|-------------|--------------------|---------------------------|
|**_ismbcalnum**, **_ismbcalnum_l**|영숫자|*c가* ASCII 영어 문자의 단일 바이트 표현인 경우에만 비영도 반환: **_ismbcdigit** 및 **_ismbcalpha**예제 를 참조하십시오.|
|**_ismbcalpha**, **_ismbcalpha_l**|사전순|*c가* ASCII 영어 문자의 단일 바이트 표현인 경우에만 비영도 반환: 0x41<=*c*<=0x5A 또는 0x61<=*c*<=0x7A; 또는 카타카나 문자: 0xA6<=*c*<=0xDF.|
|**_ismbcdigit,** **_ismbcdigit**|숫자|*c가* ASCII 자릿수의 단일 바이트 표현인 경우에만 0이 아닌 경우: 0x30<=*c*<=0x39를 반환합니다.|

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_ismbcalnum**, **_ismbcalnum_l**|\<mbstring.h>|
|**_ismbcalpha**, **_ismbcalpha_l**|\<mbstring.h>|
|**_ismbcdigit**, **_ismbcdigit_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[_ismbc 루틴](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)<br/>
