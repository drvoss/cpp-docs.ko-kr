---
title: _getdcwd, _wgetdcwd
ms.date: 4/2/2020
api_name:
- _getdcwd
- _wgetdcwd
- _o__getdcwd
- _o__wgetdcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
ms.openlocfilehash: 3a4ca8ff3f1153893282c65bc4c2becd687138ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344393"
---
# <a name="_getdcwd-_wgetdcwd"></a>_getdcwd, _wgetdcwd

지정한 드라이브의 현재 작업 디렉터리의 전체 경로를 가져옵니다.

## <a name="syntax"></a>구문

```C
char *_getdcwd(
   int drive,
   char *buffer,
   int maxlen
);
wchar_t *_wgetdcwd(
   int drive,
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>매개 변수

*드라이브*<br/>
드라이브를 지정하는 음수가 아닌 정수입니다(0 = 기본 드라이브, 1 = A, 2 = B 등).

지정된 드라이브를 사용할 수 없거나 드라이브 종류(예: 이동식, 고정, CD-ROM, RAM 디스크 또는 네트워크 드라이브)를 확인할 수 없는 경우 잘못된 매개 변수 처리기가 호출됩니다. 자세한 내용은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)를 참조하세요.

*버퍼*<br/>
경로에 대한 스토리지 위치 또는 **NULL**입니다.

**NULL을** 지정하면 이 함수는 **malloc을**사용하여 최소 *maxlen* 크기의 버퍼를 할당하고 **_getdcwd** 반환 값은 할당된 버퍼에 대한 포인터입니다. 버퍼는 **무료** 호출 하 고 포인터를 전달 하 여 해제될 수 있습니다.

*맥클렌*<br/>
경로의 최대 길이를 문자로 지정하는 비영점 양수 정수: **_getdcwd** 대한 **char** 및 **_wgetdcwd**대한 **wchar_t.**

*maxlen이* 0보다 적거나 같으면 잘못된 매개 변수 처리기가 호출됩니다. 자세한 내용은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)를 참조하세요.

## <a name="return-value"></a>Return Value

지정된 드라이브에서 현재 작업 디렉터리 또는 **NULL의**전체 경로를 나타내는 문자열에 대한 포인터로 오류를 나타냅니다.

*버퍼가* **NULL로** 지정되고 *maxlen* 문자를 할당할 메모리가 부족하면 오류가 발생하고 **errno가** **ENOMEM로**설정됩니다. 종료 null 문자를 포함한 경로의 길이가 *maxlen을*초과하면 오류가 발생하고 **errno가** **ERANGE로**설정됩니다. 이러한 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

**_getdcwd** 함수는 지정된 드라이브에서 현재 작업 디렉터리전체 경로를 가져옵니다. *buffer* 현재 작업 디렉터리가 루트로 설정되는 경우 문자열이 백슬래시(\\)로 끝납니다. 현재 작업 디렉터리가 루트 이외의 디렉터리로 설정되는 경우 문자열은 백슬래시가 아닌 디렉터리의 이름으로 끝납니다.

**_wgetdcwd** **_getdcwd**와이드 문자 버전이며 *버퍼* 매개 변수 및 반환 값은 와이드 문자 문자열입니다. 그렇지 않으면 **_wgetdcwd** **_getdcwd** 동일하게 작동합니다.

이 함수는 자체적으로 스레드로부터 안전하지 않는 **GetFullPathName**에 의존하지만 스레드로부터 안전합니다. 그러나 다중 스레드 애플리케이션에서 이 함수와 [GetFullPathName](/windows/win32/api/fileapi/nf-fileapi-getfullpathnamew)을 모두 호출하는 경우 스레드 안전성을 위반할 수 있습니다.

**_nolock** 접미사가 있는 이 함수의 버전은 스레드로부터 안전하지 않으며 다른 스레드의 간섭으로부터 보호되지 않는다는 점을 제외하고는 이 함수와 동일하게 작동합니다. 자세한 내용은 [_getdcwd_nolock, _wgetdcwd_nolock](getdcwd-nolock-wgetdcwd-nolock.md)을 참조하세요.

**_DEBUG** 및 **_CRTDBG_MAP_ALLOC** 정의되면 **_getdcwd** 및 **_wgetdcwd** 대한 호출이 **_getdcwd_dbg** 및 **_wgetdcwd_dbg** 대한 호출로 대체되어 메모리 할당을 디버깅할 수 있습니다. 자세한 내용은[_getdcwd_dbg, _wgetdcwd_dbg](getdcwd-dbg-wgetdcwd-dbg.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_getdcwd**|\<direct.h>|
|**_wgetdcwd**|\<direct.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_getdrive](getdrive.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
