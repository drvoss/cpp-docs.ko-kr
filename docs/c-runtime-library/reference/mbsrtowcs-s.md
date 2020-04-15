---
title: mbsrtowcs_s
ms.date: 4/2/2020
api_name:
- mbsrtowcs_s
- _o_mbsrtowcs_s
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
- mbsrtowcs_s
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
ms.openlocfilehash: 62ae534e8080b74ada49cca005811a049055cb65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338895"
---
# <a name="mbsrtowcs_s"></a>mbsrtowcs_s

현재 로캘의 멀티바이트 문자열을 와이드 문자열 표현으로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [mbsrtowcs](mbsrtowcs.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t * wcstr,
   size_t sizeInWords,
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
);
template <size_t size>
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t (&wcstr)[size],
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
변환된 문자 수입니다.

*wcstr*<br/>
결과로 생성되는 와이드 문자열을 저장할 버퍼의 주소입니다.

*크기인검*<br/>
단어 (넓은 문자)에서 *wcstr의* 크기입니다.

*mbstr*<br/>
변환할 멀티바이트 문자열의 위치에 대한 간접 포인터입니다.

*count*<br/>
종료 null 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)포함하지 않는 *wcstr* 버퍼에 저장할 와이드 문자의 최대 수입니다.

*mbstate*<br/>
변환 상태 개체에 **대한 mbstate_t** 포인터입니다. 이 값이 null 포인터이면 정적 내부 변환 상태 개체가 사용됩니다. 내부 **mbstate_t** 개체는 스레드에서 안전하지 않으므로 항상 고유한 *mbstate* 매개 변수를 전달하는 것이 좋습니다.

## <a name="return-value"></a>Return Value

변환이 완료되면 0이 반환되고, 실패하면 오류 코드가 반환됩니다.

|오류 조건|반환 값 및 **errno**|
|---------------------|------------------------------|
|*wcstr는* null 포인터이며 *크기인>0*|**아인발 ()에인발 (것)**|
|*mbstr은* null 포인터입니다.|**아인발 ()에인발 (것)**|
|*mbstr가* 간접적으로 가리키는 문자열에는 현재 로캘에 대해 유효하지 않은 다중 바이트 시퀀스가 포함되어 있습니다.|**EILSEQ**|
|대상 버퍼가 너무 작아서 변환된 문자열을 포함하지 *않습니다(카운트가* **_TRUNCATE**않는 한 비고 참조).|**ERANGE**|

이러한 상황 중 하나라도 발생하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 실행을 계속할 수 있는 경우 함수는 오류 코드를 반환하고 **errno를** 테이블에 표시된 대로 설정합니다.

## <a name="remarks"></a>설명

**mbsrtowcs_s** 함수는 *mbstate에*포함된 변환 상태를 사용하여 *mbstr에* 의해 간접적으로 가리키는 다중 바이트 문자 문자열을 *wcstr에*의해 가리키는 버퍼에 저장된 넓은 문자로 변환합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.

- 멀티바이트 null 문자가 발견되는 경우

- 잘못된 멀티바이트 문자가 발견되는 경우

- *wcstr* 버퍼에 저장된 와이드 문자의 수는 *개수와*같습니다.

*대상* 문자열 *wcstr는 wcstr이* null 포인터가 아니라면 오류가 있는 경우에도 항상 null-terminated입니다.

*count가* [_TRUNCATE](../../c-runtime-library/truncate.md)특수 값인 경우 **mbsrtowcs_s** null 종사에 대한 공간을 유지하면서 대상 버퍼에 맞는 만큼 문자열을 변환합니다.

**mbsrtowcs_s** 소스 문자열을 성공적으로 변환하는 경우 변환된 문자열의 와이드 문자로 크기를 놓고 null 종단을 *pReturnValue* *&#42;pReturnValue로*만듭니다. wcstr 인수가 *wcstr* null 포인터이고 필요한 버퍼 크기를 결정할 수 있는 경우에도 이 문제는 발생합니다. *wcstr이* null 포인터인 경우 *개수는* 무시됩니다.

*wcstr이* null 포인터가 아닌 경우 *mbstr이* 가리키는 포인터 개체는 null 문자 종료에 도달했기 때문에 변환이 중지된 경우 null 포인터가 할당됩니다. 그렇지 않으면 변환된 마지막 멀티바이트 문자 바로 다음의 주소(있는 경우)가 할당됩니다. 그러므로 후속 함수에서 이 호출이 중지된 변환을 다시 시작할 수 있습니다.

*mbstate가* null 포인터인 경우 라이브러리 내부 **mbstate_t** 변환 상태 정적 개체가 사용됩니다. 이 내부 정적 개체는 스레드에서 사용할 수 없으므로 고유한 *mbstate* 값을 전달하는 것이 좋습니다.

**mbsrtowcs_s** 현재 로캘에서 유효하지 않은 다중 바이트 문자를 만나는 경우 *pReturnValue&#42;*-1을 넣고, 대상 버퍼 *wcstr을* 빈 문자열로 설정하고, **errno를** **EILSEQ로**설정하고, **EILSEQ를**반환합니다.

*mbstr와* *wcstr가* 가리키는 시퀀스가 겹치면 **mbsrtowcs_s** 동작은 정의되지 않습니다. **mbsrtowcs_s** 현재 로캘의 LC_TYPE 범주의 영향을 받습니다.

> [!IMPORTANT]
> *wcstr및* *mbstr이* 겹치지 않도록 하고 그 *개수가* 변환할 다중 바이트 문자의 수를 올바르게 반영합니다.

**mbsrtowcs_s** 함수는 [mbstowcs_s](mbstowcs-s-mbstowcs-s-l.md) _mbstowcs_s_l 재시작 가능성에 의해 다릅니다. 변환 상태는 동일하거나 다른 다시 시작 가능한 함수에 대한 후속 호출에 대해 *mbstate에* 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어 응용 프로그램은 **mbslen**대신 **mbsrlen을** 사용해야 하며, **mbstowcs_s**대신 **mbsrtowcs_s** 대한 후속 호출이 사용되는 경우.

C++에서는 템플릿 오버로드로 이러한 함수를 간편하게 사용할 수 있습니다. 즉, 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 또한 기존의 비보안 함수를 그에 해당하는 안전한 최신 함수로 자동 교체할 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="exceptions"></a>예외

**mbsrtowcs_s** 함수는 이 함수가 실행중이고 *mbstate* 인수가 null 포인터가 아닌 한 현재 스레드에서 **setlocale를** 호출하는 함수가 없는 경우 다중 스레드안전입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**mbsrtowcs_s**|\<wchar.h>|

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
