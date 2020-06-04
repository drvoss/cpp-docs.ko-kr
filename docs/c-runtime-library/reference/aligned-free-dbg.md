---
title: _aligned_free_dbg
ms.date: 11/04/2016
api_name:
- _aligned_free_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _aligned_free_dbg
- aligned_free_dbg
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
ms.openlocfilehash: 18c1a23d666070afaf1eff687c7d33b0240f0ac3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171283"
---
# <a name="_aligned_free_dbg"></a>_aligned_free_dbg

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록을 해제합니다(디버그에만 해당).

## <a name="syntax"></a>구문

```C
void _aligned_free_dbg(
   void *memblock
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
[_Aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md) 함수에 반환 된 메모리 블록에 대 한 포인터입니다.

## <a name="remarks"></a>설명

**_Aligned_free_dbg** 함수는 [_aligned_free](aligned-free.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은 경우 **_aligned_free_dbg** 에 대 한 각 호출은 `_aligned_free`호출로 줄어듭니다. `_aligned_free` **_aligned_free_dbg** 와는 둘 다 기본 힙에서 메모리 블록을 해제 하지만 **_aligned_free_dbg** 디버깅 기능을 사용할 수 있습니다. 메모리 부족 상태를 시뮬레이션 하기 위해 해제 된 블록을 힙의 연결 된 목록에 유지할 수 있습니다.

사용 가능한 작업을 수행 하기 전에 모든 지정 된 파일과 블록 위치에 대해 유효성 검사를 수행 **_aligned_free_dbg** 합니다. 애플리케이션에서는 이러한 유효성 검사 정보를 제공하지 않습니다. 메모리 블록이 해제되면 디버그 힙 관리자는 자동으로 사용자 부분 양쪽에 있는 버퍼의 무결성을 확인하며 덮어쓰기가 발생하면 오류 보고서를 만듭니다. [_CrtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의 _CRTDBG_DELAY_FREE_MEM_DF 비트 필드가 설정 되 면 빈 블록은 값 0xdd로 채워지고, _FREE_BLOCK 블록 형식을 할당 하 고, 힙의 연결 된 메모리 블록 목록에 보관 합니다.

메모리 해제 중 오류가 발생하면 운영 체제에서 제공하는 실패 특성에 대한 정보를 바탕으로 `errno`가 설정됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 애플리케이션의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_aligned_free_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[디버그 루틴](../../c-runtime-library/debug-routines.md)
