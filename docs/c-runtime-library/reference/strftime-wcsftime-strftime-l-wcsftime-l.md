---
title: strftime, wcsftime, _strftime_l, _wcsftime_l
ms.date: 4/2/2020
api_name:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
- _o__strftime_l
- _o__wcsftime_l
- _o_strftime
- _o_wcsftime
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
- _tcsftime
- strftime
- wcsftime
- _strftime_l
- _wcsftime_l
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
ms.openlocfilehash: 5da2c128c54fd88bb874b360f5a966f17b14a935
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350014"
---
# <a name="strftime-wcsftime-_strftime_l-_wcsftime_l"></a>strftime, wcsftime, _strftime_l, _wcsftime_l

시간 문자열 서식을 지정합니다.

## <a name="syntax"></a>구문

```C
size_t strftime(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr
);
size_t _strftime_l(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr,
   _locale_t locale
);
size_t wcsftime(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr
);
size_t _wcsftime_l(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*스트레스트*<br/>
출력 문자열입니다.

*Maxsize*<br/>
문자로 측정된 *strDest* 버퍼의**크기(char** 또는 **wchar_t)입니다.**

*형식*<br/>
형식 컨트롤 문자열입니다.

*timeptr*<br/>
**tm** 데이터 구조.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**strftime은** *strDest에* 배치된 문자 수를 반환하고 **wcsftime은** 해당 와이드 문자 수를 반환합니다.

null 종료를 포함하여 총 문자 수가 *최대 크기보다*많으면 **strftime** 및 **wcsftime** return 0과 *strDest의* 내용이 모두 확정되지 않습니다.

*strDest의* 문자 수는 *형식의* 리터럴 문자 수와 서식 코드를 통해 *형식에* 추가할 수 있는 모든 문자와 같습니다. 문자열의 종료 null은 반환 값 계산에 포함되지 않습니다.

## <a name="remarks"></a>설명

**strftime** 및 **wcsftime** 함수는 제공된 *형식* 인수에 따라 **tm** 시간 값을 *timeptr로* 포맷하고 결과를 버퍼 *strDest에*저장합니다. 최대 *크기* 문자는 문자열에 배치됩니다. *timeptr* 구조의 필드에 대한 설명은 [asctime](asctime-wasctime.md)을 참조하십시오. **wcsftime은** **스트프타임과**동등한 와이드 문자입니다. 문자열 포인터 인수는 와이드 문자 문자열을 가리킵니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. *strDest*, *format*또는 *timeptr이* null 포인터이거나 *timeptr에서* 주소가 지정된 **tm** 데이터 구조가 유효하지 않은 경우(예: 시간 또는 날짜에 대한 범위를 벗어난 값이 포함된 경우) *format* 문자열에 잘못된 서식 지정 코드가 포함되어 있는 경우 매개 변수 [유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 함수는 0을 반환하고 **errno를** **EINVAL로**설정합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsftime**|**strftime**|**strftime**|**wcsftime**|

*형식* 인수는 하나 이상의 코드로 구성됩니다. **printf에서와**같이 서식 지정 코드 앞에 백분율**%** 기호()가 옵니다. 시작하지 않는 **%** 문자는 *strDest에*변경되지 않고 복사됩니다. 현재 로캘의 **LC_TIME** 범주는 **strftime의**출력 서식에 영향을 줍니다. (LC_TIME 대한 **LC_TIME**자세한 내용은 [setlocale를](setlocale-wsetlocale.md)참조하십시오. **strftime** 및 **wcsftime** 함수는 현재 설정된 로캘을 사용합니다. 이러한 함수의 **_strftime_l** **및 _wcsftime_l** 버전은 로캘을 매개 변수로 사용하고 현재 설정된 로캘 대신 해당 함수를 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

**strftime** 함수는 다음 서식 지정 코드를 지원합니다.

|||
|-|-|
|코드|바꾸기 문자열|
|**%a**|로캘의 축약된 요일 이름|
|**%A**|로캘의 전체 요일 이름|
|**%b**|로캘의 축약된 월 이름|
|**%B**|로캘의 전체 월 이름|
|**%c**|로캘에 적합한 날짜 및 시간 표현|
|**%C**|연도를 100으로 나누고 정수로 분할하여 소수점 수(00−99)로 분할|
|**%d**|소수자릿수로 월의 일 (01 - 31)|
|**%D**|**%m/%d/%y에** 해당|
|**%e**|한 자리 앞에 공백이 있는 소수 자릿수(1 - 31)로 월의 일|
|**%F**|**%Y%m%d에** 해당|
|**%g**|ISO 8601 주 기준 연도의 마지막 2자리(00 - 99)로|
|**%G**|ISO 8601 주 기준 연도 소수점 수|
|**%h**|축약된 월 **이름(%b에**해당)|
|**%H**|24시간 형식의 시간(00 - 23)|
|**%I**|12시간 형식의 시간(01 - 12)|
|**%j**|소수 자릿수로 올해의 일 (001 - 366)|
|**%m**|소수자릿수로 월 (01 - 12)|
|**%M**|소수 자릿수로 분 (00 - 59)|
|**%n**|줄 바호 문자 **(\n)**|
|**%p**|로케일오전/오후 12시간제 표시기|
|**%r**|로캘의 12시간 시계 시간|
|**%R**|**%H:M에** 해당|
|**%S**|소수 자릿수로 두 번째(00 - 59)|
|**%t**|가로 탭 문자 **(\t)**|
|**%T**|**%H:%M:%S,** ISO 8601 시간 형식에 해당|
|**%u**|ISO 8601 을 소수 자릿수로 (1 - 7; 월요일은 1)|
|**%U**|첫 번째 일요일이 주 1의 첫 번째 날인 소수점 수(00 - 53)로 연도의 주 수|
|**%V**|ISO 8601 주 수 소수자릿수(00 - 53)|
|**%w**|평일(0 - 6; 일요일은 0)|
|**%W**|첫 번째 월요일이 주 1의 첫 번째 날인 소수점 수(00 - 53)로 연도의 주 수|
|**%x**|로캘의 날짜 표현|
|**%X**|로캘에 대한 시간 표현|
|**%y**|세기가 없는 연도, 소수자릿수(00 - 99)|
|**%Y**|세기 포함 10진수 연도|
|**%z**|ISO 8601 형식의 UTC의 오프셋; 표준 시간대를 알 수 없는 경우 문자 없음|
|**%Z**|레지스트리 설정에 따라 로캘의 표준 시간대 이름 또는 표준 시간대 약어입니다. 표준 시간대를 알 수 없는 경우 문자 없음|
|**%%**|퍼센트 기호|

**printf** 함수에서와 같이 **#** 플래그는 모든 서식 지정 코드를 접두사로 지정할 수 있습니다. 이 경우의 서식 코드 의미는 다음과 같이 변경됩니다.

|코드 형식|의미|
|-----------------|-------------|
|**% #a**%, **%#A**, **% #b #A**, #B **%#g**, **%#G**, **% #G**, **% #h**, % **#n**, **% #p**, % #t , % **#u**, **% #u**%, **%#w**, **%#X #z**, **%#Z** **%#Z****%#%**|**#** 플래그가 무시됩니다.|
|**%#c**|로캘에 적합한 긴 날짜 및 시간 표현입니다. 예를 들면 "1995년 3월 14일 화요일 12:41:29"와 같습니다.|
|**%#x**|로캘에 적합한 긴 날짜 표현입니다. 예를 들면 "1995년 3월 14일 화요일"과 같습니다.|
|**%#d**%, **%#D**%, **%#e**, **#F**, **% #H**, % #I , **%#j #I**, **%#m**, % #M , % **#r**, **% #R**%, **%#R**, **%#S #T**, **%#j** **%#U**, **%#V**, %#W , **%#T** **%#y**#Y **%#y** **%#Y**|선행 영점 또는 공백(있는 경우)을 제거합니다.|

**%V,** **%g**및 **%G로**생산되는 ISO 8601 주 및 주 기준 연도는 월요일에 시작되는 주를 사용하며, 여기서 1주차는 1월 4일을 포함하는 주이며, 이는 일년 중 적어도 4일을 포함하는 첫 번째 주입니다. 연도의 첫 번째 월요일이 2일, 3일 또는 4일인 경우 이전 일은 이전 연도의 마지막 주에 일부입니다. 이 경우 **%V는** 53으로 대체되고 **%g와** **%G는** 모두 전년도의 숫자로 대체됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strftime**|\<time.h>|
|**wcsftime**|\<time.h> 또는 \<wchar.h>|
|**_strftime_l**|\<time.h>|
|**_wcsftime_l**|\<time.h> 또는 \<wchar.h>|

**_strftime_l** 및 **_wcsftime_l** 기능은 Microsoft에 만연합니다. 호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[time](time-time32-time64.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[로캘](../../c-runtime-library/locale.md) <br/>
[시간 관리](../../c-runtime-library/time-management.md) <br/>
[문자열 조작](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](localeconv.md) <br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md) <br/>
[스트콜 함수](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
