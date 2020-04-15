---
title: strerror, _strerror, _wcserror, __wcserror
description: Microsoft C 런타임 라이브러리(CRT) 함수에 대해 __wcserror _wcserror _strerror 설명합니다.
ms.date: 4/2/2020
api_name:
- strerror
- _strerror
- _wcserror
- __wcserror
- _o___wcserror
- _o__strerror
- _o__wcserror
- _o_strerror
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
ms.openlocfilehash: 9eecb7376cf476f0128dc20c8884746a3b4d47d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337323"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror, _strerror, _wcserror, __wcserror

시스템 오류 메시지 문자열 **(strerror**, **_wcserror)** 또는 사용자 제공 오류 메시지 문자열 **(_strerror**, **__wcserror)의**서식을 가져옵니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char * strerror(
   int errnum );

char * _strerror(
   const char *strErrMsg );

wchar_t * _wcserror(
   int errnum );

wchar_t * __wcserror(
   const wchar_t *strErrMsg );
```

### <a name="parameters"></a>매개 변수

*에러 넘 (주)*\
오류 번호입니다.

*스트러롬스그*\
사용자 제공 메시지

## <a name="return-value"></a>반환 값

이러한 모든 함수는 런타임이 소유한 스레드 로컬 저장소 버퍼에서 오류 메시지 문자열에 대한 포인터를 반환합니다. 나중에 동일한 스레드에서 호출하면 이 문자열을 덮어쓸 수 있습니다.

## <a name="remarks"></a>설명

**strerror** 함수는 *errnum을* 오류 메시지 문자열에 매핑하고 문자열에 대한 포인터를 반환합니다. **strerror** 및 **_strerror** 함수는 실제로 메시지를 인쇄하지 않습니다. 인쇄하려면 [fprintf와](fprintf-fprintf-l-fwprintf-fwprintf-l.md)같은 출력 함수를 호출합니다.

```C
if (( _access( "datafile", 2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

*strErrMsg가* **NULL로**전달되면 **_strerror** 문자열에 대한 포인터를 반환합니다. 여기에는 오류를 생성한 마지막 라이브러리 호출에 대한 시스템 오류 메시지가 포함되어 있습니다. 오류 메시지 문자열은 줄 바꿈 문자('\n')로 종료됩니다. *strErrMsg가* **NULL이**아닌 경우 문자열에는 *strErrMsg* 문자열, 콜론, 공백, 시스템 오류 메시지 및 줄 바선이 포함됩니다. 문자열 메시지는 길이가 94자일 수 있으며,**좁거나(_strerror)** 또는**너비(__wcserror)** 문자일 수 있습니다.

**_strerror** 대한 실제 오류 번호는 변수 [errno에](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)저장됩니다. 정확한 결과를 얻으려면 라이브러리 루틴이 오류를 반환한 직후 **_strerror** 호출합니다. 그렇지 않으면 나중에 라이브러리 루틴을 호출하여 **errno** 값을 덮어쓸 수 있습니다.

**_wcserror** **__wcserror** 각각 **스트러와** **_strerror**와이드 문자 버전입니다.

**_strerror** **_wcserror**및 **__wcserror** 표준 C 라이브러리의 일부가 아닌 Microsoft 관련 입니다. 휴대용 코드를 원하는 곳에 사용하지 않는 것이 좋습니다. 표준 C 호환성을 위해 **strerror를 대신 사용하십시오.**

오류 문자열을 얻으려면 더 이상 사용되지 _sys_errlist 매크로 [및](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 및 사용되지 __sys_errlist 및 **__sys_nerr**내부 **__sys_errlist** 함수 대신 **strerror** 또는 **_wcserror** 것이 좋습니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>일반 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**, **__wcserror**|\<string.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[perror](perror-wperror.md)의 예를 참조하세요.

## <a name="see-also"></a>참고 항목

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)\
[더 선명한](clearerr.md)\
[페더 ()페더 ()](ferror.md)\
[perror, _wperror](perror-wperror.md)
