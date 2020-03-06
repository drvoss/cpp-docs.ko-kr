---
title: C++Insights SDK 빌드
description: Visual Studio C++ BUILD Insights SDK에 대 한 개요입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyzing
- Relogging
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5aafcc65bc30de77131d1945c9f4e78361db14ed
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334033"
---
# <a name="c-build-insights-sdk"></a>C++Insights SDK 빌드

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

C++ BUILD insights SDK는 C++ 빌드 통찰력 플랫폼 위에 개인 설정 된 도구를 만들 수 있는 api 컬렉션입니다. 이 페이지에서는 시작 하는 데 도움이 되는 개략적인 개요를 제공 합니다.

## <a name="obtaining-the-sdk"></a>SDK 가져오기

다음 단계를 수행 C++ 하 여 BUILD Insights SDK를 NuGet 패키지로 다운로드할 수 있습니다.

1. Visual Studio 2017 이상에서 새 C++ 프로젝트를 만듭니다.
1. **솔루션 탐색기** 창에서 프로젝트를 마우스 오른쪽 단추로 클릭 합니다.
1. 상황에 맞는 메뉴에서 **NuGet 패키지 관리** 를 선택 합니다.
1. 오른쪽 위에서 **nuget.org** 패키지 소스를 선택 합니다.
1. 최신 버전의 Microsoft .Cpp Insights 패키지를 검색 합니다.
1. **설치**를 선택 합니다.
1. 라이선스에 동의 합니다.

SDK를 둘러싼 일반적인 개념에 대 한 자세한 내용은을 참조 하세요. 공식 [ C++ Build Insights 샘플 GitHub 리포지토리에](https://github.com/microsoft/cpp-build-insights-samples) 액세스 하 여 SDK를 사용 하는 실제 C++ 응용 프로그램의 예제를 볼 수도 있습니다.

## <a name="collecting-a-trace"></a>추적 수집

C++ BUILD Insights SDK를 사용 하 여 MSVC 도구 체인에서 들어오는 이벤트를 분석 하려면 먼저 추적을 수집 해야 합니다. SDK는 기본 추적 기술로 ETW(Windows용 이벤트 추적) (ETW)를 사용 합니다. 추적 수집은 다음 두 가지 방법으로 수행할 수 있습니다.

### <a name="method-1-using-vcperf-in-visual-studio-2019-and-above"></a>방법 1: Visual Studio 2019 이상에서 vcperf 사용

1. VS 2019에 대 한 관리자 권한 x64 Native Tools 명령 프롬프트를 엽니다.
1. 다음 명령을 실행 합니다. `vcperf /start MySessionName`
1. 프로젝트를 빌드합니다.
1. 다음 명령을 실행 합니다. `vcperf /stopnoanalyze MySessionName outputTraceFile.etl`

   > [!IMPORTANT]
   > Vcperf로 추적을 중지할 때 `/stopnoanalyze` 명령을 사용 합니다. C++ 빌드 Insights SDK를 사용 하 여 일반 `/stop` 명령으로 중지 된 추적을 분석할 수 없습니다.

### <a name="method-2-programmatically"></a>방법 2: 프로그래밍 방식으로

이러한 C++ BUILD Insights SDK 추적 컬렉션 함수를 사용 하 여 프로그래밍 방식으로 추적을 시작 하 고 중지할 수 있습니다. **이러한 함수 호출을 실행 하는 프로그램에는 관리 권한이 있어야 합니다.** 시작 및 중지 추적 함수만 관리 권한이 필요 합니다. C++ BUILD Insights SDK의 다른 모든 함수를 사용 하지 않고 실행할 수 있습니다.

### <a name="sdk-functions-related-to-trace-collection"></a>추적 컬렉션과 관련 된 SDK 함수

| 기능 | C++ API | C API |
|--|--|--|
| 추적 시작 | [StartTracingSession](functions/start-tracing-session.md) | [StartTracingSessionA](functions/start-tracing-session-a.md)<br />[StartTracingSessionW](functions/start-tracing-session-w.md) |
| 추적 중지 | [StopTracingSession](functions/stop-tracing-session.md) | [StopTracingSessionA](functions/stop-tracing-session-a.md)<br />[StopTracingSessionW](functions/stop-tracing-session-w.md) |
| 추적 중지<br />즉시 결과 분석 | [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md) | [StopAndAnalyzeTracingSessionA](functions/stop-and-analyze-tracing-session-a.md)<br />[StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session-w.md) |
| 추적 중지<br />즉시 결과를 다시 로깅하는 방법 | [StopAndRelogTracingSession](functions/stop-and-relog-tracing-session.md) | [StopAndRelogTracingSessionA](functions/stop-and-relog-tracing-session-a.md)<br />[StopAndRelogTracingSessionW](functions/stop-and-relog-tracing-session-w.md) |

다음 섹션에서는 분석 또는 다시 로깅 세션을 구성 하는 방법을 보여 줍니다. [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md)와 같은 결합 된 기능 함수에 필요 합니다.

## <a name="consuming-a-trace"></a>추적 사용

ETW 추적이 있으면 C++ BUILD Insights SDK를 사용 하 여 압축을 풉니다. SDK는 도구를 신속 하 게 개발할 수 있는 형식의 이벤트를 제공 합니다. SDK를 사용 하지 않고 원시 ETW 추적을 사용 하지 않는 것이 좋습니다. MSVC에서 사용 하는 이벤트 형식은 문서화 되지 않으며, 대규모 빌드로 확장 되도록 최적화 되었으며, 이해 하기 어렵습니다. 또한 C++ 빌드 INSIGHTS SDK API는 안정적 이지만 원시 ETW 추적 형식은 예 고 없이 변경 될 수 있습니다.

### <a name="sdk-types-and-functions-related-to-trace-consumption"></a>추적 사용량과 관련 된 SDK 유형 및 함수

| 기능 | C++ API | C API | 참고 |
|--|--|--|--|
| 이벤트 콜백 설정 | [IAnalyzer](other-types/ianalyzer-class.md)<br />[IRelogger 거](other-types/irelogger-class.md) | [ANALYSIS_CALLBACKS](other-types/analysis-callbacks-struct.md)<br />[RELOG_CALLBACKS](other-types/relog-callbacks-struct.md) | Build C++ Insights SDK는 콜백 함수를 통해 이벤트를 제공 합니다. 에서 C++ianalyzer 또는 ire로거가 인터페이스를 상속 하는 분석기 또는 재로 거 클래스를 만들어 콜백 함수를 구현 합니다. C에서는 전역 함수에서 콜백을 구현 하 고 ANALYSIS_CALLBACKS 또는 RELOG_CALLBACKS 구조에서이에 대 한 포인터를 제공 합니다. |
| 그룹 빌드 | [MakeStaticAnalyzerGroup](functions/make-static-analyzer-group.md)<br />[MakeStaticReloggerGroup](functions/make-static-relogger-group.md)<br />[MakeDynamicAnalyzerGroup](functions/make-dynamic-analyzer-group.md)<br />[MakeDynamicReloggerGroup](functions/make-dynamic-relogger-group.md) |  | API C++ 는 여러 분석기와 다시로 거 개체를 그룹화 하기 위한 도우미 함수 및 형식을 제공 합니다. 그룹은 복잡 한 분석을 간단한 단계로 나눌 수 있는 간단한 방법입니다. [vcperf](https://github.com/microsoft/vcperf) 는 이러한 방식으로 구성 됩니다. |
| 분석 또는 다시 로깅 | [분석](functions/analyze.md)<br />[다시 기록할](functions/relog.md) | [AnalyzeA](functions/analyze-a.md)<br />[AnalyzeW](functions/analyze-w.md)<br />[RelogA](functions/relog-a.md)<br />[RelogW](functions/relog-w.md) |  |

### <a name="analyzing-and-relogging"></a>분석 및 다시 로깅

추적을 사용 하는 작업은 분석 세션이 나 relogging 세션을 통해 수행 됩니다.

대부분의 시나리오에서는 일반적인 분석을 사용 하는 것이 적합 합니다. 이 방법을 사용 하면 `printf` 텍스트, xml, JSON, 데이터베이스, REST 호출 등의 출력 형식을 유연 하 게 선택할 수 있습니다.

다시 로깅은 ETW 출력 파일을 생성 해야 하는 특별 한 용도의 분석에 사용할 수 있습니다. Relogging을 사용 하 여 C++ Build Insights 이벤트를 고유한 ETW 이벤트 형식으로 변환할 수 있습니다. 다시 로깅을 사용 하는 경우 기존 ETW 도구 및 C++ 인프라에 Insights 데이터를 연결 하는 것이 좋습니다. 예를 들어 [vcperf](https://github.com/microsoft/vcperf) 는 relogging 인터페이스를 사용 합니다. 이는 ETW 도구인 Windows 성능 분석기에서 이해할 수 있는 데이터를 생성 해야 하기 때문입니다. Relogging 인터페이스를 사용 하려는 경우 ETW 작동 방식에 대 한 몇 가지 사전 지식이 필요 합니다.

### <a name="creating-analyzer-groups"></a>분석기 그룹 만들기

그룹을 만드는 방법을 알고 있어야 합니다. *Hello, 세계!* 를 인쇄 하는 분석기 그룹을 만드는 방법을 보여 주는 예제는 다음과 같습니다. 수신 하는 모든 작업 시작 이벤트에 대해입니다.

```cpp
using namespace Microsoft::Cpp::BuildInsights;

class Hello : public IAnalyzer
{
public:
    AnalysisControl OnStartActivity(
        const EventStack& eventStack) override
    {
        std::cout << "Hello, " << std::endl;
        return AnalysisControl::CONTINUE;
    }
};

class World : public IAnalyzer
{
public:
    AnalysisControl OnStartActivity(
        const EventStack& eventStack) override
    {
        std::cout << "world!" << std::endl;
        return AnalysisControl::CONTINUE;
    }
};

int main()
{
    Hello hello;
    World world;

    // Let's make Hello the first analyzer in the group
    // so that it receives events and prints "Hello, "
    // first.
    auto group = MakeStaticAnalyzerGroup(&hello, &world);

    unsigned numberOfAnalysisPasses = 1;

    // Calling this function initiates the analysis and
    // forwards all events from "inputTrace.etl" to my analyzer
    // group.
    Analyze("inputTrace.etl", numberOfAnalysisPasses, group);

    return 0;
}
```

## <a name="using-events"></a>이벤트 사용

### <a name="sdk-types-and-functions-related-to-events"></a>이벤트와 관련 된 SDK 형식 및 함수

| 기능 | C++ API | C API | 참고 |
|--|--|--|--|
| 이벤트 일치 및 필터링 | [MatchEventStackInMemberFunction](functions/match-event-stack-in-member-function.md)<br />[MatchEventStack](functions/match-event-stack.md)<br />[MatchEventInMemberFunction](functions/match-event-in-member-function.md)<br />[MatchEvent](functions/match-event.md) |  | API C++ 는 추적에서 관심 있는 이벤트를 쉽게 추출할 수 있도록 하는 함수를 제공 합니다. C API를 사용 하 여이 필터링을 직접 수행 해야 합니다. |
| 이벤트 데이터 형식 | [활동](cpp-event-data-types/activity.md)<br />[BackEndPass](cpp-event-data-types/back-end-pass.md)<br />[BottomUp](cpp-event-data-types/bottom-up.md)<br />[C1DLL](cpp-event-data-types/c1-dll.md)<br />[C2DLL](cpp-event-data-types/c2-dll.md)<br />[CodeGeneration](cpp-event-data-types/code-generation.md)<br />[Ds](cpp-event-data-types/command-line.md)<br />[컴파일러나](cpp-event-data-types/compiler.md)<br />[CompilerPass](cpp-event-data-types/compiler-pass.md)<br />[고 environmentvariable](cpp-event-data-types/environment-variable.md)<br />[이벤트](cpp-event-data-types/event.md)<br />[EventGroup](cpp-event-data-types/event-group.md)<br />[EventStack](cpp-event-data-types/event-stack.md)<br />[ExecutableImageOutput](cpp-event-data-types/executable-image-output.md)<br />[출력](cpp-event-data-types/exp-output.md)<br />[FileInput](cpp-event-data-types/file-input.md)<br />[FileOutput](cpp-event-data-types/file-output.md)<br />[ForceInlinee](cpp-event-data-types/force-inlinee.md)<br />[FrontEndFile](cpp-event-data-types/front-end-file.md)<br />[FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md)<br />[FrontEndPass](cpp-event-data-types/front-end-pass.md)<br />[Function](cpp-event-data-types/function.md)<br />[ImpLibOutput](cpp-event-data-types/imp-lib-output.md)<br />[호출](cpp-event-data-types/invocation.md)<br />[InvocationGroup](cpp-event-data-types/invocation-group.md)<br />[을 출력 합니다.](cpp-event-data-types/lib-output.md)<br />[링커](cpp-event-data-types/linker.md)<br />[LinkerGroup](cpp-event-data-types/linker-group.md)<br />[LinkerPass](cpp-event-data-types/linker-pass.md)<br />[LTCG](cpp-event-data-types/ltcg.md)<br />[ObjOutput](cpp-event-data-types/obj-output.md)<br />[OptICF](cpp-event-data-types/opt-icf.md)<br />[OptLBR](cpp-event-data-types/opt-lbr.md)<br />[OptRef](cpp-event-data-types/opt-ref.md)<br />[Pass1.log](cpp-event-data-types/pass1.md)<br />[Pass2](cpp-event-data-types/pass2.md)<br />[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md)<br />[SimpleEvent](cpp-event-data-types/simple-event.md)<br />[기호 이름](cpp-event-data-types/symbol-name.md)<br />[템플릿 인스턴스화](cpp-event-data-types/template-instantiation.md)<br />[TemplateInstantiationGroup](cpp-event-data-types/template-instantiation-group.md)<br />[스레드](cpp-event-data-types/thread.md)<br />[위쪽 아래쪽](cpp-event-data-types/top-down.md)<br />[TraceInfo](cpp-event-data-types/trace-info.md)<br />[WholeProgramAnalysis](cpp-event-data-types/whole-program-analysis.md) | [CL_PASS_DATA](c-event-data-types/cl-pass-data-struct.md)<br />[EVENT_COLLECTION_DATA](c-event-data-types/event-collection-data-struct.md)<br />[EVENT_DATA](c-event-data-types/event-data-struct.md)<br />[EVENT_ID](c-event-data-types/event-id-enum.md)<br />[FILE_DATA](c-event-data-types/file-data-struct.md)<br />[FILE_TYPE_CODE](c-event-data-types/file-type-code-enum.md)<br />[FRONT_END_FILE_DATA](c-event-data-types/front-end-file-data-struct.md)<br />[FUNCTION_DATA](c-event-data-types/function-data-struct.md)<br />[FUNCTION_FORCE_INLINEE_DATA](c-event-data-types/function-force-inlinee-data-struct.md)<br />[INVOCATION_DATA](c-event-data-types/invocation-data-struct.md)<br />[INVOCATION_VERSION_DATA](c-event-data-types/invocation-version-data-struct.md)<br />[MSVC_TOOL_CODE](c-event-data-types/msvc-tool-code-enum.md)<br />[NAME_VALUE_PAIR_DATA](c-event-data-types/name-value-pair-data-struct.md)<br />[SYMBOL_NAME_DATA](c-event-data-types/symbol-name-data-struct.md)<br />[TEMPLATE_INSTANTIATION_DATA](c-event-data-types/template-instantiation-data-struct.md)<br />[TEMPLATE_INSTANTIATION_KIND_CODE](c-event-data-types/template-instantiation-kind-code-enum.md)<br />[TRACE_INFO_DATA](c-event-data-types/trace-info-data-struct.md)<br />[TRANSLATION_UNIT_PASS_CODE](c-event-data-types/translation-unit-pass-code-enum.md) |  |

### <a name="activities-and-simple-events"></a>활동 및 단순 이벤트

이벤트는 *활동* 및 *단순 이벤트*의 두 가지 범주로 구분 됩니다. 활동은 시작 및 끝을 포함 하는 지속적인 프로세스입니다. 간단한 이벤트는 punctual 발생 하며 기간이 없습니다. C++ BUILD Insights SDK를 사용 하 여 MSVC 추적을 분석 하는 경우 작업이 시작 및 중지 될 때 별도의 이벤트를 받게 됩니다. 간단한 이벤트가 발생 하는 경우에는 이벤트를 하나만 받게 됩니다.

### <a name="parent-child-relationships"></a>부모-자식 관계

작업 및 단순 이벤트는 부모-자식 관계를 통해 서로 관련 됩니다. 활동 또는 단순 이벤트의 부모는 발생 하는 활동입니다. 예를 들어, 소스 파일을 컴파일할 때 컴파일러는 파일을 구문 분석 한 다음 코드를 생성 해야 합니다. 구문 분석 및 코드 생성 활동은 모두 컴파일러 활동의 자식입니다.

간단한 이벤트에는 기간이 없으므로 그 안에 발생 하는 다른 작업은 없습니다. 따라서 자식은 없습니다.

각 작업 및 단순 이벤트의 부모-자식 관계는 [이벤트 테이블](event-table.md)에 표시 됩니다. 이러한 관계를 파악 하는 것 C++ 은 Build Insights 이벤트를 사용할 때 중요 합니다. 이벤트의 전체 컨텍스트를 이해 하려면이를 사용 해야 하는 경우가 많습니다.

### <a name="properties"></a>속성

모든 이벤트에는 다음과 같은 속성이 있습니다.

| 속성 | 설명 |
|--|--|
| 유형 식별자 | 이벤트 유형을 고유 하 게 식별 하는 번호입니다. |
| 인스턴스 식별자 | 추적 내에서 이벤트를 고유 하 게 식별 하는 번호입니다. 동일한 형식의 두 이벤트가 추적에서 발생 하는 경우에는 둘 다 고유한 인스턴스 식별자를 가져옵니다. |
| 시작 시간 | 작업이 시작 된 시간 또는 간단한 이벤트가 발생 한 시간입니다. |
| 프로세스 식별자 | 이벤트가 발생 한 프로세스를 식별 하는 번호입니다. |
| 스레드 식별자 | 이벤트가 발생 한 스레드를 식별 하는 번호입니다. |
| 프로세서 인덱스 | 이벤트를 내보낸 논리적 프로세서를 나타내는 0부터 시작 하는 인덱스입니다. |
| 이벤트 이름 | 이벤트 유형을 설명 하는 문자열입니다. |

단순 이벤트 이외의 모든 활동에는 다음과 같은 속성도 있습니다.

| 속성 | 설명 |
|--|--|
| 중지 시간 | 작업이 중지 된 시간입니다. |
| 제외 기간 | 자식 활동에 소요 된 시간을 제외 하 고 활동에 소요 된 시간입니다. |
| CPU 시간 | CPU가 활동에 연결 된 스레드의 코드를 실행 하는 데 걸린 시간입니다. 활동에 연결 된 스레드가 중지 된 시간을 포함 하지 않습니다. |
| 배타 CPU 시간 | CPU 시간과 동일 하지만 자식 활동에 소요 된 CPU 시간을 제외 합니다. |
| 벽 시계 시간 업무 | 전체 벽 시계 시간에 대 한 활동의 기여도입니다. 벽 시계 시간 책임은 활동 간의 병렬 처리를 고려 합니다. 예를 들어 관련이 없는 두 활동이 병렬로 실행 된다고 가정 하겠습니다. 두 시간 모두 10 초, 정확히 동일한 시작 및 중지 시간을 갖습니다. 이 경우 빌드 정보는 5 초의 벽 시계 시간 책임을 모두 할당 합니다. 이와 달리 이러한 활동은 겹치지 않고 다른 활동을 실행 하는 경우 10 초의 벽 시계 시간 책임이 할당 됩니다. |
| 전용 벽 시계 시간 업무 | 벽 시계 시간 책임과 동일 하지만 자식 활동의 벽 시계 시간 책임은 제외 됩니다. |

일부 이벤트에는 언급 한 속성 이외의 속성이 있습니다. 이 경우 이러한 추가 속성이 [이벤트 테이블](event-table.md)에 나열 됩니다.

### <a name="consuming-events-provided-by-the-c-build-insights-sdk"></a>Build Insights SDK에서 제공 C++ 하는 이벤트 소비

#### <a name="the-event-stack"></a>이벤트 스택입니다.

Build Insights C++ SDK가 이벤트를 제공할 때마다 스택의 형태로 제공 됩니다. 스택의 마지막 항목은 현재 이벤트와 해당 부모 계층 이전의 항목입니다. 예를 들어, [LTCG](event-table.md#ltcg) 의 시작 및 중지 이벤트는 링커의 pass 1 중에 발생 합니다. 이 경우 수신 하는 스택은 \[[링커](event-table.md#linker), [pass1.log](event-table.md#pass1), LTCG\]를 포함 합니다. 부모 계층은 이벤트를 루트에 다시 추적할 수 있으므로 편리 합니다. 위에서 언급 한 LTCG 작업이 느려지는 경우 관련 된 링커 호출을 즉시 알아볼 수 있습니다.

#### <a name="matching-events-and-event-stacks"></a>이벤트 및 이벤트 스택 일치

Build C++ Insights SDK는 추적에 모든 이벤트를 제공 하지만 대부분의 하위 집합에 대해서만 관심을 갖습니다. 일부 경우에는 *이벤트 스택의*하위 집합에 대해서만 관심을 가질 수 있습니다. SDK는 필요한 이벤트 또는 이벤트 스택을 신속 하 게 추출 하 고 그렇지 않은 이벤트를 거부 하는 기능을 제공 합니다. 이러한 일치 함수를 통해 수행 됩니다.

|  |  |
|--|--|
| [MatchEvent](functions/match-event.md) | 지정 된 형식 중 하 나와 일치 하는 경우 이벤트를 유지 합니다. 람다 또는 다른 호출 가능 형식으로 일치 하는 이벤트를 전달 합니다. 이 함수는 이벤트의 부모 계층 구조를 고려 하지 않습니다. |
| [MatchEventInMemberFunction](functions/match-event-in-member-function.md) | 멤버가 멤버 함수의 매개 변수에 지정 된 형식과 일치 하면 이벤트를 유지 합니다. 일치 하는 이벤트를 멤버 함수로 전달 합니다. 이 함수는 이벤트의 부모 계층 구조를 고려 하지 않습니다. |
| [MatchEventStack](functions/match-event-stack.md) | 이벤트와 해당 부모 계층이 모두 지정 된 형식과 일치 하면 이벤트를 유지 합니다. 이벤트와 일치 하는 부모 계층 이벤트를 람다 또는 다른 호출 가능 형식으로 전달 합니다. |
| [MatchEventStackInMemberFunction](functions/match-event-stack-in-member-function.md) | 이벤트와 해당 부모 계층이 모두 멤버 함수의 매개 변수 목록에 지정 된 형식과 일치 하면 이벤트를 유지 합니다. 이벤트와 일치 하는 부모 계층 이벤트를 멤버 함수로 전달 합니다. |

`MatchEventStack`와 같은 이벤트 스택 일치 함수는 일치 시킬 부모 계층을 설명할 때 간격을 허용 합니다. 예를 들어 \[[링커](event-table.md#linker), [LTCG](event-table.md#ltcg)\] 스택에 관심이 있을 수 있습니다. 또한 \[링커, [pass1.log](event-table.md#pass1), LTCG\] 스택과 일치 합니다. 지정 된 마지막 유형은 일치 시킬 이벤트 유형 이어야 하며 부모 계층의 일부가 아닙니다.

#### <a name="capture-classes"></a>클래스 캡처

`Match*` 함수를 사용 하려면 일치 시킬 형식을 지정 해야 합니다. 이러한 형식은 *캡처 클래스*목록에서 선택 됩니다. 캡처 클래스는 아래에 설명 된 여러 범주로 제공 됩니다.

| 범주 | 설명 |
|--|--|
| 정확하게 일치 | 이러한 캡처 클래스는 특정 이벤트 유형과 일치 하는 데 사용 됩니다. [컴파일러 이벤트와](event-table.md#compiler) 일치 하는 [컴파일러](cpp-event-data-types/compiler.md) 클래스를 예로 들 수 있습니다. |
| 와일드카드 | 이러한 캡처 클래스를 사용 하 여 지원 되는 이벤트 목록의 모든 이벤트를 일치 시킬 수 있습니다. 예를 들어 [작업](cpp-event-data-types/activity.md) 와일드 카드는 임의의 작업 이벤트와 일치 합니다. 또 다른 예는 [FRONT_END_PASS](event-table.md#front-end-pass) 또는 [BACK_END_PASS](event-table.md#back-end-pass) 이벤트와 일치할 수 있는 [CompilerPass](cpp-event-data-types/compiler-pass.md) 와일드 카드입니다. |
| 그룹 | 그룹 캡처 클래스의 이름은 *그룹*으로 끝납니다. 간격을 무시 하 고 행에 있는 같은 형식의 여러 이벤트를 일치 시키는 데 사용 됩니다. 이벤트 스택에 있는 수를 알 수 없으므로 재귀 이벤트를 일치 시킬 때만 의미가 있습니다. 예를 들어 [FRONT_END_FILE](event-table.md#front-end-file) 작업은 컴파일러에서 파일을 구문 분석할 때마다 발생 합니다. 컴파일러가 파일을 구문 분석 하는 동안 include 지시문을 찾을 수 있기 때문에이 작업은 재귀적입니다. [FrontEndFile](cpp-event-data-types/front-end-file.md) 클래스는 스택에서 하나의 FRONT_END_FILE 이벤트만 일치 시킵니다. [FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md) 클래스를 사용 하 여 전체 포함 계층 구조를 일치 시킵니다. |
| 와일드 카드 그룹 | 와일드 카드 그룹은 와일드 카드 및 그룹의 속성을 결합 합니다. 이 범주의 유일한 클래스는 단일 이벤트 스택에서 모든 [링커](event-table.md#linker) 및 [컴파일러](event-table.md#compiler) 이벤트를 일치 시키고 캡처하는 [InvocationGroup](cpp-event-data-types/invocation-group.md)입니다. |

각 이벤트와 일치 하는 데 사용할 수 있는 캡처 클래스를 알아보려면 [이벤트 표](event-table.md) 를 참조 하세요.

#### <a name="after-matching-using-captured-events"></a>일치 후: 캡처한 이벤트 사용

일치가 성공적으로 완료 되 면 `Match*` 함수는 캡처 클래스 개체를 생성 하 고 지정 된 함수에 전달 합니다. 이러한 캡처 클래스 개체를 사용 하 여 이벤트의 속성에 액세스 합니다.

#### <a name="example"></a>예제

```cpp
AnalysisControl MyAnalyzer::OnStartActivity(const EventStack& eventStack)
{
    // The event types to match are specified in the PrintIncludes function
    // signature.  
    MatchEventStackInMemberFunction(eventStack, this, &MyAnalyzer::PrintIncludes);
}

// We want to capture event stacks where:
// 1. The current event is a FrontEndFile activity.
// 2. The current FrontEndFile activity has at least one parent FrontEndFile activity
//    and possibly many.
void PrintIncludes(FrontEndFileGroup parentIncludes, FrontEndFile currentFile)
{
    // Once we reach this point, the event stack we are interested in has been matched.
    // The current FrontEndFile activity has been captured into 'currentFile', and
    // its entire inclusion hierarchy has been captured in 'parentIncludes'.

    cout << "The current file being parsed is: " << currentFile.Path() << endl;
    cout << "This file was reached through the following inclusions:" << endl;

    for (auto& f : parentIncludes)
    {
        cout << f.Path() << endl;
    }
}
```

::: moniker-end
