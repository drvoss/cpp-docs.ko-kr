---
title: srand
ms.date: 4/2/2020
api_name:
- srand
- _o_srand
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
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- srand
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.openlocfilehash: 3f6f97ad9a3bd0d7e4e88ad1797d369f012bbe5e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913601"
---
# <a name="srand"></a>srand

**Rand** 함수에서 사용 하는 의사 난수 생성기의 시작 초기값을 설정 합니다.

## <a name="syntax"></a>구문

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>매개 변수

*seed*<br/>
의사 난수 생성을 위한 시드

## <a name="remarks"></a>설명

**Srand** 함수는 현재 스레드에서 일련의 의사 난수 정수를 생성 하기 위한 시작점을 설정 합니다. 동일한 결과 시퀀스를 만들도록 생성기를 다시 초기화 하려면 **srand** 함수를 호출 하 고 동일한 *초기값* 인수를 다시 사용 합니다. *초기값* 의 다른 모든 값은 생성기를 의사 (pseudo) 시퀀스에서 다른 시작 점으로 설정 합니다. **rand** 는 생성 된 의사 난수를 검색 합니다. **Srand** 호출 하기 전에 **rand** 를 호출 하면 **srand** 를 호출 하는 것과 동일한 시퀀스가 생성 되며 *초기값* 이 1로 전달 됩니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[rand](rand.md)의 예제를 참조하세요.

## <a name="see-also"></a>참조

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
