---
title: '방법: 도면 도구 사용'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.drawing
helpviewer_keywords:
- Image editor [C++], selecting drawing tools
- Image editor [C++], toolbar
- drawing tools
- Image editor [C++], drawing lines
- shapes, drawing
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 1f8c6eef-7760-45a9-a5cb-9e15c6f91245
ms.openlocfilehash: b0041124c35414a0c1c998642b5321319602c872
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359848"
---
# <a name="how-to-use-a-drawing-tool"></a>방법: 도면 도구 사용

**이미지 편집기에는** 모두 같은 방식으로 작동하는 자유형 그리기 및 삭제 도구가 있습니다. 도구를 선택하고 필요한 경우 [전경 및 배경 색과](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) 크기 및 모양 옵션을 선택합니다. 그런 다음 포인터를 이미지로 이동하고 클릭하거나 드래그하여 그리거나 지웁습니다.

## <a name="drawing-tools"></a>도면 도구

**이미지 편집기** 도구 모음 또는 **이미지** 메뉴에서 그리기 도구를 선택할 수 있습니다. **지우개** 도구, **브러시** 도구 또는 **에어브러시** 도구를 선택하면 옵션 선택기에서 해당 도구의 옵션이 표시됩니다.

> [!TIP]
> [이미지 편집기 도구 모음의](../windows/toolbar-image-editor-for-icons.md)단추 위로 커서를 마우스로 가리키면 도구 설명이 나타납니다. 이러한 팁은 여기에 언급 된 특정 단추를 식별하는 데 도움이됩니다.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>이미지 편집기 도구 모음에서 그리기 도구를 선택하고 사용하려면

1. **이미지 편집기** 도구 모음에서 단추를 선택합니다.

   - **지우개** 도구는 왼쪽 마우스 버튼을 누르면 현재 배경색으로 이미지 위에 페인트됩니다.

      > [!TIP]
      > **지우개** 도구를 사용하는 대신 그리기 도구 중 하나를 사용하여 배경색으로 그리는 것이 더 편리할 수 있습니다.

   - **연필** 도구는 한 픽셀의 일정한 너비로 자유로이 그립니다.

   - **브러시** 도구에는 다양한 모양과 크기가 있습니다.

   - **에어브러시** 도구는 브러시 중앙에 색상 픽셀을 임의로 분산합니다.

1. 필요한 경우 색상과 브러시를 선택합니다.

   - 색상 [팔레트에서](../windows/colors-window-image-editor-for-icons.md)왼쪽 마우스 단추를 선택하여 전경 색상 또는 오른쪽 마우스 단추를 선택하여 배경색을 선택합니다.

   - 옵션 [선택기에서](../windows/toolbar-image-editor-for-icons.md)사용할 브러시를 나타내는 모양을 선택합니다.

1. 그리기 또는 페인팅을 시작할 이미지의 위치를 가리킵니다. 선택한 도구에 따라 포인터모양이 변경됩니다.

1. 왼쪽 마우스 단추(전경 색상의 경우) 또는 오른쪽 마우스 단추(배경 색의 경우)를 누르고 그릴 때 길게 누릅니다.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>이미지 메뉴에서 그리기 도구를 선택하고 사용하려면

1. 메뉴 이미지**도구로** **이동합니다.** > 

1. 계단식 하위 메뉴에서 사용할 도구를 선택합니다.

## <a name="lines-or-closed-figures"></a>선 또는 닫힌 그림

선과 닫힌 그림을 그리는 **이미지 편집기** 도구는 모두 동일한 방식으로 작동합니다. 선의 경우 이러한 점은 끝점입니다. 닫힌 그림의 경우 이러한 점은 그림을 경계하는 사각형의 반대쪽 모서리입니다.

선은 현재 브러시 선택에 의해 결정된 너비로 그려지고, 액자 그림은 현재 폭 선택에 의해 결정된 폭으로 그려집니다. 왼쪽 마우스 단추를 누르면 현재 전경 색상이나 오른쪽 마우스 단추를 누르면 현재 배경 색으로 줄바임이 그려집니다.

### <a name="to-draw-a-line"></a>선을 그리려면

1. 이미지 [편집기 도구 모음을](../windows/toolbar-image-editor-for-icons.md) 사용하거나 **메뉴 이미지**> **도구로** 이동하여 **선** 도구를 선택합니다.

1. 필요한 경우 색상과 브러시를 선택합니다.

   - 색상 [팔레트에서](../windows/colors-window-image-editor-for-icons.md)왼쪽 마우스 단추를 선택하여 전경 색상 또는 오른쪽 마우스 단추를 선택하여 배경색을 선택합니다.

   - 옵션 [선택기에서](../windows/toolbar-image-editor-for-icons.md)사용할 브러시를 나타내는 모양을 선택합니다.

1. 포인터를 줄의 시작점에 배치합니다.

1. 선의 끝점으로 드래그합니다.

### <a name="to-draw-a-closed-figure"></a>닫힌 그림을 그리려면

1. 이미지 **편집기** 도구 모음을 사용하거나 **메뉴 이미지** > **도구로** 이동하여 닫힌 **그림 그리기** 도구를 선택합니다.

   **닫힌 그림 그리기** 도구는 해당 버튼에 표시된 대로 그림을 만듭니다.

1. 필요한 경우 색상과 선 너비를 선택합니다.

1. 그림을 그릴 사각형 영역의 한 모서리로 포인터를 이동합니다.

1. 포인터를 대각선 반대쪽 모서리로 끕습니다.

## <a name="custom-brushes"></a>사용자 정의 브러시

사용자 지정 브러시는 이미지 편집기의 기성용 브러시 중 하나처럼 선택하고 사용하는 **이미지의**직사각형 부분입니다. 선택 항목에서 수행할 수 있는 모든 작업은 사용자 지정 브러시에서도 수행할 수 있습니다.

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>이미지의 일부에서 사용자 지정 브러시를 만들려면

1. 브러시에 사용할 이미지 부분을 선택합니다.

1. **Shift** 키를 길게 누르고, 선택 에서 선택하고 이미지 에서 드래그하거나 **메뉴 이미지** > **사용 선택을 브러시로**이동합니다.

   선택 영역은 선택 영역의 색상을 이미지 전체에 분산하는 사용자 지정 브러시가 됩니다. 선택 영역의 복사본은 드래그 경로를 따라 남아 있습니다. 더 느리게 드래그할수록 더 많은 복사본이 만들어집니다.

   > [!NOTE]
   > 먼저 이미지의 일부를 선택하지 않고 **선택 영역을 브러시로 선택하면** 전체 이미지가 브러시로 사용됩니다. 사용자 지정 브러시를 사용하는 결과는 불투명 또는 투명 [배경을](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)선택했는지 여부에 따라 달라집니다.

현재 배경색과 일치하는 사용자 지정 브러시의 픽셀은 일반적으로 투명합니다. 배경색 픽셀이 기존 이미지 위에 페인트되도록 이 동작을 변경할 수 있습니다.

스탬프 나 스텐실과 같은 사용자 정의 브러시를 사용하여 다른 특수 효과를 만들 수 있습니다.

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>배경 색에 사용자 정의 브러시 모양을 그리려면

1. 불투명또는투명한배경을선택합니다.

1. 배경색을 그릴 색상으로 설정합니다.

1. 그릴 사용자 지정 브러시를 배치합니다.

1. 오른쪽 마우스 버튼을 선택합니다. 사용자 지정 브러시의 불투명 영역은 배경색으로 그려집니다.

### <a name="to-double-or-halve-the-custom-brush-size"></a>사용자 정의 브러시 크기를 두 배 또는 절반으로 줄이려면

**[플러스 기호()** **+** 키]를 눌러 브러시 크기를 두**-** 배로 늘리거나 마이너스 **기호()** 키를 눌러 반으로 줄입니다.

### <a name="to-cancel-the-custom-brush"></a>사용자 지정 브러시를 취소하려면

**Esc를** 누르거나 다른 그리기 도구를 선택합니다.

## <a name="requirements"></a>요구 사항

없음

## <a name="see-also"></a>참고 항목

[아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)<br/>
[방법: 아이콘 또는 기타 이미지 만들기](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[방법: 이미지 편집](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[방법: 색상으로 작업](../windows/working-with-color-image-editor-for-icons.md)<br/>
[가속기 키](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
