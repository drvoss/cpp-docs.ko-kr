---
title: __p__commode
ms.date: 4/2/2020
api_name:
- __p__commode
- _o___p__commode
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: fa589c1972d27854e3f794d8283f49d9db5d053a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349311"
---
# <a name="__p__commode"></a>__p__commode

파일 I/O 연산에 대한 기본 *파일 커밋 모드*를 지정하는 `_commode` 전역 변수에 대한 포인터입니다.

## <a name="syntax"></a>구문

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>Return Value

`_commode` 전역 변수에 대한 포인터입니다.

## <a name="remarks"></a>설명

`__p__commode` 함수는 내부용이며 사용자 코드에서 호출할 수 없습니다.

파일 커밋 모드에서는 중요한 데이터를 디스크에 쓰는 시기를 지정합니다. 자세한 내용은 [fflush](../c-runtime-library/reference/fflush.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|__p\__commode|internal.h|
