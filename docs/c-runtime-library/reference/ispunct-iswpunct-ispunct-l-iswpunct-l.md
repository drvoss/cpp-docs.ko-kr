---
title: ispunct, iswpunct, _ispunct_l, _iswpunct_l
ms.date: 4/2/2020
api_name:
- ispunct
- _iswpunct_l
- iswpunct
- _ispunct_l
- _o_ispunct
- _o_iswpunct
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
- iswpunct
- _istpunct
- ispunct
helpviewer_keywords:
- _istpunct function
- _ispunct_l function
- iswpunct function
- ispunct function
- istpunct function
- ispunct_l function
- _iswpunct_l function
- iswpunct_l function
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
ms.openlocfilehash: 3072f147d2adff2c50304d2d2052947ca32cb060
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342804"
---
# <a name="ispunct-iswpunct-_ispunct_l-_iswpunct_l"></a>ispunct, iswpunct, _ispunct_l, _iswpunct_l

정수가 문장 부호 문자를 나타내는지 여부를 확인합니다.

## <a name="syntax"></a>구문

```C
int ispunct(
   int c
);
int iswpunct(
   wint_t c
);
int _ispunct_l(
   int c,
   _locale_t locale
);
int _iswpunct_l(
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

*c가* 문장 부호 문자의 특정 표현인 경우 이러한 각 루틴은 0이 아닌 것을 반환합니다. **ispunct는** 공백 문자또는 **isalnum이** 아닌 문자가 아닌 인쇄 가능한 문자에 대해 비영값을 반환합니다. **iswpunct는** 공백 이넓은 문자도 아니고 **iswalnum이** 영하지 않은 넓은 문자도 아닌 인쇄 가능한 와이드 문자에 대해 비영값을 반환합니다. *c가* 테스트 조건을 충족하지 않는 경우 이러한 각 루틴은 0을 반환합니다.

**ispunct** 함수에 대한 테스트 조건의 결과는 로캘의 **LC_CTYPE** 범주 설정에 따라 달라집니다. 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md) 를 참조하십시오. **_l** 접미사가 없는 이러한 함수의 버전은 로캘 종속 동작에 대해 현재 로캘을 사용합니다. **_l** 접미사가 있는 버전은 대신 전달된 로캘을 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

**ispunct** 및 **_ispunct_l** 동작은 *c가* EOF가 아니거나 0에서 0xFF 범위(포함)가 아닌 경우 정의되지 않습니다. 디버그 CRT 라이브러리가 사용되고 *c가* 이러한 값 중 하나가 아닌 경우 함수는 어설션을 발생시게 됩니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **이스트푸틀트**|**ispunct**|[_ismbcpunct](ismbcgraph-functions.md)|**iswpunct**|

## <a name="remarks"></a>설명

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**ispunct**|\<ctype.h>|
|**iswpunct**|\<ctype.h> 또는 \<wchar.h>|
|**_ispunct_l**|\<ctype.h>|
|**_iswpunct_l**|\<ctype.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
