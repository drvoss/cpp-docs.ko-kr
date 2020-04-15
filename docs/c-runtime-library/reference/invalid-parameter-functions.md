---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson
ms.date: 4/2/2020
api_name:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
- _o__invalid_parameter_noinfo
- _o__invalid_parameter_noinfo_noreturn
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CORECRT/_invalid_parameter
- _invalid_parameter
- CORECRT/_invalid_parameter_noinfo
- _invalid_parameter_noinfo
- CORECRT/_invalid_parameter_noinfo_noreturn
- _invalid_parameter_noinfo_noreturn
- CORECRT/_invoke_watson
- _invoke_watson
ms.assetid: a4d6f1fd-ce56-4783-8719-927151a7a814
ms.openlocfilehash: 0f0a3ea3e1f2e43d53650b4017905c696269ce20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343938"
---
# <a name="_invalid_parameter-_invalid_parameter_noinfo-_invalid_parameter_noinfo_noreturn-_invoke_watson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson

이러한 함수는 C 런타임 라이브러리에서 CRT 라이브러리 함수에 전달된 유효하지 않은 매개 변수를 처리하는 데 사용됩니다. 코드에서는 유효하지 않은 매개 변수의 기본 처리 또는 사용자 지정 가능한 처리를 지원하기 위해 이러한 함수를 사용할 수도 있습니다.

## <a name="syntax"></a>구문

```C
extern "C" void __cdecl
_invalid_parameter(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);

extern "C" void __cdecl
_invalid_parameter_noinfo(void);

extern "C" __declspec(noreturn) void __cdecl
_invalid_parameter_noinfo_noreturn(void);

extern "C" __declspec(noreturn) void __cdecl
_invoke_watson(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);
```

## <a name="parameters"></a>매개 변수

*expression*<br/>
잘못된 소스 코드 매개 변수 식을 나타내는 문자열입니다.

*function_name*<br/>
처리기를 호출한 함수의 이름입니다.

*File_name*<br/>
처리기가 호출된 소스 코드 파일입니다.

*line_number*<br/>
처리기가 호출된 소스 코드의 줄 번호입니다.

*예약*<br/>
사용되지 않습니다.

## <a name="return-value"></a>Return Value

이러한 함수는 값을 반환하지 않습니다. **_invalid_parameter_noinfo_noreturn** 및 **_invoke_watson** 함수는 호출자에게 반환되지 않으며 경우에 따라 **_invalid_parameter** 및 **_invalid_parameter_noinfo** 호출자에게 반환되지 않을 수 있습니다.

## <a name="remarks"></a>설명

C 런타임 라이브러리 함수가 유효하지 않은 매개 변수를 전달하는 경우 라이브러리 함수는 프로그래머가 여러 가지 작업을 수행하도록 지정할 수 있는 함수인 *잘못된 매개 변수 처리기*를 호출합니다. 예를 들어 사용자에게 문제를 보고하거나, 로그에 기록하거나, 디버거를 중단하거나, 프로그램을 종료하거나, 아무 작업도 수행하지 않을 수 있습니다. 프로그래머가 함수를 지정하지 않으면 기본 **처리기인 _invoke_watson**호출됩니다.

기본적으로 디버그 코드에서 유효하지 않은 매개 변수가 식별되면 CRT 라이브러리 함수는 자세한 매개 변수를 사용하여 **함수 _invalid_parameter** 호출합니다. 디버그가 아닌 코드에서는 빈 매개 변수를 사용하여 **_invalid_parameter** 함수를 호출하는 **_invalid_parameter_noinfo** 함수가 호출됩니다. 디버그CRT 라이브러리 함수에 프로그램 종료가 필요한 경우 **_invalid_parameter_noinfo_noreturn** 함수가 호출되고 빈 매개 변수를 사용하여 **_invalid_parameter** 함수를 호출한 다음 프로그램 종료를 강제로 **_invoke_watson** 함수를 호출합니다.

**_invalid_parameter** 함수는 사용자 정의 잘못된 매개 변수 처리기가 설정되었는지 여부를 확인하고, 이 경우 호출합니다. 예를 들어 사용자 정의 스레드 로컬 처리기가 현재 스레드에서 [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)를 호출하여 설정된 경우 호출되면 함수가 반환됩니다. 그러지 않고 사용자 정의 전역 잘못된 매개 변수 처리기가 [set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)를 호출하여 설정된 경우 호출되면 함수가 반환됩니다. 그렇지 않으면 기본 처리기 **_invoke_watson** 호출됩니다. **_invoke_watson** 기본 동작은 프로그램을 종료하는 것입니다. 사용자 정의 처리기가 종료되거나 반환될 수 있습니다. 복구가 확실하지 않으면 사용자 정의 처리기에서 프로그램을 종료하는 것이 좋습니다.

기본 처리기 **_invoke_watson** 호출될 때 프로세서가 [__fastfail](../../intrinsics/fastfail.md) 작업을 지원하는 경우 **FAST_FAIL_INVALID_ARG** 매개 변수를 사용하여 호출되고 프로세스가 종료됩니다. 그렇지 않으면 빠른 실패 예외가 발생하며 연결된 디버거에서 catch할 수 있습니다. 프로세스를 계속 할 수 있는 경우 **STATUS_INVALID_CRUNTIME_PARAMETER**예외 코드 상태를 사용 하 여 Windows **TerminateProcess** 함수에 대 한 호출에 의해 종료 됩니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|------------------|
|**_invalid_parameter,** **_invalid_parameter_noinfo,** **_invalid_parameter_noinfo_noreturn,** **_invoke_watson**|\<corecrt.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)<br/>
