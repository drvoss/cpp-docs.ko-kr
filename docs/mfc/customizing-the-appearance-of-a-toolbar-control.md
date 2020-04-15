---
title: 도구 모음 컨트롤의 모양 사용자 지정
ms.date: 11/04/2016
f1_keywords:
- TBSTYLE_
helpviewer_keywords:
- flat toolbars
- CToolBar class [MFC], styles
- transparent toolbars
- TBSTYLE_ styles [MFC]
- CToolBarCtrl class [MFC], object styles
- toolbar controls [MFC], style
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
ms.openlocfilehash: 9f4f9d90113d5074555d1b0cc411f854abc67fe5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377470"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>도구 모음 컨트롤의 모양 사용자 지정

클래스는 `CToolBarCtrl` 도구 모음 개체의 모양(및 경우에 따라 동작)에 영향을 주는 많은 스타일을 제공합니다. 도구 모음 컨트롤을 처음 `dwCtrlStyle` 만들 `CToolBarCtrl::Create` 때 `CToolBar::CreateEx`(또는) 멤버 함수의 매개변수를 설정하여 도구 모음 개체를 수정합니다.

다음 스타일은 도구 모음 단추의 "3D" 측면과 단추 텍스트의 배치에 영향을 미칩니다.

- **TBSTYLE_FLAT** 도구 모음과 단추가 모두 투명한 플랫 도구 모음을 만듭니다. 단추 텍스트가 단추 비트맵 아래에 나타납니다. 이 스타일을 사용하면 커서 아래의 단추가 자동으로 강조 표시됩니다.

- **TBSTYLE_TRANSPARENT** 투명 도구 모음을 만듭니다. 투명 도구 모음에서 도구 모음은 투명하지만 단추는 그렇지 않습니다. 단추 텍스트가 단추 비트맵 아래에 나타납니다.

- **TBSTYLE_LIST** 단추 비트맵 의 오른쪽에 단추 텍스트를 배치합니다.

> [!NOTE]
> 다시 그리기 문제를 방지하려면 도구 모음 개체가 표시되기 전에 **TBSTYLE_FLAT** **및 TBSTYLE_TRANSPARENT** 스타일을 설정해야 합니다.

다음 스타일은 도구 모음에서 사용자가 끌어서 놓기를 사용하여 도구 모음 개체 내에서 개별 단추의 위치를 조정할 수 있는지 여부를 결정합니다.

- **TBSTYLE_ALTDRAG** 사용자가 ALT를 누를 때 도구 모음 단추의 위치를 드래그하여 변경할 수 있습니다. 이 스타일을 지정하지 않으면 단추를 드래그하는 동안 SHIFT를 누르고 있어야 합니다.

    > [!NOTE]
    >  도구 모음 단추를 끌 수 있도록 **하려면 CCS_ADJUSTABLE** 스타일을 지정해야 합니다.

- **TBSTYLE_REGISTERDROP** 마우스 **포인터가** 도구 모음 단추를 통과할 때 TBN_GETOBJECT 알림 메시지를 생성하여 대상 삭제 를 요청합니다.

나머지 스타일은 도구 모음 개체의 시각적 및 비시각적 측면에 영향을 미칩니다.

- **TBSTYLE_WRAPABLE** 여러 줄의 단추를 가질 수 있는 도구 모음을 만듭니다. 도구 모음 단추는 도구 모음이 너무 좁아서 동일한 줄에 모든 단추를 포함할 때 다음 줄로 "줄 바꿈"할 수 있습니다. 래핑은 분리 및 비그룹 경계에서 발생합니다.

- **TBSTYLE_CUSTOMERASE** **WM_ERASEBKGND** **메시지를** 처리 NM_CUSTOMDRAW 알림 메시지를 생성합니다.

- **TBSTYLE_TOOLTIPS** 응용 프로그램에서 도구 모음의 단추에 대한 설명 텍스트를 표시하는 데 사용할 수 있는 도구 설명 컨트롤을 만듭니다.

도구 모음 스타일 및 확장 된 스타일의 전체 목록은 Windows SDK에서 [도구 모음 컨트롤 및 단추 스타일](/windows/win32/Controls/toolbar-control-and-button-styles) 및 도구 모음 확장 [스타일을](/windows/win32/Controls/toolbar-extended-styles) 참조하십시오.

## <a name="see-also"></a>참고 항목

[CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
