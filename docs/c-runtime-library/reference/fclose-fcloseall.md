---
title: fclose, _fcloseall
ms.date: 4/2/2020
api_name:
- fclose
- _fcloseall
- _o__fcloseall
- _o_fclose
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
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: b2ee14c5fc8bb47cc2652443c0263bd14147c90d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347485"
---
# <a name="fclose-_fcloseall"></a>fclose, _fcloseall

**스트림(fclose)을**닫거나 모든 오픈**스트림(_fcloseall)을**닫습니다.

## <a name="syntax"></a>구문

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

**스트림이** 성공적으로 닫히면 fclose0을 반환합니다. **_fcloseall** 닫힌 스트림의 총 수를 반환합니다. 두 함수 모두 오류를 나타내기 위해 **EOF를** 반환합니다.

## <a name="remarks"></a>설명

**프close** 함수는 *스트림을*닫습니다. *스트림이* **NULL인**경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 **fclose는** **errno를** **EINVAL로** 설정하고 **EOF를**반환합니다. 이 함수를 호출하기 전에 *항상 스트림* 포인터를 확인하는 것이 좋습니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

**_fcloseall** 함수는 **stdin,** **stdout,** **stderr** (및 MS-DOS, **_stdaux** 및 **_stdprn)를**제외한 모든 열린 스트림을 닫습니다. 또한 **tmpfile에**의해 생성 된 임시 파일을 닫고 삭제합니다. 두 함수에서 모두 스트림과 연결된 모든 버퍼가 플러시된 후 닫힙니다. 시스템 할당 버퍼는 스트림이 닫힐 때 해제됩니다. **setbuf** 및 **setvbuf를** 사용 하 여 사용자가 할당 하는 버퍼는 자동으로 해제 되지 않습니다.

**참고:** 이러한 함수를 사용하여 스트림을 닫으면 기본 파일 설명자와 OS 파일 핸들(또는 소켓)이 닫히고 스트림도 닫힙니다. 따라서 파일이 원래 파일 핸들 또는 파일 설명자로 열렸고 **fclose으로**닫힌 경우 **_close** 호출하여 파일 설명기를 닫지 마십시오. 파일 핸들을 닫기 위해 Win32 함수 **CloseHandle을** 호출하지 마십시오.

**다른** 스레드의 간섭으로부터 보호하기 위한 코드가 포함되어 **_fcloseall.** **fclose의**비잠금 버전은 **_fclose_nolock**를 참조하십시오.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fclose**|\<stdio.h>|
|**_fcloseall**|\<stdio.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[fopen](fopen-wfopen.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
