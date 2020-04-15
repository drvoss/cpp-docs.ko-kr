---
title: 헤더 항목에 대한 끌어서 놓기 지원 제공
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: 8dfaabf3da62c216d3da662f59c57b63e695d9ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371158"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>헤더 항목에 대한 끌어서 놓기 지원 제공

헤더 항목에 대한 끌어서 놓기 지원을 제공하려면 HDS_DRAGDROP 스타일을 지정합니다. 헤더 항목에 대한 끌어서 놓기 지원을 통해 사용자는 헤더 컨트롤의 헤더 항목의 순서를 다시 정렬할 수 있습니다. 기본 비헤이비어는 헤더 항목이 삭제된 경우 드래그되는 헤더 항목의 반투명 드래그 이미지와 새 위치의 시각적 표시기를 제공합니다.

일반적인 끌어서 놓기 기능과 마찬가지로 HDN_BEGINDRAG 및 HDN_ENDDRAG 알림을 처리하여 기본 끌어서 놓기 동작을 확장할 수 있습니다. [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) 멤버 함수를 재정의하여 드래그 이미지의 모양을 사용자 지정할 수도 있습니다.

> [!NOTE]
> 목록 컨트롤에서 포함된 헤더 컨트롤에 대한 끌어서 놓기 지원을 제공하는 경우 [목록 제어 스타일 변경](../mfc/changing-list-control-styles.md) 항목의 확장 스타일 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

[CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)
