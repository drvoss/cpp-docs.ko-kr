---
title: _flushall
ms.date: 4/2/2020
api_name:
- _flushall
- _o__flushall
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _flushall
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
ms.openlocfilehash: 93181c0fe941a1c5e259e706771495666329bcb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346617"
---
# <a name="_flushall"></a>_flushall

모든 스트림을 플러시하고 모든 버퍼를 지웁니다.

## <a name="syntax"></a>구문

```C
int _flushall( void );
```

## <a name="return-value"></a>Return Value

**_flushall** 오픈 스트림(입력 및 출력)의 수를 반환합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

기본적으로 **_flushall** 함수는 열려 있는 출력 스트림과 연결된 모든 버퍼의 내용을 적절한 파일에 씁니다. 열려 있는 입력 스트림과 연결된 모든 버퍼에서 현재 내용이 지워집니다. 이 버퍼는 대개 자동으로 디스크에 데이터를 쓸 수 있는 최적의 시간을 결정하는 운영 체제에서 유지 관리됩니다. 버퍼가 채워졌을 때 스트림이 닫히거나 스트림을 닫지 않고 프로그램이 정상적으로 종료됩니다.

읽기가 **_flushall**호출을 따르는 경우 입력 파일에서 버퍼로 새 데이터를 읽습니다. **_flushall**호출한 후에도 모든 스트림이 열려 있습니다.

런타임 라이브러리의 디스크에 커밋 기능을 사용하면 중요한 데이터가 운영 체제 버퍼 대신 디스크에 직접 기록되어 있는지 확인할 수 있습니다. 기존 프로그램을 다시 작성하지 않고 프로그램의 개체 파일을 Commode.obj와 연결하여 이 기능을 활성화할 수 있습니다. 결과 실행 파일에서 **_flushall** 호출하여 모든 버퍼의 내용을 디스크에 씁니다. **_flushall** 및 [플러시만](fflush.md) Commode.obj의 영향을 받습니다.

디스크에 커밋 기능을 제어하는 방법에 대한 자세한 내용은 [스트림 I/O](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md) 및 [_fdopen](fdopen-wfdopen.md)을 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_flushall**|\<stdio.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_flushall.c
// This program uses _flushall
// to flush all open buffers.

#include <stdio.h>

int main( void )
{
   int numflushed;

   numflushed = _flushall();
   printf( "There were %d streams flushed\n", numflushed );
}
```

```Output
There were 3 streams flushed
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_commit](commit.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[setvbuf](setvbuf.md)<br/>
