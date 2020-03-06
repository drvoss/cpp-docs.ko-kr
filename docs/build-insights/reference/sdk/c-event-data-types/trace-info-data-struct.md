---
title: TRACE_INFO_DATA 구조체
description: C++ BUILD Insights SDK TRACE_INFO_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACE_INFO_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 04cb5c013bca8879507983d169b38e5af0f1322b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335053"
---
# <a name="trace_info_data-structure"></a>TRACE_INFO_DATA 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`TRACE_INFO_DATA` 구조는 분석 또는 relogged 추적을 설명 합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct TRACE_INFO_DATA_TAG
{
    unsigned long           LogicalProcessorCount;
    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;

} TRACE_INFO_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `LogicalProcessorCount` | 추적이 수집 된 컴퓨터의 논리 프로세서 수입니다. |
| `TickFrequency` | 틱 기간을 평가할 때 사용할 초당 틱 수입니다. |
| `StartTimestamp` | 이 필드는 추적이 시작 될 때 캡처된 틱 값으로 설정 됩니다. |
| `StopTimestamp` | 이 필드는 추적이 중지 될 때 캡처된 틱 값으로 설정 됩니다. |

## <a name="remarks"></a>주의

`StopTimestamp`에서 `StartTimestamp`를 빼서 전체 추적 중에 경과 된 틱 수를 가져옵니다. `TickFrequency`를 사용 하 여 결과 값을 시간 단위로 변환 합니다. 틱을 시간 단위로 변환 하는 예는 [EVENT_DATA](event-data-struct.md)를 참조 하세요.

::: moniker-end
