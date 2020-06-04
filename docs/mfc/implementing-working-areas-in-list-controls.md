---
title: 리스트 컨트롤의 작업 영역 구현
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
ms.openlocfilehash: 91577203163247bd230fecb083cf1c50e2875b98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377220"
---
# <a name="implementing-working-areas-in-list-controls"></a>리스트 컨트롤의 작업 영역 구현

기본적으로 목록 컨트롤은 모든 항목을 표준 그리드 방식으로 정렬합니다. 그러나 목록 항목을 직사각형 그룹으로 정렬하는 작업 영역인 다른 방법이 지원됩니다. 작업 영역을 구현하는 목록 컨트롤 이미지의 경우 Windows SDK에서 목록 보기 컨트롤 사용을 참조하십시오.

> [!NOTE]
> 작업 영역은 목록 컨트롤이 아이콘 또는 작은 아이콘 모드인 경우에만 표시됩니다. 그러나 보기가 보고서 또는 목록 모드로 전환되면 현재 작업 영역이 유지됩니다.

작업 영역을 사용하여 빈 테두리(항목의 왼쪽, 위쪽 및/또는 오른쪽에)를 표시하거나 일반적으로 테두리가 없을 때 가로 스크롤 막대가 표시될 수 있습니다. 또 다른 일반적인 용도는 항목을 이동하거나 삭제할 수 있는 여러 작업 영역을 만드는 것입니다. 이 방법을 사용하면 다른 의미를 가진 단일 뷰에서 영역을 만들 수 있습니다. 그런 다음 사용자는 항목을 다른 영역에 배치하여 분류할 수 있습니다. 이 예제는 읽기/쓰기 파일에 대한 영역과 읽기 전용 파일에 대한 다른 영역이 있는 파일 시스템의 보기입니다. 파일 항목이 읽기 전용 영역으로 이동되면 자동으로 읽기 전용영역이 됩니다. 읽기 전용 영역에서 읽기/쓰기 영역으로 파일을 이동하면 파일이 읽기/쓰기됩니다.

`CListCtrl`는 목록 컨트롤에서 작업 영역을 만들고 관리하기 위한 여러 멤버 기능을 제공합니다. [GetWorkAreas](../mfc/reference/clistctrl-class.md#getworkareas) 및 [SetWorkAreas](../mfc/reference/clistctrl-class.md#setworkareas) 검색 하 `CRect` 고 `RECT` 목록 컨트롤에 대 한 현재 구현 된 작업 영역을 저장 하는 개체 (또는 구조체)의 배열을 설정 합니다. 또한 [GetNumberOfWorkAreas](../mfc/reference/clistctrl-class.md#getnumberofworkareas) 목록 컨트롤에 대 한 작업 영역의 현재 수를 검색합니다 (기본적으로 0).

## <a name="items-and-working-areas"></a>항목 및 작업 영역

작업 영역이 작성되면 작업 영역 내에 있는 항목이 해당 영역의 구성원이 됩니다. 마찬가지로 항목이 작업 영역으로 이동되면 항목이 이동된 작업 영역의 구성원이 됩니다. 항목이 작업 영역 내에 있지 않으면 자동으로 첫 번째(인덱스 0) 작업 영역의 구성원이 됩니다. 항목을 만들고 특정 작업 영역 내에 배치하려면 항목을 만든 다음 [SetItemPosition에](../mfc/reference/clistctrl-class.md#setitemposition)대한 호출을 사용하여 원하는 작업 영역으로 이동해야 합니다. 아래 두 번째 예제에서는 이 기술을 보여 줍니다.

다음 예제에서는 목록 컨트롤()에서 각 작업 영역 주위에 10픽셀 너비의 테두리가 있는`m_WorkAreaListCtrl`동일한 크기의 네 개의 작업 영역()을`rcWorkAreas`구현합니다.

[!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]

[ApproximateViewRect에](../mfc/reference/clistctrl-class.md#approximateviewrect) 대한 호출은 한 지역의 모든 항목을 표시하는 데 필요한 총 면적의 추정치를 얻기 위해 만들어졌습니다. 이 추정치는 4개의 영역으로 나누어지고 5픽셀 너비의 테두리로 패딩처리됩니다.

다음 예제에서는 각 그룹 ()에`rcWorkAreas`기존 목록 항목을 할당`m_WorkAreaListCtrl`하 고 컨트롤 보기 () 새로 고침 효과 완료 합니다.

[!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]

## <a name="see-also"></a>참고 항목

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
