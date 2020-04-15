---
title: _set_abort_behavior
ms.date: 4/2/2020
api_name:
- _set_abort_behavior
- _o__set_abort_behavior
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
- _set_abort_behavior
- set_abort_behavior
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.openlocfilehash: fd3a3c2f99d1702cdccf68328c2122b965b2d078
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337877"
---
# <a name="_set_abort_behavior"></a>_set_abort_behavior

프로그램이 비정상적으로 종료될 때 수행할 작업을 지정합니다.

> [!NOTE]
> 테스트 또는 디버깅 시나리오를 제외 하 고 Microsoft Store 응용 프로그램을 종료 하려면 [중단 함수를](abort.md) 사용 하지 마십시오. [Microsoft 스토어 정책에](/legal/windows/agreements/store-policies)따라 스토어 앱을 닫는 프로그래밍 방식 또는 UI 방법은 허용되지 않습니다. 자세한 내용은 [UWP 앱 수명 주기를](/windows/uwp/launch-resume/app-lifecycle)참조하십시오.

## <a name="syntax"></a>구문

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>매개 변수

*플래그*<br/>
[중단](abort.md) 플래그의 새 값입니다.

*마스크*<br/>
설정할 [중단](abort.md) 플래그 비트에 대한 마스크입니다.

## <a name="return-value"></a>Return Value

플래그의 이전 값입니다.

## <a name="remarks"></a>설명

두 개의 [중단](abort.md) 플래그가 있습니다: **_WRITE_ABORT_MSG** **및 _CALL_REPORTFAULT**. **_WRITE_ABORT_MSG** 프로그램이 비정상적으로 종료될 때 유용한 문자 메시지가 인쇄되는지 여부를 결정합니다. 이 메시지는 응용 프로그램이 [중단](abort.md) 함수를 호출했다는 것을 명시합니다. 기본 동작은 메시지를 인쇄하는 것입니다. **_CALL_REPORTFAULT**설정하면 Watson 크래시 덤프가 생성되고 [중단이](abort.md) 호출될 때 보고되도록 지정합니다. 기본적으로 DEBUG가 아닌 모드에서는 크래시 덤프 보고가 사용하도록 설정됩니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_set_abort_behavior.c
// compile with: /TC
#include <stdlib.h>

int main()
{
   printf("Suppressing the abort message. If successful, this message"
          " will be the only output.\n");
   // Suppress the abort message
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);
   abort();
}
```

```Output
Suppressing the abort message. If successful, this message will be the only output.
```

## <a name="see-also"></a>참고 항목

[중단](abort.md)<br/>
