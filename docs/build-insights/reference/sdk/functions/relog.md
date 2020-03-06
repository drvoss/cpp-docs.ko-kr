---
title: 다시 기록할
description: C++ BUILD Insights SDK Relog 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Relog
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1ce09101deebd957de4b9305762dc37f38b53f4e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334285"
---
# <a name="relog"></a>다시 기록할

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`Relog` 함수는 ETW (ETW(Windows용 이벤트 추적)) 추적에서 MSVC 이벤트를 읽고 수정 된 새 ETW 추적에 기록 하는 데 사용 됩니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const char*                                   inputLogFile,
    const char*                                   outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const wchar_t*                                inputLogFile,
    const wchar_t*                                outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>매개 변수

*TAnalyzerGroupMembers*\
이 매개 변수는 항상 추론 됩니다.

*TReloggerGroupMembers*\
이 매개 변수는 항상 추론 됩니다.

*Inputlogfile*\
이벤트를 읽으려고 하는 입력 ETW 추적입니다.

*Outputlogfile*\
새 이벤트를 쓸 파일입니다.

*numberOfAnalysisPasses*\
입력 추적에서 실행할 분석 패스의 수입니다. Trace는 제공 된 분석기 그룹을 분석 통과 당 한 번씩 전달 합니다.

*systemEventsRetentionFlags*\
Relogged 추적에 유지할 시스템 ETW 이벤트를 지정 하는 비트 마스크입니다. 자세한 내용은 [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md)를 참조 하세요.

*analyzerGroup*\
Relogging 세션의 분석 단계에 사용 되는 분석기 그룹입니다. [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) 를 호출 하 여 분석기 그룹을 만듭니다. [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md)에서 가져온 동적 분석기 그룹을 사용 하려면 먼저 해당 주소를 `MakeStaticAnalyzerGroup`으로 전달 하 여 정적 분석기 그룹 내에 캡슐화 합니다.

*reloggerGroup*\
*Outputlogfile*에 지정 된 추적 파일에 이벤트를 다시 기록 하는 재로 거 group입니다. [MakeStaticReloggerGroup](make-static-relogger-group.md) 를 호출 하 여 재로 거 거 그룹을 만듭니다. [MakeDynamicReloggerGroup](make-dynamic-relogger-group.md)에서 가져온 동적 재로 거 거 그룹을 사용 하려면 먼저 해당 주소를 `MakeStaticReloggerGroup`으로 전달 하 여 정적 재로 거 그룹 내에 캡슐화 합니다.

### <a name="return-value"></a>반환 값

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

### <a name="remark"></a>설명

입력 추적은 *numberOfAnalysisPasses* 번 분석기 그룹을 통해 전달 됩니다. 다시 로깅 패스에는 유사한 옵션이 없습니다. 모든 분석 단계가 완료 된 후에 다시 trough가 다시 전달 됩니다.

Relogging 거 클래스 내에서 CPU 샘플과 같은 시스템 이벤트의 재 로깅은 지원 되지 않습니다. *SystemEventsRetentionFlags* 매개 변수를 사용 하 여 출력 추적에 유지할 시스템 이벤트를 결정 합니다.

::: moniker-end
