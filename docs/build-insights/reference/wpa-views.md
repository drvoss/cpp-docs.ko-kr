---
title: '참조: Windows Performance Analyzer 뷰'
description: Windows 성능 C++ 분석기에서 사용할 수 있는 Build Insights 보기에 대 한 참조입니다.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: eb3e20ed3ca4231b10efaf36310f6fbc0f5980bf
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333895"
---
# <a name="reference-windows-performance-analyzer-views"></a>참조: Windows Performance Analyzer 뷰

::: moniker range="<=vs-2017"

C++ Build Insights 도구는 Visual Studio 2019에서 사용할 수 있습니다. 해당 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2019로 설정 합니다.

::: moniker-end
::: moniker range="vs-2019"

이 문서는 C++ Windows 성능 분석기 (WPA)에서 사용할 수 있는 각 Build Insights 보기에 대 한 세부 정보를 제공 합니다. 이 페이지를 사용 하 여 다음을 찾을 수 있습니다.

- 데이터 열 설명 하거나
- 용도 및 기본 설정 보기 모드를 포함 하 여 각 보기에 사용할 수 있는 사전 설정입니다.

WPA를 처음 사용 하는 경우 먼저 [wpa의 기본 사항에 대해 C++ ](/cpp/build-insights/tutorials/wpa-basics)숙지 하는 것이 좋습니다.

## <a name="build-explorer"></a>빌드 탐색기

빌드 탐색기 뷰를 사용 하 여 다음 작업을 수행 합니다.

- 병렬 처리 문제 진단
- 빌드 시간이 구문 분석, 코드 생성 또는 링크를 통해 결정 되는 경우를 확인 합니다.
- 병목 상태 및 비정상적으로 긴 빌드 작업을 식별 합니다.

### <a name="build-explorer-view-data-columns"></a>빌드 탐색기 뷰 데이터 열

| 열 이름 | 설명 |
|-|-|
| BuildTimelineDescription | 현재 작업 또는 속성이 발생 하는 타임 라인에 대 한 텍스트 설명입니다. |
| BuildTimelineId          | 현재 작업 또는 속성이 발생 하는 타임 라인에 대 한 0부터 시작 하는 식별자입니다. |
| 구성 요소                | 현재 이벤트를 내보낼 때 컴파일하거나 연결 되는 구성 요소입니다. 이 이벤트에 연결 된 구성 요소가 없는 경우이 열의 값은 *\<호출 X 정보\>* 입니다. X는 이벤트를 내보낼 때 실행 되는 호출에 대 한 고유 숫자 식별자입니다. 이 식별자는이 이벤트의 InvocationId 열에 있는 식별자와 동일 합니다. |
| 개수                    | 이 데이터 행으로 표시 되는 작업 또는 속성의 수입니다. 이 값은 항상 1 이며 여러 행을 그룹화 하는 경우에만 집계 시나리오에 유용 합니다. |
| ExclusiveCPUTime         | 이 작업에서 사용한 CPU 시간 (밀리초)입니다. 자식 활동에 소요 된 시간은이 크기에 포함 되지 않습니다. |
| ExclusiveDuration        | 작업의 밀리초 기간입니다. 자식 활동의 기간은이 크기에 포함 되지 않습니다. |
| InclusiveCPUTime         | 이 작업 및 모든 자식 작업에서 사용한 CPU 시간 (밀리초)입니다. |
| InclusiveDuration        | 모든 자식 활동을 포함 하 여이 활동의 밀리초 기간입니다. |
| InvocationDescription    | 이 이벤트가 발생 한 호출에 대 한 텍스트 설명입니다. 설명에는 *cl.exe* 인지, *링크 .exe*인지, 그리고 고유한 숫자 호출 식별자가 포함 됩니다. 해당 하는 경우 호출 중에 컴파일 또는 연결 된 구성 요소에 대 한 전체 경로를 포함 합니다. 구성 요소를 빌드하지 않는 호출 또는 여러 구성 요소를 작성 하는 호출의 경우 경로는 비어 있습니다. 호출 식별자는 InvocationId 열에 있는 식별자와 동일 합니다. |
| InvocationId             | 이 이벤트가 발생 한 호출에 대 한 고유 숫자 식별자입니다. |
| 이름                     | 이 이벤트가 나타내는 작업 또는 속성의 이름입니다. |
| 시간                     | 이벤트가 발생 한 시기를 식별 하는 타임 스탬프입니다. |
| 도구                     | 이 이벤트가 발생 했을 때 실행 되는 도구입니다. 이 열의 값은 CL 또는 링크 중 하나입니다. |
| 형식                     | 현재 이벤트의 형식입니다. 이 값은 작업 또는 속성입니다. |
| 값                    | 현재 이벤트가 속성 인 경우이 열에 해당 값이 포함 됩니다. 현재 이벤트가 작업 인 경우이 열은 비어 있습니다. |

### <a name="build-explorer-view-presets"></a>빌드 탐색기 뷰 미리 설정

| 기본 설정 이름           | 기본 설정 보기 모드 | 사용 방법 |
|-----------------------|---------------------|------------|
| 활동 통계   | 그래프/테이블       | 이 사전 설정을 사용 하 여 모든 빌드 탐색기 작업에 대 한 집계 된 통계를 볼 수 있습니다. 테이블 모드에서는 구문 분석, 코드 생성 또는 링커를 통해 빌드를 지배 하는지 여부를 한눈에 파악할 수 있습니다. 각 작업에 대 한 집계 기간은 내림차순으로 정렬 됩니다. 위쪽 노드를 확장 하 여 이러한 최상위 활동에 가장 많은 시간을 소요 하는 호출을 쉽게 찾을 수 있습니다. 원하는 경우에는 WPA 설정을 조정 하 여 평균 또는 다른 유형의 집계를 표시할 수 있습니다. 그래프 모드에서는 빌드하는 동안 각 활동이 활성 상태인 경우를 참조 하세요. |
| 어떠한           | 그래프               | 그래프 뷰에서 시작 시간을 기준으로 정렬 된 호출 목록을 아래로 스크롤합니다. CPU (샘플링 된) 뷰와 함께 사용 하 여 CPU 사용률이 낮은 영역에 맞게 조정 되는 호출을 찾을 수 있습니다. 병렬 처리 문제를 검색 합니다. |
| 호출 속성 | Table               | 지정 된 컴파일러 또는 링커 호출에 대 한 주요 정보를 빠르게 찾습니다. 해당 버전, 작업 디렉터리 또는 호출에 사용 되는 전체 명령줄을 결정 합니다. |
| Timeline             | 그래프               | 빌드가 병렬화 된 방법의 막대 그래프를 확인 합니다. 병렬 처리 문제 및 병목 상태를 한눈에 파악 합니다. 사용자 요구에 따라 막대에 다른 의미를 할당 하도록 WPA를 구성 합니다. 모든 호출의 색으로 구분 된 막대 그래프를 보려면 호출 설명을 마지막 그룹화 된 열로 선택 합니다. 시간이 많이 걸리는 원인을 신속 하 게 식별 하는 데 도움이 됩니다. 그런 다음 가장 긴 부분을 보기 위해 작업 이름을 마지막 그룹화 된 열로 확대 하 고 선택 합니다. |

## <a name="files"></a>Files

파일 뷰를 사용 하 여 다음 작업을 수행 합니다.

- 가장 자주 포함 되는 헤더를 확인 합니다.
- 미리 컴파일된 헤더 (PCH)에 포함할 항목을 결정 하는 데 도움이 됩니다.

### <a name="files-view-data-columns"></a>파일 뷰 데이터 열

| 열 이름              | 설명 |
|--------------------------|-------------|
| ActivityName             | 이 파일 이벤트를 내보낼 때 진행 중인 작업입니다. 현재이 값은 항상 *구문 분석*입니다. |
| BuildTimelineDescription | * |
| BuildTimelineId          | * |
| 구성 요소                | * |
| 개수                    | * |
| 깊이                    | 이 파일이 있는 포함 트리의 위치 (0부터 시작)입니다. 계산은 포함 트리의 루트에서 시작 합니다. 값 0은 일반적으로 .c/.cpp 파일에 해당 합니다. |
| ExclusiveDuration        | * |
| IncludedBy               | 현재 파일을 포함 하는 파일의 전체 경로입니다. |
| IncludedPath             | 현재 파일의 전체 경로입니다. |
| InclusiveDuration        | * |
| InvocationId             | * |
| StartTime                | 현재 파일 이벤트를 내보낸 시간을 나타내는 타임 스탬프입니다. |
| 도구                     | * |

이 열의 값이 [빌드 탐색기](#build-explorer-view-data-columns) 뷰의 값과 동일 \*.

### <a name="files-view-presets"></a>파일 보기 미리 설정

| 기본 설정 이름 | 기본 설정 보기 모드 | 사용 방법 |
|-------------|---------------------|------------|
| 통계  | Table               | 목록을 내림차순으로 살펴보면 집계 된 구문 분석 시간이 가장 높은 파일을 확인 합니다. 이 정보를 사용 하 여 헤더를 재구성 하거나 PCH에 포함할 항목을 결정 합니다. |

## <a name="functions"></a>함수

함수 뷰는 코드 생성 시간이 과도 하 게 긴 함수를 식별 하는 데 사용 됩니다.

### <a name="functions-view-data-columns"></a>함수 뷰 데이터 열

| 열 이름              | 설명 |
|--------------------------|-------------|
| ActivityName             | 이 함수 이벤트를 내보낼 때 진행 중인 작업입니다. 현재이 값은 항상 *Codegeneration*입니다. |
| BuildTimelineDescription | * |
| BuildTimelineId          | * |
| 구성 요소                | * |
| 개수                    | * |
| 지속 시간                 | 이 함수에 대 한 코드 생성 활동의 기간입니다. |
| FunctionName             | 코드를 생성 하는 함수의 이름입니다. |
| InvocationId             | * |
| StartTime                | 현재 함수 이벤트를 내보낸 시간을 나타내는 타임 스탬프입니다. |
| 도구                     | * |

이 열의 값이 [빌드 탐색기](#build-explorer-view-data-columns) 뷰의 값과 동일 \*.

### <a name="functions-view-presets"></a>함수 뷰 사전 설정

| 기본 설정 이름 | 기본 설정 보기 모드 | 사용 방법 |
|-------------|---------------------|------------|
| 통계  | Table               | 목록을 내림차순으로 살펴보면 집계 된 코드 생성 시간이 가장 높은 함수를 확인 합니다. 코드에서 **__forceinline** 키워드를 과도 하 게 사용 하는 경우 또는 일부 기능이 너무 클 수 있습니다. |
| Timeline   | 그래프               | 이 막대 그래프를 살펴보면 생성 하는 데 가장 많은 시간이 걸리는 함수의 위치와 기간을 확인할 수 있습니다. 빌드 탐색기 보기에서 병목 현상이 병목 상태와 일치 하는지 확인 합니다. 이렇게 하면 적절 한 조치를 취하여 코드 생성 시간을 줄이고 빌드 시간을 활용할 수 있습니다. |

## <a name="see-also"></a>참고 항목

[빌드 Insights를 C++ 사용 하 여 시작](/cpp/build-insights/get-started-with-cpp-build-insights)\
[참조: vcperf 명령](vcperf-commands.md)\
[자습서: Windows Performance Analyzer 기본 사항](/cpp/build-insights/tutorials/wpa-basics)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
