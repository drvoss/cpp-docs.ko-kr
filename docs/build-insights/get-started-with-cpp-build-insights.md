---
title: C++ Build Insights 활용 시작
description: 빌드 정보에 대 C++ 한 개략적인 개요입니다.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2a5799fecc885b96f4278e0f5077662ce5fd7c8f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332009"
---
# <a name="get-started-with-c-build-insights"></a>C++ Build Insights 활용 시작

::: moniker range="<=vs-2017"

C++ Build Insights 도구는 Visual Studio 2019에서 사용할 수 있습니다. 해당 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2019로 설정 합니다.

::: moniker-end
::: moniker range="vs-2019"

C++빌드 통찰력은 MSVC (Microsoft 시각적 개체 C++ ) 도구 체인에 대 한 향상 된 가시성을 제공 하는 도구 모음입니다. 도구는 C++ 빌드에 대 한 데이터를 수집 하 고 다음과 같은 일반적인 질문에 대답 하는 데 도움이 되는 형식으로 표시 합니다.

- 빌드가 충분히 병렬 처리 되나요?
- 미리 컴파일된 헤더 (PCH)에 포함 해야 하는 항목은 무엇 인가요?
- 빌드 속도를 높이기 위해 초점을 맞춰야 하는 특정 병목 현상이 있나요?

이 기술의 주요 구성 요소는 다음과 같습니다.

- 빌드에 대 한 추적을 수집 하는 데 사용할 수 있는 명령줄 유틸리티인 *vcperf*
- WPA에서 빌드 추적을 볼 수 있도록 하는 Windows 성능 분석기 (WPA) 확장
- C++ BUILD insights SDK는 빌드 insights 데이터를 사용 C++ 하는 고유한 도구를 만들기 위한 소프트웨어 개발 키트입니다.

아래 링크를 클릭 하 여 이러한 구성 요소를 신속 하 게 시작 하세요.

[자습서: vcperf 및 Windows Performance Analyzer](tutorials/vcperf-and-wpa.md)\
C++ 프로젝트에 대 한 빌드 추적을 수집 하는 방법 및 WPA에서 프로젝트를 보는 방법에 대해 알아봅니다.

[자습서: Windows 성능 기본 사항](tutorials/wpa-basics.md)\
빌드 추적을 분석 하는 데 유용한 WPA 팁을 검색 합니다.

Insights SDK\ 빌드 [ C++ ](reference/sdk/overview.md)
C++ BUILD Insights SDK에 대 한 개요입니다.

::: moniker-end
