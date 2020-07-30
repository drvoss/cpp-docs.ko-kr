---
title: ':::no-loc(strtol):::, :::no-loc(wcstol):::, :::no-loc(_strtol_l):::, :::no-loc(_wcstol_l):::'
ms.date: 4/2/2020
api_name:
- ':::no-loc(strtol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_wcstol_l):::'
- '_o_:::no-loc(_strtol_l):::'
- '_o_:::no-loc(_wcstol_l):::'
- '_o_:::no-loc(strtol):::'
- '_o_:::no-loc(wcstol):::'
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ':::no-loc(_wcstol_l):::'
- ':::no-loc(strtol):::'
- ':::no-loc(_tcstol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_tcstol_l):::'
helpviewer_keywords:
- ':::no-loc(wcstol)::: function'
- :::no-loc(wcstol):::_l function
- ':::no-loc(_tcstol)::: function'
- string conversion, to integers
- tcstol function
- :::no-loc(strtol):::_l function
- ':::no-loc(_wcstol_l)::: function'
- ':::no-loc(_strtol_l)::: function'
- ':::no-loc(strtol)::: function'
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
no-loc:
- ':::no-loc(strtol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_wcstol_l):::'
- ':::no-loc(LONG_MAX):::'
- ':::no-loc(LONG_MIN):::'
- ':::no-loc(errno):::'
- ':::no-loc(ERANGE):::'
- ':::no-loc(EINVAL):::'
- ':::no-loc(LC_NUMERIC):::'
- ':::no-loc(_tcstol):::'
- ':::no-loc(_tcstol_l):::'
- ':::no-loc(localeconv):::'
- ':::no-loc(setlocale):::'
- ':::no-loc(_wsetlocale):::'
- ':::no-loc(strtod):::'
- ':::no-loc(_strtod_l):::'
- ':::no-loc(wcstod):::'
- ':::no-loc(_wcstod_l):::'
- ':::no-loc(strtoll):::'
- ':::no-loc(_strtoll_l):::'
- ':::no-loc(wcstoll):::'
- ':::no-loc(_wcstoll_l):::'
- ':::no-loc(strtoul):::'
- ':::no-loc(_strtoul_l):::'
- ':::no-loc(wcstoul):::'
- ':::no-loc(_wcstoul_l):::'
- ':::no-loc(atof):::'
- ':::no-loc(_atof_l):::'
- ':::no-loc(_wtof):::'
- ':::no-loc(_wtof_l):::'
ms.openlocfilehash: a5265b434f14f299532d6f5ebb65c83d75ea63ca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232406"
---
# <a name="no-locstrtol-no-locwcstol-no-loc_strtol_l-no-loc_wcstol_l"></a>:::no-loc(strtol):::, :::no-loc(wcstol):::, :::no-loc(_strtol_l):::, :::no-loc(_wcstol_l):::

문자열을 **`long`** 정수 값으로 변환 합니다.

## <a name="syntax"></a>구문

```C
long :::no-loc(strtol):::(
   const char *string,
   char **end_ptr,
   int base
);
long :::no-loc(wcstol):::(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base
);
long :::no-loc(_strtol_l):::(
   const char *string,
   char **end_ptr,
   int base,
   _locale_t locale
);
long :::no-loc(_wcstol_l):::(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*문자열*\
변환할 Null 종료 문자열입니다.

*end_ptr*\
출력 매개 변수는 마지막 해석 문자 뒤의 문자를 가리키도록 설정 합니다. **NULL**인 경우 무시 됩니다.

*하단*\
사용할 기수입니다.

*로캘을*\
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

**:::no-loc(strtol):::**, **:::no-loc(wcstol):::** , **:::no-loc(_strtol_l):::** 및 **:::no-loc(_wcstol_l):::** 는 *문자열*에 표시 된 값을 반환 합니다. 변환할 수 없는 경우 0을 반환 합니다. 표현이 오버플로를 발생 시키는 경우 또는를 반환 **:::no-loc(LONG_MAX):::** **:::no-loc(LONG_MIN):::** 합니다.

**:::no-loc(errno):::****:::no-loc(ERANGE):::** 오버플로 또는 언더플로가 발생 하면가로 설정 됩니다. **:::no-loc(EINVAL):::** *문자열이* **NULL**인 경우로 설정 됩니다. 또는 *base* 가 0이 아니고 2 보다 작거나 36 보다 큰 경우입니다. **:::no-loc(ERANGE):::**, 및 기타 반환 코드에 대 한 자세한 내용은 **:::no-loc(EINVAL):::** [_dos :::no-loc(errno)::: , :::no-loc(errno)::: , _sys_errlist 및 _sys_nerr](../../c-runtime-library/:::no-loc(errno):::-dos:::no-loc(errno):::-sys-errlist-and-sys-nerr.md)를 참조 하세요.

## <a name="remarks"></a>설명

**:::no-loc(strtol):::**,, **:::no-loc(wcstol):::** 및 함수는 문자열을으로 **:::no-loc(_strtol_l):::** **:::no-loc(_wcstol_l):::** 변환 *string* **`long`** 합니다. 숫자의 일부로 인식 되지 않는 첫 번째 문자에서 *문자열* 읽기를 중지 합니다. 이 문자는 종료 null 문자 이거나 *base*보다 크거나 같은 첫 번째 영숫자 문자일 수 있습니다.

**:::no-loc(wcstol):::** 및 **:::no-loc(_wcstol_l):::** 는 및의 와이드 문자 버전 **:::no-loc(strtol):::** 입니다 **:::no-loc(_strtol_l):::** . *문자열* 인수는 와이드 문자열입니다. 이러한 함수는와 동일 하 게 작동 **:::no-loc(strtol):::** **:::no-loc(_strtol_l):::** 합니다. 로캘의 **:::no-loc(LC_NUMERIC):::** 범주 설정에 따라 *문자열*의 기 개수 문자 (분수 표식 또는 소수점) 인식이 결정 됩니다. 함수 **:::no-loc(strtol):::** 및는 **:::no-loc(wcstol):::** 현재 로캘을 사용 합니다. **:::no-loc(_strtol_l):::****:::no-loc(_wcstol_l):::** 대신 전달 된 로캘을 사용 합니다. 자세한 내용은 [ :::no-loc(setlocale)::: ] 및 [로캘](../../c-runtime-library/locale.md)을 참조 하세요.

*End_ptr* **NULL**인 경우에는 무시 됩니다. 그렇지 않은 경우 검색을 중지 한 문자에 대 한 포인터는 *end_ptr*가 가리키는 위치에 저장 됩니다. 올바른 숫자를 찾을 수 없거나 잘못 된 기본이 지정 된 경우 변환이 가능 하지 않습니다. 그런 다음 *문자열* 의 값은 *end_ptr*가 가리키는 위치에 저장 됩니다.

**:::no-loc(strtol):::***문자열* 은 다음 형식의 문자열을 가리키도록 합니다.

> [*공백*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*영숫자*]

대괄호 ( `[ ]` )는 선택적 요소를 둘러쌉니다. 단일 요소를 대체 하는 중괄호와 세로 막대 ( `{ | }` )를 둘러쌉니다. *공백은 무시* 되는 공백과 탭 문자로 구성 될 수 있습니다. *영숫자* 는 10 진수 또는 ' a ' ~ ' z ' (또는 ' a ' ~ ' z ')입니다. 이 폼에 맞지 않는 첫 번째 문자는 검색을 중지 합니다. *Base* 가 2에서 36 사이인 경우 숫자의 밑으로 사용 됩니다. *Base* 가 0 인 경우 *문자열* 에서 가리키는 문자열의 초기 문자를 사용 하 여 기본를 확인 합니다. 첫 번째 문자가 0이 고 두 번째 문자가 ' x ' 또는 ' X '가 아니면 문자열은 8 진수 정수로 해석 됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'이면 문자열은 16진수 정수로 해석됩니다. 첫 번째 문자가 '1'~'9' 이면 문자열은 10진수 정수로 해석됩니다. 문자 ' a ' ~ ' z ' (또는 ' A ' ~ ' Z ')에는 값 10 ~ 35이 할당 됩니다. 검색에서는 값이 *base*보다 작은 문자만 사용할 수 있습니다. 밑의 범위를 벗어난 첫 번째 문자가 발견되면 검색이 중지됩니다. 예를 들어 *문자열* 은 "01"로 시작 한다고 가정 합니다. *Base* 가 0 인 경우 스캐너는 8 진수 정수인 것으로 가정 합니다. ' 8 ' 또는 ' 9 ' 문자는 검색을 중지 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**:::no-loc(_tcstol):::**|**:::no-loc(strtol):::**|**:::no-loc(strtol):::**|**:::no-loc(wcstol):::**|
|**:::no-loc(_tcstol_l):::**|**:::no-loc(_strtol_l):::**|**:::no-loc(_strtol_l):::**|**:::no-loc(_wcstol_l):::**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**:::no-loc(strtol):::**|\<stdlib.h>|
|**:::no-loc(wcstol):::**|\<stdlib.h> 또는 \<wchar.h>|
|**:::no-loc(_strtol_l):::**|\<stdlib.h>|
|**:::no-loc(_wcstol_l):::**|\<stdlib.h> 또는 \<wchar.h>|

**:::no-loc(_strtol_l):::** 및 **:::no-loc(_wcstol_l):::** 함수는 Microsoft 전용 이며 표준 C 라이브러리의 일부가 아닙니다. 호환성에 대한 자세한 내용은 [Compatibility](../compatibility.md)을 참조하세요.

## <a name="example"></a>예제

의 예제를 참조 하세요 [:::no-loc(strtod):::](:::no-loc(strtod):::-:::no-loc(strtod):::-l-:::no-loc(wcstod):::-:::no-loc(wcstod):::-l.md) .

## <a name="see-also"></a>참고 항목

[데이터 변환](../data-conversion.md)\
[로캘을](../locale.md)\
[:::no-loc(localeconv):::](:::no-loc(localeconv):::.md)\
[:::no-loc(setlocale):::, :::no-loc(_wsetlocale):::](:::no-loc(setlocale):::-w:::no-loc(setlocale):::.md)\
[문자열-숫자 값 함수](../string-to-numeric-value-functions.md)\
[:::no-loc(strtod):::, :::no-loc(_strtod_l):::, :::no-loc(wcstod):::, :::no-loc(_wcstod_l):::](:::no-loc(strtod):::-:::no-loc(strtod):::-l-:::no-loc(wcstod):::-:::no-loc(wcstod):::-l.md)\
[:::no-loc(strtoll):::, :::no-loc(_strtoll_l):::, :::no-loc(wcstoll):::, :::no-loc(_wcstoll_l):::](:::no-loc(strtoll):::-:::no-loc(strtoll):::-l-:::no-loc(wcstoll):::-:::no-loc(wcstoll):::-l.md)\
[:::no-loc(strtoul):::, :::no-loc(_strtoul_l):::, :::no-loc(wcstoul):::, :::no-loc(_wcstoul_l):::](:::no-loc(strtoul):::-:::no-loc(strtoul):::-l-:::no-loc(wcstoul):::-:::no-loc(wcstoul):::-l.md)\
[:::no-loc(atof):::, :::no-loc(_atof_l):::, :::no-loc(_wtof):::, :::no-loc(_wtof_l):::](:::no-loc(atof):::-:::no-loc(atof):::-l-wtof-wtof-l.md)
