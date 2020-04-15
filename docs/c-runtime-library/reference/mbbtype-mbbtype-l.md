---
title: _mbbtype, _mbbtype_l
ms.date: 4/2/2020
api_name:
- _mbbtype
- _mbbtype_l
- _o__mbbtype
- _o__mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
ms.openlocfilehash: 7e2e818ed70ec393e4f81008f76ca9efe9cfa7e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341406"
---
# <a name="_mbbtype-_mbbtype_l"></a>_mbbtype, _mbbtype_l

이전 바이트에 따라 바이트 형식을 반환합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _mbbtype(
   unsigned char c,
   int type
);
int _mbbtype_l(
   unsigned char c,
   int type,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*C*<br/>
테스트할 문자입니다.

*종류*<br/>
테스트할 바이트의 형식입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**_mbbtype** 문자열에서 바이트 형식을 반환합니다. 이 결정은 컨트롤 테스트 조건을 제공하는 *형식*의 값에 의해 지정된 컨텍스트에 따라 다가능합니다. *형식은* 문자열의 이전 바이트 의 형식입니다. 다음 표의 매니페스트 상수는 Mbctype.h에 정의됩니다.

|*형식* 값|**_mbbtype** 테스트|반환 값|*C*|
|---------------------|--------------------------|------------------|---------|
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|**_MBC_SINGLE** (0)|단일 바이트(0x20 - 0x7E, 0xA1 - 0xDF)|
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|**_MBC_LEAD** (1)|멀티바이트 문자의 리드 바이트(0x81 - 0x9F, 0xE0 - 0xFC)|
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|**_MBC_ILLEGAL**<br /><br /> ( -1)|유효하지 않은 문자(0x20 - 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC를 제외한 모든 값|
|1|유효한 후행 바이트|**_MBC_TRAIL** (2)|다바이트 문자의 후행 바이트(0x40 - 0x7E, 0x80 - 0xFC)|
|1|유효한 후행 바이트|**_MBC_ILLEGAL**<br /><br /> ( -1)|유효하지 않은 문자(0x20 - 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC를 제외한 모든 값|

## <a name="remarks"></a>설명

**_mbbtype** 함수는 다바이트 문자의 바이트 유형을 결정합니다. *형식* 값이 1을 제외한 모든 값인 경우 _mbbtype 다바이트 문자의 유효한 단일 바이트 또는 리드 바이트에 대한 **테스트를** 합니다. *형식* 값이 1이면 **_mbbtype** 다중 바이트 문자의 유효한 추적 바이트에 대한 테스트를 합니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정설정의 영향을 받습니다. 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md) 를 참조하십시오. 이 함수의 **_mbbtype** 버전은 이 로캘 종속 동작에 대해 현재 로캘을 사용합니다. **_mbbtype_l** 버전은 대신 전달되는 로캘 매개 변수를 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

이전 버전에서는 **_mbbtype** **chkctype.** 새 코드의 경우 **대신 _mbbtype** 사용합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* 반환 값으로 사용되는 매니페스트 상수의 정의에 해당합니다.

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[바이트 분류](../../c-runtime-library/byte-classification.md)<br/>
