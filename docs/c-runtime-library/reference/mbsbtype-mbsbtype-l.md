---
title: _mbsbtype, _mbsbtype_l
ms.date: 4/2/2020
api_name:
- _mbsbtype_l
- _mbsbtype
- _o__mbsbtype
- _o__mbsbtype_l
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
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
ms.openlocfilehash: d71a061d9af5028c9bc6b4008f9904606a233592
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340868"
---
# <a name="_mbsbtype-_mbsbtype_l"></a>_mbsbtype, _mbsbtype_l

문자열 내에서 바이트의 형식을 반환합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _mbsbtype(
   const unsigned char *mbstr,
   size_t count
);
int _mbsbtype_l(
   const unsigned char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*mbstr*<br/>
멀티바이트 문자 시퀀스의 주소입니다.

*count*<br/>
문자열의 헤드로부터의 바이트 오프셋입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**_mbsbtype** 및 **_mbsbtype_l** 지정된 바이트에서 테스트 결과를 나타내는 정수 값을 반환합니다. 다음 표의 매니페스트 상수는 Mbctype.h에 정의됩니다.

|반환 값|바이트 형식|
|------------------|---------------|
|**_MBC_SINGLE** (0)|싱글바이트 문자입니다. 예를 들어 코드 페이지 932에서 지정된 바이트가 0x20 - 0x7E 또는 0xA1 - 0xDF 내에 있는 경우 **_mbsbtype** 0을 반환합니다.|
|**_MBC_LEAD** (1)|멀티바이트 문자의 선행 바이트입니다. 예를 들어 코드 페이지 932에서 지정된 바이트가 0x81 - 0x9F 또는 0xE0 - 0xFC 범위 내에 있는 경우 **_mbsbtype** 1을 반환합니다.|
|**_MBC_TRAIL** (2)|멀티바이트 문자의 후행 바이트입니다. 예를 들어 코드 페이지 932에서 지정된 바이트가 0x40 - 0x7E 또는 0x80 - 0xFC 범위 내에 있는 경우 **_mbsbtype** 2를 반환합니다.|
|**_MBC_ILLEGAL** (-1)|**NULL** 문자열, 잘못된 문자 또는 *mbstr의*오프셋 *카운트에서* 바이트 앞에 있는 null 바이트 .|

## <a name="remarks"></a>설명

**_mbsbtype** 함수는 다중 바이트 문자열의 바이트 유형을 결정합니다. 함수는 *mbstr에서*오프셋 *카운트의* 바이트만 검사하며 지정된 바이트 전에 잘못된 문자를 무시합니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정에 따른 영향을 받습니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요. **_l** 접미사가 없는 이 함수 버전은 이 로캘 종속 동작에 대해 현재 로캘을 사용합니다. **_l** 접미사가 있는 버전은 대신 전달된 로캘 매개 변수를 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

입력 문자열이 **NULL인**경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 **errno가** **EINVAL로** 설정되고 함수가 **_MBC_ILLEGAL**반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* 매니페스트 상수에 대해 반환 값으로 사용됩니다.

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[바이트 분류](../../c-runtime-library/byte-classification.md)<br/>
