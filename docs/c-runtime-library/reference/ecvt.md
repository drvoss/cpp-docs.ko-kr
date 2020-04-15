---
title: _ecvt
ms.date: 4/2/2020
api_name:
- _ecvt
- _o__ecvt
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ecvt
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
ms.openlocfilehash: 5e1760d5c68e650f6fbf44866d4e368b9d6233b6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348020"
---
# <a name="_ecvt"></a>_ecvt

**이중** 숫자를 문자열로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_ecvt_s](ecvt-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_ecvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>매개 변수

*value*<br/>
변환할 숫자입니다.

*count*<br/>
저장된 자릿수입니다.

*12월*<br/>
저장된 소수점 위치입니다.

*서명*<br/>
변환된 숫자의 부호입니다.

## <a name="return-value"></a>Return Value

**_ecvt** 숫자 문자열에 대한 포인터를 반환합니다. 오류가 발생한 경우 **NULL입니다.**

## <a name="remarks"></a>설명

**_ecvt** 함수는 부동 소수점 번호를 문자 문자열로 변환합니다. *값* 매개 변수는 변환할 부동 소수점 번호입니다. 이 함수는 *최대 값* 의 숫자를 문자열로 *계산하고* null 문자('\0')를 더합니다. *값의* 숫자 수가 *개수를*초과하면 낮은 순서의 숫자가 반올림됩니다. *자릿수보다* 적은 경우 문자열은 0으로 패딩됩니다.

**_ecvt** 반환되는 총 자릿수는 **_CVTBUFSIZE**초과하지 않습니다.

숫자만 문자열에 저장됩니다. 소수점의 위치와 *값의* 부호는 호출 후 *dec* 및 *sign에서* 얻을 수 있습니다. *dec* 매개 변수는 문자열의 시작 부분에 대해 소수점의 위치를 제공하는 정수 값을 가리킵니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. *sign* 매개 변수는 변환된 숫자의 부호를 나타내는 정수를 가리킵니다. 정수 값이 0이면 숫자가 양수입니다. 그렇지 않으면 숫자가 음수입니다.

**_ecvt** **_fcvt** 차이는 *카운트* 매개 변수의 해석에 있습니다. **_ecvt** *계산을* 출력 문자열의 총 자릿수로 해석하는 반면 **_fcvt** 소수점 다음의 자릿수로 *계산합니다.*

**_ecvt** **_fcvt** 변환에 대해 정적으로 할당된 단일 버퍼를 사용합니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. *dec* 또는 *sign이* **NULL**또는 *count가* 0인 경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있으면 **errno가** **EINVAL로** 설정되고 **NULL이** 반환됩니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_ecvt.c
// compile with: /W3
// This program uses _ecvt to convert a
// floating-point number to a character string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int     decimal,   sign;
   char    *buffer;
   int     precision = 10;
   double  source = 3.1415926535;

   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996
   // Note: _ecvt is deprecated; consider using _ecvt_s instead
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",
           source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0
```

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
