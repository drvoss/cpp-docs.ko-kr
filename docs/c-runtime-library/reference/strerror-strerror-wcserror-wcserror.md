---
title: strerror, _strerror, _wcserror, __wcserror
description: Microsoft CRT (C 런타임 라이브러리) 함수 strerror, _strerror, _wcserror 및 __wcserror에 대해 설명 합니다.
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 30885974b9c9fbf0fdca0e52808fb8bd1dfbaffe
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920029"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror, _strerror, _wcserror, __wcserror

시스템 오류 메시지 문자열 (**strerror**, **_wcserror**)을 가져오거나 사용자가 제공한 오류 메시지 문자열의 형식을 지정 합니다 (**_strerror**, **__wcserror**). 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md)를 참조하세요.

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

*errnum*\
오류 번호입니다.

*strErrMsg*\
사용자 제공 메시지

## <a name="return-value"></a>반환 값

이러한 모든 함수는 런타임에 소유 하는 스레드 로컬 저장소 버퍼에서 오류 메시지 문자열에 대 한 포인터를 반환 합니다. 나중에 동일한 스레드에서를 호출 하면이 문자열을 덮어쓸 수 있습니다.

## <a name="remarks"></a>설명

**Strerror** 함수는 *errnum* 을 오류 메시지 문자열로 매핑하고 해당 문자열에 대 한 포인터를 반환 합니다. **Strerror** 및 **_strerror** 함수는 실제로 메시지를 인쇄 하지 않습니다. 인쇄 하려면 [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)와 같은 출력 함수를 호출 합니다.

```C
if (( _access( "datafile", 2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

*StrErrMsg* 가 **NULL**로 전달 되는 경우 **_strerror** 는 문자열에 대 한 포인터를 반환 합니다. 오류를 생성 한 마지막 라이브러리 호출에 대 한 시스템 오류 메시지를 포함 합니다. 오류 메시지 문자열은 줄 바꿈 문자('\n')로 종료됩니다. *StrErrMsg* 가 **NULL**이 아닌 경우 문자열에는 *strErrMsg* 문자열, 콜론, 공백, 시스템 오류 메시지 및 줄 바꿈 문자가 순서 대로 포함 됩니다. 문자열 메시지의 길이는 최대 94 자이 하 여야 하 고 길이는 좁은 (**_strerror**) 또는 와이드 문자 (**__wcserror**)입니다.

**_Strerror** 의 실제 오류 번호는 변수 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)에 저장 됩니다. 정확한 결과를 생성 하려면 라이브러리 루틴이 오류를 반환한 후 즉시 **_strerror** 를 호출 합니다. 그렇지 않으면 나중에 라이브러리 루틴을 호출 하 여 **errno** 값을 덮어쓸 수 있습니다.

**_wcserror** 및 **__wcserror** 는 각각 **strerror** 및 **_strerror**의 와이드 문자 버전입니다.

**_strerror**, **_wcserror**및 **__Wcserror** 은 Microsoft 전용 이며 표준 C 라이브러리의 일부가 아닙니다. 이식 가능한 코드를 원하는 위치에 사용 하지 않는 것이 좋습니다. 표준 C 호환성의 경우 **strerror** 를 대신 사용 합니다.

오류 문자열을 얻으려면 사용 되지 않는 매크로 [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 및 [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 및 사용 되지 않는 내부 함수 **__sys_errlist** 및 **__sys_nerr**대신 **strerror** 또는 **_wcserror** 를 사용 하는 것이 좋습니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

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

## <a name="see-also"></a>참조

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)\
[clearerr](clearerr.md)\
[ferror](ferror.md)\
[perror, _wperror](perror-wperror.md)
