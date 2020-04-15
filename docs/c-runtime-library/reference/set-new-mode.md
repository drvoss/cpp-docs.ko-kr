---
title: _set_new_mode
ms.date: 4/2/2020
api_name:
- _set_new_mode
- _o__set_new_mode
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_new_mode
- _set_new_mode
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
ms.openlocfilehash: 3a27717d65714de54f477e4e2b3f243c4631fd8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332326"
---
# <a name="_set_new_mode"></a>_set_new_mode

**malloc에**대한 새 처리기 모드를 설정합니다.

## <a name="syntax"></a>구문

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>매개 변수

*뉴핸들러모드*<br/>
**malloc에**대한 새로운 처리기 모드; 유효한 값은 0 또는 1입니다.

## <a name="return-value"></a>Return Value

**malloc에**대한 이전 처리기 모드 집합을 반환합니다. 반환 값이 1이면 메모리를 할당하지 못하면 **malloc이** 이전에 새 처리기 루틴이라고 불렸음을 나타냅니다. 반환 값 0은 반환값이 아님을 나타냅니다. *newhandlermode* 인수가 0 또는 1과 같지 않으면 -1을 반환합니다.

## <a name="remarks"></a>설명

C++ **_set_new_mode** 함수는 [malloc](malloc.md)에 대한 새 처리기 모드를 설정합니다. 새 처리기 모드는 오류가 발생할 경우 **malloc이** [_set_new_handler](set-new-handler.md)설정된 대로 새 처리기 루틴을 호출할지 여부를 나타냅니다. 기본적으로 **malloc는** 메모리할당 실패시 새 처리기 루틴을 호출하지 않습니다. **malloc가** 메모리를 할당하지 못하면 **동일한** 이유로 **새** 연산자가 수행하는 것과 동일한 방식으로 새 처리기 루틴을 호출하도록 이 기본 동작을 재정의할 수 있습니다. 자세한 내용은 *C++ 언어 참조*의 [new](../../cpp/new-operator-cpp.md) 및 [delete](../../cpp/delete-operator-cpp.md) 연산자를 참조하세요. 기본값을 재정의하려면 다음을

```cpp
_set_new_mode(1);
```

프로그램 초기에 또는 Newmode.obj와 연결 [(링크 옵션](../../c-runtime-library/link-options.md)참조).

이 함수는 해당 매개 변수의 유효성을 검사합니다. *newhandlermode* 0 또는 1 이외의 것이면 함수는 매개 변수 유효성 검사에 설명된 대로 잘못된 매개 변수 처리기를 [호출합니다.](../../c-runtime-library/parameter-validation.md) 실행을 계속할 수 있는 경우 <strong>_set_new_mode</strong> -1을 반환하고 **errno를** 로 설정합니다. `EINVAL`

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[무료](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
