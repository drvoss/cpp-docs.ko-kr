---
title: '튜토리얼: Windows 성능 분석기 기본 사항'
description: Windows 성능 분석기에서 기본 작업을 완료하는 방법에 대한 자습서입니다.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ae1050b9389527a12f5bdbea6d695c0f20510127
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323397"
---
# <a name="tutorial-windows-performance-analyzer-basics"></a>튜토리얼: Windows 성능 분석기 기본 사항

::: moniker range="<=vs-2017"

C++ 빌드 인사이트 도구는 Visual Studio 2019에서 사용할 수 있습니다. 이 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range="vs-2019"

C++ 빌드 인사이트를 효과적으로 사용하려면 WPA(Windows 성능 분석기)에 대한 지식이 필요합니다. 이 문서에서는 일반적인 WPA 작업에 익숙해질 수 있습니다. WPA 사용 방법에 대한 자세한 내용은 [Windows 성능 분석기](/windows-hardware/test/wpt/windows-performance-analyzer) 설명서를 참조하십시오.

## <a name="change-the-view-mode"></a>뷰 모드 변경

WPA는 흔적을 탐색할 수 있는 두 가지 기본 보기 모드를 제공합니다.

- 그래프 모드, 및
- 테이블 모드로 바있습니다.

뷰 창 상단의 뷰 모드 아이콘을 사용하여 둘 사이를 전환할 수 있습니다.

![그래프 모드와 테이블 모드 사이를 전환합니다.](media/wpa-switching-view-mode.gif)

## <a name="select-presets"></a>사전 설정 선택

대부분의 C++ 빌드 인사이트 WPA 보기에는 선택할 수 있는 여러 사전 설정이 있습니다. 뷰 창 상단의 드롭다운 메뉴를 사용하여 원하는 사전 설정을 선택할 수 있습니다.

![사전 설정을 선택합니다.](media/wpa-presets.png)

## <a name="zoom-in-and-out"></a>확대/축소

일부 빌드 추적은 너무 커서 세부 정보를 만들기가 어렵습니다. 관심 있는 영역을 확대하려면 그래프를 마우스 오른쪽 단추로 클릭하고 **확대/축소를**선택합니다. **확대/축소 수행을**선택하여 언제든지 이전 설정으로 돌아갈 수 있습니다. 이 이미지는 선택 영역과 **확대/축소** 명령을 사용하여 그래프의 섹션을 확대하는 예제를 보여 주며 있습니다.

![그래프를 확대합니다.](media/wpa-zooming.gif)

## <a name="group-by-different-columns"></a>다른 열별로 그룹화

추적이 표시되는 방식을 사용자 지정할 수 있습니다. 뷰 창 상단의 기어 아이콘을 클릭하고 탐색기 보기 편집기 빌드에서 열을 다시 정렬합니다. 이 대화 상자의 노란색 선 위에 있는 열은 데이터 행이 그룹화되어 있는 열입니다. 노란색 선 바로 위의 열은 특별합니다: 그래프 보기에서 색상 막대에 표시됩니다.

이 이미지는 링크 호출의 예제 막대 그래프를 보여 주었습니다. 기어 아이콘을 사용하여 탐색기 탐색기 보기 편집기 만들기 대화 상자를 엽니다. 그런 다음 구성 요소 및 이름 열 항목을 노란색 선 위로 드래그합니다. 세부 수준을 높이고 링커 내부에서 실제로 어떤 일이 일어났는지 확인하기 위해 구성이 변경되었습니다.

![그래프를 확대합니다.](media/wpa-grouping.gif)

## <a name="see-also"></a>참고 항목

[튜토리얼: vcperf 및 Windows 성능 분석기](vcperf-and-wpa.md)\
[참조: vcperf 명령](/cpp/build-insights/reference/vcperf-commands)\
[참조: Windows 성능 분석기 보기](/cpp/build-insights/reference/wpa-views)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
