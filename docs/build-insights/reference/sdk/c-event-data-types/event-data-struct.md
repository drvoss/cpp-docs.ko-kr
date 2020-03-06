---
title: EVENT_DATA 구조체
description: C++ BUILD Insights SDK EVENT_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 572cbdaba346ddb77b665b5677b978c83a80aa3d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335215"
---
# <a name="event_data-structure"></a>EVENT_DATA 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`EVENT_DATA` 구조는 분석 또는 relogging 세션에서 받은 이벤트를 설명 합니다. 이러한 세션은 [Analyze](../functions/analyze.md), [AnalyzeA](../functions/analyze-a.md), [AnalyzeW](../functions/analyze-w.md), [Relog](../functions/relog.md), [reloga](../functions/relog-a.md)또는 [reloga](../functions/relog-w.md) 함수를 호출 하 여 시작 됩니다.

## <a name="syntax"></a>구문

```cpp
typedef struct EVENT_DATA_TAG
{
    unsigned short          EventId;
    unsigned long long      EventInstanceId;

    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;
    long long               ExclusiveDurationTicks;
    long long               CPUTicks;
    long long               ExclusiveCPUTicks;
    long long               WallClockTimeResponsibilityTicks;
    long long               ExclusiveWallClockTimeResponsibilityTicks;

    const void*             Data;

    unsigned long           ProcessId;
    unsigned long           ThreadId;
    unsigned short          ProcessorIndex;

    const char*             EventName;
    const wchar_t*          EventWideName;

} EVENT_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `EventId` | 이벤트를 식별 하는 번호입니다. 이벤트 식별자 목록은 [EVENT_ID](event-id-enum.md)를 참조 하세요. |
| `EventInstanceId` | 추적 내에서 현재 이벤트를 고유 하 게 식별 하는 번호입니다. 동일한 추적을 여러 번 분석 하거나 다시 로깅하는 경우에는이 값이 변경 되지 않습니다. 이 필드를 사용 하 여 동일한 추적을 통해 여러 분석 또는 다시 로깅 패스에서 동일한 이벤트를 식별할 수 있습니다. |
| `TickFrequency` | 틱 기간을 평가할 때 사용할 초당 틱 수입니다. |
| `StartTimestamp` | 이벤트가 *작업*인 경우이 필드는 작업이 시작 될 때 캡처된 틱 값으로 설정 됩니다. 이 이벤트가 *간단한 이벤트*인 경우이 필드는 이벤트가 발생 했을 때 캡처된 틱 값으로 설정 됩니다. |
| `StopTimestamp` | 이벤트가 *활동*인 경우이 필드는 활동이 중지 될 때 캡처된 틱 값으로 설정 됩니다. 이 작업에 대 한 중지 이벤트가 아직 수신 되지 않은 경우이 필드는 0으로 설정 됩니다. 이 이벤트가 *간단한 이벤트*이면이 필드는 0으로 설정 됩니다. |
| `ExclusiveDurationTicks` | 이 이벤트가 *활동*인 경우이 필드는이 활동에서 직접 발생 한 틱 수로 설정 됩니다. 자식 활동에서 발생 한 틱 수는 제외 됩니다. *단순 이벤트*의 경우이 필드는 0으로 설정 됩니다. |
| `CPUTicks` | 이 이벤트가 *작업*인 경우이 필드는이 작업 중에 발생 한 CPU 틱 수로 설정 됩니다. CPU 틱은 일반 틱과 다릅니다. Cpu 틱은 CPU가 활동에서 코드를 실행 하는 경우에만 계산 됩니다. 작업과 연결 된 스레드가 절전 모드 이면 CPU 틱이 계산 되지 않습니다. *단순 이벤트*의 경우이 필드는 0으로 설정 됩니다. |
| `ExclusiveCPUTicks` | 이 필드는 자식 활동에서 발생 한 CPU 틱을 포함 하지 않는다는 점을 제외 하 고 `CPUTicks`와 동일한 의미를 갖습니다. *단순 이벤트*의 경우이 필드는 0으로 설정 됩니다. |
| `WallClockTimeResponsibilityTicks` | 이 이벤트가 *활동*인 경우이 필드는 전체 벽 시계 시간에 대 한이 활동의 기여를 나타내는 틱 수로 설정 됩니다. 벽 시계 시간 업무 눈금이 일반 틱과 다릅니다. 벽 시계 시간 책임 틱은 활동 간의 병렬 처리를 고려 합니다. 예를 들어 두 병렬 활동의 기간은 50이 고 동일한 시작 및 중지 시간이 있을 수 있습니다. 이 경우에는 둘 다 벽 시계 시간 책임이 25 틱으로 할당 됩니다. *단순 이벤트*의 경우이 필드는 0으로 설정 됩니다. |
| `ExclusiveWallClockTimeResponsibilityTicks` | 이 필드는 자식 활동의 벽 시계 시간 책임이 포함 되지 않는다는 점을 제외 하 고 `WallClockTimeResponsibilityTicks`와 동일한 의미를 갖습니다. *단순 이벤트*의 경우이 필드는 0으로 설정 됩니다. |
| `Data` | 이벤트에 저장 된 추가 데이터를 가리킵니다. `EventId` 필드에 따라 가리키는 데이터 형식이 다릅니다. |
| `ProcessId` | 이벤트가 발생 한 프로세스의 식별자입니다. |
| `ThreadId` | 이벤트가 발생 한 스레드의 식별자입니다. |
| `ProcessorIndex` | 이벤트가 발생 한 0으로 인덱싱된 CPU 번호입니다. |
| `EventName` | `EventId`으로 식별 되는 엔터티의 이름을 포함 하는 ANSI 문자열입니다. |
| `EventWideName` | `EventId`으로 식별 되는 엔터티의 이름을 포함 하는 와이드 문자열입니다. |

## <a name="remarks"></a>주의

`EVENT_DATA`의 많은 필드가 틱 개수를 포함 합니다. C++Build Insights는 창의 성능 카운터를 틱의 원본으로 사용 합니다. 틱 개수는 `TickFrequency` 필드와 함께 사용 하 여 초와 같은 적절 한 시간 단위로 변환 해야 합니다. 이 변환을 수행 하려면 아래 예제를 참조 하세요. `EVENT_DATA`는 활동의 일반 틱 수에 대 한 필드를 포함 하지 않습니다. 이 값을 얻으려면 `StopTimestamp`에서 `StartTimestamp`을 뺍니다. `EVENT_DATA`은 C API 사용자가 사용 하는 구조입니다. API C++ 사용자의 경우 [이벤트](../cpp-event-data-types/event.md) 와 같은 클래스에서 시간 변환이 자동으로 수행 됩니다.

`EVENT_DATA` `Data` 필드의 값은 `EventId` 필드의 값에 따라 달라 집니다. `Data`의 값은 아래 표에 설명 되어 있습니다. 일부 엔터티 식별자가 아래 테이블에 없을 수 있습니다. 이 경우 `Data` 필드는 `nullptr` 또는 0으로 설정 됩니다.

| `EventId` 값 | `Data`가 가리키는 형식입니다. |
|--|--|
| `EVENT_ID_BACK_END_PASS` | [CL_PASS_DATA](cl-pass-data-struct.md) |
| `EVENT_ID_COMMAND_LINE` | `const wchar_t` |
| `EVENT_ID_COMPILER` | [INVOCATION_DATA](invocation-data-struct.md) |
| `EVENT_ID_ENVIRONMENT_VARIABLE` | [NAME_VALUE_PAIR_DATA](name-value-pair-data-struct.md) |
| `EVENT_ID_EXECUTABLE_IMAGE_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_EXP_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_FILE_INPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_FORCE_INLINE` | [FUNCTION_FORCE_INLINEE_DATA](function-force-inlinee-data-struct.md) |
| `EVENT_ID_FRONT_END_FILE` | [FRONT_END_FILE_DATA](front-end-file-data-struct.md) |
| `EVENT_ID_FRONT_END_PASS` | [CL_PASS_DATA](cl-pass-data-struct.md) |
| `EVENT_ID_FUNCTION` | [FUNCTION_DATA](function-data-struct.md) |
| `EVENT_ID_IMP_LIB_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_LIB_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_LINKER` | [INVOCATION_DATA](invocation-data-struct.md) |
| `EVENT_ID_OBJ_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_SYMBOL_NAME` | [SYMBOL_NAME_DATA](symbol-name-data-struct.md) |
| `EVENT_ID_TEMPLATE_INSTANTIATION` | [TEMPLATE_INSTANTIATION_DATA](template-instantiation-data-struct.md) |

## <a name="tick-conversion-example"></a>눈금 변환 예

```cpp
//
// We have the elapsed number of ticks, along with the
// number of ticks per second. We use these values
// to convert to the number of elapsed microseconds.
// To guard against loss-of-precision, we convert
// to microseconds *before* dividing by ticks-per-second.
//

long long ConvertDurationToMicroseconds(const sruct EVENT_DATA& eventData)
{
    long long duration = eventData.StopTimestamp - eventData.StartTimestamp;
    long long duration *= 1000000;
    return duration / eventData.TickFrequency;
}
```

::: moniker-end
