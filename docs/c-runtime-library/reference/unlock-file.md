---
title: _unlock_file
ms.date: 4/2/2020
api_name:
- _unlock_file
- _o__unlock_file
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _unlock_file
- unlock_file
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
ms.openlocfilehash: 46d07a8b3645ae0d68276d96271be0a246716f0b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361217"
---
# <a name="_unlock_file"></a>_unlock_file

다른 프로세스에서 파일에 액세스할 수 있도록 파일의 잠금을 해제합니다.

## <a name="syntax"></a>구문

```C
void _unlock_file(
   FILE* file
);
```

### <a name="parameters"></a>매개 변수

*파일*<br/>
파일 핸들입니다.

## <a name="remarks"></a>설명

**_unlock_file** 함수는 파일로 지정된 파일의 잠금을 *해제합니다.* 파일의 잠금을 해제하면 다른 프로세스에서 파일에 액세스할 수 있습니다. **_lock_file** *이전에 파일* 포인터에서 호출되지 않는 한이 함수를 호출할 수 없습니다. _unlock_file **_unlock_file** 호출하면 잠겨 있지 않은 파일에서 교착 상태가 발생할 수 있습니다. 관련 예제는 [_lock_file](lock-file.md)을 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_unlock_file**|\<stdio.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
