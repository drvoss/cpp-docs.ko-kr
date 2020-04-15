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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: a8d018d429b2a484f88b7c1e0679f1f799983910
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355493"
---
# <a name="srand"></a>srand

**rand** 함수에서 사용하는 의사 난수 생성기의 시작 시드 값을 설정합니다.

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

**srand** 함수는 현재 스레드에서 일련의 의사 임의 정수를 생성하기 위한 시작점을 설정합니다. 생성기를 다시 초기화하여 동일한 결과 시퀀스를 만들려면 **srand** 함수를 호출하고 동일한 *시드* 인수를 다시 사용합니다. *시드에* 대한 다른 값은 생성기를 의사 랜덤 시퀀스의 다른 시작점으로 설정합니다. **rand는** 생성되는 의사 임의의 숫자를 검색합니다. **srand에** 대한 호출 전에 **rand를** 호출하는 것은 *시드가* 1로 전달된 **스랜드** 호출과 동일한 시퀀스를 생성합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[rand](rand.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[랜드](rand.md)<br/>
