---
title: _get_tzname
ms.date: 4/2/2020
api_name:
- _get_tzname
- _o__get_tzname
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_tzname
- get_tzname
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
ms.openlocfilehash: 50f1f6e4320e3ef905b4eda67ba1d458a5b1df08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344882"
---
# <a name="_get_tzname"></a>_get_tzname

표준 시간대 이름 또는 일광 표준 시간대 이름(DST)의 문자열 표현을 검색합니다.

## <a name="syntax"></a>구문

```C
errno_t _get_tzname(
    size_t* pReturnValue,
    char* timeZoneName,
    size_t sizeInBytes,
    int index
);
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
null 터미네이터를 포함하는 *timeZoneName의* 문자열 길이입니다.

*시간대 이름*<br/>
*인덱스에*따라 표준 시간대 이름 또는 일광 표준 표준 표준 시간대 이름(DST)을 표현하기 위한 문자 문자열의 주소입니다.

*sizeInBytes*<br/>
*timeZoneName* 문자열의 크기입니다.

*index*<br/>
검색할 두 표준 시간대 이름 중 하나의 인덱스입니다.

|*index*|*시간대의 내용존이름*|*시간영역이름* 기본값|
|-|-|-|
|0|표준 시간대 이름|"PST"|
|1|일광 표준 시간대 이름|"PDT"|
|> 1 또는 < 0|**에르노는** **아인발로** 설정|수정 안 됨|

런타임에 값을 명시적으로 변경하는 경우가 아니면 기본값은 각각 "PST" 및 "PDT"입니다.

## <a name="return-value"></a>Return Value

성공하면 0, 그렇지 않으면 **errno** 형식 값입니다.

*timeZoneName이* **NULL이거나** *sizeInBytes가* 0이거나 0보다 작으면(둘 다 아님) 매개 변수 유효성 [검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 이 함수는 **errno를** **EINVAL로** 설정하고 **EINVAL**을 반환합니다.

### <a name="error-conditions"></a>오류 조건

|*pReturnValue*|*시간대 이름*|*sizeInBytes*|*index*|반환 값|*시간대의 내용존이름*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|TZ 이름의 크기|**Null**|0|0 또는 1|0|수정 안 됨|
|TZ 이름의 크기|any|> 0|0 또는 1|0|TZ 이름|
|수정 안 됨|**Null**|> 0|any|**아인발 ()에인발 (것)**|수정 안 됨|
|수정 안 됨|any|0|any|**아인발 ()에인발 (것)**|수정 안 됨|
|수정 안 됨|any|> 0|> 1|**아인발 ()에인발 (것)**|수정 안 됨|

## <a name="remarks"></a>설명

**_get_tzname** 함수는 현재 표준 시간대 이름 또는 일광 표준 표준 표준 시간대 이름(DST)의 문자열 표현을 인덱스 값에 따라 *timeZoneName의* 주소로 검색하고 *pReturnValue의*문자열 크기를 검색합니다. *timeZoneName이* **NULL이고** *sizeInBytes가* 0인 경우 지정된 표준 시간대를 유지하는 데 필요한 문자열의 크기와 바이트 단위로 종료null이 *pReturnValue*에서 반환됩니다. 인덱스 값은 표준 표준 시간대의 경우 0이거나 일광 표준 표준 시간대의 경우 1이어야 합니다. *인덱스의* 다른 값에는 결정되지 않은 결과가 있습니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="example"></a>예제

This sample calls **_get_tzname** to get the required buffer size to display the current Daylight standard time zone name, allocates a buffer of that size, calls **_get_tzname** again to load the name in the buffer, and prints it to the console.

```C
// crt_get_tzname.c
// Compile by using: cl /W4 crt_get_tzname.c
#include <stdio.h>
#include <time.h>
#include <malloc.h>

enum TZINDEX {
    STD,
    DST
};

int main()
{
    size_t tznameSize = 0;
    char * tznameBuffer = NULL;

    // Get the size of buffer required to hold DST time zone name
    if (_get_tzname(&tznameSize, NULL, 0, DST))
        return 1;    // Return an error value if it failed

    // Allocate a buffer for the name
    if (NULL == (tznameBuffer = (char *)(malloc(tznameSize))))
        return 2;    // Return an error value if it failed

    // Load the name in the buffer
    if (_get_tzname(&tznameSize, tznameBuffer, tznameSize, DST))
        return 3;    // Return an error value if it failed

    printf_s("The current Daylight standard time zone name is %s.\n", tznameBuffer);
    return 0;
}
```

### <a name="output"></a>출력

```Output
The current Daylight standard time zone name is PDT.
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
