---
title: exit, _Exit, _exit
ms.date: 4/2/2020
api_name:
- _exit
- exit
- _o__exit
- _o_exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
ms.openlocfilehash: 5bdb5ff5c8309e03a49f9518f65a45d5757e9bfa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347630"
---
# <a name="exit-_exit-_exit"></a>exit, _Exit, _exit

호출 프로세스를 종료합니다. **종료** 함수는 정리 후 종료합니다. **_exit** 즉시 **종료할 _Exit** 있습니다.

> [!NOTE]
> 테스트 또는 디버깅 시나리오를 제외 하 고 범용 Windows 플랫폼 (UWP) 응용 프로그램을 종료 하려면이 메서드를 사용 하지 마십시오. [Microsoft 스토어 정책에](/legal/windows/agreements/store-policies)따라 스토어 앱을 닫는 프로그래밍 방식 또는 UI 방법은 허용되지 않습니다. 자세한 내용은 [UWP 앱 수명 주기를](/windows/uwp/launch-resume/app-lifecycle)참조하십시오. Windows 10 앱에 대한 자세한 내용은 [Windows 10 앱에 대한 방법 가이드](https://developer.microsoft.com/windows/apps)를 참조하세요.

## <a name="syntax"></a>구문

```C
void exit(
   int const status
);
void _Exit(
   int const status
);
void _exit(
   int const status
);
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
종료 상태 코드입니다.

## <a name="remarks"></a>설명

**종료,** **_Exit** 및 **_exit** 함수는 호출 프로세스를 종료합니다. **exit** 함수는 스레드 로컬 개체에 대해 소멸자 호출한 다음 **atexit** 및 **_onexit**등록된 함수인 LIFO(마지막 선입시) 순서로 호출한 다음 프로세스를 종료하기 전에 모든 파일 버퍼를 플러시합니다. **_Exit** 및 **_exit** 함수는 스레드 로컬 개체를 파괴하거나 **atexit** 또는 **_onexit** 함수를 처리하지 않고 스트림 버퍼를 플러시하지 않고 프로세스를 종료합니다.

**종료,** **_Exit** 및 **_exit** 호출은 값을 반환하지 않지만 *상태* 값은 프로세스가 종료된 후 호스트 환경 또는 대기 호출 프로세스에서 사용할 수 있습니다. 일반적으로 호출자는 *상태* 값을 0으로 설정하여 일반 종료를 나타내거나 다른 값으로 오류를 나타냅니다. *상태* 값은 운영 체제 일괄 처리 명령 **ERRORLEVEL에** 사용할 수 있으며 두 개의 상수 중 하나로 표현됩니다: **EXIT_SUCCESS**0 또는 **EXIT_FAILURE**값을 나타내는 EXIT_FAILURE.

**출구,** **_Exit**, **_exit**, **quick_exit _exit,** **_cexit**및 **_c_exit** 기능은 다음과 같이 작동합니다.

|함수|Description|
|--------------|-----------------|
|**종료**|전체 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**_Exit**|최소 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**_exit**|최소 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**quick_exit**|빠른 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드를 호스트 환경에 제공합니다.|
|**_cexit**|전체 C 라이브러리 종료 절차를 수행하고 호출자에게 반환됩니다. 프로세스를 종료하지 않습니다.|
|**_c_exit**|최소 C 라이브러리 종료 절차를 수행하고 호출자에게 반환됩니다. 프로세스를 종료하지 않습니다.|

**종료,** **_Exit** 또는 **_exit** 함수를 호출할 때 호출 시 존재하는 임시 또는 자동 개체에 대한 소멸자가 호출되지 않습니다. 자동 개체는 함수에 정의된 비정적 로컬 개체입니다. 임시 개체는 함수 호출에서 반환되는 값과 같이 컴파일러에서 만든 개체입니다. 다음과 같이 **exit**, **_Exit**또는 **_exit**호출하기 전에 자동 개체를 삭제하려면 다음과 같이 개체에 대한 소멸자 호출을 명시적으로 호출합니다.

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

**dllMain에서** **출구를** 호출하는 **DLL_PROCESS_ATTACH** 사용하지 마십시오. **DLLMain** 함수를 종료하려면 **FALSE** **false를 DLL_PROCESS_ATTACH.**

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**출구**, **_Exit**, **_exit**|\<process.h> 또는 \<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_exit.c
// This program returns an exit code of 1. The
// error code could be tested in a batch file.

#include <stdlib.h>

int main( void )
{
   exit( 1 );
}
```

## <a name="see-also"></a>참고 항목

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[중단](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit, _c_exit](cexit-c-exit.md)<br/>
[_exec, _wexec 기능](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[_spawn, _wspawn 기능](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
