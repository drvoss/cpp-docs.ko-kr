---
title: RELOG_CALLBACKS 구조
description: C++ 빌드 인사이트 SDK RELOG_CALLBACKS 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 60e7db81a48731090a23b82332704a79a51e97df
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328967"
---
# <a name="relog_callbacks-structure"></a>RELOG_CALLBACKS 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `RELOG_CALLBACKS` [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 개체를 초기화할 때 사용됩니다. ETW(Windows용 이벤트 추적) 추적을 다시 기록하는 동안 호출할 함수를 지정합니다.

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
| `OnStartActivity` | 활동 시작 이벤트를 처리하기 위해 호출되었습니다. |
| `OnStopActivity` | 활동 중지 이벤트를 처리하기 위해 호출됩니다. |
| `OnSimpleEvent` | 간단한 이벤트를 처리하기 위해 호출됩니다. |
| `OnTraceInfo` | 리로깅 패스의 시작 부분에 한 `OnBeginReloggingPass` 번 호출 된 후 호출 되었습니다. |
| `OnBeginRelogging` | 리로깅 세션을 시작할 때 리로깅 패스가 시작되기 전에 호출됩니다. |
| `OnEndRelogging` | 리로깅 세션이 종료될 때 리로깅 패스가 종료된 후 호출됩니다. |
| `OnBeginReloggingPass` | 이벤트를 처리하기 전에 리로깅 패스를 시작할 때 호출됩니다. |
| `OnEndReloggingPass` | 모든 이벤트를 처리한 후 리로깅 패스를 종료할 때 호출됩니다. |

## <a name="remarks"></a>설명

구조의 모든 `RELOG_CALLBACKS` 멤버는 유효한 함수를 가리겨야 합니다. 허용된 함수 서명에 대한 자세한 내용은 [OnRelogEventFunc](on-relog-event-func-typedef.md), [OnTraceInfoFunc](on-trace-info-func-typedef.md)및 [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md)을 참조하십시오.

::: moniker-end
