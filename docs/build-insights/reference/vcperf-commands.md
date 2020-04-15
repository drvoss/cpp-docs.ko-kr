---
title: '참조: vcperf 명령'
description: 명령줄 유틸리티 vcperf.exe에 대한 참조입니다.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9d3b0a9dbdfe922dc87f91006441e1f65d54c8a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323246"
---
# <a name="reference-vcperf-commands"></a>참조: vcperf 명령

::: moniker range="<=vs-2017"

C++ 빌드 인사이트 도구는 Visual Studio 2019에서 사용할 수 있습니다. 해당 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range="vs-2019"

이 문서에서는 *vcperf.exe에서*사용할 수 있는 명령과 사용 방법을 나열하고 설명합니다.

## <a name="commands-to-start-and-stop-traces"></a>추적을 시작하고 중지하는 명령

*중요: 다음 명령에는 모두 관리 권한이 필요합니다.*

| 옵션           | 인수 및 설명 |
|------------------|---------------------------|
| `/start`         | `[/nocpusampling]` `<sessionName>` |
|                  | *vcperf.exe는* 지정된 세션 이름 아래에서 추적을 시작하도록 지시합니다. 지정된 컴퓨터에서 한 번에 하나의 활성 세션만 있을 수 있습니다. <br/><br/> `/nocpusampling` 옵션이 지정되면 *vcperf.exe는* CPU 샘플을 수집하지 않습니다. Windows 성능 분석기에서 CPU 사용량(샘플) 보기의 사용을 방지하지만 수집된 추적을 작게 만듭니다. <br/><br/> 추적이 시작되면 *vcperf.exe가* 즉시 반환됩니다. 이벤트는 컴퓨터에서 실행되는 모든 프로세스에 대해 시스템 전체에서 수집됩니다. 즉, *vcperf.exe를*실행하는 데 사용한 명령 프롬프트와 동일한 명령 프롬프트에서 프로젝트를 빌드할 필요가 없습니다. 예를 들어 Visual Studio에서 프로젝트를 빌드할 수 있습니다. |
| `/stop`          | `<sessionName>` `<outputFile.etl>` |
|                  | 지정된 세션 이름으로 식별된 추적을 중지합니다. 추적에서 사후 처리 단계를 실행하여 WPA(Windows 성능 분석기)에서 볼 수 있는 파일을 생성합니다. 최상의 시청 환경을 위해 C++ 빌드 인사이트 추가 기능이 포함된 WPA 버전을 사용하십시오. 자세한 내용은 [C++ 빌드 인사이트를 시작하기](/cpp/build-insights/get-started-with-cpp-build-insights)를 참조하십시오. 매개 `<outputFile.etl>` 변수는 출력 파일을 저장할 위치를 지정합니다. |
| `/stopnoanalyze` | `<sessionName>` `<rawOutputFile.etl>` |
|                  | 지정된 세션 이름으로 식별된 추적을 중지하고 지정된 출력 파일에 처리되지 않은 원시 데이터를 기록합니다. 결과 파일은 WPA에서 볼 수 없습니다. <br/><br/> `/stop` 명령과 관련된 사후 처리 단계는 때때로 길어질 수 있습니다. 명령을 `/stopnoanalyze` 사용하여 이 사후 처리 단계를 지연시킬 수 있습니다. Windows `/analyze` 성능 분석기에서 볼 수 있는 파일을 생성할 준비가 되면 명령을 사용합니다. |

## <a name="miscellaneous-commands"></a>기타 명령

| 옵션     | 인수 및 설명 |
|------------|---------------------------|
| `/analyze` | `<rawInputFile.etl> <outputFile.etl>` |
|            | 명령에 의해 생성된 원시 추적 `/stopnoanalyze` 파일을 수락합니다. 이 추적에서 사후 처리 단계를 실행하여 Windows 성능 분석기에서 볼 수 있는 파일을 생성합니다. 최상의 시청 환경을 위해 C++ 빌드 인사이트 추가 기능이 포함된 WPA 버전을 사용하십시오. 자세한 내용은 [C++ 빌드 인사이트를 시작하기](/cpp/build-insights/get-started-with-cpp-build-insights)를 참조하십시오. |

## <a name="see-also"></a>참고 항목

[C++ 빌드 인사이트 로 시작하기](/cpp/build-insights/get-started-with-cpp-build-insights)\
[튜토리얼: Windows 성능 분석기 기본 사항](/cpp/build-insights/tutorials/wpa-basics)\
[참조: Windows 성능 분석기 보기](wpa-views.md)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
