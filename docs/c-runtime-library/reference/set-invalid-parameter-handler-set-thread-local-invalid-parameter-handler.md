---
title: _set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler
ms.date: 4/2/2020
api_name:
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
- _o__set_invalid_parameter_handler
- _o__set_thread_local_invalid_parameter_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_invalid_parameter_handler
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
helpviewer_keywords:
- invalid parameter handler
- set_invalid_parameter_handler function
- _set_invalid_parameter_handler function
- _set_thread_local_invalid_parameter_handler function
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
ms.openlocfilehash: 0637937d4596d28875c40efec62f79a32f533dcf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337678"
---
# <a name="_set_invalid_parameter_handler-_set_thread_local_invalid_parameter_handler"></a>_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler

CRT가 잘못된 인수를 발견할 때 호출할 함수를 설정합니다.

## <a name="syntax"></a>구문

```C
_invalid_parameter_handler _set_invalid_parameter_handler(
   _invalid_parameter_handler pNew
);
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(
   _invalid_parameter_handler pNew
);
```

### <a name="parameters"></a>매개 변수

*pNew*<br/>
새로운 잘못된 매개 변수 처리기에 대한 함수 포인터입니다.

## <a name="return-value"></a>Return Value

호출 이전의 잘못된 매개 변수 처리기에 대한 포인터입니다.

## <a name="remarks"></a>설명

많은 C 런타임 함수가 자신에게 전달되는 인수의 유효성을 확인합니다. 잘못된 인수가 전달되면 함수는 **errno** 오류 번호를 설정하거나 오류 코드를 반환할 수 있습니다. 이 경우 잘못된 매개 변수 처리기도 호출됩니다. C 런타임은 프로그램을 종료하고 런타임 오류 메시지를 표시하는 기본 전역 잘못된 매개 변수 처리기를 제공합니다. **_set_invalid_parameter_handler** 사용하여 고유한 함수를 전역 유효하지 않은 매개 변수 처리기로 설정할 수 있습니다. 또한 C 런타임은 스레드 로컬 잘못된 매개 변수 처리기도 지원합니다. 스레드-local 매개 변수 처리기가 **_set_thread_local_invalid_parameter_handler**사용하여 스레드에서 설정된 경우 스레드에서 호출된 C 런타임 함수는 전역 처리기 대신 해당 처리기를 사용합니다. 한 번에 하나의 함수만 전역 잘못된 인수 처리기로 지정할 수 있습니다. 스레드당 하나의 함수만 스레드 로컬 잘못된 인수 처리기로 지정할 수 있지만, 각 스레드의 스레드 로컬 처리기는 서로 다를 수 있습니다. 따라서 다른 스레드의 동작에 영향을 주지 않고 코드의 특정 부분에서 사용되는 처리기를 변경할 수 있습니다.

런타임이 잘못된 매개 변수 함수를 호출할 때 이는 일반적으로 복구할 수 없는 오류가 발생했음을 의미합니다. 직접 제공하는 잘못된 매개 변수 처리기 함수는 저장할 수 있는 모든 데이터를 저장한 다음 중단되어야 하며, 오류를 확실히 복구할 수 있지 않는 한 컨트롤을 main 함수로 반환하면 안 됩니다.

잘못된 매개 변수 처리기 함수에는 다음과 같은 프로토타입이 있어야 합니다.

```C
void _invalid_parameter(
   const wchar_t * expression,
   const wchar_t * function,
   const wchar_t * file,
   unsigned int line,
   uintptr_t pReserved
);
```

*식* 인수는 오류를 발생 시킨 인수 식의 넓은 문자열 표현입니다. *함수* 인수는 잘못된 인수를 받은 CRT 함수의 이름입니다. *파일* 인수는 함수를 포함하는 CRT 원본 파일의 이름입니다. *줄* 인수는 해당 파일의 줄 번호입니다. 마지막 인수는 예약되어 있습니다. CRT 라이브러리의 디버그 버전을 사용하지 않는 한 매개 변수는 모두 **NULL** 값을 갖습니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_invalid_parameter_handler**, **_set_thread_local_invalid_parameter_handler**|C: \<stdlib.h><br /><br /> C++: \<cstdlib> 또는 \<stdlib.h>|

**_set_invalid_parameter_handler** 및 **_set_thread_local_invalid_parameter_handler** 함수는 Microsoft에 따라 다릅니다. 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

다음 예제에서는 잘못된 매개 변수 오류 처리기를 사용하여 잘못된 매개 변수를 받은 함수와 CRT 소스의 파일 및 줄을 출력합니다. 디버그 CRT 라이브러리가 사용되면 잘못된 매개 변수 오류도 어설션을 생성하지만 이 예제에서는 [_CrtSetReportMode](crtsetreportmode.md)를 통해 사용되지 않도록 설정되었습니다.

```C
// crt_set_invalid_parameter_handler.c
// compile with: /Zi /MTd
#include <stdio.h>
#include <stdlib.h>
#include <crtdbg.h>  // For _CrtSetReportMode

void myInvalidParameterHandler(const wchar_t* expression,
   const wchar_t* function,
   const wchar_t* file,
   unsigned int line,
   uintptr_t pReserved)
{
   wprintf(L"Invalid parameter detected in function %s."
            L" File: %s Line: %d\n", function, file, line);
   wprintf(L"Expression: %s\n", expression);
   abort();
}

int main( )
{
   char* formatString;

   _invalid_parameter_handler oldHandler, newHandler;
   newHandler = myInvalidParameterHandler;
   oldHandler = _set_invalid_parameter_handler(newHandler);

   // Disable the message box for assertions.
   _CrtSetReportMode(_CRT_ASSERT, 0);

   // Call printf_s with invalid parameters.

   formatString = NULL;
   printf(formatString);
}
```

```Output
Invalid parameter detected in function common_vfprintf. File: minkernel\crts\ucrt\src\appcrt\stdio\output.cpp Line: 32
Expression: format != nullptr
```

## <a name="see-also"></a>참고 항목

[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[보안 강화 버전의 CRT 기능](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
