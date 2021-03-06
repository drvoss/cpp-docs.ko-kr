---
title: "_aligned_free_dbg | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _aligned_free_dbg
apilocation:
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
apitype: DLLExport
f1_keywords:
- _aligned_free_dbg
- aligned_free_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6eb10bd52593f3ec2f1ca7c30fa31c7d3ce9058
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="alignedfreedbg"></a>_aligned_free_dbg
[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록을 해제합니다(디버그에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
void _aligned_free_dbg(  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memblock`  
 `_aligned_malloc` 또는 `_aligned_offset_malloc` 함수로 반환된 메모리 블록에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `_aligned_free_dbg` 함수는 [_aligned_free](../../c-runtime-library/reference/aligned-free.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_aligned_free_dbg`에 대한 각 호출이 `_aligned_free`에 대한 호출로 줄어듭니다. 둘 다 `_aligned_free` 및 `_aligned_free_dbg` 기본 힙에서 메모리 블록 하지만 `_aligned_free_dbg` 디버깅 기능을 수용: 메모리 부족 조건을 시뮬레이션 하는 힙의 연결된 리스트에서 해제 된 상태로 유지 하는 기능을 차단 합니다.  
  
 `_aligned_free_dbg`는 해제 작업을 수행하기 전에 지정된 파일과 블록 위치 모두에 대해 유효성 검사를 수행합니다. 응용 프로그램에서는 이러한 유효성 검사 정보를 제공하지 않습니다. 메모리 블록이 해제되면 디버그 힙 관리자는 자동으로 사용자 부분 양쪽에 있는 버퍼의 무결성을 확인하며 덮어쓰기가 발생하면 오류 보고서를 만듭니다. [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의 `_CRTDBG_DELAY_FREE_MEM_DF` 비트 필드가 설정되면 빈 블록은 값 0xDD로 채워지고, 빈 블록에는 `_FREE_BLOCK` 블록 형식이 할당되고, 메모리 블록에 대한 힙의 연결된 목록에서 보관됩니다.  
  
 메모리 해제 중 오류가 발생하면 운영 체제에서 제공하는 실패 특성에 대한 정보를 바탕으로 `errno`가 설정됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_aligned_free_dbg`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)