---
title: __p__fmode
ms.date: 11/04/2016
api_name:
- __p__fmode
api_location:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: 2364a22d52c5bc418e4499a4a639c8e06559063a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171452"
---
# <a name="__p__fmode"></a>__p__fmode

파일 I/O 연산에 대한 기본 `_fmode`파일 변환 모드*를 지정하는*  전역 변수에 대한 포인터입니다.

## <a name="syntax"></a>구문

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Return Value

`_fmode` 전역 변수에 대한 포인터입니다.

## <a name="remarks"></a>설명

`__p__fmode` 함수는 내부용이며 사용자 코드에서 호출할 수 없습니다.

파일 변환 모드는 `binary`_open`text` 및 [_pipe](../c-runtime-library/reference/open-wopen.md) I/O 연산에 대한 [ 또는 ](../c-runtime-library/reference/pipe.md) 변환을 지정합니다. 자세한 내용은 [_fmode](../c-runtime-library/fmode.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|__p\__fmode|stdlib.h|
