---
title: fwrite
ms.date: 4/2/2020
api_name:
- fwrite
- _o_fwrite
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
- fwrite
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
ms.openlocfilehash: a5bd6da3c8d16189f7ff0db744901e03513acc21
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345402"
---
# <a name="fwrite"></a>fwrite

스트림에 데이터를 씁니다.

## <a name="syntax"></a>구문

```C
size_t fwrite(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*버퍼*<br/>
쓸 데이터에 대한 포인터입니다.

*크기*<br/>
항목 크기입니다(바이트).

*count*<br/>
쓸 항목의 최대 수입니다.

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

**fwrite는** 실제로 작성된 전체 항목의 수를 반환하며 오류가 발생할 경우 *개수보다* 적을 수 있습니다. 또한 오류가 발생하면 파일 위치 표시기를 확인할 수 없습니다. *스트림* 또는 *버퍼가* null 포인터이거나 기록할 바이트수가 유니코드 모드로 지정된 경우 함수는 [Parameter Validation에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이 함수는 **errno를** **EINVAL로** 설정하고 0을 반환합니다.

## <a name="remarks"></a>설명

**fwrite** 함수는 *버퍼에서* 출력 *스트림에*이르기까지 각각 *크기* 길이의 항목을 *계산하기* 위해 기록합니다. *스트림과* 연결된 파일 포인터(있는 경우)는 실제로 작성된 바이트 수에 따라 증가합니다. *스트림이* 텍스트 모드에서 열리면 각 줄 피드가 캐리지 리턴 라인 피드 쌍으로 바뀝습니다. 이렇게 바뀌더라도 반환 값에는 영향을 미치지 않습니다.

*예를* 들어, **fopen을** 호출하고 **ccs=UNICODE, ccs=UTF-16LE**또는 **ccs=UTF-8을**포함하는 모드 매개 변수를 사용하여 *스트림이* 열리는 경우 또는 **_setmode** 및 **_O_WTEXT,** **_O_U16TEXT**또는 **_O_U8TEXT**포함하는 모드 매개 변수를 사용하여 모드가 유니코드 변환 **wchar_t** 모드로 변경되는 경우 **ccs=UTF-16LE***버퍼는* wchar_t wchar_t. 이 모드에서 홀수 바이트를 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다.

이 함수는 호출 스레드를 잠그기 때문에 스레드로부터 안전하게 보호됩니다. 비잠금 버전은 **_fwrite_nolock**를 참조하십시오.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fwrite**|\<stdio.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[fread](fread.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
