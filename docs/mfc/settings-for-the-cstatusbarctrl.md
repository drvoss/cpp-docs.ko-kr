---
title: CStatusBarCtrl에 대한 설정
ms.date: 11/04/2016
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
ms.openlocfilehash: dd7c68d6721c48f751c04437e43c8770f6ec5736
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365373"
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl에 대한 설정

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) 상태 창의 기본 위치는 부모 창의 아래쪽을 따라 있지만 부모 창의 클라이언트 영역 맨 위에 표시되도록 CCS_TOP 스타일을 지정할 수 있습니다.

상태 창의 오른쪽 끝에 크기 조정 그립을 포함하도록 `CStatusBarCtrl` SBARS_SIZEGRIP 스타일을 지정할 수 있습니다. 크기 조정 그립은 크기 조정 테두리와 유사합니다. 사용자가 클릭하고 드래그하여 부모 창의 크기를 조정할 수 있는 직사각형 영역입니다.

> [!NOTE]
> CCS_TOP SBARS_SIZEGRIP 스타일을 결합하면 시스템이 상태 창에서 끌어도 결과 크기 조정 그립이 작동하지 않습니다.

상태 창의 창 프로시저는 컨트롤 창의 초기 크기와 위치를 자동으로 설정합니다. 너비는 부모 창의 클라이언트 영역과 동일합니다. 높이는 상태 창의 장치 컨텍스트와 창 테두리의 너비에 현재 선택된 글꼴의 메트릭을 기반으로 합니다.

창 프로시저는 WM_SIZE 메시지를 받을 때마다 상태 창의 크기를 자동으로 조정합니다. 일반적으로 부모 창의 크기가 변경되면 부모는 상태 창에 WM_SIZE 메시지를 보냅니다.

픽셀의 최소 높이를 지정하여 [SetMinHeight를](../mfc/reference/cstatusbarctrl-class.md#setminheight)호출하여 상태 창의 도면 영역의 최소 높이를 설정할 수 있습니다. 도면 영역에는 창의 테두리가 포함되지 않습니다.

[GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders)를 호출하여 상태 창의 테두리 너비를 검색합니다. 이 멤버 함수에는 가로 테두리, 세로 테두리 및 사각형 사이의 테두리를 받는 세 요소 배열에 대한 포인터가 포함됩니다.

## <a name="see-also"></a>참고 항목

[CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
