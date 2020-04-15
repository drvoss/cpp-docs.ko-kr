---
title: _cwait
ms.date: 4/2/2020
api_name:
- _cwait
- _o__cwait
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
- api-ms-win-crt-process-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cwait
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
ms.openlocfilehash: d54f62c8ce391b2c8ead92a0a73ac48e6f2b3cb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348159"
---
# <a name="_cwait"></a>_cwait

다른 프로세스가 종료될 때까지 기다립니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
intptr_t _cwait(
   int *termstat,
   intptr_t procHandle,
   int action
);
```

### <a name="parameters"></a>매개 변수

*용어 통계*<br/>
지정된 프로세스의 결과 코드가 저장되는 버퍼 또는 **NULL에**대한 포인터 .

*프로크 핸들*<br/>
대기할 프로세스의 핸들(즉, **_cwait** 반환되기 전에 종료해야 하는 프로세스)입니다.

*작업*<br/>
NULL: Windows 운영 체제 응용 프로그램에서 무시됩니다. 다른 응용 프로그램의 경우: *procHandle에서*수행할 작업 코드입니다.

## <a name="return-value"></a>Return Value

지정된 프로세스가 성공적으로 완료되면 지정된 프로세스의 핸들을 반환하고 지정된 프로세스에서 반환되는 결과 코드에 *termstat를* 설정합니다. 그렇지 않으면 -1을 반환하고 다음과 같이 **errno를** 설정합니다.

|값|Description|
|-----------|-----------------|
|**ECHILD**|지정된 프로세스가 *없거나, procHandle이* 유효하지 않거나, [GetExitCodeProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) 또는 [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) API에 대한 호출이 실패했습니다.|
|**아인발 ()에인발 (것)**|*작업이* 잘못되었습니다.|

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

**_cwait** 함수는 *procHandle*에서 제공하는 지정된 프로세스의 프로세스 ID가 종료될 때까지 기다립니다. **_cwait** 전달되는 *procHandle값은* 지정된 프로세스를 만든 [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) 함수에 대한 호출에서 반환되는 값이어야 합니다. **_cwait** 호출되기 전에 프로세스 ID가 종료되면 **_cwait** 즉시 반환됩니다. **_cwait** 유효한 핸들 *(procHandle)이*존재하는 다른 알려진 프로세스를 기다리는 모든 프로세스에서 사용할 수 있습니다.

*termstat는* 지정된 프로세스의 반환 코드가 저장되는 버퍼를 가리킵니다. *termstat값은* 지정된 프로세스가 Windows [ExitProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitprocess) API를 호출하여 정상적으로 종료되었는지 여부를 나타냅니다. **ExitProcess는** 지정된 프로세스가 **종료** 또는 **_exit**호출하거나 **main에서**반환하거나 **main**의 끝에 도달하는 경우 내부적으로 호출됩니다. *termstat를*통해 다시 전달되는 값에 대한 자세한 내용은 [GetExitCodeProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess)을 참조하십시오. *termstat에* **NULL** 값을 사용하여 **_cwait** 호출되는 경우 지정된 프로세스의 반환 코드가 저장되지 않습니다.

이러한 환경에서 부모-자식 관계가 구현되지 않으므로 *작업* 매개 변수는 Windows 운영 체제에서 무시됩니다.

*procHandle이* -1 또는 -2(현재 프로세스 또는 스레드에 대한 핸들)가 아니면 핸들이 닫힙니다. 따라서 이 경우 반환된 핸들을 사용하지 마세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_cwait**|\<process.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_cwait.c
// compile with: /c
// This program launches several processes and waits
// for a specified process to finish.

#define _CRT_RAND_S

#include <windows.h>
#include <process.h>
#include <stdlib.h>
#include <stdio.h>
#include <time.h>

// Macro to get a random integer within a specified range
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))

struct PROCESS
{
   int     nPid;
   char    name[40];
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };

int main( int argc, char *argv[] )
{
   int termstat, c;
   unsigned int number;

   srand( (unsigned)time( NULL ) );    // Seed randomizer

   // If no arguments, this is the calling process
   if ( argc == 1 )
   {
      // Spawn processes in numeric order
      for ( c = 0; c < 4; c++ ) {
         _flushall();
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],
                                    process[c].name, NULL );
      }

      // Wait for randomly specified process, and respond when done
      c = getrandom( 0, 3 );
      printf( "Come here, %s.\n", process[c].name );
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );
      printf( "Thank you, %s.\n", process[c].name );

   }
   // If there are arguments, this must be a spawned process
   else
   {
      // Delay for a period that's determined by process number
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );
      printf( "Hi, Dad. It's %s.\n", argv[1] );
   }
}
```

```Output
Hi, Dad. It's Ann.
Come here, Ann.
Thank you, Ann.
Hi, Dad. It's Beth.
Hi, Dad. It's Carl.
Hi, Dad. It's Dave.
```

## <a name="see-also"></a>참고 항목

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn, _wspawn 기능](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
