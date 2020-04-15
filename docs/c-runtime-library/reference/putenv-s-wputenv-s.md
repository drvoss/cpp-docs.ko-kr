---
title: _putenv_s, _wputenv_s
ms.date: 4/2/2020
api_name:
- _wputenv_s
- _putenv_s
- _o__putenv_s
- _o__wputenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
ms.openlocfilehash: f0164feed05b409ba29ca713f11f4f3323dbaac3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338398"
---
# <a name="_putenv_s-_wputenv_s"></a>_putenv_s, _wputenv_s

환경 변수를 생성, 수정 또는 제거합니다. 이러한 버전의 [_putenv, _wputenv](putenv-wputenv.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 향상된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t _putenv_s(
   const char *varname,
   const char *value_string
);
errno_t _wputenv_s(
   const wchar_t *varname,
   const wchar_t *value_string
);
```

### <a name="parameters"></a>매개 변수

*바르나메*<br/>
환경 변수 이름입니다.

*value_string*<br/>
환경 변수를 설정할 값입니다.

## <a name="return-value"></a>Return Value

성공하면 0을 반환하고, 그렇지 않으면 오류 코드를 반환합니다.

### <a name="error-conditions"></a>오류 조건

|*바르나메*|*value_string*|반환 값|
|------------|-------------|------------------|
|**Null**|any|**아인발 ()에인발 (것)**|
|any|**Null**|**아인발 ()에인발 (것)**|

오류 조건 중 하나가 발생할 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이러한 함수는 **EINVAL을** 반환하고 **errno를** **EINVAL로**설정합니다.

## <a name="remarks"></a>설명

**_putenv_s** 함수는 새 환경 변수를 추가하거나 기존 환경 변수의 값을 수정합니다. 환경 변수는 프로세스가 실행되는 환경을 정의합니다(예: 프로그램에 연결할 라이브러리의 기본 검색 경로). **_wputenv_s** **_putenv_s**와이드 문자 버전입니다. **_wputenv_s** *envstring* 인수는 와이드 문자 문자열입니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tputenv_s**|**_putenv_s**|**_putenv_s**|**_wputenv_s**|

*varname은* 추가하거나 수정할 환경 변수의 이름이며 *value_string* 변수값입니다. *varname이* 이미 환경의 일부인 경우 해당 값은 *value_string*대체됩니다. 그렇지 않으면 새 *varname* 변수와 *해당 value_string* 환경에 추가됩니다. *value_string*대한 빈 문자열(즉, "")을 지정하여 환경에서 변수를 제거할 수 있습니다.

**_putenv_s** 및 **_wputenv_s** 현재 프로세스에 로컬인 환경에만 영향을 미칩니다. 명령 수준 환경을 수정하는 데 사용할 수 없습니다. 이러한 함수는 운영 체제가 프로세스에 대해 만드는 환경 "세그먼트"가 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조에서만 작동합니다. 현재 프로세스가 종료되면 환경이 호출 프로세스의 수준(대부분의 경우 운영 체제 수준)으로 되돌아갑니다. 그러나 수정된 환경은 **_spawn,** **_exec**또는 **시스템에**의해 생성되는 모든 새 프로세스에 전달될 수 있으며 이러한 새 프로세스는 **_putenv_s** 및 **_wputenv_s**의해 추가되는 새 항목을 가져옵니다.

환경 항목을 직접 변경하지 마십시오. 대신 **_putenv_s** 사용하거나 **_wputenv_s** 사용하여 변경합니다. 특히 **_environ[]** 전역 배열의 요소를 직접 해제하면 잘못된 메모리가 해결될 수 있습니다.

**getenv** 및 **_putenv_s** 전역 변수 **_environ** 사용하여 환경 테이블에 액세스합니다. **_wgetenv** **_wputenv_s** **_wenviron**사용합니다. **_putenv_s** **_wputenv_s** **_environ** **_wenviron**값을 변경할 수 있으며, 따라서 *envp* 인수를 **main으로** 무효화하고 **_wenvp** 인수를 **wmain**. 따라서 **_environ** 사용하거나 **_wenviron** 사용하여 환경 정보에 액세스하는 것이 더 안전합니다. **_putenv_s** 및 **_wputenv_s** 전역 변수와의 관계에 대한 자세한 내용은 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)를 참조하십시오.

> [!NOTE]
> **함수의 _putenv_s** 및 **_getenv_s** 패밀리는 스레드에서 안전하지 않습니다. **_getenv_s** _putenv_s 문자열을 수정하는 **동안** 문자열 포인터를 반환할 수 있으므로 임의 오류가 발생할 수 있습니다. 이러한 함수에 대한 호출은 동기화해야 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_putenv_s**|\<stdlib.h>|
|**_wputenv_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

**_putenv_s**사용하는 방법을 보여 주는 샘플은 [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
