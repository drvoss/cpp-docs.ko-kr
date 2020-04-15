---
title: C++ 인사이트 SDK 구축
description: 비주얼 스튜디오 C++ 빌드 인사이트 SDK의 개요입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyzing
- Relogging
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 126abb0d039227eb269500966d46ef0a729763ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323256"
---
# <a name="c-build-insights-sdk"></a>C++ 인사이트 SDK 구축

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

C++ 빌드 인사이트 SDK는 C++ 빌드 인사이트 플랫폼 위에 개인화된 도구를 만들 수 있는 API 모음입니다. 이 페이지에서는 시작하는 데 도움이 되는 수준 개요를 제공합니다.

## <a name="obtaining-the-sdk"></a>SDK 획득

다음 단계에 따라 C++ 빌드 인사이트 SDK를 NuGet 패키지로 다운로드할 수 있습니다.

1. Visual Studio 2017 이상에서 새 C++ 프로젝트를 만듭니다.
1. 솔루션 **탐색기** 창에서 프로젝트를 마우스 오른쪽 단추로 클릭합니다.
1. 컨텍스트 메뉴에서 **NuGet 패키지 관리를 선택합니다.**
1. 오른쪽 상단에서 **nuget.org** 패키지 소스를 선택합니다.
1. Microsoft.Cpp.BuildInsights 패키지의 최신 버전을 검색합니다.
1. **설치를**선택합니다.
1. 라이센스를 수락합니다.

SDK를 둘러싼 일반적인 개념에 대한 자세한 내용은 계속 읽어보십시오. 또한 공식 [C++ Build Insights 샘플 GitHub 리포지토리에](https://github.com/microsoft/cpp-build-insights-samples) 액세스하여 SDK를 사용하는 실제 C++ 응용 프로그램의 예를 볼 수도 있습니다.

## <a name="collecting-a-trace"></a>추적 수집

C++ 인사이트 빌드 SDK를 사용하여 MSVC 도구 체인에서 나오는 이벤트를 분석하려면 먼저 추적을 수집해야 합니다. SDK는 기본 추적 기술로 Windows용 이벤트 추적(ETW)을 사용합니다. 추적 수집은 두 가지 방법으로 수행할 수 있습니다.

### <a name="method-1-using-vcperf-in-visual-studio-2019-and-above"></a>방법 1: Visual Studio 2019 이상에서 vcperf 사용

1. VS 2019에 대한 상승 된 x64 기본 도구 명령 프롬프트를 엽니 다.
1. 다음 명령을 실행합니다. `vcperf /start MySessionName`
1. 프로젝트를 빌드합니다.
1. 다음 명령을 실행합니다. `vcperf /stopnoanalyze MySessionName outputTraceFile.etl`

   > [!IMPORTANT]
   > vcperf로 추적을 `/stopnoanalyze` 중지할 때 명령을 사용합니다. C++ 빌드 인사이트 SDK를 사용하여 일반 `/stop` 명령으로 중지된 추적을 분석할 수 없습니다.

### <a name="method-2-programmatically"></a>방법 2: 프로그래밍 방식으로

이러한 C++ 빌드 인사이트 SDK 추적 컬렉션 함수를 사용하여 프로그래밍 방식으로 추적을 시작하고 중지합니다. **이러한 함수 호출을 실행하는 프로그램에는 관리 권한이 있어야 합니다.** 추적 시작 및 중지 함수에만 관리 권한이 필요합니다. C++ 빌드 인사이트 SDK의 다른 모든 함수는 이러한 함수 없이 실행할 수 있습니다.

### <a name="sdk-functions-related-to-trace-collection"></a>추적 수집과 관련된 SDK 함수

| 기능 | C++ API | C API |
|--|--|--|
| 추적 시작 | [스타트트레이싱세션](functions/start-tracing-session.md) | [스타트트레이싱세션A](functions/start-tracing-session-a.md)<br />[스타트트레이싱세션W](functions/start-tracing-session-w.md) |
| 추적 중지 | [스톱트레이싱세션](functions/stop-tracing-session.md) | [스톱트레이싱세션A](functions/stop-tracing-session-a.md)<br />[스톱트레이싱세션W](functions/stop-tracing-session-w.md) |
| 추적 중지 및<br />결과를 즉시 분석 | [스톱앤분석트레이싱세션](functions/stop-and-analyze-tracing-session.md) | [스톱앤분석트레이싱세션A](functions/stop-and-analyze-tracing-session-a.md)<br />[스톱앤분석트레이싱세션](functions/stop-and-analyze-tracing-session-w.md) |
| 추적 중지 및<br />즉시 결과를 다시 기록 | [스톱앤로그트레이싱세션](functions/stop-and-relog-tracing-session.md) | [스톱앤로그트레이싱세션A](functions/stop-and-relog-tracing-session-a.md)<br />[스톱앤로그트레이싱세션W](functions/stop-and-relog-tracing-session-w.md) |

다음 섹션에서는 분석 또는 리로깅 세션을 구성하는 방법을 보여 줄 수 있습니다. [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md)과 같은 결합된 기능 기능에 필요합니다.

## <a name="consuming-a-trace"></a>추적 사용

ETW 추적이 있으면 C++ 빌드 인사이트 SDK를 사용하여 압축을 풀어보세요. SDK는 도구를 신속하게 개발할 수 있는 형식으로 이벤트를 제공합니다. SDK를 사용하지 않고 원시 ETW 추적을 사용하지 않는 것이 좋습니다. MSVC에서 사용하는 이벤트 형식은 문서화되지 않았으며 대규모 빌드로 확장되도록 최적화되어 있으며 이해하기 어렵습니다. 또한 C++ 빌드 인사이트 SDK API는 안정적이며 원시 ETW 추적 형식은 예고 없이 변경될 수 있습니다.

### <a name="sdk-types-and-functions-related-to-trace-consumption"></a>추적 소비와 관련된 SDK 유형 및 함수

| 기능 | C++ API | C API | 메모 |
|--|--|--|--|
| 이벤트 콜백 설정 | [I분석기](other-types/ianalyzer-class.md)<br />[아이레로거](other-types/irelogger-class.md) | [ANALYSIS_CALLBACKS](other-types/analysis-callbacks-struct.md)<br />[RELOG_CALLBACKS](other-types/relog-callbacks-struct.md) | C++ 빌드 인사이트 SDK는 콜백 함수를 통해 이벤트를 제공합니다. C++에서 IAnalyzer 또는 IRelogger 인터페이스를 상속하는 분석기 또는 relogger 클래스를 만들어 콜백 함수를 구현합니다. C에서 전역 함수에서 콜백을 구현 하고 ANALYSIS_CALLBACKS 또는 RELOG_CALLBACKS 구조에서 포인터를 제공합니다. |
| 그룹 작성 | [정전기 분석기 그룹 만들기](functions/make-static-analyzer-group.md)<br />[메이크스테틱 리로거그룹](functions/make-static-relogger-group.md)<br />[메이크다이내믹분석기그룹](functions/make-dynamic-analyzer-group.md)<br />[메이크다이나믹리로거그룹](functions/make-dynamic-relogger-group.md) |  | C++ API는 도우미 함수와 형식을 제공하여 여러 분석기 및 리로거 개체를 함께 그룹화합니다. 그룹은 복잡한 분석을 더 간단한 단계로 나누는 깔끔한 방법입니다. [vcperf는](https://github.com/microsoft/vcperf) 이러한 방식으로 구성됩니다. |
| 분석 또는 리깅 | [분석](functions/analyze.md)<br />[리로그 (재기록)](functions/relog.md) | [분석A](functions/analyze-a.md)<br />[분석W](functions/analyze-w.md)<br />[레로가](functions/relog-a.md)<br />[리로그W](functions/relog-w.md) |  |

### <a name="analyzing-and-relogging"></a>분석 및 리깅

추적을 사용하는 것은 분석 세션 또는 리로깅 세션을 통해 수행됩니다.

일반 분석을 사용하는 것은 대부분의 시나리오에 적합합니다. 이 방법을 사용하면 `printf` 텍스트, xml, JSON, 데이터베이스, REST 호출 등 출력 형식을 유연하게 선택할 수 있습니다.

리로깅은 ETW 출력 파일을 생성해야 하는 특수 목적 분석을 위한 것입니다. 리로깅을 사용하여 C++ Build Insights 이벤트를 고유한 ETW 이벤트 형식으로 변환할 수 있습니다. 리로깅을 적절하게 사용하면 C++ Build Insights 데이터를 기존 ETW 도구 및 인프라에 연결하는 것이 좋습니다. 예를 들어 [vcperf는](https://github.com/microsoft/vcperf) 리로깅 인터페이스를 사용합니다. 이는 ETW 도구인 Windows 성능 분석기에서 이해할 수 있는 데이터를 생성해야 하기 때문입니다. 리로깅 인터페이스를 사용하려는 경우 ETW 작동 방식에 대한 몇 가지 사전 지식이 필요합니다.

### <a name="creating-analyzer-groups"></a>분석기 그룹 만들기

그룹을 만드는 방법을 아는 것이 중요합니다. 다음은 *Hello, world를* 인쇄하는 분석기 그룹을 만드는 방법을 보여 주는 예제입니다! 모든 활동 시작 이벤트에 대해 수신합니다.

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

### <a name="sdk-types-and-functions-related-to-events"></a>이벤트와 관련된 SDK 유형 및 기능

| 기능 | C++ API | C API | 메모 |
|--|--|--|--|
| 이벤트 일치 및 필터링 | [매치이벤트스택인멤버기능](functions/match-event-stack-in-member-function.md)<br />[매치이벤트스택](functions/match-event-stack.md)<br />[매치이벤트인멤버기능](functions/match-event-in-member-function.md)<br />[매치 이벤트](functions/match-event.md) |  | C++ API는 추적에서 관심 있는 이벤트를 쉽게 추출할 수 있는 기능을 제공합니다. C API를 사용하면 이 필터링을 직접 수행해야 합니다. |
| 이벤트 데이터 형식 | [활동](cpp-event-data-types/activity.md)<br />[백엔드 패스](cpp-event-data-types/back-end-pass.md)<br />[상향식](cpp-event-data-types/bottom-up.md)<br />[C1DLL](cpp-event-data-types/c1-dll.md)<br />[C2DLL](cpp-event-data-types/c2-dll.md)<br />[코드 제너레이션](cpp-event-data-types/code-generation.md)<br />[명령줄](cpp-event-data-types/command-line.md)<br />[컴파일러](cpp-event-data-types/compiler.md)<br />[컴파일러 패스](cpp-event-data-types/compiler-pass.md)<br />[EnvironmentVariable](cpp-event-data-types/environment-variable.md)<br />[이벤트](cpp-event-data-types/event.md)<br />[이벤트 그룹](cpp-event-data-types/event-group.md)<br />[이벤트 스택](cpp-event-data-types/event-stack.md)<br />[실행 가능한이미지출력](cpp-event-data-types/executable-image-output.md)<br />[출력 량](cpp-event-data-types/exp-output.md)<br />[파일 입력](cpp-event-data-types/file-input.md)<br />[파일 출력](cpp-event-data-types/file-output.md)<br />[포스인린](cpp-event-data-types/force-inlinee.md)<br />[프론트 엔드 파일](cpp-event-data-types/front-end-file.md)<br />[프론트 엔드 파일 그룹](cpp-event-data-types/front-end-file-group.md)<br />[프론트엔드패스](cpp-event-data-types/front-end-pass.md)<br />[기능](cpp-event-data-types/function.md)<br />[임립출력](cpp-event-data-types/imp-lib-output.md)<br />[호출](cpp-event-data-types/invocation.md)<br />[호출 그룹](cpp-event-data-types/invocation-group.md)<br />[LibOutput](cpp-event-data-types/lib-output.md)<br />[링커](cpp-event-data-types/linker.md)<br />[링커 그룹](cpp-event-data-types/linker-group.md)<br />[링커 패스](cpp-event-data-types/linker-pass.md)<br />[LTCG](cpp-event-data-types/ltcg.md)<br />[Obj출력](cpp-event-data-types/obj-output.md)<br />[옵티피피그](cpp-event-data-types/opt-icf.md)<br />[옵틀브르](cpp-event-data-types/opt-lbr.md)<br />[옵트레프](cpp-event-data-types/opt-ref.md)<br />[패스 1](cpp-event-data-types/pass1.md)<br />[패스 2](cpp-event-data-types/pass2.md)<br />[프리트CG옵트레프](cpp-event-data-types/pre-ltcg-opt-ref.md)<br />[심플 이벤트](cpp-event-data-types/simple-event.md)<br />[기호 이름](cpp-event-data-types/symbol-name.md)<br />[템플릿 인스턴스화](cpp-event-data-types/template-instantiation.md)<br />[템플릿 인스턴스화 그룹](cpp-event-data-types/template-instantiation-group.md)<br />[스레드](cpp-event-data-types/thread.md)<br />[하향하](cpp-event-data-types/top-down.md)<br />[트레이스정보](cpp-event-data-types/trace-info.md)<br />[전체 프로그램 분석](cpp-event-data-types/whole-program-analysis.md) | [CL_PASS_DATA](c-event-data-types/cl-pass-data-struct.md)<br />[EVENT_COLLECTION_DATA](c-event-data-types/event-collection-data-struct.md)<br />[EVENT_DATA](c-event-data-types/event-data-struct.md)<br />[EVENT_ID](c-event-data-types/event-id-enum.md)<br />[FILE_DATA](c-event-data-types/file-data-struct.md)<br />[FILE_TYPE_CODE](c-event-data-types/file-type-code-enum.md)<br />[FRONT_END_FILE_DATA](c-event-data-types/front-end-file-data-struct.md)<br />[FUNCTION_DATA](c-event-data-types/function-data-struct.md)<br />[FUNCTION_FORCE_INLINEE_DATA](c-event-data-types/function-force-inlinee-data-struct.md)<br />[INVOCATION_DATA](c-event-data-types/invocation-data-struct.md)<br />[INVOCATION_VERSION_DATA](c-event-data-types/invocation-version-data-struct.md)<br />[MSVC_TOOL_CODE](c-event-data-types/msvc-tool-code-enum.md)<br />[NAME_VALUE_PAIR_DATA](c-event-data-types/name-value-pair-data-struct.md)<br />[SYMBOL_NAME_DATA](c-event-data-types/symbol-name-data-struct.md)<br />[TEMPLATE_INSTANTIATION_DATA](c-event-data-types/template-instantiation-data-struct.md)<br />[TEMPLATE_INSTANTIATION_KIND_CODE](c-event-data-types/template-instantiation-kind-code-enum.md)<br />[TRACE_INFO_DATA](c-event-data-types/trace-info-data-struct.md)<br />[TRANSLATION_UNIT_PASS_CODE](c-event-data-types/translation-unit-pass-code-enum.md) |  |

### <a name="activities-and-simple-events"></a>액티비티 및 간단한 이벤트

이벤트는 *활동과* *간단한 이벤트의*두 가지 범주로 나뉩니다. 활동은 시작과 끝이 있는 시간에 진행 중인 프로세스입니다. 간단한 이벤트는 시간 엄수 발생이며 지속 시간이 없습니다. C++ 빌드 인사이트 SDK를 통해 MSVC 추적을 분석할 때 활동이 시작되고 중지될 때 별도의 이벤트를 받게 됩니다. 간단한 이벤트가 발생하면 하나의 이벤트만 받게 됩니다.

### <a name="parent-child-relationships"></a>부모-자식 관계

활동과 간단한 이벤트는 부모-자식 관계를 통해 서로 관련됩니다. 활동 또는 간단한 이벤트의 부모는 활동 또는 간단한 이벤트가 발생하는 포괄 활동입니다. 예를 들어 소스 파일을 컴파일할 때 컴파일러는 파일을 구문 분석한 다음 코드를 생성해야 합니다. 구문 분석 및 코드 생성 활동은 컴파일러 활동의 두 자식입니다.

간단한 이벤트에는 지속 시간이 없으므로 내부에서 다른 이벤트는 발생하지 않습니다. 따라서, 그들은 어떤 아이가 없습니다.

각 활동의 부모-자식 관계 및 간단한 이벤트가 [이벤트 테이블에](event-table.md)표시됩니다. C++ Build Insights 이벤트를 사용하는 경우 이러한 관계를 아는 것이 중요합니다. 이벤트의 전체 컨텍스트를 이해하기 위해 이에 의존해야 하는 경우가 많습니다.

### <a name="properties"></a>속성

모든 이벤트에는 다음과 같은 속성이 있습니다.

| 속성 | Description |
|--|--|
| 유형 식별자 | 이벤트 유형을 고유하게 식별하는 숫자입니다. |
| 인스턴스 식별자 | 추적 내의 이벤트를 고유하게 식별하는 숫자입니다. 동일한 형식의 두 이벤트가 추적에서 발생하는 경우 둘 다 고유한 인스턴스 식별자를 가져옵니다. |
| 시작 시간 | 활동이 시작된 시간 또는 간단한 이벤트가 발생한 시간입니다. |
| 프로세스 식별자 | 이벤트가 발생한 프로세스를 식별하는 숫자입니다. |
| 스레드 식별자 | 이벤트가 발생한 스레드를 식별하는 숫자입니다. |
| 프로세서 인덱스 | 이벤트가 내보낸 논리 프로세서를 나타내는 0기반 인덱스입니다. |
| 이벤트 이름 | 이벤트 형식을 설명하는 문자열입니다. |

단순 이벤트 이외의 모든 활동에도 다음과 같은 속성이 있습니다.

| 속성 | Description |
|--|--|
| 중지 시간 | 활동이 중지된 시간입니다. |
| 배타적 지속 시간 | 하위 활동에 소요된 시간을 제외한 활동에 소요된 시간입니다. |
| CPU 시간 | CPU가 활동에 연결된 스레드에서 코드를 실행하는 데 소요된 시간입니다. 활동에 연결된 스레드가 절전 모드인 시간은 포함되지 않습니다. |
| 독점 CPU 시간 | CPU 시간과 동일하지만 자식 활동에 소요된 CPU 시간을 제외합니다. |
| 월-클럭 시간 책임 | 전체 월 클럭 시간에 대한 활동의 기여도입니다. 월 시계 시간 책임은 활동 간의 병렬성을 고려합니다. 예를 들어 관련없는 두 활동이 병렬로 실행된다고 가정해 보겠습니다. 둘 다 10 초의 지속 시간을 가지고 있으며, 정확히 같은 시작 및 중지 시간을 가짐을 가합니다. 이 경우 인사이트 빌드는 월-클럭 시간(월 시계 시간) 5초를 모두 할당합니다. 반대로 이러한 활동이 겹치지 않고 차례로 실행되는 경우 둘 다 10초의 월 시계 시간 책임이 할당됩니다. |
| 전용 월-클럭 시간 책임 | 월-시계 시간 책임과 동일하지만, 아동 활동의 월-시계 시간 책임은 제외합니다. |

일부 이벤트에는 언급된 것 이상으로 자체 속성이 있습니다. 이 경우 이러한 추가 속성은 [이벤트 테이블에](event-table.md)나열됩니다.

### <a name="consuming-events-provided-by-the-c-build-insights-sdk"></a>C++ 빌드 인사이트 SDK에서 제공하는 이벤트 소비

#### <a name="the-event-stack"></a>이벤트 스택

C++ 빌드 인사이트 SDK가 이벤트를 제공 할 때마다 스택 형태로 제공됩니다. 스택의 마지막 항목은 현재 이벤트이며 상위 계층 구조 이전의 항목입니다. 예를 [들어, LTCG](event-table.md#ltcg) 시작 및 중지 이벤트는 링커의 패스 1 동안 발생합니다. 이 경우 수신할 스택에는 \[ [LINKER,](event-table.md#linker) [PASS1,](event-table.md#pass1)LTCG\]가 포함됩니다. 상위 계층 구조는 이벤트를 루트로 추적할 수 있으므로 편리합니다. 위에서 언급한 LTCG 활동이 느린 경우 어떤 링커 호출이 관련되었는지 즉시 확인할 수 있습니다.

#### <a name="matching-events-and-event-stacks"></a>이벤트 및 이벤트 스택 일치

C++ 빌드 인사이트 SDK는 모든 이벤트를 추적으로 제공하지만 대부분의 경우 이벤트의 하위 집합에만 신경을 써야 합니다. 경우에 따라 *이벤트 스택의*하위 집합에 대해서만 신경을 쓸 수 있습니다. SDK는 필요한 이벤트 또는 이벤트 스택을 신속하게 추출하고 필요하지 않은 이벤트 스택을 거부하는 데 도움이 되는 시설을 제공합니다. 이러한 일치 하는 함수를 통해 수행 됩니다.

|  |  |
|--|--|
| [매치 이벤트](functions/match-event.md) | 지정된 형식 중 하나와 일치하는 경우 이벤트를 유지합니다. 일치하는 이벤트를 람다 또는 다른 호출 가능한 유형으로 전달합니다. 이벤트의 상위 계층 구조는 이 함수에서 고려되지 않습니다. |
| [매치이벤트인멤버기능](functions/match-event-in-member-function.md) | 멤버 함수의 매개 변수에 지정된 형식과 일치하는 경우 이벤트를 유지합니다. 일치하는 이벤트를 멤버 함수로 전달합니다. 이벤트의 상위 계층 구조는 이 함수에서 고려되지 않습니다. |
| [매치이벤트스택](functions/match-event-stack.md) | 이벤트와 상위 계층 이 지정된 형식과 일치하는 경우 이벤트를 유지합니다. 이벤트와 일치하는 상위 계층 구조 이벤트를 lambda 또는 다른 호출 가능한 유형으로 전달합니다. |
| [매치이벤트스택인멤버기능](functions/match-event-stack-in-member-function.md) | 이벤트와 상위 계층 이 멤버 함수의 매개 변수 목록에 지정된 형식과 일치하는 경우 이벤트를 유지합니다. 이벤트와 일치하는 상위 계층 구조를 멤버 함수로 전달합니다. |

이벤트 스택 일치 함수는 부모 계층 구조를 일치하도록 설명할 때 간격을 `MatchEventStack` 허용합니다. 예를 들어 \[ [LINKER](event-table.md#linker), [LTCG](event-table.md#ltcg) \] 스택에 관심이 있다고 말할 수 있습니다. 또한 \[링커, [PASS1,](event-table.md#pass1)LTCG\] 스택과 일치합니다. 마지막으로 지정된 형식은 일치하는 이벤트 유형이어야 하며 상위 계층의 일부가 아닙니다.

#### <a name="capture-classes"></a>클래스 캡처

함수를 `Match*` 사용하려면 일치할 형식을 지정해야 합니다. 이러한 형식은 *캡처 클래스*목록에서 선택됩니다. 캡처 클래스는 아래에 설명된 여러 범주로 나뉩니다.

| 범주 | Description |
|--|--|
| Exact | 이러한 캡처 클래스는 특정 이벤트 유형과 일치하는 데 사용되며 다른 클래스는 일치하지 않습니다. 예를 들어 [컴파일러](cpp-event-data-types/compiler.md) 이벤트와 일치하는 [컴파일러](event-table.md#compiler) 클래스가 있습니다. |
| 와일드카드 | 이러한 캡처 클래스는 지원하는 이벤트 목록의 모든 이벤트와 일치하는 데 사용할 수 있습니다. 예를 들어 [활동](cpp-event-data-types/activity.md) 와일드카드는 모든 활동 이벤트와 일치합니다. 또 다른 예로 [컴파일러패스](cpp-event-data-types/compiler-pass.md) 와일드카드로 [FRONT_END_PASS](event-table.md#front-end-pass) 또는 [BACK_END_PASS](event-table.md#back-end-pass) 이벤트를 일치시킬 수 있습니다. |
| 그룹 | 그룹 캡처 클래스의 이름은 *그룹에서*끝납니다. 간격을 무시하고 동일한 유형의 여러 이벤트를 연속으로 일치시도록 하는 데 사용됩니다. 이벤트 스택에 얼마나 많은 이벤트가 있는지 알 수 없으므로 재귀 이벤트를 일치시킬 때만 의미가 있습니다. 예를 들어 [컴파일러가](event-table.md#front-end-file) 파일을 구문 분석할 때마다 FRONT_END_FILE 활동이 발생합니다. 컴파일러는 파일을 구문 분석하는 동안 include 지시문을 찾을 수 있으므로 이 작업은 재귀적입니다. [FrontEndFile](cpp-event-data-types/front-end-file.md) 클래스는 스택에서 하나의 FRONT_END_FILE 이벤트만 일치합니다. [FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md) 클래스를 사용하여 전체 포함 계층 구조와 일치합니다. |
| 와일드카드 그룹 | 와일드카드 그룹은 와일드카드 및 그룹의 속성을 결합합니다. 이 범주의 유일한 클래스는 [호출 그룹이며,](cpp-event-data-types/invocation-group.md)모든 [LINKER](event-table.md#linker) 및 컴파일러 이벤트를 단일 이벤트 스택에서 일치시키고 [캡처합니다.](event-table.md#compiler) |

[이벤트 테이블을](event-table.md) 참조하여 각 이벤트와 일치하는 데 사용할 수 있는 캡처 클래스를 알아봅니다.

#### <a name="after-matching-using-captured-events"></a>일치 후: 캡처된 이벤트 사용

일치가 성공적으로 완료되면 함수는 `Match*` capture 클래스 개체를 생성하고 지정된 함수로 전달합니다. 이러한 캡처 클래스 개체를 사용하여 이벤트의 속성에 액세스합니다.

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
