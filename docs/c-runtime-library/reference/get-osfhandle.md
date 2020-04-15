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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: a12c0c93ae15350a4b91a8aa905acb941f8b6a10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345038"
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

*Fd*<br/>
기존 파일 설명자입니다.

## <a name="return-value"></a>Return Value

*fd가* 유효한 경우 운영 체제 파일 핸들을 반환합니다. 그렇지 않으면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있으면 INVALID_HANDLE_VALUE(-1)로 반환됩니다. **INVALID_HANDLE_VALUE** 또한 **errno를** **EBADF로**설정하여 잘못된 파일 핸들을 나타냅니다. 결과가 Win32 파일 핸들로 사용될 때 경고를 방지하려면 **HANDLE** 유형으로 캐스팅합니다.

> [!NOTE]
> **stdin**, **stdout**및 **stderr가** 스트림과 연결되지 않은 경우(예: 콘솔 창이 없는 Windows 응용 프로그램에서) 이러한 스트림에 대한 파일 설명자 값이 [_fileno](fileno.md) 특수 값 -2로 반환됩니다. 마찬가지로 **_fileno**호출의 결과 대신 0, 1 또는 2를 파일 설명자 매개 변수로 사용하는 경우 **_get_osfhandle** 파일 설명자가 스트림과 연결되지 않고 **errno를**설정하지 않을 때 특수 값 -2를 반환합니다. 그러나 유효한 파일 핸들 값이 아니며 이 값을 사용하려고 시도하는 후속 호출은 실패할 수 있습니다.

**EBADF** 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하십시오.

## <a name="remarks"></a>설명

**_get_osfhandle**의해 운영 체제 (OS) 파일 핸들을 얻은 파일을 닫려면 파일 설명자 *fd에* [_close](close.md) 호출하십시오. 이 함수의 반환 값에 **CloseHandle을** 호출하지 마십시오. 기본 OS 파일 핸들은 *fd* 파일 설명자가 소유하며 *fd에서* [_close](close.md) 호출될 때 닫힙입니다. 파일 설명자가 `FILE *` 스트림에 의해 소유되는 경우 해당 `FILE *` 스트림에서 [fclose를](fclose-fcloseall.md) 호출하면 파일 설명자와 기본 OS 파일 핸들이 모두 닫힙습니다. 이 경우 파일 설명자에서 [_close](close.md) 호출하지 마십시오.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
