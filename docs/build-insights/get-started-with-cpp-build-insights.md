---
title: C++ Build Insights 활용 시작
description: C++ 빌드 인사이트에 대한 높은 수준의 개요입니다.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3a75dfe3bf1263cce53d70b764607cad4eec86d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325723"
---
# <a name="get-started-with-c-build-insights"></a>C++ Build Insights 활용 시작

::: moniker range="<=vs-2017"

C++ 빌드 인사이트 도구는 Visual Studio 2019에서 사용할 수 있습니다. 해당 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range="vs-2019"

C++ 빌드 인사이트는 MSVC(Microsoft Visual C++) 도구 체인에 대한 가시성을 높이는 도구 모음입니다. 도구는 C++ 빌드에 대한 데이터를 수집하고 다음과 같은 일반적인 질문에 대답하는 데 도움이 되는 형식으로 제공합니다.

- 빌드가 충분히 병렬화되어 있습니까?
- 미리 컴파일된 헤더(PCH)에 무엇을 포함해야 합니까?
- 빌드 속도를 높이기 위해 중점을 두어야 할 특정 병목 현상이 있습니까?

이 기술의 주요 구성 요소는 다음과 같습니다.

- *vcperf.exe*, 빌드에 대한 추적을 수집하는 데 사용할 수있는 명령 줄 유틸리티,
- WPA에서 빌드 트레이스를 볼 수 있는 WPA(Windows 성능 분석기) 확장
- C++ 빌드 인사이트 SDK는 C++ 빌드 인사이트 데이터를 사용하는 사용자 고유의 도구를 만들기 위한 소프트웨어 개발 키트입니다.

아래 링크를 클릭하여 다음 구성 요소를 빠르게 시작하십시오.

[튜토리얼: vcperf 및 Windows 성능 분석기](tutorials/vcperf-and-wpa.md)\
C++ 프로젝트에 대한 빌드 추적을 수집하는 방법과 WPA에서 이를 보는 방법에 대해 알아봅니다.

[튜토리얼: 윈도우 성능 기본 사항](tutorials/wpa-basics.md)\
빌드 추적을 분석하기 위한 유용한 WPA 팁을 알아보십시오.

[C++ 인사이트 SDK 구축](reference/sdk/overview.md)\
C++ 빌드 인사이트 SDK의 개요입니다.

::: moniker-end
