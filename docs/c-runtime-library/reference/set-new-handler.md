---
title: _set_new_handler
ms.date: 4/2/2020
api_name:
- _set_new_handler
- _o__set_new_handler
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
- _set_new_handler
- set_new_handler
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
ms.openlocfilehash: c3f1b9bd8bf2a4404e2239858e4c3c59b755bacd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332371"
---
# <a name="_set_new_handler"></a>_set_new_handler

**new** 연산자에서 메모리 할당에 실패하는 경우 오류 처리 메커니즘에 제어를 전달합니다.

## <a name="syntax"></a>구문

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>매개 변수

*pNewHandler*<br/>
애플리케이션에서 제공하는 메모리 처리 함수에 대한 포인터입니다. 인수가 0이면 새 처리기가 제거됩니다.

## <a name="return-value"></a>Return Value

**_set_new_handler**등록된 이전 예외 처리 함수에 대한 포인터를 반환하여 나중에 이전 함수를 복원할 수 있습니다. 이전 함수가 설정되지 않은 경우 반환 값을 사용하여 기본 동작을 복원할 수 있습니다. 이 값은 **NULL일**수 있습니다.

## <a name="remarks"></a>설명

C++ **_set_new_handler** 함수는 **새** 연산자가 메모리를 할당하지 못할 경우 제어를 얻는 예외 처리 함수를 지정합니다. **새** 오류가 발생하면 런타임 시스템은 인수로 전달된 예외 처리 함수를 자동으로 호출하여 **_set_new_handler.** **new.h에**정의된 _PNH int 형식 **int를** 반환하고 **size_t**형식의 인수를 취하는 함수에 대한 포인터입니다. **size_t** 사용하여 할당할 공간의 양을 지정합니다.

기본 처리기가 없습니다.

**_set_new_handler** 기본적으로 가비지 수집 방식입니다. 런타임 시스템은 함수가 0이 아닌 값을 반환할 때마다 할당을 다시 시도하고 함수가 0을 반환할 경우 실패합니다.

프로그램에서 **_set_new_handler** 함수의 발생은 런타임 시스템과 인수 목록에 지정된 예외 처리 함수를 등록합니다.

```cpp
// set_new_handler1.cpp
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <new.h>

int handle_program_memory_depletion( size_t )
{
   // Your code
}

int main( void )
{
   _set_new_handler( handle_program_memory_depletion );
   int *pi = new int[BIG_NUMBER];
}
```

**마지막으로 _set_new_handler** 함수에 전달된 함수 주소를 저장하고 나중에 복원할 수 있습니다.

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

C++ [_set_new_mode](set-new-mode.md) 함수는 [malloc](malloc.md)에 대한 새 처리기 모드를 설정합니다. 새 처리기 모드는 오류가 발생할 경우 **malloc이** **_set_new_handler**설정된 대로 새 처리기 루틴을 호출할지 여부를 나타냅니다. 기본적으로 **malloc는** 메모리할당 실패시 새 처리기 루틴을 호출하지 않습니다. **malloc가** 메모리를 할당하지 못하면 **동일한** 이유로 **새** 연산자가 수행하는 것과 동일한 방식으로 새 처리기 루틴을 호출하도록 이 기본 동작을 재정의할 수 있습니다. 기본값을 재정의하려면 다음을

```cpp
_set_new_mode(1);
```

초기 프로그램 또는 Newmode.obj에 대한 링크에서 호출합니다.

사용자 정의가 `operator new` 제공되면 새 처리기 함수가 실패시 자동으로 호출되지 않습니다.

자세한 내용은 *C++ 언어 참조*의 [new](../../cpp/new-operator-cpp.md) 및 [delete](../../cpp/delete-operator-cpp.md)를 참조하세요.

동적으로 연결된 모든 DLL 또는 실행 _set_new_handler 대한 단일 **_set_new_handler** 처리기가 있습니다. 처리기가 다른 처리기로 대체되거나 다른 DLL 또는 실행 _set_new_handler 설정된 처리기를 교체하는 _set_new_handler **호출하는** 경우에도 마찬가지입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_new_handler**|\<new.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 예제에서는 할당이 실패하면 컨트롤이 MyNewHandler로 전송됩니다. MyNewHandler에 전달된 인수는 요청된 바이트 수입니다. MyNewHandler에서 반환된 값은 할당을 다시 시도해야 하는지 여부를 나타내는 플래그입니다. 0이 아닌 값은 할당을 다시 시도해야 함을 나타내며 값 0은 할당에 실패했음을 나타냅니다.

```cpp
// crt_set_new_handler.cpp
// compile with: /c
#include <stdio.h>
#include <new.h>
#define BIG_NUMBER 0x1fffffff

int coalesced = 0;

int CoalesceHeap()
{
   coalesced = 1;  // Flag RecurseAlloc to stop
   // do some work to free memory
   return 0;
}
// Define a function to be called if new fails to allocate memory.
int MyNewHandler( size_t size )
{
   printf("Allocation failed. Coalescing heap.\n");

   // Call a function to recover some heap space.
   return CoalesceHeap();
}

int RecurseAlloc() {
   int *pi = new int[BIG_NUMBER];
   if (!coalesced)
      RecurseAlloc();
   return 0;
}

int main()
{
   // Set the failure handler for new to be MyNewHandler.
   _set_new_handler( MyNewHandler );
   RecurseAlloc();
}
```

```Output
Allocation failed. Coalescing heap.

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>참고 항목

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[무료](free.md)<br/>
[realloc](realloc.md)<br/>
