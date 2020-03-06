---
title: '자습서: vcperf 및 Windows Performance Analyzer'
description: 빌드 추적을 분석 C++ 하는 데 vcperf 및 WPA를 사용 하는 방법에 대 한 자습서입니다.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 091e366da9342f2561620d975ead2f01b5439bad
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334045"
---
# <a name="tutorial-vcperf-and-windows-performance-analyzer"></a>자습서: vcperf 및 Windows Performance Analyzer

::: moniker range="<=vs-2017"

C++ Build Insights 도구는 Visual Studio 2019에서 사용할 수 있습니다. 해당 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2019로 설정 합니다.

::: moniker-end
::: moniker range="vs-2019"

이 자습서에서는 *vcperf* 를 사용 하 여 C++ 빌드 추적을 수집 하는 방법에 대해 알아봅니다. Windows 성능 분석기에서이 추적을 보는 방법에 대해서도 알아봅니다.

## <a name="step-1-install-and-configure-windows-performance-analyzer"></a>1 단계: Windows Performance Analyzer 설치 및 구성

WPA는 Windows ADK (평가 및 배포 키트)에서 사용할 수 있는 추적 뷰어입니다. Visual Studio 설치 관리자를 사용 하 여 설치할 수 있는 구성 요소에 속하지 않는 별도의 유틸리티입니다.

빌드 정보를 지 원하는 C++ WPA 버전은 현재 Windows ADK Insider preview 에서만 사용할 수 있습니다. 이 미리 보기에 액세스 하려면 [Windows 참가자 프로그램](https://insider.windows.com)에 등록 해야 합니다. Windows ADK preview를 얻기 위해 Windows 10 Insider preview 운영 체제를 설치할 필요가 없습니다. Windows 참가자 프로그램에 Microsoft 계정을 등록 하기만 하면 됩니다.

### <a name="to-download-and-install-wpa"></a>WPA를 다운로드 하 여 설치 하려면

참고: windows 성능 분석기를 설치 하려면 Windows 8 이상이 필요 합니다.

1. Windows ADK Insider preview [다운로드 페이지로](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewADK)이동 합니다.

1. Windows ADK Insider Preview를 다운로드 합니다. 디스크 이미지입니다.

1. 디스크 이미지를 열고 *adksetup* 설치 관리자를 실행 합니다.

1. 설치 하려는 기능에 대 한 메시지가 표시 되 면 **Windows 성능 도구 키트**를 선택 합니다. 원하는 경우 다른 기능을 선택할 수 있지만 WPA를 설치할 필요는 없습니다.

   ![Windows Performance Analyzer 설치 관리자의 기능 선택 화면](media/wpa-installation.png)

### <a name="configuration-steps"></a>빌드 정보를 구성 하려면

1. WPA를 시작 합니다.

1. **창** 을 선택 하 > **테이블 (실험적)을 선택**합니다.

1. **진단** 섹션으로 스크롤합니다.

1. 모든 MSVC Build Insights 뷰를 선택 합니다.

   ![Windows 성능 분석기의 테이블 선택 패널](media/wpa-configuration.png)

## <a name="step-2-trace-your-build-with-vcperfexe"></a>2 단계: vcperf를 사용 하 여 빌드 추적

빌드 정보 C++ 데이터를 보려면 먼저 다음 단계를 수행 하 여 추적 파일로 수집 합니다.

1. 관리자 모드에서 Visual Studio 2019에 대 한 네이티브 도구 또는 크로스 도구 개발자 명령 프롬프트를 엽니다. 시작 메뉴 항목을 마우스 오른쪽 단추로 클릭 하 고 **추가** > **관리자 권한으로 실행**을 선택 합니다.

1. 명령 프롬프트 창에서 다음 명령을 입력 합니다.

   **vcperf/start _세션 이름_**

   세션 이름을 선택 하 여 세션 이름 *에 대해 기억할 수 있습니다.*

1. 일반적인 방법으로 프로젝트를 빌드합니다. 동일한 명령 프롬프트 창을 사용 하 여 빌드할 필요는 없습니다.

1. 명령 프롬프트 창에서 다음 명령을 입력 합니다.

   **vcperf/stop _세션 이름_ _tracefile .etl_**

   *이전 세션 이름에* 대해 선택한 것과 동일한 세션 이름을 사용 합니다. *Tracefile .etl* 추적 파일에 적절 한 이름을 선택 합니다.

개발자 명령 프롬프트 창에서 일반적인 *vcperf* 명령 시퀀스는 다음과 같습니다.

![간단한 vcperf 사용 시나리오](media/vcperf-simple-usage.png)

### <a name="important-notes-about-vcperfexe"></a>Vcperf에 대 한 중요 참고 사항

- *Vcperf* 추적을 시작 하거나 중지 하려면 관리자 권한이 필요 합니다. **관리자 권한으로 실행**을 사용 하 여 여는 개발자 명령 프롬프트 창을 사용 합니다.

- 한 번에 하나의 추적 세션만 컴퓨터에서 실행 될 수 있습니다.

- 추적을 시작 하는 데 사용한 세션 이름을 명심 해야 합니다. 이름을 모르는 상태에서 실행 중인 세션을 중지 하는 것이 문제가 될 수 있습니다.

- *Cl.exe* *및 debug.exe와 마찬가지로*명령줄 유틸리티 *vcperf* 가 설치에 포함 되어 있습니다. 이 구성 요소를 가져오기 위해 추가 단계가 필요 하지 않습니다.

- *vcperf* 는 시스템에서 실행 되는 모든 MSVC 도구에 대 한 정보를 수집 합니다. 따라서 추적을 수집 하는 데 사용한 것과 동일한 명령 프롬프트에서 빌드를 시작할 필요가 없습니다. 다른 명령 프롬프트 또는 Visual Studio 에서도 프로젝트를 빌드할 수 있습니다.

## <a name="step-3-view-your-trace-in-windows-performance-analyzer"></a>3 단계: Windows 성능 분석기에서 추적 보기

WPA를 시작 하 고 방금 수집한 추적을 엽니다. WPA는이를 C++ Build Insights 추적으로 인식 하 고 왼쪽의 그래프 탐색기 패널에 다음 뷰가 표시 되어야 합니다.

- 빌드 탐색기
- Files
- 함수

이러한 보기가 표시 되지 않는 경우 [1 단계](#configuration-steps)에 설명 된 대로 WPA가 올바르게 구성 되어 있는지 두 번 확인 합니다. 다음과 같이 뷰를 오른쪽의 빈 분석 창으로 끌어서 빌드 데이터를 볼 수 있습니다.

![Windows 성능 C++ 분석기에서 Build Insights 추적 보기](media/wpa-viewing-trace.gif)

다른 뷰는 그래프 탐색기 패널에서 사용할 수 있습니다. 포함 된 정보에 관심이 있는 경우 분석 창으로 끌어 놓습니다. 유용한 것은 빌드 전반의 CPU 사용률을 보여 주는 CPU (샘플링 된) 뷰입니다.

## <a name="more-information"></a>자세한 정보

[자습서: Windows Performance Analyzer 기본 사항](wpa-basics.md)\
빌드 추적을 분석 하는 데 사용할 수 있는 일반적인 WPA 작업에 대해 알아봅니다.

[참조: vcperf 명령](/cpp/build-insights/reference/vcperf-commands)\
*Vcperf* 명령 참조는 사용 가능한 모든 명령 옵션을 나열 합니다.

[참조: Windows Performance Analyzer 뷰](/cpp/build-insights/reference/wpa-views)\
WPA의 C++ Build Insights 보기에 대 한 자세한 내용은이 문서를 참조 하세요.

[Windows 성능 분석기](/windows-hardware/test/wpt/windows-performance-analyzer)\
공식 WPA 설명서 사이트입니다.

::: moniker-end
