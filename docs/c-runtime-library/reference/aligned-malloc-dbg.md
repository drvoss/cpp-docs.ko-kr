---
title: _aligned_malloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_malloc_dbg
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
- _aligned_malloc_dbg
- aligned_malloc_dbg
helpviewer_keywords:
- aligned_malloc_dbg function
- _aligned_malloc_dbg function
ms.assetid: fb0429c3-685d-4826-9075-2515c5bdc5c6
ms.openlocfilehash: 49278c2282698478ad96cc1c7b1ad27add0a6787
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170941"
---
# <a name="_aligned_malloc_dbg"></a>_aligned_malloc_dbg

디버깅 헤더에 대한 추가 공간이 있는 지정된 정렬 경계에서 메모리 블록을 할당하고 버퍼를 덮어씁니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void * _aligned_malloc_dbg(
    size_t size,
    size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
요청된 메모리 할당의 크기입니다.

*할당*<br/>
2의 정수 제곱이어야 하는 맞춤 값입니다.

*filename*<br/>
할당 작업 또는 NULL을 요청한 소스 파일의 이름에 대한 포인터입니다.

*linenumber*<br/>
할당 작업이 요청되었거나 NULL인 소스 파일의 줄 번호입니다.

## <a name="return-value"></a>Return Value

할당 된 메모리 블록에 대 한 포인터 이거나, 작업에 실패 한 경우 NULL입니다.

## <a name="remarks"></a>설명

**_aligned_malloc_dbg** 은 [_aligned_malloc](aligned-malloc.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은 경우 **_aligned_malloc_dbg** 에 대 한 각 호출은 `_aligned_malloc`호출로 줄어듭니다. `_aligned_malloc`와 **_aligned_malloc_dbg** 모두 기본 힙에서 메모리 블록을 할당 하지만 **_aligned_malloc_dbg** 는 여러 디버깅 기능을 제공 합니다 .이는 블록의 사용자 부분 양쪽에 있는 버퍼를 사용 하 여 누수를 테스트 하 고 *파일 이름*/*linenumber* 정보를 사용 하 여 할당 요청의 원본을 결정 합니다. 블록 형식 매개 변수를 사용 하 여 특정 할당 형식을 추적 하는 것은 정렬 된 할당에 대해 지원 되는 디버그 기능이 아닙니다. 정렬 된 할당은 _NORMAL_BLOCK 블록 형식으로 표시 됩니다.

**_aligned_malloc_dbg** 는 요청한 *크기*보다 약간 더 많은 공간을 사용 하 여 메모리 블록을 할당 합니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 애플리케이션에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 블록이 할당되면 블록의 사용자 부분은 값 0xCD로 채워지고 각 덮어쓰기 버퍼는 0xFD로 채워집니다.

**_aligned_malloc_dbg** 는 메모리 할당이 실패 하거나 필요한 메모리 양 (앞에서 언급 한 오버 헤드 포함)이 `_HEAP_MAXREQ`을 초과 하는 경우 `ENOMEM` `errno` 설정 합니다. 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요. 또한 **_aligned_malloc_dbg** 은 해당 매개 변수의 유효성을 검사 합니다. *Alignment* 가 2의 거듭제곱이 아니거나 *크기가* 0 인 경우이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 합니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 NULL을 반환 하 고 `errno`를 `EINVAL`로 설정 합니다.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 애플리케이션의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_aligned_malloc_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참고 항목

[디버그 루틴](../../c-runtime-library/debug-routines.md)
