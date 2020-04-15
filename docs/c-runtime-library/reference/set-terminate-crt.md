---
title: set_terminate(CRT)
ms.date: 4/2/2020
api_name:
- set_terminate
- _o_set_terminate
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
- set_terminate
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 08ea5bb8c446fadac6a7bcf7ca172c5d14546776
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332097"
---
# <a name="set_terminate-crt"></a>set_terminate(CRT)

**종료에**의해 호출될 사용자 고유의 종료 루틴을 설치합니다.

## <a name="syntax"></a>구문

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>매개 변수

*용어 기능*<br/>
작성하는 terminate 함수에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

**set_terminate** 의해 등록된 이전 함수에 대한 포인터를 반환하여 나중에 이전 함수를 복원할 수 있습니다. 이전 함수가 설정되지 않은 경우 반환 값을 사용하여 기본 동작을 복원할 수 있습니다. 이 값은 **NULL**일 수 있습니다.

## <a name="remarks"></a>설명

**set_terminate** 함수는 **terminate에**의해 호출 된 함수로 *함수를* 설치합니다. **set_terminate** C++ 예외 처리와 함께 사용되며 예외가 throw되기 전에 프로그램의 어느 지점에서든 호출될 수 있습니다. **해지** [호출은](abort.md) 기본적으로 중단됩니다. 고유한 종료 함수를 작성하고 함수 이름을 **인수로** set_terminate 호출하여 이 기본값을 변경할 수 있습니다. **terminate는** **set_terminate**인수로 주어진 마지막 함수를 호출합니다. 원하는 정리 작업을 수행 한 후 *termFunction* 프로그램을 종료 해야 합니다. 종료되지 않으면(호출자에게 반환되는 경우) [중단이](abort.md) 호출됩니다.

다중 스레드 환경에서 terminate 함수는 각 스레드에 대해 개별적으로 유지 관리됩니다. 각 새 스레드는 자체 terminate 함수를 설치해야 합니다. 따라서 각 스레드는 자체 종료 처리를 담당합니다.

**terminate_function** 형식은 EH에 정의되어 있습니다. H는 사용자 정의 종료 함수에 대한 포인터로, **void를**반환하는 *termFunction.* 사용자 지정 함수 *termFunction* 인수를 사용할 수 있으며 호출자에게 반환되지 않아야 합니다. 이 경우 [중단이](abort.md) 호출됩니다. *예외는 용어*내에서 throw되지 않을 수 있습니다Function .

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **set_terminate** 함수는 디버거 외부에서만 작동합니다.

동적으로 연결된 모든 DLL 또는 EXEs에 대한 단일 **set_terminate** 처리기가 있습니다. 처리기가 다른 처리기로 대체될 수 **set_terminate** 호출하거나 다른 DLL 또는 EXE로 설정된 처리기를 교체할 수 있습니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**set_terminate**|\<eh.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[terminate](terminate-crt.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)<br/>
[중단](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[종료](terminate-crt.md)<br/>
[예기치 않은](unexpected-crt.md)<br/>
