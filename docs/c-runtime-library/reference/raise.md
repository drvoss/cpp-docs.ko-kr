---
title: raise
ms.date: 4/2/2020
api_name:
- raise
- _o_raise
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
- Raise
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.openlocfilehash: b38a3430274b2324e345be30ce9e38f0c2749fa3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338258"
---
# <a name="raise"></a>raise

실행 중인 프로그램에 신호를 보냅니다.

> [!NOTE]
> 테스트 또는 디버깅 시나리오를 제외 하 고 Microsoft Store 응용 프로그램을 종료 하려면이 메서드를 사용 하지 마십시오. [Microsoft 스토어 정책에](/legal/windows/agreements/store-policies)따라 스토어 앱을 닫는 프로그래밍 방식 또는 UI 방법은 허용되지 않습니다. 자세한 내용은 [UWP 앱 수명 주기를](/windows/uwp/launch-resume/app-lifecycle)참조하십시오.

## <a name="syntax"></a>구문

```C
int raise(
   int sig
);
```

### <a name="parameters"></a>매개 변수

*sig*<br/>
생성할 신호입니다.

## <a name="return-value"></a>Return Value

**raise**는 정상적으로 실행되면 0을 반환합니다. 그렇지 않으면 0이 아닌 값을 반환합니다.

## <a name="remarks"></a>설명

**raise** 함수는 *sig*를 실행 프로그램으로 보냅니다. 이전의 **signal** 호출에서 *sig*용 신호 처리 함수를 설치한 경우 **raise**는 해당 함수를 실행합니다. 처리기 함수가 설치되지 않은 경우에는 다음과 같이 신호 값 *sig*와 연결된 기본 작업이 수행됩니다.

|신호|의미|기본값|
|------------|-------------|-------------|
|**SIGABRT**|비정상적인 종료|호출 프로그램을 종료하고 종료 코드 3을 생성합니다.|
|**SIGFPE**|부동 소수점 오류|호출 프로그램을 종료합니다.|
|**SIGILL**|잘못된 명령|호출 프로그램을 종료합니다.|
|**SIGINT**|CTRL+C 인터럽트|호출 프로그램을 종료합니다.|
|**SIGSEGV**|잘못된 스토리지 액세스|호출 프로그램을 종료합니다.|
|**SIGTERM**|프로그램에 종료 요청이 전송됨|신호를 무시합니다.|

인수가 위에 지정되어 있는 유효한 신호가 아니면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 처리되지 않으면 함수는 **errno를** **EINVAL으로** 설정하고 영하지 않은 값을 반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**raise**|\<signal.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[중단](abort.md)<br/>
[신호](signal.md)<br/>
