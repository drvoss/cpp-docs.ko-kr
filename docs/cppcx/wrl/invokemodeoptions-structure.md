---
title: InvokeModeOptions 구조체
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 9bca49479d97ee371f6728f90a9aa96da0387f54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213839"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions 구조체

대리자 큐의 모든 이벤트를 시작할지, 아니면 오류가 발생 한 후 발생을 중지할지를 지정 합니다. 허용 되는 값은 `InvokeMode` 열거형에 지정 됩니다.

## <a name="syntax"></a>구문

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>요구 사항

**헤더:** 이벤트. h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)<br/>
[Microsoft:: WRL:: AgileEventSource 클래스](agileeventsource-class.md)
