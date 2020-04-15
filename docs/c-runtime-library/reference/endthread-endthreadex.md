---
title: _endthread, _endthreadex
ms.date: 4/2/2020
api_name:
- _endthread
- _endthreadex
- _o__endthread
- _o__endthreadex
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
- _endthread
- endthreadex
- _endthreadex
- endthread
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
ms.openlocfilehash: c76f479255080400e07678ef5dbde572b7a9dffc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348030"
---
# <a name="_endthread-_endthreadex"></a>_endthread, _endthreadex

스레드를 종료합니다. **_endthread** **_beginthread** 의해 생성된 스레드를 종료하고 **_endthreadex** **_beginthreadex**.

## <a name="syntax"></a>구문

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>매개 변수

*retval*<br/>
스레드 종료 코드입니다.

## <a name="remarks"></a>설명

**_endthread** **호출하거나** _endthreadex 명시적으로 호출하여 스레드를 종료할 수 있습니다. 그러나 **_endthread** 또는 **_endthreadex** _beginthread **또는** **_beginthreadex**매개 변수로 전달 된 루틴에서 스레드가 반환 될 때 자동으로 호출 됩니다. **endthread** 또는 **_endthreadex** 대한 호출로 스레드를 종료하면 스레드에 할당된 리소스를 적절하게 복구할 수 있습니다.

> [!NOTE]
> Libcmt.lib로 연결된 실행 파일의 경우 런타임 시스템이 할당된 리소스를 회수하지 않도록 Win32 [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API를 호출하지 마세요. **_endthread** 및 **_endthreadex** 할당된 스레드 리소스를 회수한 다음 **ExitThread**를 호출합니다.

**_endthread** 스레드 핸들을 자동으로 닫습니다. (이 동작은 Win32 **ExitThread** API와 다릅니다.) 따라서 **_beginthread** 및 **_endthread**사용하는 경우 Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) API를 호출하여 스레드 핸들을 명시적으로 닫지 마십시오.

Win32 **ExitThread** API와 마찬가지로 **_endthreadex** 스레드 핸들을 닫지 않습니다. 따라서 **_beginthreadex** 및 **_endthreadex**사용할 때는 Win32 **CloseHandle** API를 호출하여 스레드 핸들을 닫아야 합니다.

> [!NOTE]
> **_endthread** **및 _endthreadex** 스레드에 보류 중인 C++ 소멸자가 호출되지 않습니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

다중 스레드 버전의 유일한 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 입니다.

## <a name="example"></a>예제

[_beginthread](beginthread-beginthreadex.md)에 대한 예를 참조하세요.

## <a name="see-also"></a>참고 항목

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
