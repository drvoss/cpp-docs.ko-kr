---
title: Rich Edit 컨트롤의 개요
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
ms.openlocfilehash: 9ef696bc348dfb18b797b487224b97261020e11c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366865"
---
# <a name="overview-of-the-rich-edit-control"></a>Rich Edit 컨트롤의 개요

> [!IMPORTANT]
> 응용 프로그램이 SDI, MDI 또는 대화 상자 기반인지 여부에 관계없이 대화 상자에서 풍부한 편집 컨트롤을 사용하는 경우 대화 상자가 표시되기 전에 [AfxInitRichEdit를](../mfc/reference/application-information-and-management.md#afxinitrichedit) 한 번 호출해야 합니다. 이 함수를 호출하는 일반적인 장소는 프로그램의 `InitInstance` 멤버 함수에 있습니다. 대화 상자를 처음 표시할 때마다 호출할 필요가 없습니다. 로 작업하는 경우 `AfxInitRichEdit` 호출할 필요가 없습니다. `CRichEditView`

리치 편집[컨트롤(CRichEditCtrl)은](../mfc/reference/cricheditctrl-class.md)텍스트 서식을 지정하기 위한 프로그래밍 인터페이스를 제공합니다. 그러나 응용 프로그램은 사용자가 서식 지정 작업을 사용할 수 있도록 하는 데 필요한 모든 사용자 인터페이스 구성 요소를 구현 해야 합니다. 즉, 리치 편집 컨트롤은 선택한 텍스트의 문자 또는 단락 특성 변경을 지원합니다. 문자 속성의 몇 가지 예는 굵게, 기울임꼴, 글꼴 패밀리 및 점 크기입니다. 단락 특성의 예로는 선형, 여백 및 탭 중지가 있습니다. 그러나 도구 모음 단추, 메뉴 항목 또는 형식 문자 대화 상자인지 여부에 관계없이 사용자 인터페이스를 제공하는 것은 사용자의 선택입니다. 현재 선택 영역의 특성에 대한 풍부한 편집 컨트롤을 쿼리하는 기능도 있습니다. 이러한 함수를 사용하여 속성에 대한 현재 설정을 표시하는 경우(예: 선택 영역에 굵은 문자 서식 지정 특성이 있는 경우 명령 UI에 확인 표시를 설정).

문자 및 단락 서식에 대한 자세한 내용은 이 항목의 [후반부에서 문자 서식](../mfc/character-formatting-in-rich-edit-controls.md) 및 [단락 서식을](../mfc/paragraph-formatting-in-rich-edit-controls.md) 참조하세요.

리치 편집 컨트롤은 다중 줄 편집 컨트롤에 사용되는 거의 모든 작업 및 알림 메시지를 지원합니다. 따라서 이미 편집 컨트롤을 사용하는 응용 프로그램을 쉽게 변경하여 풍부한 편집 컨트롤을 사용할 수 있습니다. 추가 메시지 및 알림을 사용하면 응용 프로그램에서 풍부한 편집 컨트롤에 고유한 기능에 액세스할 수 있습니다. 컨트롤 편집에 대한 자세한 내용은 [CEdit](../mfc/reference/cedit-class.md)을 참조하십시오.

알림에 대한 자세한 내용은 이 항목의 [후반부의 리치 편집 컨트롤의 알림을](../mfc/notifications-from-a-rich-edit-control.md) 참조하세요.

## <a name="see-also"></a>참고 항목

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
