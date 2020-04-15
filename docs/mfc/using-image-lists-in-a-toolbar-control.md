---
title: 도구 모음 컨트롤에서 이미지 목록 사용
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: 81468528c15300a7e9ace6b20fd9fb34818f1928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366492"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>도구 모음 컨트롤에서 이미지 목록 사용

기본적으로 도구 모음 컨트롤의 단추에서 사용하는 이미지는 단일 비트맵으로 저장됩니다. 그러나 단추 이미지를 이미지 목록 집합에 저장할 수도 있습니다. 도구 모음 컨트롤 개체는 최대 세 개의 개별 이미지 목록을 사용할 수 있습니다.

- 사용 가능한 이미지 목록 현재 활성화된 도구 모음 단추에 대한 이미지가 포함되어 있습니다.

- 사용 안 함 이미지 목록 현재 사용 안 함 의 도구 모음 단추에 대 한 이미지를 포함 합니다.

- 강조 표시된 이미지 목록 현재 강조 표시된 도구 모음 단추에 대한 이미지가 포함되어 있습니다. 이 이미지 목록은 도구 모음에서 TBSTYLE_FLAT 스타일을 사용하는 경우에만 사용됩니다.

이러한 이미지 목록은 `CToolBarCtrl` 도구 모음 컨트롤에서 개체와 연결할 때 사용됩니다. 이 연결은 [CToolBarCtrl::SetImageList,](../mfc/reference/ctoolbarctrl-class.md#setimagelist) [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist)및 [SetHotImageList를](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist)호출하여 수행됩니다.

기본적으로 MFC는 클래스를 `CToolBar` 사용하여 MFC 응용 프로그램 도구 모음을 구현합니다. 그러나 멤버 `GetToolBarCtrl` 함수를 사용하여 포함된 `CToolBarCtrl` 개체를 검색할 수 있습니다. 그런 다음 반환된 `CToolBarCtrl` 개체를 사용하여 멤버 함수를 호출할 수 있습니다.

`m_ToolBarImages`다음 예제에서는 개체()에`m_ToolBarDisabledImages` `CToolBarCtrl` `m_ToolBarCtrl`사용 () 및 사용 안 함() 이미지 목록을 할당 하여 이 기술을 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
> 도구 모음 개체에서 사용하는 이미지 목록은 영구 객체여야 합니다. 이러한 이유로 일반적으로 MFC 클래스의 데이터 멤버입니다. 이 예제에서는 주 프레임 창 클래스입니다.

이미지 목록이 `CToolBarCtrl` 개체와 연결되면 프레임워크에 적절한 단추 이미지가 자동으로 표시됩니다.

## <a name="see-also"></a>참고 항목

[CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
