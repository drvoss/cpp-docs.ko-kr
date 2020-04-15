---
title: mbrtoc16, mbrtoc323
ms.date: 4/2/2020
api_name:
- mbrtoc16
- mbrtoc32
- _o_mbrtoc16
- _o_mbrtoc32
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
ms.openlocfilehash: 91755d19eacf73f19700eed7fffbffc529d4e235
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340975"
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32

문자열의 첫 번째 UTF-8 multibyte 문자를 동등한 UTF-16 또는 UTF-32 문자로 변환합니다.

## <a name="syntax"></a>구문

```C
size_t mbrtoc16(
   char16_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);

size_t mbrtoc32(
   char32_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);
```

### <a name="parameters"></a>매개 변수

*대상*\
변환할 **char16_t** UTF-8 multibyte 문자와 **char32_t** char16_t 또는 이에 해당하는 포인터입니다. null이면 함수는 값을 저장하지 않습니다.

*소스*\
변환할 UTF-8 multibyte 문자 문자열에 대한 포인터입니다.

*max_bytes*\
변환할 문자를 검사할 *소스의* 최대 바이트 수입니다. 이 인수는 *원본에*남아 있는 null 터미네이터를 포함하여 1바이트와 바이트 수 사이의 값이어야 합니다.

*상태*\
UTF-8 multibyte 문자열을 하나 이상의 출력 문자로 해석하는 데 사용되는 **mbstate_t** 변환 상태 개체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

성공시 현재 *상태* 값을 감안할 때 적용되는 이러한 조건 중 첫 번째 값의 값을 반환합니다.

|값|조건|
|-----------|---------------|
|0|*소스에서* 변환된 다음 *max_bytes* 또는 그 이하의 문자는 대상이 null이 *아닌* 경우 저장된 값인 null 와이드 문자에 해당합니다.<br /><br /> *상태는* 초기 시프트 상태를 포함합니다.|
|1에서 *max_bytes*사이 , 포함|반환되는 값은 유효한 다중 바이트 문자를 완료하는 *소스의* 바이트 수입니다. *변환된* 와이드 문자는 대상이 null이 아닌 경우 저장됩니다.|
|-3|*대상이* null이 아닌 경우 함수에 대한 이전 호출로 인해 다음 와이드 문자가 *대상에* 저장되었습니다. 함수에 대한 이 호출에서 *소스의* 바이트가 사용되지 않습니다.<br /><br /> *소스가* 둘 이상의 와이드 문자(예: 서로게이트 쌍)를 나타내야 하는 UTF-8 다중바이트 문자를 가리키면 다음 함수 호출에서 추가 문자를 기록하도록 *상태* 값이 업데이트됩니다.|
|-2|다음 *max_bytes* 바이트는 완전하지만 잠재적으로 유효한 UTF-8 다바이트 문자를 나타냅니다. *값은 대상에*저장되지 않습니다. 이 결과는 *max_bytes* 0이면 발생할 수 있습니다.|
|-1|인코딩 오류가 발생했습니다. 다음 *max_bytes* 바이트 이하는 완전하고 유효한 UTF-8 multibyte 문자에 기여하지 않습니다. *값은 대상에*저장되지 않습니다.<br /><br /> **EILSEQ는** **errno에** 저장되며 변환 상태 값 *상태가* 지정되지 않습니다.|

## <a name="remarks"></a>설명

**mbrtoc16** 함수는 *소스에서* *최대 max_bytes* 바이트를 읽고 첫 번째 완전하고 유효한 UTF-8 multibyte 문자를 찾은 다음 해당 UTF-16 문자를 *대상에*저장합니다. 문자에 서로게이트 쌍과 같은 UTF-16 출력 문자가 두 개 이상 필요한 경우 *상태* 값은 **다음 호출에서 mbrtoc16에** *대한 대상에* 다음 UTF-16 문자를 저장하도록 설정됩니다. **mbrtoc32** 함수는 동일하지만 출력은 UTF-32 문자로 저장됩니다.

*원본이* null인 경우 이러한 함수는 *대상에*대한 NULL 인수, `""` *소스에*대해 **null** 이 긴 문자열(빈 문자열, null-terminated string)을 사용하여 만든 호출과 동일한 max_bytes *반환합니다.* *대상* 및 *max_bytes* 전달된 값은 무시됩니다.

*원본이* null이 아닌 경우 함수는 문자열의 시작 부분에서 시작하여 최대 *max_bytes* 바이트를 검사하여 시프트 시퀀스를 포함하여 다음 UTF-8 multibyte 문자를 완료하는 데 필요한 바이트 수를 결정합니다. 검사된 바이트에 유효하고 완전한 UTF-8 다바이트 문자가 포함된 경우 함수는 문자를 동등한 16비트 또는 32비트 너비의 문자 또는 문자로 변환합니다. *대상이* null이 아닌 경우 함수는 대상에 첫 번째(그리고 가능한 경우에만) 결과 문자를 저장합니다. 추가 출력 문자가 필요한 경우 함수에 대한 후속 호출이 추가 문자를 출력하고 값 -3을 반환하도록 값이 *상태로*설정됩니다. 더 이상 출력 문자가 필요하지 않으면 *상태가* 초기 시프트 상태로 설정됩니다.

UTF-8 이외 문자를 UTF-16 LE 문자로 변환하려면 [mbrtowc,](mbrtowc.md) [mbtowc 또는 _mbtowc_l](mbtowc-mbtowc-l.md) 함수를 사용합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**mbrtoc16**, **mbrtoc32**|\<uchar.h>|\<cuchar>|

호환성에 대한 자세한 내용은 [Compatibility](../compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[데이터 변환](../data-conversion.md)\
[로캘](../locale.md)\
[다중 바이트 문자 시퀀스의 해석](../interpretation-of-multibyte-character-sequences.md)\
[c16rtomb, c32rtomb](c16rtomb-c32rtomb1.md)\
[mbrtowc](mbrtowc.md)\
[mbsrtowcs](mbsrtowcs.md)\
[mbsrtowcs_s](mbsrtowcs-s.md)
