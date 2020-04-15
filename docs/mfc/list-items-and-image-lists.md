---
title: 목록 항목 및 이미지 목록
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
ms.openlocfilehash: d378c6e07280349f9995981ad794039ebc015b25
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353058"
---
# <a name="list-items-and-image-lists"></a>목록 항목 및 이미지 목록

목록[컨트롤(CListCtrl)의](../mfc/reference/clistctrl-class.md)"항목"은 아이콘, 레이블 및 기타 정보("하위 항목")로 구성됩니다.

목록 제어 항목의 아이콘은 이미지 목록에 포함되어 있습니다. 하나의 이미지 목록에는 아이콘 보기에 사용되는 전체 크기의 아이콘이 포함되어 있습니다. 두 번째 선택 사항인 이미지 목록에는 컨트롤의 다른 보기에서 사용할 수 있는 동일한 아이콘의 작은 버전이 포함되어 있습니다. 세 번째 선택적 목록에는 특정 뷰의 작은 아이콘 앞에 표시하기 위한 확인란과 같은 "상태" 이미지가 포함되어 있습니다. 네 번째 선택적 목록에는 목록 컨트롤의 개별 헤더 항목에 표시되는 이미지가 포함되어 있습니다.

> [!NOTE]
> 목록 보기 컨트롤이 LVS_SHAREIMAGELISTS 스타일로 만들어진 경우 더 이상 사용되지 않을 때 이미지 목록을 삭제해야 합니다. 동일한 이미지 목록을 여러 목록 보기 컨트롤에 할당하는 경우 이 스타일을 지정합니다. 그렇지 않으면 두 개 이상의 컨트롤이 동일한 이미지 목록을 삭제하려고 시도할 수 있습니다.

목록 항목에 대한 자세한 내용은 Windows SDK의 [목록 보기 이미지 목록](/windows/win32/Controls/using-list-view-controls) 및 항목 및 하위 [항목을](/windows/win32/Controls/using-list-view-controls) 참조하십시오. 또한 이 문서 패밀리의 *MFC 참조* 및 [CImageList 사용에서 클래스 CImageList를](../mfc/using-cimagelist.md) 참조하십시오. [CImageList](../mfc/reference/cimagelist-class.md)

목록 컨트롤을 만들려면 목록에 새 항목을 삽입할 때 사용할 이미지 목록을 제공해야 합니다. 다음 예제에서는 *m_pImagelist* `CImageList` 형식의 포인터이고 *데이터* 멤버인 m_listctrl `CListCtrl` 이 절차를 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]

그러나 목록 보기 또는 목록 컨트롤에 아이콘을 표시하지 않으려면 이미지 목록이 필요하지 않습니다.

## <a name="see-also"></a>참고 항목

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
