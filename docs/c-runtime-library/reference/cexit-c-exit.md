---
title: _cexit, _c_exit
ms.date: 4/2/2020
api_name:
- _c_exit
- _cexit
- _o__cexit
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
- _cexit
- c_exit
- _c_exit
- cexit
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
ms.openlocfilehash: 9eb856efca054423465aa7d30092edaf83a65eeb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333527"
---
# <a name="_cexit-_c_exit"></a>_cexit, _c_exit

정리 작업을 수행하고 프로세스 종료 없이 반환합니다.

## <a name="syntax"></a>구문

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>설명

**_cexit** 함수는 **atexit** 및 **_onexit**의해 등록된 함수인 마지막 IN, 선불(LIFO) 순서로 호출합니다. 그런 다음 **_cexit** 모든 I/O 버퍼를 플러시하고 반환하기 전에 모든 열린 스트림을 닫습니다. **_c_exit** **_exit** 동일하지만 **atexit** 또는 **_onexit** 처리하거나 스트림 버퍼를 플러시하지 않고 호출 프로세스로 돌아갑니다. **,** **_cexit** **_exit**및 **_c_exit** 동작은 다음 표에 나와 있습니다.

|함수|동작|
|--------------|--------------|
|**종료**|전체 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드와 함께 종료됩니다.|
|**_exit**|빠른 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드와 함께 종료됩니다.|
|**_cexit**|전체 C 라이브러리 종료 절차를 수행하고 호출자에게 반환하지만, 프로세스를 종료하지 않습니다.|
|**_c_exit**|빠른 C 라이브러리 종료 절차를 수행하고 호출자에게 반환하지만, 프로세스를 종료하지 않습니다.|

**_cexit** 또는 **_c_exit** 함수를 호출할 때 호출 시 존재하는 임시 또는 자동 개체에 대한 소멸자는 호출되지 않습니다. 자동 개체는 개체가 정적으로 선언되지 않은 함수에서 정의된 개체입니다. 임시 개체는 컴파일러에 의해 생성된 개체입니다. **_cexit** 또는 **_c_exit**호출하기 전에 자동 개체를 삭제하려면 다음과 같이 개체에 대한 소멸자 호출을 명시적으로 호출합니다.

```cpp
myObject.myClass::~myClass( );
```

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[중단](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec 기능](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn 기능](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
