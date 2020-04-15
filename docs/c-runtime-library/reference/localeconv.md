---
title: localeconv
ms.date: 4/2/2020
api_name:
- localeconv
- _o_localeconv
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- localeconv
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
ms.openlocfilehash: a617980d60b3a12c06b30aab6cd457792a1aa770
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342151"
---
# <a name="localeconv"></a>localeconv

로캘 설정에 대한 자세한 정보를 가져옵니다.

## <a name="syntax"></a>구문

```C
struct lconv *localeconv( void );
```

## <a name="return-value"></a>Return Value

**localeconv** 형식 [구조체 lconv의](../../c-runtime-library/standard-types.md)채워진 개체에 대 한 포인터를 반환 합니다. 개체에 포함된 값은 스레드 로컬 저장소의 로캘 설정에서 복사되며 **localeconv에**대한 후속 호출로 덮어쓸 수 있습니다. 이 개체의 값을 변경하면 로캘 설정이 수정되지 않습니다. **LC_ALL,** **LC_MONETARY**의 *범주* 값을 사용하여 [setlocale를](setlocale-wsetlocale.md) 호출하거나 구조의 내용을 덮어 쓸 **LC_NUMERIC.**

## <a name="remarks"></a>설명

**localeconv** 함수는 현재 로캘에 대한 숫자 서식에 대한 자세한 정보를 가져옵니다. 이 정보는 **lconv** 형식의 구조체에 저장됩니다. LOCALE.H에 저장된 **lconv** 구조체에는 다음 멤버가 포함됩니다.

|필드|의미|
|-|-|
decimal_point,<br/>_W_decimal_point|비금전적 수량에 대한 소수점 문자에 대한 포인터입니다.
thousands_sep,<br/>_W_thousands_sep|숫자 그룹을 비금전적 수량에 대한 소수점 의 왼쪽으로 구분하는 문자에 대한 포인터입니다.
그룹화|비금전적 수량의 각 숫자 그룹의 크기를 포함하는 **char-size**정수에 대한 포인터입니다.
int_curr_symbol,<br/>_W_int_curr_symbol|현재 로캘에 대한 국제 통화 기호에 대한 포인터입니다. 처음 세 문자는 *ISO 4217 Codes for the Representation of Currency and Funds* 표준에 정의된 대로 영문자 국제 통화 기호를 지정합니다. 네 번째 문자(null 문자 바로 앞)는 통화 수량에서 국제 통화 기호를 구분합니다.
currency_symbol,<br/>_W_currency_symbol|현재 로캘에 대한 현지 통화 기호에 대한 포인터입니다.
mon_decimal_point,<br/>_W_mon_decimal_point|금전적 수량에 대한 소수점 문자에 대한 포인터입니다.
mon_thousands_sep,<br/>_W_mon_thousands_sep|화폐 수량에서 소수점 자리의 왼쪽에 숫자 그룹에 대한 구분 기호에 대한 포인터.
mon_grouping|금전적 수량의 각 숫자 그룹의 크기를 포함하는 **char-size**정수에 대한 포인터입니다.
positive_sign,<br/>_W_positive_sign|음수가 아닌 통화 수량에 대한 부호를 나타내는 문자열입니다.
negative_sign,<br/>_W_negative_sign|음수 통화 수량에 대한 부호를 나타내는 문자열입니다.
int_frac_digits|국제적으로 서식이 지정된 통화 수량에서 소수점 오른쪽의 자릿수입니다.
frac_digits|서식이 지정된 통화 수량에서 소수점 오른쪽의 자릿수입니다.
p_cs_precedes|통화 기호가 음수가 아닌 서식이 지정된 통화 수량에 대한 값보다 앞에 오면 1로 설정합니다. 기호가 값 다음에 오면 0으로 설정합니다.
p_sep_by_space|통화 기호가 음수가 아닌 서식이 지정된 통화 수량에 대한 값에서 공백으로 구분되면 1로 설정합니다. 공백으로 구분되지 않으면 0으로 설정합니다.
n_cs_precedes|통화 기호가 음수 서식이 지정된 통화 수량에 대한 값보다 앞에 오면 1로 설정합니다. 기호가 값 다음에 오면 0으로 설정합니다.
n_sep_by_space|통화 기호가 음수 서식이 지정된 통화 수량에 대한 값에서 공백으로 구분되면 1로 설정합니다. 공백으로 구분되지 않으면 0으로 설정합니다.
p_sign_posn|음수가 아닌 서식이 지정된 통화 수량에서 양수 부호의 위치입니다.
n_sign_posn|음수 서식이 지정된 통화 수량에서 양수 부호의 위치입니다.

지정된 경우를 제외하고, 버전이 있는 `char *` `wchar_t *` **lconv** 구조의 멤버는 문자열에 대한 포인터입니다. <strong>\*</strong> **wchar_t** 대해 **""(또는** **L")과** 같은 것은 길이가 0이거나 현재 로캘에서 지원되지 않습니다. **decimal_point** 및 **_W_decimal_point** 항상 지원되며 0이 아닌 길이입니다.

구조의 **char** 멤버는 문자가 아닌 작은 비음수입니다. **CHAR_MAX**와 동일한 이러한 멤버는 현재 로캘에서 지원되지 않습니다.

**그룹화** 및 **mon_grouping** 값은 다음 규칙에 따라 해석됩니다.

- **CHAR_MAX** - 더 이상 그룹화하지 마십시오.

- 0 - 남은 각 숫자에 대해 이전 요소를 사용합니다.

- *n* - 현재 그룹을 구성하는 숫자 수입니다. 다음 요소를 검사하여 현재 그룹 앞 다음 숫자 그룹의 크기를 확인합니다.

**int_curr_symbol**에 대한 값은 다음 규칙에 따라 해석됩니다.

- 처음 세 문자는 *ISO 4217 Codes for the Representation of Currency and Funds* 표준에 정의된 대로 영문자 국제 통화 기호를 지정합니다.

- 네 번째 문자(null 문자 바로 앞)는 통화 수량에서 국제 통화 기호를 구분합니다.

**p_cs_precedes** 및 **n_cs_precedes**에 대한 값은 다음 규칙에 따라 해석됩니다. **n_cs_precedes** 규칙은 괄호 안에 표시됩니다.

- 0 - 통화 기호는 음수(음수) 형식의 통화 값에 대한 값을 따릅니다.

- 1 - 통화 기호는 음수(음수) 형식의 통화 값 앞에 옵니다.

**p_sep_by_space** 및 **n_sep_by_space**에 대한 값은 다음 규칙에 따라 해석됩니다. **n_sep_by_space** 규칙은 괄호 안에 표시됩니다.

- 0 - 통화 기호는 음수(음수) 형식의 화폐 값에 대한 공간별로 값과 분리됩니다.

- 1 - 비음수(음수) 형식의 화폐 값에 대해 통화 기호와 값 사이에 공백이 없습니다.

**p_sign_posn** 및 **n_sign_posn**에 대한 값은 다음 규칙에 따라 해석됩니다.

- 0 - 괄호는 수량 및 통화 기호를 둘러싸는 것입니다.

- 1 - 기호 문자열 앞에 수량 및 통화 기호가 앞에 옵니다.

- 2 - 기호 문자열은 수량 및 통화 기호를 따릅니다.

- 3 - 기호 문자열바로 앞에 통화 기호 앞에 옵니다.

- 4 - 서명 문자열은 즉시 통화 기호를 따릅니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**localeconv**|\<locale.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고 항목

[로캘](../../c-runtime-library/locale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[스트콜 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
