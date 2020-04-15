---
title: isupper, _isupper_l, iswupper, _iswupper_l
ms.date: 4/2/2020
api_name:
- isupper
- iswupper
- _iswupper_l
- _isupper_l
- _o_isupper
- _o_iswupper
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
- isupper
- _istupper
- iswupper
helpviewer_keywords:
- istupper function
- iswupper function
- isupper_l function
- _isupper_l function
- iswupper_l function
- _istupper function
- _iswupper_l function
- isupper function
ms.assetid: da2bcc9f-241c-48c0-9a0e-ad273827e16a
ms.openlocfilehash: 713689649b33873796b7a73bad6a4ac6e8acc998
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342795"
---
# <a name="isupper-_isupper_l-iswupper-_iswupper_l"></a>isupper, _isupper_l, iswupper, _iswupper_l

정수가 대문자를 나타내는지 여부를 확인합니다.

## <a name="syntax"></a>구문

```C
int isupper(
   int c
);
int _isupper_l (
   int c,
   _locale_t locale
);
int iswupper(
   wint_t c
);
int _iwsupper_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*C*<br/>
테스트할 정수입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

*c가* 대문자의 특정 표현인 경우 이러한 각 루틴은 0이 아닌 것을 반환합니다. **isupper는** *c가* 대문자(A - Z)인 경우 비영도 값을 반환합니다. **iswupper는** *c가* 대문자에 해당하는 넓은 문자이거나 *c가* **iswcntrl,** **iswdigit,** **iswpunct,** 또는 **iswunct 또는 iswunct** 가 아닌 와이드 문자의 구현 정의 집합 중 하나인 경우 비영도 값을 반환합니다. *c가* 테스트 조건을 충족하지 않는 경우 이러한 각 루틴은 0을 반환합니다.

**_l** 접미사가 있는 이러한 함수의 버전은 로캘 에 종속된 동작에 대해 현재 로캘 대신 전달된 로캘을 사용합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

**isupper** 및 **_isupper_l** 동작은 *c가* EOF가 아니거나 0에서 0xFF 범위(포함)가 아닌 경우 정의되지 않습니다. 디버그 CRT 라이브러리가 사용되고 *c가* 이러한 값 중 하나가 아닌 경우 함수는 어설션을 발생시게 됩니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istupper**|**isupper**|[_ismbcupper](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**이스워퍼**|
|**_istupper_l**|**_isupper_l**|[_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**_iswupper_l**|

## <a name="remarks"></a>설명

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**isupper**|\<ctype.h>|
|**_isupper_l**|\<ctype.h>|
|**이스워퍼**|\<ctype.h> 또는 \<wchar.h>|
|**_iswupper_l**|\<ctype.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
