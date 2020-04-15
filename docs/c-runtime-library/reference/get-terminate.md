---
title: _get_terminate
ms.date: 4/2/2020
api_name:
- _get_terminate
- _o__get_terminate
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
- get_terminate
- _get_terminate
- __get_terminate
helpviewer_keywords:
- __get_terminate function
- get_terminate function
- _get_terminate function
ms.assetid: c8f168c4-0ad5-4832-a522-dd1ef383c208
ms.openlocfilehash: fff90037851b23f3525f514aba0f6f913f9dd776
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344929"
---
# <a name="_get_terminate"></a>_get_terminate

종료에 의해 호출될 종료 루틴을 **반환합니다.**

## <a name="syntax"></a>구문

```C
terminate_function _get_terminate( void );
```

## <a name="return-value"></a>Return Value

[set_terminate](set-terminate-crt.md)로 등록된 함수에 대한 포인터를 반환합니다. 함수가 설정되지 않은 경우 반환 값을 사용하여 기본 동작을 복원할 수 있습니다. 이 값은 **NULL**일 수 있습니다.

## <a name="remarks"></a>설명

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_terminate**|\<eh.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)<br/>
[중단](abort.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[종료](terminate-crt.md)<br/>
[예기치 않은](unexpected-crt.md)<br/>
