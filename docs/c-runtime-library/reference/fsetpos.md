---
title: fsetpos
ms.date: 4/2/2020
api_name:
- fsetpos
- _o_fsetpos
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
- fsetpos
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
ms.openlocfilehash: 22b8cebd0154c0dbfc3d21843380ebc9a139059a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345728"
---
# <a name="fsetpos"></a>fsetpos

스트림 위치 표시기를 설정합니다.

## <a name="syntax"></a>구문

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

*Pos*<br/>
위치 표시기 스토리지입니다.

## <a name="return-value"></a>Return Value

성공하면 **fsetpos는 0을** 반환합니다. 오류가 발생할 경우 함수는 영하지 않은 값을 반환하고 **errno를** 다음 매니페스트 상수 중 하나로 설정합니다(ERRNO에 정의되어 있습니다). H): **EBADF는**파일에 액세스할 수 없거나 *스트림이* 가리키는 개체가 유효한 파일 구조가 아님을 의미합니다. 또는 스트림 *또는* *pos에* 대한 잘못된 값이 전달되었다는 것을 의미하는 **EINVAL입니다.** 잘못된 매개 변수가 전달되면 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

**fsetpos** 함수는 *스트림에* 대한 파일 위치 표시기를 *pos*값으로 설정하며, 이는 *스트림에*대해 **fgetpos에** 대한 사전 호출에서 얻어진다. 이 함수는 파일 끝 표시기를 지우고 스트림에서 [unetc의](ungetc-ungetwc.md) 효과를 *취소합니다.* **fsetpos를**호출한 후 *스트림의* 다음 작업은 입력 또는 출력일 수 있습니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[fgetpos](fgetpos.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
