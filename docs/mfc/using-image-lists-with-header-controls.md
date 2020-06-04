---
title: 이미지 목록과 헤더 컨트롤 함께 사용
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
ms.openlocfilehash: 8002c16d1cdf5e0683b642001409b6da9c260660
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366467"
---
# <a name="using-image-lists-with-header-controls"></a>이미지 목록과 헤더 컨트롤 함께 사용

헤더 항목에는 헤더 항목 내에 이미지를 표시할 수 있습니다. 연결된 이미지 목록에 저장된 이 이미지는 16 x 16 픽셀이며 목록 보기 컨트롤에 사용되는 아이콘 이미지와 동일한 특성을 가짐입니다. 이 동작을 성공적으로 구현하려면 먼저 이미지 목록을 만들고 초기화하고 목록을 헤더 컨트롤과 연결한 다음 이미지를 표시할 헤더 항목의 특성을 수정해야 합니다.

다음 절차에서는 헤더 컨트롤()에 대한 포인터와`m_pHdrCtrl`이미지 목록()에`m_pHdrImages`대한 포인터를 사용하여 세부 정보를 보여 줍니다.

### <a name="to-display-an-image-in-a-header-item"></a>헤더 항목에 이미지를 표시하려면

1. [CImageList](../mfc/reference/cimagelist-class.md) 생성자 사용 하 여 새 이미지 목록을 구성 (또는 기존 이미지 목록 개체를 사용 하 여) 결과 포인터를 저장 합니다.

1. [CImageList::Create를](../mfc/reference/cimagelist-class.md#create)호출하여 새 이미지 목록 개체를 초기화합니다. 다음 코드는 이 호출의 한 예입니다.

   [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. 각 헤더 항목에 대한 이미지를 추가합니다. 다음 코드는 미리 정의된 두 개의 이미지를 추가합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. 이미지 목록을 헤더 컨트롤과 연결하여 [CHeaderCtrl::SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist)에 대한 호출을 호출합니다.

1. 헤더 항목을 수정하여 연결된 이미지 목록에서 이미지를 표시합니다. 다음 예제에서는 `m_phdrImages`에서 첫 번째 헤더 항목에 첫 `m_pHdrCtrl`번째 이미지를 할당합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

사용되는 매개 변수 값에 대한 자세한 내용은 해당 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)을 참조하십시오.

> [!NOTE]
> 동일한 이미지 목록을 사용하여 여러 컨트롤을 가질 수 있습니다. 예를 들어 표준 목록 보기 컨트롤에는 목록 보기 컨트롤의 작은 아이콘 보기와 목록 뷰 컨트롤의 헤더 항목 모두에서 사용되는 이미지 목록(16 x 16 픽셀 이미지)이 있을 수 있습니다.

## <a name="see-also"></a>참고 항목

[CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)
