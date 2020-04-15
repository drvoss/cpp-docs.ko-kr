---
title: TRACE_INFO_DATA 구조
description: C++ 빌드 인사이트 SDK TRACE_INFO_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACE_INFO_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 70ae17a376f79cad7a669d81e482f551afd0ec62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325272"
---
# <a name="trace_info_data-structure"></a>TRACE_INFO_DATA 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `TRACE_INFO_DATA` 분석되거나 다시 기록되는 추적을 설명합니다.

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
| `LogicalProcessorCount` | 추적이 수집된 컴퓨터의 논리 프로세서 수입니다. |
| `TickFrequency` | 틱으로 측정된 기간을 평가할 때 사용할 초당 틱 수입니다. |
| `StartTimestamp` | 이 필드는 추적이 시작될 때 캡처된 눈금 값으로 설정됩니다. |
| `StopTimestamp` | 이 필드는 추적이 중지될 때 캡처된 틱 값으로 설정됩니다. |

## <a name="remarks"></a>설명

전체 `StartTimestamp` 추적 `StopTimestamp` 중에 경과된 틱 수를 얻기 위해 빼서 뺍니다. 결과 `TickFrequency` 값을 시간 단위로 변환하는 데 사용합니다. 틱을 시간 단위로 변환하는 예제의 경우 [EVENT_DATA](event-data-struct.md)을 참조하십시오.

::: moniker-end
