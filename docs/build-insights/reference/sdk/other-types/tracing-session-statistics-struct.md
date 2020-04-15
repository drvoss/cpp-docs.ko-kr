---
title: TRACING_SESSION_STATISTICS 구조
description: C++ 빌드 인사이트 SDK TRACING_SESSION_OPTIONS 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 96cff3a231fd515ec1c52a048b8350a63ba46a39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323374"
---
# <a name="tracing_session_statistics-structure"></a>TRACING_SESSION_STATISTICS 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `TRACING_SESSION_STATISTICS` 수집된 추적에 대한 통계를 설명합니다. 추적 세션을 중지할 때 해당 필드가 설정됩니다.

## <a name="syntax"></a>구문

```cpp
typedef struct TRACING_SESSION_STATISTICS_TAG
{
    unsigned long MSVCEventsLost;
    unsigned long MSVCBuffersLost;
    unsigned long SystemEventsLost;
    unsigned long SystemBuffersLost;

} TRACING_SESSION_STATISTICS;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `MSVCEventsLost` | 삭제된 MSVC 이벤트 수입니다. |
| `MSVCBuffersLost` | 삭제된 MSVC 이벤트 버퍼의 수입니다. |
| `SystemEventsLost` | 삭제된 시스템 이벤트 수입니다. |
| `SystemBuffersLost` | 삭제된 시스템 이벤트 버퍼의 수입니다. |

## <a name="remarks"></a>설명

이 구조는 다음 함수를 호출할 때 채워집니다.

- [스톱트레이싱세션](../functions/stop-tracing-session.md)
- [스톱트레이싱세션A](../functions/stop-tracing-session-a.md)
- [스톱트레이싱세션W](../functions/stop-tracing-session-w.md)
- [스톱앤분석트레이싱세션](../functions/stop-and-analyze-tracing-session.md)
- [스톱앤분석트레이싱세션A](../functions/stop-and-analyze-tracing-session-a.md)
- [스톱앤분석트레이싱세션W](../functions/stop-and-analyze-tracing-session-w.md)
- [스톱앤로그트레이싱세션](../functions/stop-and-relog-tracing-session.md)
- [스톱앤로그트레이싱세션A](../functions/stop-and-relog-tracing-session-a.md)
- [스톱앤로그트레이싱세션W](../functions/stop-and-relog-tracing-session-w.md)

::: moniker-end
