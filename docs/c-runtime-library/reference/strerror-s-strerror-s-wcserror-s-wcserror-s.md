---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s
ms.date: 4/2/2020
api_name:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
- _o__strerror_s
- _o__wcserror_s
- _o_strerror_s
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
- wcserror_s
- __wcserror_s
- _tcserror_s
- _wcserror_s
- tcserror_s
- strerror_s
- _strerror_s
helpviewer_keywords:
- __wcserror_s function
- error messages, printing
- tcserror_s function
- printing error messages
- strerror_s function
- _wcserror_s function
- _tcserror_s function
- _strerror_s function
- wcserror_s function
- error messages, getting
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
ms.openlocfilehash: ef712ecb6236513d169b4a8836b1365b0aca0633
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337362"
---
# <a name="strerror_s-_strerror_s-_wcserror_s-__wcserror_s"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

시스템 오류 메시지 **(strerror_s**, **_wcserror_s)를**얻거나 사용자 제공 오류 메시지 **(_strerror_s**, **__wcserror_s)를**인쇄합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t strerror_s(
   char *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t _strerror_s(
   char *buffer,
   size_t numberOfElements,
   const char *strErrMsg
);
errno_t _wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t __wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *strErrMsg
);
template <size_t size>
errno_t strerror_s(
   char (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t _strerror_s(
   char (&buffer)[size],
   const char *strErrMsg
); // C++ only
template <size_t size>
errno_t _wcserror_s(
   wchar_t (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t __wcserror_s(
   wchar_t (&buffer)[size],
   const wchar_t *strErrMsg
); // C++ only
```

### <a name="parameters"></a>매개 변수

*버퍼*<br/>
오류 문자열을 저장할 버퍼입니다.

*숫자오브엘리먼트*<br/>
버퍼의 크기입니다.

*에러 넘 (주)*<br/>
오류 번호입니다.

*스트러롬스그*<br/>
사용자 제공 메시지

## <a name="return-value"></a>Return Value

성공시 0, 실패시 오류 코드.

### <a name="error-condtions"></a>오류 조건

|*버퍼*|*숫자오브엘리먼트*|*스트러롬스그*|*버퍼의* 내용|
|--------------|------------------------|-----------------|--------------------------|
|**Null**|any|any|해당 없음|
|any|0|any|수정 안 됨|

## <a name="remarks"></a>설명

**strerror_s** 함수는 *errnum을* 오류 메시지 문자열에 매핑하여 *버퍼에서*문자열을 반환합니다. **_strerror_s** 오류 번호를 받지 않습니다. **errno의** 현재 값을 사용하여 적절한 메시지를 결정합니다. **strerror_s** **_strerror_s** 실제로 메시지를 인쇄하지 않습니다: 이를 위해 [fprintf와](fprintf-fprintf-l-fwprintf-fwprintf-l.md)같은 출력 함수를 호출해야합니다.

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

*strErrMsg가* **NULL인**경우 **_strerror_s** 오류를 생성한 마지막 라이브러리 호출에 대한 시스템 오류 메시지를 포함하는 *버퍼의* 문자열을 반환합니다. 오류 메시지 문자열은 줄 바꿈 문자('\n')로 종료됩니다. *strErrMsg가* **NULL과**같지 않은 경우 **_strerror_s** 문자열 메시지, 콜론, 공간, 오류를 생성하는 마지막 라이브러리 호출에 대한 시스템 오류 메시지 및 줄 바선 문자를 포함하는 *버퍼의 문자열을* 반환합니다. 문자열 메시지는 94자 이하여야 합니다.

이러한 함수는 길이가 *숫자를* 초과하는 경우 오류 메시지를 트렁킨다OfElements -1. *버퍼의* 결과 문자열은 항상 null-종료됩니다.

**_strerror_s** 대한 실제 오류 번호는 변수 [errno에](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)저장됩니다. [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수를 통해 시스템 오류 메시지에 액세스합니다. 이 변수는 오류 번호순으로 정렬된 메시지 배열입니다. **_strerror_s** **errno** 값을 변수 **_sys_errlist**인덱스로 사용하여 적절한 오류 메시지에 액세스합니다. 변수 [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 값은 **_sys_errlist** 배열의 최대 요소 수로 정의됩니다. 정확한 결과를 얻으려면 라이브러리 루틴이 오류와 함께 반환된 직후 **_strerror_s** 호출합니다. 그렇지 않으면 **strerror_s** 또는 **_strerror_s** 대한 후속 호출은 **errno** 값을 덮어쓸 수 있습니다.

**_wcserror_s** **__wcserror_s** 각각 **strerror_s** **_strerror_s**와이드 문자 버전입니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 버퍼가 **NULL이거나** 크기 매개 변수가 0인 경우 매개 변수 유효성 [검사에](../../c-runtime-library/parameter-validation.md) 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 함수는 **EINVAL을** 반환하고 **errno를** **EINVAL로**설정합니다.

**_strerror_s**, **_wcserror_s**및 **__wcserror_s** ANSI 정의의 일부가 아니라 대신 Microsoft 확장입니다. 이식성이 필요한 곳에는 사용하지 마십시오. ANSI 호환성을 위해 **대신 strerror_s** 사용하십시오.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

이러한 함수의 디버그 라이브러리 버전은 먼저 버퍼를 0xFE로 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<string.h>|
|**_wcserror_s,** **__wcserror_s**|\<string.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[perror](perror-wperror.md)의 예를 참조하세요.

## <a name="see-also"></a>참고 항목

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
