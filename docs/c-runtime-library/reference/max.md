---
title: __max
ms.date: 04/05/2018
api_name:
- __max
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- max
- __max
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
ms.openlocfilehash: 4cdfd99ec344cd357900d76dfc7f9400046e448a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170191"
---
# <a name="__max"></a>__max

두 값 중 더 큰 값을 반환 하는 전처리기 매크로입니다.

## <a name="syntax"></a>구문

```C
#define __max(a,b) (((a) > (b)) ? (a) : (b))
```

### <a name="parameters"></a>매개 변수

*a*, *b*<br/>
비교될 숫자 형식의 값입니다.

## <a name="return-value"></a>Return Value

**__max** 는 해당 인수 중 더 큰 값을 반환 합니다.

## <a name="remarks"></a>설명

**__Max** 매크로는 두 값을 비교 하 고 더 큰 값을 반환 합니다. 인수는 서명되거나 서명되지 않은 모든 숫자 데이터 형식일 수 있습니다. 두 인수와 반환 값은 동일한 데이터 형식이어야 합니다.

반환 되는 인수는 매크로에 의해 두 번 계산 됩니다. 인수가 계산 될 때 값을 변경 하는 식인 경우 (예: `*p++`) 예기치 않은 결과가 발생할 수 있습니다.

## <a name="requirements"></a>요구 사항

|매크로|필수 헤더|
|-------------|---------------------|
|**__max**|\<stdlib.h>|

## <a name="example"></a>예제

자세한 내용은 [__min](min.md)에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[__min](min.md)<br/>
