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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 9e2e23acb041004b9e96d1c6558ae195ed522155
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914790"
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

*termstat*<br/>
지정 된 프로세스의 결과 코드가 저장 되는 버퍼에 대 한 포인터 이거나 **NULL**입니다.

*procHandle*<br/>
대기 중인 프로세스에 대 한 핸들입니다 (즉, **_cwait** 를 반환 하기 전에 종료 되어야 하는 프로세스).

*action*<br/>
NULL: Windows 운영 체제 응용 프로그램에서 무시 됩니다. 다른 응용 프로그램: *procHandle*에서 수행할 작업 코드입니다.

## <a name="return-value"></a>Return Value

지정 된 프로세스가 성공적으로 완료 되 면는 지정 된 프로세스의 핸들을 반환 하 고 *termstat* 를 지정 된 프로세스에서 반환 되는 결과 코드로 설정 합니다. 그렇지 않으면-1을 반환 하 고 **errno** 를 다음과 같이 설정 합니다.

|값|설명|
|-----------|-----------------|
|**ECHILD**|지정 된 프로세스가 없거나 *procHandle* 이 잘못 되었거나 [Getexitcodeprocess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) 또는 [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) API에 대 한 호출이 실패 했습니다.|
|**EINVAL**|*동작이* 잘못 되었습니다.|

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

**_Cwait** 함수는 *procHandle*에서 제공 하는 지정 된 프로세스의 프로세스 ID가 종료 될 때까지 대기 합니다. **_Cwait** 전달 되는 *procHandle* 의 값은 지정 된 프로세스를 만든 [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) 함수 호출에서 반환 되는 값 이어야 합니다. **_Cwait** 가 호출 되기 전에 프로세스 ID가 종료 되 면 **_cwait** 즉시 반환 됩니다. **_cwait** 는 모든 프로세스에서 유효한 핸들 (*procHandle*)이 존재 하는 기타 알려진 프로세스를 기다리는 데 사용할 수 있습니다.

*termstat* 는 지정 된 프로세스의 반환 코드가 저장 될 버퍼를 가리킵니다. *Termstat* 값은 지정 된 프로세스가 Windows [exitprocess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitprocess) API를 호출 하 여 정상적으로 종료 되었는지 여부를 나타냅니다. 지정 된 프로세스가 **exit** 또는 **_exit**를 호출 하거나, **main**에서 반환 되거나, **main**의 끝에 도달 하는 경우 **exitprocess** 가 내부적으로 호출 됩니다. *Termstat*를 통해 다시 전달 되는 값에 대 한 자세한 내용은 [Getexitcodeprocess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess)를 참조 하세요. *Termstat*에 **NULL** 값을 사용 하 여 **_cwait** 를 호출 하면 지정 된 프로세스의 반환 코드가 저장 되지 않습니다.

*작업* 매개 변수는 이러한 환경에서 부모-자식 관계가 구현 되지 않으므로 Windows 운영 체제에서 무시 됩니다.

*ProcHandle* 가-1 또는-2 (현재 프로세스 또는 스레드에 대 한 핸들)가 아닌 경우 핸들이 닫힙니다. 따라서 이 경우 반환된 핸들을 사용하지 마세요.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

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

## <a name="see-also"></a>참조

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
