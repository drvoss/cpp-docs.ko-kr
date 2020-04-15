---
title: '튜토리얼: vcperf 및 Windows 성능 분석기'
description: C ++ 빌드 추적을 분석하기 위해 vcperf 및 WPA를 사용하는 방법에 대한 자습서입니다.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c22f3dfddfd346d4f0eee898cb5164fd8923336e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323420"
---
# <a name="tutorial-vcperf-and-windows-performance-analyzer"></a>튜토리얼: vcperf 및 Windows 성능 분석기

::: moniker range="<=vs-2017"

C++ 빌드 인사이트 도구는 Visual Studio 2019에서 사용할 수 있습니다. 이 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range="vs-2019"

이 자습서에서는 *vcperf.exe를* 사용하여 C++ 빌드의 추적을 수집하는 방법을 배웁니다. Windows 성능 분석기에서 이 추적을 보는 방법도 알아봅니다.

## <a name="step-1-install-and-configure-windows-performance-analyzer"></a>1단계: Windows 성능 분석기 설치 및 구성

WPA는 Windows 평가 및 배포 키트(ADK)에서 사용할 수 있는 추적 뷰어입니다. Visual Studio 설치 관리자와 함께 설치할 수 있는 구성 요소의 일부가 아닌 별도의 유틸리티입니다.

C++ 빌드 인사이트를 지원하는 WPA 버전은 현재 Windows ADK 참가자 미리 보기에서만 사용할 수 있습니다. 이 미리 보기에 액세스하려면 Windows [참가자 프로그램에](https://insider.windows.com)등록해야 합니다. Windows ADK 미리 보기를 얻으려면 Windows 10 참가자 미리 보기 운영 체제를 설치할 필요가 없습니다. Windows 참가자 프로그램으로 Microsoft 계정을 등록하기만 하면 됩니다.

### <a name="to-download-and-install-wpa"></a>WPA를 다운로드하고 설치하려면

참고: Windows 성능 분석기를 설치하려면 Windows 8 이상이 필요합니다.

1. Windows ADK 참가자 미리 보기 [다운로드 페이지로](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewADK)이동합니다.

1. Windows ADK 내부자 미리 보기를 다운로드합니다. 디스크 이미지입니다.

1. 디스크 이미지를 열고 *adksetup.exe* 설치 프로그램을 실행합니다.

1. 설치하려는 기능에 대한 메시지가 표시되면 **Windows 성능 도구 키트를**선택합니다. 원하는 경우 다른 기능을 선택할 수 있지만 WPA를 설치할 필요는 없습니다.

   ![Windows 성능 분석기 설치 관리자의 기능 선택 화면](media/wpa-installation.png)

### <a name="to-configure-build-insights"></a><a name="configuration-steps"></a>빌드 인사이트를 구성하려면

1. WPA를 시작합니다.

1. **창** > **선택 테이블(실험)** 을 선택합니다.

1. 진단 섹션으로 아래로 **스크롤합니다.**

1. 모든 MSVC 빌드 인사이트 보기를 선택합니다.

   ![Windows 성능 분석기의 테이블 선택 패널](media/wpa-configuration.png)

## <a name="step-2-trace-your-build-with-vcperfexe"></a>2단계: vcperf.exe로 빌드 추적

C++ 인사이트 빌드 데이터를 보려면 먼저 다음 단계를 수행하여 추적 파일로 수집합니다.

1. 관리자 모드에서 Visual Studio 2019에 대한 기본 도구 또는 교차 도구 개발자 명령 프롬프트를 엽니다. (시작 메뉴 항목을 마우스 오른쪽 단추로 클릭하고**관리자로** **더 실행 하기** > 를 선택 합니다.)

1. 명령 프롬프트 창에서 다음 명령을 입력합니다.

   **vcperf.exe /시작 _세션 이름_**

   *세션 이름에*대해 기억할 세션 이름을 선택합니다.

1. 평소와 같이 프로젝트를 빌드합니다. 빌드할 때 동일한 명령 프롬프트 창을 사용할 필요가 없습니다.

1. 명령 프롬프트 창에서 다음 명령을 입력합니다.

   **vcperf.exe /중지 _세션이름_ _추적파일.etl_**

   이전에 *SessionName에* 대해 선택한 세션 이름을 사용합니다. *traceFile.etl* 추적 파일에 적합한 이름을 선택합니다.

다음은 개발자 명령 프롬프트 창에서 일반적인 *vcperf.exe* 명령 시퀀스가 어떻게 보이는지입니다.

![간단한 vcperf.exe 사용 시나리오](media/vcperf-simple-usage.png)

### <a name="important-notes-about-vcperfexe"></a>vcperf.exe에 대한 중요 참고 사항

- *vcperf.exe* 추적을 시작하거나 중지하려면 관리자 권한이 필요합니다. **Run을 관리자로**사용하여 여는 개발자 명령 프롬프트 창을 사용합니다.

- 한 번에 하나의 추적 세션만 컴퓨터에서 실행할 수 있습니다.

- 추적을 시작하는 데 사용한 세션 이름을 기억해야 합니다. 이름을 모르고 실행 중인 세션을 중지하는 것이 번거로할 수 있습니다.

- *cl.exe* 및 *link.exe와*마찬가지로 명령줄 유틸리티 *vcperf.exe가* MSVC 설치에 포함되어 있습니다. 이 구성 요소를 얻으려면 추가 단계가 필요하지 않습니다.

- *vcperf.exe시스템에서* 실행되는 모든 MSVC 도구에 대한 정보를 수집합니다. 따라서 추적을 수집하는 데 사용한 것과 동일한 명령 프롬프트에서 빌드를 시작할 필요가 없습니다. 다른 명령 프롬프트또는 Visual Studio에서 프로젝트를 빌드할 수 있습니다.

## <a name="step-3-view-your-trace-in-windows-performance-analyzer"></a>3단계: Windows 성능 분석기에서 추적 보기

WPA를 실행하고 방금 수집한 추적을 엽니다. WPA는 이를 C++ 빌드 인사이트 추적으로 인식해야 하며 왼쪽그래프 탐색기 패널에 다음 보기가 표시되어야 합니다.

- 빌드 탐색기
- 파일
- 함수

이러한 뷰가 표시되지 않으면 [1단계에](#configuration-steps)설명된 대로 WPA가 올바르게 구성되었는지 다시 한 번 확인합니다. 다음과 같이 뷰를 오른쪽의 빈 분석 창으로 드래그하여 빌드 데이터를 볼 수 있습니다.

![Windows 성능 분석기에서 C++ 빌드 인사이트 추적 보기](media/wpa-viewing-trace.gif)

다른 보기는 그래프 탐색기 패널에서 사용할 수 있습니다. 포함된 정보에 관심이 있을 때 분석 창으로 드래그합니다. 유용한 것은 빌드 전체에서 CPU 사용률을 보여 주므로 CPU(샘플) 보기입니다.

## <a name="more-information"></a>자세한 정보

[튜토리얼: Windows 성능 분석기 기본 사항](wpa-basics.md)\
빌드 추적을 분석하는 데 도움이 되는 일반적인 WPA 작업에 대해 알아봅니다.

[참조: vcperf 명령](/cpp/build-insights/reference/vcperf-commands)\
*vcperf.exe* 명령 참조에는 사용 가능한 모든 명령 옵션이 나열됩니다.

[참조: Windows 성능 분석기 보기](/cpp/build-insights/reference/wpa-views)\
WPA의 C++ 빌드 인사이트 보기에 대한 자세한 내용은 이 문서를 참조하십시오.

[윈도우 성능 분석기](/windows-hardware/test/wpt/windows-performance-analyzer)\
공식 WPA 문서 사이트입니다.

::: moniker-end
