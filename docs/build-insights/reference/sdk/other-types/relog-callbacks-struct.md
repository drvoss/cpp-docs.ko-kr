---
title: RELOG_CALLBACKS 구조체
description: C++ BUILD Insights SDK RELOG_CALLBACKS 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c5dbed196e6cafaa301b6e07cd0f5546a0f4d563
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333985"
---
# <a name="relog_callbacks-structure"></a>RELOG_CALLBACKS 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

[RELOG_DESCRIPTOR](relog-descriptor-struct.md) 개체를 초기화할 때 `RELOG_CALLBACKS` 구조가 사용 됩니다. ETW(Windows용 이벤트 추적) (ETW) 추적을 다시 로깅하는 동안 호출할 함수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct RELOG_CALLBACKS_TAG
{
    OnRelogEventFunc        OnStartActivity;
    OnRelogEventFunc        OnStopActivity;
    OnRelogEventFunc        OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginRelogging;
    OnBeginEndPassFunc      OnEndRelogging;
    OnBeginEndPassFunc      OnBeginReloggingPass;
    OnBeginEndPassFunc      OnEndReloggingPass;
} RELOG_CALLBACKS;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `OnStartActivity` | 작업 시작 이벤트를 처리 하기 위해 호출 됩니다. |
| `OnStopActivity` | 작업 중지 이벤트를 처리 하기 위해 호출 됩니다. |
| `OnSimpleEvent` | 간단한 이벤트를 처리 하기 위해 호출 됩니다. |
| `OnTraceInfo` | `OnBeginReloggingPass`가 호출 된 후에 다시 로깅 단계가 시작 될 때 한 번 호출 됩니다. |
| `OnBeginRelogging` | 다시 로깅 단계가 시작 되기 전에 relogging 세션을 시작할 때 호출 됩니다. |
| `OnEndRelogging` | 다시 로깅 단계가 종료 된 후에 다시 로깅 세션을 종료할 때 호출 됩니다. |
| `OnBeginReloggingPass` | 이벤트를 처리 하기 전에 다시 로깅 통과를 시작할 때 호출 됩니다. |
| `OnEndReloggingPass` | 모든 이벤트를 처리 한 후에 relogging pass를 종료할 때 호출 됩니다. |

## <a name="remarks"></a>주의

`RELOG_CALLBACKS` 구조체의 모든 멤버는 유효한 함수를 가리켜야 합니다. 허용 되는 함수 서명에 대 한 자세한 내용은 [OnRelogEventFunc](on-relog-event-func-typedef.md), [ontraceinfofunc](on-trace-info-func-typedef.md)및 [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md)를 참조 하세요.

::: moniker-end
