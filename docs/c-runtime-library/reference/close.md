---
title: _close
ms.date: 4/2/2020
api_name:
- _close
- _o__close
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
- _close
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
ms.openlocfilehash: 4d8b702a10624ae80629b4ce4644c428322500cb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348652"
---
# <a name="_close"></a>_close

파일을 닫습니다.

## <a name="syntax"></a>구문

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>매개 변수

*Fd*<br/>
열려 있는 파일을 참조하는 파일 설명자입니다.

## <a name="return-value"></a>Return Value

**_close** 파일이 성공적으로 닫힌 경우 0을 반환합니다. 반환 값 -1은 오류를 나타냅니다.

## <a name="remarks"></a>설명

**_close** 함수는 *fd와*연결된 파일을 닫습니다.

파일 설명자와 기본 OS 파일 핸들을 닫습니다. 따라서 파일이 원래 Win32 함수 **CreateFile을** 사용하여 열리고 **_open_osfhandle**사용하여 파일 설명자로 변환된 경우 **CloseHandle을** 호출할 필요가 없습니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. *fd가* 잘못된 파일 설명자인 경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있으면 함수가 -1을 반환하고 **errno가** **EBADF로**설정됩니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_close**|\<io.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_open](open-wopen.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
