---
title: __CxxFrameHandler
ms.date: 11/04/2016
api_name:
- __CxxFrameHandler
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __CxxFrameHandler
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
ms.openlocfilehash: db856850688e378cde9eaa1fb510cb325ce0644b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170984"
---
# <a name="__cxxframehandler"></a>__CxxFrameHandler

내부 CRT 함수입니다. CRT에서 구조화된 예외 프레임을 처리하는 데 사용됩니다.

## <a name="syntax"></a>구문

```cpp
EXCEPTION_DISPOSITION __CxxFrameHandler(
      EHExceptionRecord  *pExcept,
      EHRegistrationNode *pRN,
      void               *pContext,
      DispatcherContext  *pDC
   )
```

#### <a name="parameters"></a>매개 변수

*pExcept*<br/>
가능한 `catch` 문에 전달되는 예외 레코드입니다.

*pRN*<br/>
예외를 처리하는 데 사용되는 스택 프레임에 대한 동적 정보입니다. 자세한 내용은 ehdata.h를 참조하세요.

*pContext*<br/>
컨텍스트입니다. Intel 프로세서에는 사용되지 않습니다.

*pDC*<br/>
함수 시작 및 스택 프레임에 대한 추가 정보입니다.

## <a name="return-value"></a>Return Value

*try-except Statement*에서 사용하는 [필터 식](../cpp/try-except-statement.md) 값 중 하나입니다.

## <a name="remarks"></a>설명

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|__CxxFrameHandler|excpt.h, ehdata.h|
