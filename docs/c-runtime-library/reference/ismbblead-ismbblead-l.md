---
title: _ismbblead, _ismbblead_l
description: Microsoft CRT (C 런타임 라이브러리) _ismbblead 및 _ismbblead_l 함수에 대해 설명 합니다.
ms.date: 4/2/2020
api_name:
- _ismbblead_l
- _ismbblead
- _o__ismbblead
- _o__ismbblead_l
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
ms.openlocfilehash: 7680793b71c4535ed75433ac98167e52a39896ba
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918662"
---
# <a name="_ismbblead-_ismbblead_l"></a>_ismbblead, _ismbblead_l

문자를 테스트 하 여 멀티 바이트 문자의 선행 바이트 인지 여부를 확인 합니다.

## <a name="syntax"></a>구문

```C
int _ismbblead(
   unsigned int c
);
int _ismbblead_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*\
테스트할 정수입니다.

*로캘을*\
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

정수 *c* 가 멀티 바이트 문자의 첫 번째 바이트인 경우 0이 아닌 값을 반환 합니다.

## <a name="remarks"></a>설명

멀티바이트 문자는 선행 바이트와 그 뒤에 오는 후행 바이트로 구성됩니다. 선행 바이트는 지정된 문자 집합에 대한 특정 범위에 있는 것으로 구분됩니다. 예를 들어 코드 페이지 932에만 0x81-0x9F 및 0xE0-0xFC의 선행 바이트 범위를 사용할 수 있습니다.

**_ismbblead** 은 로캘 종속 동작에 현재 로캘을 사용 합니다. **_ismbblead_l** 은 전달 된 로캘을 대신 사용 한다는 점을 제외 하 고 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

로캘이 u t f-8 이면 **_ismbblead** 및 **_ismbblead_l** 는 *c* 가 선행 바이트 인지 여부에 관계 없이 항상 0 (false)을 반환 합니다.

**_ismbblead** 및 **_ismbblead_l** 는 Microsoft 전용 이며 표준 C 라이브러리의 일부가 아닙니다. 이식 가능한 코드를 원하는 위치에 사용 하지 않는 것이 좋습니다. 표준 C 호환성의 경우 **mbrlen** 을 대신 사용 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

### <a name="generic-text-routine-mappings"></a>일반 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istlead**|항상 false를 반환합니다.|**_ismbblead**|항상 false를 반환합니다.|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_ismbblead**|\<mbctype.h> 또는 \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbblead_l**|\<mbctype.h> 또는 \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* 테스트 조건에 대한 매니페스트 상수에 해당합니다.

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참조

[바이트 분류](../../c-runtime-library/byte-classification.md)\
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)\
[mbrlen](mbrlen.md)
