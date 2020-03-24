---
title: __p__commode
ms.date: 11/04/2016
api_name:
- __p__commode
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: e3121c127c3ebf0f5fccdeb7ae0f67d0164d0965
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171478"
---
# <a name="__p__commode"></a>__p__commode

파일 I/O 연산에 대한 기본 `_commode`파일 커밋 모드*를 지정하는*  전역 변수에 대한 포인터입니다.

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

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|__p\__commode|internal.h|
