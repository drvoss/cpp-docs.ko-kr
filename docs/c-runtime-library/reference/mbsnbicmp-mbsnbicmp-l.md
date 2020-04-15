---
title: _mbsnbicmp, _mbsnbicmp_l
ms.date: 4/2/2020
api_name:
- _mbsnbicmp_l
- _mbsnbicmp
- _o__mbsnbicmp
- _o__mbsnbicmp_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _mbsnbicmp_l
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
ms.openlocfilehash: 80d2708396cdaeb86c25932c3d13129fb318719a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340573"
---
# <a name="_mbsnbicmp-_mbsnbicmp_l"></a>_mbsnbicmp, _mbsnbicmp_l

두 개의 다중 바이트 문자열의 **n** 바이트를 비교 하 고 대/소문자를 무시 합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _mbsnbicmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>매개 변수

*문자열1,* *문자열2*<br/>
비교할 Null 종료 문자열입니다.

*count*<br/>
비교할 바이트 수입니다.

## <a name="return-value"></a>Return Value

반환 값은 부분 문자열 간의 관계를 나타냅니다.

|반환 값|Description|
|------------------|-----------------|
|< 0|*문자열1* 하위 문자열보다 적은 *문자열2* 하위 문자열입니다.|
|0|*string1* 하위 문자열과 동일한 *문자열2* 하위 문자열입니다.|
|> 0|*문자열1* *문자열2* 하위 문자열보다 큰 문자열입니다.|

오류가 발생하면 **_mbsnbicmp** String.h 및 Mbstring.h에 정의된 **_NLSCMPERROR**반환합니다.

## <a name="remarks"></a>설명

**_mbsnbicmp** 함수는 *string1* 및 *string2의*첫 번째 *카운트* 바이트에서 가장 많은 수의 서수 비교를 수행합니다. 비교는 각 문자를 소문자로 변환하여 수행됩니다. [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) **_mbsnbicmp**. *카운트* 문자를 비교하기 전에 종료 null 문자가 두 문자열 중 하나에 도달하면 비교가 종료됩니다. *카운트* 문자를 비교하기 전에 종결 null 문자에 도달할 때 문자열이 같으면 짧은 문자열이 작습니다.

**_mbsnbicmp** 문자열을 문자 대신 *바이트* 수로 비교한다는 점을 제외하면 [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)유사합니다.

ASCII 테이블의 'Z'와 'a' 사이에 있는 문자('[', '\\', ']', '^', '_' 및 '\`')를 포함하는 두 문자열은 대소문자에 따라 서로 다른 방식으로 비교됩니다. 예를 들어 두 문자열 "ABCDE" 및 "ABCD^"는 비교가 소문자("abcde" > "abcd^")인 경우 한 가지 방법을 비교하고 다른 방법("ABCDE" < "ABCD^")을 비교합니다.

**_mbsnbicmp** 현재 사용 중인 다중 바이트 코드 페이지에 따라 [다중 바이트](../../c-runtime-library/code-pages.md) 문자 시퀀스를 인식합니다. 현재 로캘 설정은 적용되지 않습니다.

*string1* 또는 *string2가* null 포인터인 경우 **_mbsnbicmp** 매개 변수 유효성 검사에 설명된 대로 잘못된 매개 변수 처리기를 [호출합니다.](../../c-runtime-library/parameter-validation.md) 실행을 계속할 수 있는 경우 함수는 **_NLSCMPERROR** 반환하고 **errno를** **EINVAL로**설정합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbsnbicmp**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
