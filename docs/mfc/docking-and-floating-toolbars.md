---
title: 도구 모음 고정 및 고정 해제
ms.date: 11/04/2016
f1_keywords:
- CBRS_SIZE_DYNAMIC
- CBRS_SIZE_FIXED
helpviewer_keywords:
- size [MFC], toolbars
- size
- frame windows [MFC], toolbar docking
- CBRS_ALIGN_ANY constant [MFC]
- palettes, floating
- toolbars [MFC], docking
- CBRS_SIZE_DYNAMIC constant [MFC]
- floating toolbars
- toolbars [MFC], size
- toolbars [MFC], floating
- fixed-size toolbars
- CBRS_SIZE_FIXED constant [MFC]
- toolbar controls [MFC], wrapping
- toolbars [MFC], wrapping
- floating palettes
ms.assetid: b7f9f9d4-f629-47d2-a3c4-2b33fa6b51e4
ms.openlocfilehash: 30113565167b96b0df84a65768a1dfabe92ceffe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369765"
---
# <a name="docking-and-floating-toolbars"></a>도구 모음 고정 및 고정 해제

Microsoft 파운데이션 클래스 라이브러리는 도킹 가능한 도구 모음을 지원합니다. 도킹 가능한 도구 모음을 부모 창의 모든 측면에 연결하거나 도킹하거나 자체 미니 프레임 창에서 분리하거나 부동할 수 있습니다. 이 문서에서는 응용 프로그램에서 도킹 가능한 도구 모음을 사용하는 방법을 설명합니다.

응용 프로그램 마법사를 사용하여 응용 프로그램의 스켈레톤을 생성하는 경우 도킹 가능한 도구 모음을 사용할지 여부를 선택하라는 메시지가 표시됩니다. 기본적으로 응용 프로그램 마법사는 응용 프로그램에 도킹 가능한 도구 모음을 배치하는 데 필요한 세 가지 작업을 수행하는 코드를 생성합니다.

- [프레임 창에서 도킹을 활성화합니다.](#_core_enabling_docking_in_a_frame_window)

- [도구 모음에 대한 도킹을 활성화합니다.](#_core_enabling_docking_for_a_toolbar)

- [도구 모음을 프레임 창에 도킹합니다.](#_core_docking_the_toolbar)

이러한 단계가 없는 경우 응용 프로그램에 표준 도구 모음이 표시됩니다. 응용 프로그램의 각 도킹 가능한 도구 모음에 대해 마지막 두 단계를 수행해야 합니다.

이 문서에서 다루는 다른 항목은 다음과 같습니다.

- [도구 모음 부동](#_core_floating_the_toolbar)

- [도구 모음의 동적으로 크기 조정](#_core_dynamically_resizing_the_toolbar)

- [고정 스타일 도구 모음의 둘러싸기 위치 설정](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)

MFC 일반 샘플 [DOCKTOOL](../overview/visual-cpp-samples.md) 예제를 참조하십시오.

## <a name="enabling-docking-in-a-frame-window"></a><a name="_core_enabling_docking_in_a_frame_window"></a>프레임 창에서 도킹 사용

도구 모음을 프레임 창에 도킹하려면 도킹을 허용하려면 프레임 창(또는 대상)을 사용하도록 설정해야 합니다. 이 작업은 프레임 창의 어느 쪽이 도킹을 허용하는지 나타내는 스타일 비트 집합인 하나의 *DWORD* 매개 변수를 사용하는 [CFrameWnd::EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking) 함수를 사용하여 수행됩니다. 도구 모음이 도킹하려고 하고 도킹할 수 있는 여러 면이 있는 경우 전달된 `EnableDocking` 매개변수에 표시된 면은 위쪽, 아래쪽, 왼쪽, 오른쪽 순서로 사용됩니다. 어디서나 컨트롤 바를 도킹할 수 있도록 **CBRS_ALIGN_ANY** 하려면 `EnableDocking`CBRS_ALIGN_ANY 전달합니다.

## <a name="enabling-docking-for-a-toolbar"></a><a name="_core_enabling_docking_for_a_toolbar"></a>도구 모음에 대한 도킹 사용

도킹 대상을 준비한 후에는 도구 모음(또는 소스)을 비슷한 방식으로 준비해야 합니다. [CControlBar::도킹하려는](../mfc/reference/ccontrolbar-class.md#enabledocking) 각 도구 모음에 대해 EnableDocking을 호출하여 도구 모음이 도킹할 대상 측면을 지정합니다. 프레임 창에서 도킹을 사용하도록 `CControlBar::EnableDocking` 설정된 측면과 일치하도록 호출에 지정된 측면이 없는 경우 도구 모음이 도킹할 수 없습니다. 부동 이면 프레임 창에 도킹할 수 없는 부동 도구 모음으로 남아 있습니다.

원하는 효과가 영구적으로 부동 도구 모음인 `EnableDocking` 경우 매개변수가 0인 호출합니다. 그런 다음 [CFrameWnd::FloatControlBar를](../mfc/reference/cframewnd-class.md#floatcontrolbar)호출합니다. 도구 모음은 부동 상태로 유지되어 영구적으로 아무 곳에도 도킹할 수 없습니다.

## <a name="docking-the-toolbar"></a><a name="_core_docking_the_toolbar"></a>도구 모음 도킹

프레임워크는 사용자가 도킹을 허용하는 프레임 창의 측면에 도구 모음을 놓려고 할 때 [CFrameWnd::DockControlBar를](../mfc/reference/cframewnd-class.md#dockcontrolbar) 호출합니다.

또한 언제든지 이 함수를 호출하여 컨트롤 막대를 프레임 창에 도킹할 수 있습니다. 이 작업은 일반적으로 초기화 중에 수행됩니다. 두 개 이상의 도구 모음을 프레임 창의 특정 측면에 도킹할 수 있습니다.

## <a name="floating-the-toolbar"></a><a name="_core_floating_the_toolbar"></a>도구 모음 부동

프레임 창에서 도킹 가능한 도구 모음을 부동 도구 모음이라고 합니다. [CFrameWnd::FloatControlBar를](../mfc/reference/cframewnd-class.md#floatcontrolbar) 호출하여 이 작업을 수행합니다. 부동 도구 모음, 배치할 점 및 부동 도구 모음이 수평 또는 수직인지 여부를 결정하는 선형 스타일을 지정합니다.

프레임워크는 사용자가 도킹된 위치에서 도구 모음을 드래그하여 도킹이 활성화되지 않은 위치에 삭제할 때 이 함수를 호출합니다. 프레임 창 내부 또는 외부의 어느 곳에나 있을 수 있습니다. 와 `DockControlBar`마찬가지로 초기화 중에 이 함수를 호출할 수도 있습니다.

도킹 가능한 도구 모음의 MFC 구현은 도킹 가능한 도구 모음을 지원하는 일부 응용 프로그램에서 발견되는 확장된 기능 중 일부를 제공하지 않습니다. 사용자 지정 가능한 도구 모음과 같은 기능은 제공되지 않습니다.

## <a name="dynamically-resizing-the-toolbar"></a><a name="_core_dynamically_resizing_the_toolbar"></a>도구 모음의 동적으로 크기 조정

Visual C++ 버전 4.0을 사용하면 응용 프로그램 사용자가 부동 도구 모음의 크기를 동적으로 조정할 수 있습니다. 일반적으로 도구 모음에는 가로로 표시되는 길고 선형 모양이 있습니다. 그러나 도구 모음의 방향과 모양을 변경할 수 있습니다. 예를 들어 사용자가 프레임 창의 세로 측면 중 하나에 도구 모음을 도킹하면 셰이프가 세로 레이아웃으로 변경됩니다. 여러 행의 단추가 있는 사각형으로 도구 모음의 모양을 바꿀 수도 있습니다.

다음을 수행할 수 있습니다.

- 동적 크기 조정을 도구 모음 특성으로 지정합니다.

- 고정 크기 조정을 도구 모음 특성으로 지정합니다.

이 지원을 제공하기 위해 [CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) 멤버 함수에 대한 호출에 사용할 두 가지 새로운 도구 모음 스타일이 있습니다. 아래에 이 계정과 키의 예제가 나와 있습니다.

- **CBRS_SIZE_DYNAMIC** 컨트롤 바는 동적입니다.

- **CBRS_SIZE_FIXED** 컨트롤 바가 고정되어 있습니다.

크기 동적 스타일을 사용하면 사용자가 부동 하는 동안 도구 모음의 크기를 조정할 수 있지만 도킹 된 동안에는 없습니다. 도구 모음은 사용자가 가장자리를 끌 때 모양을 변경해야 하는 위치에 "래핑"됩니다.

크기 고정 스타일은 도구 모음의 둘러싸기 상태를 유지하여 각 열의 단추 위치를 고정합니다. 응용 프로그램의 사용자는 도구 모음의 모양을 변경할 수 없습니다. 도구 모음은 단추 사이의 구분 기호 위치와 같은 지정된 위치에 래핑됩니다. 도구 모음이 도킹되었는지 부동 여부에 관계없이 이 셰이프를 유지합니다. 이 효과는 여러 개의 단추 열이 있는 고정 된 팔레트입니다.

[CToolBar::GetButtonStyle을](../mfc/reference/ctoolbar-class.md#getbuttonstyle) 사용하여 도구 모음의 단추에 대한 상태와 스타일을 반환할 수도 있습니다. 단추의 스타일에 따라 단추가 표시되는 방식과 사용자 입력에 응답하는 방식이 결정됩니다. 상태는 단추를 래핑된 상태에 있는지 여부를 알려줍니다.

## <a name="setting-wrap-positions-for-a-fixed-style-toolbar"></a><a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a>고정 스타일 도구 모음에 대한 둘러싸기 위치 설정

크기 고정 스타일이 있는 도구 모음의 경우 도구 모음이 줄 바꿈할 도구 모음 단추 인덱스를 지정합니다. 다음 코드는 주 프레임 창의 `OnCreate` 재정의에서 이 작업을 수행하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]

MFC 일반 샘플 [DOCKTOOL은](../overview/visual-cpp-samples.md) 클래스 [CControlBar](../mfc/reference/ccontrolbar-class.md) 및 [CToolBar의](../mfc/reference/ctoolbar-class.md) 멤버 함수를 사용하여 도구 모음의 동적 레이아웃을 관리하는 방법을 보여 주며 있습니다. 파일 편집막대를 참조하십시오. 도크툴의 CPP.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [도구 모음 기본 사항](../mfc/toolbar-fundamentals.md)

- [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)

- [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>참고 항목

[MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)
