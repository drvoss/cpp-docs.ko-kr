---
title: '자습서: Windows Performance Analyzer 기본 사항'
description: Windows 성능 분석기에서 기본 작업을 완료 하는 방법에 대 한 자습서입니다.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f197e7dfd852cd66039f7279f90e42b0cf75fd86
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333889"
---
# <a name="tutorial-windows-performance-analyzer-basics"></a>자습서: Windows Performance Analyzer 기본 사항

::: moniker range="<=vs-2017"

C++ Build Insights 도구는 Visual Studio 2019에서 사용할 수 있습니다. 해당 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2019로 설정 합니다.

::: moniker-end
::: moniker range="vs-2019"

빌드 C++ 통찰력을 효과적으로 사용 하려면 WPA (Windows 성능 분석기)에 대 한 지식이 필요 합니다. 이 문서를 통해 일반적인 WPA 작업을 익힐 수 있습니다. WPA를 사용 하는 방법에 대 한 자세한 내용은 [Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer) 설명서를 참조 하세요.

## <a name="change-the-view-mode"></a>보기 모드 변경

WPA는 추적을 탐색 하는 데 사용할 수 있는 두 가지 기본 보기 모드를 제공 합니다.

- 그래프 모드 및
- 테이블 모드입니다.

보기 창의 맨 위에 있는 보기 모드 아이콘을 사용 하 여 둘 사이를 전환할 수 있습니다.

![그래프 모드와 테이블 모드 간을 전환 합니다.](media/wpa-switching-view-mode.gif)

## <a name="select-presets"></a>사전 설정 선택

대부분 C++ 의 BUILD Insights WPA 보기에는 선택할 수 있는 여러 가지 미리 설정이 있습니다. 보기 창의 맨 위에 있는 드롭다운 메뉴를 사용 하 여 원하는 미리 설정을 선택할 수 있습니다.

![미리 설정을 선택 합니다.](media/wpa-presets.png)

## <a name="zoom-in-and-out"></a>확대 및 축소

일부 빌드 추적은 매우 크므로 세부 정보를 확인 하기가 어렵습니다. 관심 있는 영역을 확대 하려면 그래프를 마우스 오른쪽 단추로 클릭 하 고 **확대/축소**를 선택 합니다. 언제 든 지 **실행 취소**를 선택 하 여 이전 설정으로 돌아갈 수 있습니다. 이 이미지는 선택 항목을 사용 하는 예제와 **확대/축소** 명령을 사용 하 여 그래프의 특정 섹션을 확대 하는 예를 보여 줍니다.

![그래프를 확대 합니다.](media/wpa-zooming.gif)

## <a name="group-by-different-columns"></a>다른 열을 기준으로 그룹화

추적이 표시 되는 방식을 사용자 지정할 수 있습니다. 보기 창의 맨 위에 있는 기어 아이콘을 클릭 하 고 빌드 탐색기 뷰 편집기에서 열을 다시 정렬 합니다. 이 대화 상자에서 노란색 줄 위에 있는 열은 데이터 행이 그룹화 된 열입니다. 노란색 선 바로 위의 열은 특수 합니다. 그래프 뷰에서 색이 지정 된 막대에 표시 됩니다.

이 이미지는 링크 호출의 예제 막대 그래프를 보여 줍니다. 기어 아이콘을 사용 하 여 빌드 탐색기 뷰 편집기 대화 상자를 엽니다. 그런 다음 구성 요소 및 이름 열 항목을 노란색 줄 위에 놓습니다. 구성을 변경 하 여 세부 수준을 높이고 실제로 링커 내에서 발생 한 상황을 확인 합니다.

![그래프를 확대 합니다.](media/wpa-grouping.gif)

## <a name="see-also"></a>참고 항목

[자습서: vcperf 및 Windows Performance Analyzer](vcperf-and-wpa.md)\
[참조: vcperf 명령](/cpp/build-insights/reference/vcperf-commands)\
[참조: Windows Performance Analyzer 뷰](/cpp/build-insights/reference/wpa-views)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
