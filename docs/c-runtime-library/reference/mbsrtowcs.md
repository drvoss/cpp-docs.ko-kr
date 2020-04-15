---
title: mbsrtowcs
ms.date: 4/2/2020
api_name:
- mbsrtowcs
- _o_mbsrtowcs
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
- mbsrtowcs
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
ms.openlocfilehash: 509046e1c55d89cd78b09076838983691423a1ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338888"
---
# <a name="mbsrtowcs"></a>mbsrtowcs

현재 로캘의 멀티바이트 문자열을 해당하는 와이드 문자열로 변환합니다. 이때 멀티바이트 문자의 중간에서 변환을 다시 시작할 수 있습니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [mbsrtowcs_s](mbsrtowcs-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t mbsrtowcs(
   wchar_t *wcstr,
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t mbsrtowcs(
   wchar_t (&wcstr)[size],
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*wcstr*<br/>
변환된 결과 와이드 문자열을 저장하는 주소입니다.

*mbstr*<br/>
변환할 멀티바이트 문자열의 위치에 대한 간접 포인터입니다.

*count*<br/>
변환 하 고 *wcstr에*저장 하는 문자 (바이트가 아님)의 최대 수입니다.

*mbstate*<br/>
변환 상태 개체에 **대한 mbstate_t** 포인터입니다. 이 값이 null 포인터이면 정적 내부 변환 상태 개체가 사용됩니다. 내부 **mbstate_t** 개체는 스레드에서 안전하지 않으므로 항상 고유한 *mbstate* 매개 변수를 전달하는 것이 좋습니다.

## <a name="return-value"></a>Return Value

종결 null 문자(있는 경우)를 포함하지 않고 정상적으로 변환된 문자 수를 반환합니다. 오류가 발생한 경우(size_t)(-1)를 반환하고 **errno를** EILSEQ로 설정합니다.

## <a name="remarks"></a>설명

**mbsrtowcs** 함수는 *mbstr에*의해 간접적으로 가리키는 멀티 바이트 문자의 문자열을 *mbstate에*포함된 변환 상태를 사용하여 *wcstr이*가리키는 버퍼에 저장된 넓은 문자로 변환합니다. 종료null 멀티바이트 문자가 발생하거나 현재 로캘의 유효한 문자에 해당하지 않는 다중 바이트 시퀀스가 발생하거나 *개수가* 변환될 때까지 각 문자에 대한 변환이 계속됩니다. **mbsrtowcs가** 카운트가 발생하기 전이나 *카운트가* 발생할 때 멀티 바이트 null 문자 ('\0')가 발생하면 16 비트 종료 null 문자로 변환하고 중지합니다.

따라서 *wcstr의* 와이드 문자 문자열은 **mbsrtowcs가** 변환 중에 다중 바이트 null 문자가 발생하는 경우에만 null 종료됩니다. *mbstr와* *wcstr가* 가리키는 시퀀스가 겹치는 경우 **mbsrtowcs의** 동작은 정의되지 않습니다. **mbsrtowcs는** 현재 로캘의 LC_TYPE 범주의 영향을 받습니다.

**mbsrtowcs** 기능은 다시 시작에 의해 [_mbstowcs_l, mbstowcs다르다.](mbstowcs-mbstowcs-l.md) 변환 상태는 동일하거나 다른 다시 시작 가능한 함수에 대한 후속 호출에 대해 *mbstate에* 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어, **mbsrtowcs 대신 mbsrtowcs에** 대한 후속 호출이 사용되는 경우 응용 프로그램은 **mbsrlen** 대신 **mbslen** **mbsrlen을**사용해야합니다.

*wcstr이* null 포인터가 아닌 경우 *mbstr이* 가리키는 포인터 개체는 null 문자 종료에 도달했기 때문에 변환이 중지된 경우 null 포인터가 할당됩니다. 그렇지 않으면 변환된 마지막 멀티바이트 문자 바로 다음의 주소(있는 경우)가 할당됩니다. 그러므로 후속 함수에서 이 호출이 중지된 변환을 다시 시작할 수 있습니다.

*wcstr* 인수가 null 포인터인 경우 *카운트* 인수는 무시되고 **mbsrtowcs는** 대상 문자열에 대해 넓은 문자로 필요한 크기를 반환합니다. *mbstate가* null 포인터인 경우 함수는 스레드가 안전하지 않은 정적 내부 **mbstate_t** 변환 상태 개체를 사용합니다. 문자 시퀀스 *mbstr에* 해당 다중 바이트 문자 표현이 없는 경우 -1이 반환되고 **errno가** **EILSEQ로**설정됩니다.

*mbstr* isa null 포인터인 경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 이 함수는 **errno를** **EINVAL로** 설정하고 -1을 반환합니다.

C++에서 이 함수는 해당 최신 보안 버전을 호출하는 템플릿 오버로드를 포함합니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="exceptions"></a>예외

**mbsrtowcs** 함수는 이 함수가 실행되고 *mbstate* 인수가 null 포인터가 아닌 한 현재 스레드의 함수가 **setlocale를** 호출하지 않는 한 다중 스레드 안전입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**mbsrtowcs**|\<wchar.h>|

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
