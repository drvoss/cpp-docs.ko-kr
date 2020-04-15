---
title: 이미지 목록 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 440ab6fdfe7663557f6c6a6607e617c793d26674
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371581"
---
# <a name="creating-the-image-lists"></a>이미지 목록 만들기

이미지 목록을 만드는 것은 [CListView](../mfc/reference/clistview-class.md) 또는 [CListCtrl을](../mfc/reference/clistctrl-class.md)사용 하든 동일합니다.

> [!NOTE]
> 목록 컨트롤에 스타일이 `LVS_ICON` 포함된 경우에만 이미지 목록이 필요합니다.

클래스를 `CImageList` 사용하여 하나 이상의 이미지 목록(전체 크기 아이콘, 작은 아이콘 및 상태)을 만듭니다. [CImageList를](../mfc/reference/cimagelist-class.md)참조하고 Windows SDK의 [목록 보기 이미지 목록을](/windows/win32/Controls/using-list-view-controls) 참조하십시오.

각 이미지 목록에 대해 [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) 를 호출합니다. 포인터를 해당 `CImageList` 개체에 전달합니다.

## <a name="see-also"></a>참고 항목

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
