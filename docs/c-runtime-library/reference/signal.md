---
title: signal | Microsoft Docs
ms.custom: 
ms.date: 02/12/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- signal
apilocation:
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
apitype: DLLExport
f1_keywords:
- signal
dev_langs:
- C++
helpviewer_keywords:
- signal function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23eae404bf5f8e2227d68189938defb2308f5e6b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="signal"></a>신호

인터럽트 신호 처리를 설정합니다.

> [!IMPORTANT]
> 테스트 또는 디버깅 시나리오에서 Microsoft 스토어 앱의 경우를 제외 하 고 종료 하려면이 메서드를 사용 하지 마십시오. 스토어 앱을 닫으려면 프로그래밍 또는 UI 방식으로에 따라 허용 되지 않습니다는 [Microsoft 스토어 정책](http://go.microsoft.com/fwlink/?LinkId=865936)합니다. 자세한 내용은 참조 [UWP 앱 수명 주기](http://go.microsoft.com/fwlink/p/?LinkId=865934)합니다.

## <a name="syntax"></a>구문

```C
void __cdecl *signal(int sig, int (*func)(int, int));
```

### <a name="parameters"></a>매개 변수
_sig_  
신호 값입니다.

_func_  
두 번째 매개 변수는 실행 될 함수에 대 한 포인터입니다. 첫 번째 매개 변수는 신호 값이고 두 번째 매개 변수는 첫 번째 매개 변수가 SIGFPE일 때 사용할 수 있는 하위 코드입니다.

## <a name="return-value"></a>반환 값

`signal` 주어진된 신호와 연관 된 func의 이전 값을 반환 합니다. 예를 들어 경우의 이전 값 _func_ 되었습니다 `SIG_IGN`, 반환 값은 또한 `SIG_IGN`합니다. `SIG_ERR`의 반환 값은 오류를 나타냅니다. 이 경우 `errno`가 `EINVAL`로 설정됩니다.

반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

`signal` 함수를 사용하면 프로세스가 운영 체제에서 인터럽트 신호를 처리하는 여러 방법 중 하나를 선택할 수 있습니다. _sig_ 인수는 인터럽트를 `signal` 응답 신호에 정의 된 다음 매니페스트 상수 중 하나 여야 합니다. 8.

|_sig_ 값|설명|
|-----------------|-----------------|
|`SIGABRT`|비정상적인 종료|
|`SIGFPE`|부동 소수점 오류|
|`SIGILL`|잘못된 명령|
|`SIGINT`|Ctrl+C 신호|
|`SIGSEGV`|잘못된 저장소 액세스|
|`SIGTERM`|종료 요청|

경우 _sig_ 이 아닌 위의 값 중에서 잘못 된 매개 변수 처리기가 호출에 정의 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `SIG_ERR`을 반환합니다.

기본적으로 `signal` 의 값에 관계 없이 3, 종료 코드로 호출 프로그램을 종료 _sig_합니다.

> [!NOTE]
> `SIGINT`는 Win32 응용 프로그램에 대해 지원되지 않습니다. Ctrl+C 인터럽트가 발생할 때 Win32 운영 체제는 특히 해당 인터럽트를 처리하기 위해 새 스레드를 생성합니다. 이렇게 하면 UNIX에서와 같은 단일 스레드 응용 프로그램이 다중 스레드가 되며 예기치 않은 동작을 발생시킵니다.

_func_ 인수는 미리 정의 된 상수 중 하나에 사용자가 작성 하는 신호 처리기에 대 한 주소 `SIG_DFL` 또는 `SIG_IGN`, 신호에도 정의 합니다. 8. 경우 _func_ 는 함수는 주어진된 신호에 대 한 신호 처리기로 설치 됩니다. 신호 처리기의 프로토타입에 하나의 형식 인수를 필요한 _sig_, 형식의 `int`합니다. 통해 실제 인수를 제공 하는 운영 체제 _sig_ 인터럽트가 발생할 때 인수가 인터럽트를 생성 한 신호입니다. 따라서 앞의 표에 나열된 6개의 매니페스트 상수를 신호 처리기에서 사용하여 인터럽트가 발생했는지 여부를 확인하고 적절한 조치를 취할 수 있습니다. 예를 들어, 호출할 수 있습니다 `signal` 는 동일한 처리기 또는 두 개의 서로 다른 신호를 할당 한 다음 테스트를 두 번의 _sig_ 수신 신호에 따라 다른 작업을 수행 하려면 처리기에 대 한 인수입니다.

부동 소수점 예외에 대 한 테스트 하는 경우 (`SIGFPE`), _func_ 여러 매니페스트 상수 중 하나인 선택적 두 번째 인수를 사용 하는 함수를 가리키는-FLOAT에 정의 되어 있습니다. H-폼의 `FPE_xxx`합니다. `SIGFPE` 신호가 발생할 때 두 번째 인수의 값을 테스트하여 부동 소수점 예외의 유형을 확인하고 적절한 조치를 취할 수 있습니다. 이 인수 및 가능한 값은 Microsoft 확장입니다.

값, 부동 소수점 예외에 대 한 _func_ 신호를 받을 때 다시 설정 되지 않습니다. 부동 소수점 예외에서 복구하려면 try/except 절을 사용하여 부동 소수점 작업을 둘러쌉니다. 또한 [setjmp](../../c-runtime-library/reference/setjmp.md)를 [longjmp](../../c-runtime-library/reference/longjmp.md)와 함께 사용하여 복구할 수 있습니다. 이 두 경우 모두에서 호출 프로세스는 실행을 다시 시작하고 프로세스의 부동 소수점 상태를 정의되지 않은 상태로 둡니다.

신호 처리기가 반환하는 경우 호출 프로세스는 인터럽트 신호를 받은 시점 직후 실행을 다시 시작합니다. 이는 신호 또는 작동 모드의 유형에 상관없이 적용됩니다.

지정된 된 함수를 실행 하기 전에 값 _func_ 로 설정 된 `SIG_DFL`합니다. 다음 인터럽트 신호는 `SIG_DFL`에 대한 장애가 있는 호출에서 별도로 지정하지 않는 한 `signal`에 대해 설명된 대로 처리됩니다. 이 기능을 사용하면 호출된 함수에서 신호를 다시 설정할 수 있습니다.

인터럽트가 발생할 때 신호 처리기 루틴이 일반적으로 비동기적으로 호출되기 때문에 런타임 작업이 불완전하고 알 수 없는 상태일 때 신호 처리기 함수가 제어될 수 있습니다. 다음 목록에서는 신호 처리기 루틴에서 사용할 수 있는 함수를 결정하는 제한 사항을 요약합니다.

- 하위 수준 또는 STDIO.H I/O 루틴(예: `printf` 또는 `fread`)을 실행하지 마십시오.

- 힙 루틴 또는 힙 루틴을 사용하는 루틴을 호출하지 마십시오(예: `malloc`, `_strdup` 또는 `_putenv`). 자세한 내용은 [malloc](../../c-runtime-library/reference/malloc.md)를 참조하세요.

- 시스템 호출을 생성하는 함수를 사용하지 마십시오(예: `_getcwd` 또는 `time`).

- 사용 하지 마십시오 `longjmp` 부동 소수점 예외로 인해 인터럽트가 발생 하지 않으면 (즉, _sig_ 은 `SIGFPE`). 이 경우 먼저 `_fpreset`을 호출하여 부동 소수점 패키지를 다시 초기화합니다.

- 오버레이 루틴을 사용하지 마십시오.

함수를 사용하여 `SIGFPE` 예외를 트래핑할 경우 함수는 부동 소수점 코드를 포함해야 합니다. 프로그램에 부동 소수점 코드가 없으며 런타임 라이브러리의 신호 처리 코드가 필요한 경우 volatile double을 선언하고 0으로 초기화합니다.

`volatile double d = 0.0f;`

`SIGILL` 및 `SIGTERM` 신호는 Windows에서 생성되지 않습니다. 이는 ANSI 호환성을 위해 포함됩니다. 따라서 `signal`을 사용하여 이러한 신호에 대한 신호 처리기를 설정하고 [raise](../../c-runtime-library/reference/raise.md)를 호출하여 이러한 신호를 명시적으로 생성할 수도 있습니다.

신호 설정은 `_exec` 또는 `_spawn` 함수를 호출하여 만든 생성된 프로세스에서 유지되지 않습니다. 신호 설정은 새 프로세스에서 기본값으로 다시 설정됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`signal`|\<signal.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예

다음 예제에서는 `signal`을 사용하여 일부 사용자 지정 동작을 `SIGABRT` 신호에 추가하는 방법을 보여 줍니다. abort 동작에 대한 자세한 내용은 [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md)를 참조하세요.

```C
// crt_signal.c
// compile with: /EHsc /W4
// Use signal to attach a signal handler to the abort routine
#include <stdlib.h>
#include <signal.h>
#include <tchar.h>

void SignalHandler(int signal)
{
    if (signal == SIGABRT) {
        // abort signal handler code
    } else {
        // ...
    }
}

int main()
{
    typedef void (*SignalHandlerPointer)(int);

    SignalHandlerPointer previousHandler;
    previousHandler = signal(SIGABRT, SignalHandler);

    abort();
}
```

```Output
This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>참고 항목

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)  
[exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)  
[_fpreset](../../c-runtime-library/reference/fpreset.md)  
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)  
