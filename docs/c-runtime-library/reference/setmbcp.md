---
title: _setmbcp
ms.date: 4/2/2020
api_name:
- _setmbcp
- _o__setmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _setmbcp
- setmbcp
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
ms.openlocfilehash: 61086471c6194aaa8434d291647978bf891a8aea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337598"
---
# <a name="_setmbcp"></a>_setmbcp

새 멀티바이트 코드 페이지를 설정합니다.

## <a name="syntax"></a>구문

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>매개 변수

*코드 페이지*<br/>
로캘 독립적인 멀티바이트 루틴에 대한 새 코드 페이지 설정입니다.

## <a name="return-value"></a>Return Value

코드 페이지가 올바르게 설정되면 0을 반환합니다. 코드 *페이지에*대해 잘못된 코드 페이지 값이 제공되면 -1을 반환하고 코드 페이지 설정은 변경되지 않습니다. 메모리 할당 오류가 발생하면 **errno를** **EINVAL로** 설정합니다.

## <a name="remarks"></a>설명

**_setmbcp** 함수는 새 다중 바이트 코드 페이지를 지정합니다. 기본적으로 런타임 시스템은 멀티바이트 코드 페이지를 시스템 기본 ANSI 코드 페이지로 자동 설정합니다. 멀티바이트 코드 페이지 설정은 로캘에 종속되지 않는 모든 멀티바이트 루틴에 적용됩니다. 그러나 **_setmbcp** 현재 로캘에 대해 정의된 코드 페이지를 사용하도록 지시할 수 있습니다(다음 매니페스트 상수 및 관련 동작 결과 목록 참조). 멀티바이트 코드 페이지가 아닌 로캘 코드 페이지를 사용하는 멀티바이트 루틴의 목록은 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)을 참조하세요.

멀티바이트 코드 페이지는 다음 런타임 라이브러리 루틴의 멀티바이트 문자 처리에도 영향을 줍니다.

||||
|-|-|-|
|[_exec 함수](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_spawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

또한 다중 바이트 문자 *argv* 또는 *envp* 프로그램 인수를 매개 변수(예: **_exec** 및 **_spawn** 패밀리)로 수신하는 모든 런타임 라이브러리 루틴은 멀티바이트 코드 페이지에 따라 이러한 문자열을 처리합니다. 따라서 이러한 루틴은 다중 바이트 코드 페이지를 변경하는 **_setmbcp** 호출의 영향을 받습니다.

*코드 페이지* 인수를 다음 값 중 으로 설정할 수 있습니다.

- **_MB_CP_ANSI** 프로그램 시작 시 운영 체제에서 얻은 ANSI 코드 페이지를 사용합니다.

- **_MB_CP_LOCALE** [setlocale에](setlocale-wsetlocale.md)이전 호출에서 얻은 현재 로캘의 코드 페이지를 사용 합니다.

- **_MB_CP_OEM** 프로그램 시작 시 운영 체제에서 얻은 OEM 코드 페이지를 사용합니다.

- **_MB_CP_SBCS** 단일 바이트 코드 페이지를 사용합니다. 코드 페이지가 **_MB_CP_SBCS**설정되면 [_ismbblead](ismbblead-ismbblead-l.md) 같은 루틴은 항상 false를 반환합니다.

- **_MB_CP_UTF8** UTF-8을 사용하십시오.  코드 페이지가 **_MB_CP_UTF8**설정되면 [_ismbblead](ismbblead-ismbblead-l.md) 같은 루틴은 항상 false를 반환합니다.

- 값이 ANSI, OEM 또는 기타 운영 체제 지원 코드 페이지인지 여부에 관계없이 다른 유효한 코드 페이지 값입니다(지원되지 않는 UTF-7 제외).

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_setmbcp**|\<mbctype.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
