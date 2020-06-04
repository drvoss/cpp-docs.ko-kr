---
title: 컨트롤에 열 추가(보고서 뷰)
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
ms.openlocfilehash: 34d7b62985748b9b9d741c083ec9b34fce06b309
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370879"
---
# <a name="adding-columns-to-the-control-report-view"></a>컨트롤에 열 추가(보고서 뷰)

> [!NOTE]
> 다음 절차는 [CListView](../mfc/reference/clistview-class.md) 또는 [CListCtrl](../mfc/reference/clistctrl-class.md) 개체에 적용됩니다.

목록 컨트롤이 보고서 보기에 있으면 열이 표시되어 각 목록 컨트롤 항목의 다양한 하위 항목을 구성하는 방법을 제공합니다. 이 조직은 목록 컨트롤의 열과 목록 제어 항목의 연결된 하위 항목 간의 일대일 대응으로 구현됩니다. 하위 항목에 대한 자세한 내용은 [컨트롤에 항목 추가 를](../mfc/adding-items-to-the-control.md)참조하십시오. 보고서 보기의 목록 컨트롤의 예는 Windows 95 및 Windows 98 탐색기의 세부 정보 보기에서 제공됩니다. 첫 번째 열에는 폴더, 파일 아이콘 및 레이블이 나열됩니다. 다른 열에는 파일 크기, 파일 형식, 마지막으로 수정된 날짜 등이 나열됩니다.

열은 언제든지 목록 컨트롤에 추가할 수 있지만 컨트롤에 스타일 비트가 켜져 `LVS_REPORT` 있는 경우에만 열이 표시됩니다.

각 열에는 열에 레이블을 지정하고 사용자가 열의 크기를 조정할 수 있는 연결된 헤더 [항목(CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)참조) 개체가 있습니다.

목록 컨트롤이 보고서 보기를 지원하는 경우 목록 제어 항목에서 가능한 각 하위 항목에 대한 열을 추가해야 합니다. [LVCOLUMN](/windows/win32/api/commctrl/ns-commctrl-lvcolumnw) 구조를 준비 한 다음 [InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn)을 호출하여 열을 추가합니다. 필요한 열(헤더 항목이라고도 함)을 추가한 후 포함된 헤더 컨트롤에 속하는 멤버 함수 및 스타일을 사용하여 순서를 다시 정렬할 수 있습니다. 자세한 내용은 [헤더 컨트롤의 항목 순서를](../mfc/ordering-items-in-the-header-control.md)참조하십시오.

> [!NOTE]
> 목록 컨트롤이 **LVS_NOCOLUMNHEADER** 스타일로 만들어지면 열을 삽입하려는 모든 시도는 무시됩니다.

## <a name="see-also"></a>참고 항목

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
