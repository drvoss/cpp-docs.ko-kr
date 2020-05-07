---
title: _get_osfhandle
ms.date: 4/2/2020
api_name:
- _get_osfhandle
- _o__get_osfhandle
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_osfhandle
- _get_osfhandle
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: 085bf20a12d9b77be0977521bde2ab75d9b2636a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918279"
---
# <a name="_get_osfhandle"></a>_get_osfhandle

지정된 파일 설명자와 연결된 운영 체제 파일 핸들을 검색합니다.

## <a name="syntax"></a>구문

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
기존 파일 설명자입니다.

## <a name="return-value"></a>Return Value

*Fd* 가 유효한 경우 운영 체제 파일 핸들을 반환 합니다. 그렇지 않으면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속 해 서 실행 하도록 허용한 경우 **INVALID_HANDLE_VALUE** (-1)을 반환 합니다. 또한 **errno** 를 **ebadf**로 설정 하 여 잘못 된 파일 핸들을 나타냅니다. 결과를 Win32 파일 핸들로 사용할 때 경고를 방지 하려면 **핸들** 형식으로 캐스팅 합니다.

> [!NOTE]
> **Stdin**, **stdout**및 **stderr** 이 스트림과 연결 되지 않은 경우 (예: 콘솔 창이 없는 Windows 응용 프로그램에서) 이러한 스트림의 파일 설명자 값은 [_fileno](fileno.md) 에서 특수 값-2로 반환 됩니다. 마찬가지로 **_fileno**에 대 한 호출의 결과로 0, 1 또는 2를 파일 설명자 매개 변수로 사용 하는 경우 파일 설명자가 스트림과 연결 되어 있지 않고 **errno**를 설정 하지 않은 경우에도 특수 값-2가 반환 **_get_osfhandle** . 그러나이 값은 유효한 파일 핸들 값이 아닙니다 .이 값을 사용 하려고 시도 하는 후속 호출은 실패할 수 있습니다.

**Ebadf** 및 기타 오류 코드에 대 한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조 하세요.

## <a name="remarks"></a>설명

**_Get_osfhandle**에서 os (운영 체제) 파일 핸들을 가져오는 파일을 닫으려면 파일 설명자 *fd*에서 [_close](close.md) 를 호출 합니다. 이 함수의 반환 값에 대해 **CloseHandle** 을 호출 하지 마세요. 기본 OS 파일 핸들은 *fd* 파일 설명자가 소유 하며, *fd*에서 [_close](close.md) 가 호출 될 때 닫힙니다. 스트림이 파일 설명자를 소유 하는 경우 해당 `FILE *` 스트림에서 [fclose](fclose-fcloseall.md) 를 호출 하면 파일 설명자와 기본 OS 파일 핸들이 모두 닫힙니다. `FILE *` 이 경우에는 파일 설명자에 대해 [_close](close.md) 를 호출 하지 마세요.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참조

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
