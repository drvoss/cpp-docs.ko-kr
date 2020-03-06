---
title: TRACING_SESSION_MSVC_EVENT_FLAGS 상수
description: C++ BUILD Insights SDK TRACING_SESSION_MSVC_EVENT_FLAGS 상수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_MSVC_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e77e63d881315a6579668967751bc24f44a27749
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333877"
---
# <a name="tracing_session_msvc_event_flags-constants"></a>TRACING_SESSION_MSVC_EVENT_FLAGS 상수

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`TRACING_SESSION_MSVC_EVENT_FLAGS` 상수는 추적 하는 동안 수집할 MSVC 이벤트를 설명 하는 데 사용 됩니다. [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) 구조체의 `MsvcEventFlags` 필드를 초기화 하는 데 사용 합니다.

## <a name="syntax"></a>구문

```cpp
static const unsigned long long
    TRACING_SESSION_MSVC_EVENT_FLAGS_BASIC                                = 0x0001ULL;

static const unsigned long long
    TRACING_SESSION_MSVC_EVENT_FLAGS_FRONTEND_FILES                       = 0x0004ULL;

static const unsigned long long
    TRACING_SESSION_MSVC_EVENT_FLAGS_FRONTEND_TEMPLATE_INSTANTIATIONS     = 0x0008ULL;

static const unsigned long long
    TRACING_SESSION_MSVC_EVENT_FLAGS_BACKEND_FUNCTIONS                    = 0x1000ULL;

static const unsigned long long
    TRACING_SESSION_MSVC_EVENT_FLAGS_ALL                                  = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>멤버

| 이름 | 이 플래그에 의해 설정 된 이벤트 |
|--|--|
| `TRACING_SESSION_MSVC_EVENT_FLAGS_BASIC` | 이 플래그는 다음 이벤트와 연결 됩니다. 명시적으로 지정 되지 않은 경우에 C++ 도 BUILD Insights SDK에서 기본적으로 활성화 됩니다. 이러한 이벤트는 사용 하지 않도록 설정할 수 없습니다.<br/><br/>[BACK_END_PASS](../event-table.md#back-end-pass)[BOTTOM_UP](../event-table.md#bottom-up)<br/>[C1_DLL](../event-table.md#c1-dll)<br/>[C2_DLL](../event-table.md#c2-dll)<br/>[CODE_GENERATION](../event-table.md#code-generation)<br/>[COMMAND_LINE](../event-table.md#command-line)<br/>[컴파일러나](../event-table.md#compiler)<br/>[ENVIRONMENT_VARIABLE](../event-table.md#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output)<br/>[EXP_OUTPUT](../event-table.md#exp-output)<br/>[FILE_INPUT](../event-table.md#file-input)<br/>[FRONT_END_PASS](../event-table.md#front-end-pass)<br/>[FRONT_END_PASS](../event-table.md#front-end-pass)<br/>[IMP_LIB_OUTPUT](../event-table.md#imp-lib-output)<br/>[LIB_OUTPUT](../event-table.md#lib-output)<br/>[링커](../event-table.md#linker)<br/>[LTCG](../event-table.md#ltcg)<br/>[OBJ_OUTPUT](../event-table.md#obj-output)<br/>[OPT_ICF](../event-table.md#opt-icf)<br/>[OPT_LBR](../event-table.md#opt-lbr)<br/>[OPT_REF](../event-table.md#opt-ref)<br/>[PASS1.LOG](../event-table.md#pass1)<br/>[PASS2](../event-table.md#pass2)<br/>[PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref)<br/>[스레드](../event-table.md#thread)<br/>[TOP_DOWN](../event-table.md#top-down)<br/>[WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) |
| `TRACING_SESSION_MSVC_EVENT_FLAGS_FRONTEND_FILES` | [FRONT_END_FILE](../event-table.md#front-end-file) |
| `TRACING_SESSION_MSVC_EVENT_FLAGS_FRONTEND_TEMPLATE_INSTANTIATIONS` | [SYMBOL_NAME](../event-table.md#symbol-name)<br/>[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) |
| `TRACING_SESSION_MSVC_EVENT_FLAGS_BACKEND_FUNCTIONS` | [FORCE_INLINEE](../event-table.md#force-inlinee)<br/>[FUNCTION](../event-table.md#function) |
| `TRACING_SESSION_MSVC_EVENT_FLAGS_ALL` | 이 플래그는 모든 이벤트를 설정 합니다. |

::: moniker-end
