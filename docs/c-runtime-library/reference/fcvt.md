---
title: _fcvt
ms.date: 4/2/2020
api_name:
- _fcvt
- _o__fcvt
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
- _fcvt
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
ms.openlocfilehash: a017ed58b962520793d5b10b088793dbc9b8a83d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347424"
---
# <a name="_fcvt"></a>_fcvt

부동 소수점 숫자를 문자열로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_fcvt_s](fcvt-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_fcvt(
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
소수점 뒤의 자릿수입니다.

*12월*<br/>
저장된 소수점 위치의 포인터입니다.

*서명*<br/>
저장된 부호 표시기의 포인터입니다.

## <a name="return-value"></a>Return Value

**_fcvt** 숫자 **문자열에** 대한 포인터를 반환합니다.

## <a name="remarks"></a>설명

**_fcvt** 함수는 부동 소수점 번호를 null 종료 된 문자 문자열로 변환합니다. *값* 매개 변수는 변환할 부동 소수점 번호입니다. **_fcvt** *값의* 숫자를 문자열로 저장하고 null 문자('\0')를 더합니다. *count* 매개 변수는 소수점 이후에 저장할 자릿수를 지정합니다. 초과 숫자는 장소를 *계산하기* 위해 반올림됩니다. 정밀도 의 *개수* 보다 작은 경우 문자열은 0으로 패딩됩니다.

**_fcvt** 반환되는 총 자릿수는 **_CVTBUFSIZE**초과하지 않습니다.

숫자만 문자열에 저장됩니다. 소수점의 위치와 *값의* 부호는 호출 후 *dec* 및 sign에서 얻을 수 있습니다. *dec* 매개변수는 정수 값을 가리킵니다. 이 정수 값은 문자열의 시작 부분에 대해 소수점의 위치를 제공합니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. 매개 변수 *기호는* *값의*부호를 나타내는 정수를 가리킵니다. *값이* 양수인 경우 정수는 0으로 설정되고 *값이* 음수인 경우 영해가 아닌 숫자로 설정됩니다.

**_ecvt** **_fcvt** 차이는 *카운트* 매개 변수의 해석에 있습니다. **_ecvt** *계산을* 출력 문자열의 총 자릿수로 해석하는 반면 **_fcvt** 소수점 다음의 자릿수로 *계산합니다.*

**_ecvt** **_fcvt** 변환에 대해 정적으로 할당된 단일 버퍼를 사용합니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. *dec* 또는 *sign이* **NULL**또는 *count가* 0인 경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있으면 **errno가** **EINVAL로** 설정되고 **NULL이** 반환됩니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fcvt.c
// compile with: /W3
// This program converts the constant
// 3.1415926535 to a string and sets the pointer
// buffer to point to that string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int  decimal, sign;
   char *buffer;
   double source = 3.1415926535;

   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996
   // Note: _fcvt is deprecated; consider using _fcvt_s instead
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",
            source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0
```

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
